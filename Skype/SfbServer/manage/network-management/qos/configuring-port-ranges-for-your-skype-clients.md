---
title: クライアントのポート範囲とサービス品質ポリシーの構成
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: この記事では、クライアントのポート範囲を構成し、Windows 10 で実行されているクライアントの Skype for Business Server でサービス品質ポリシーを構成する方法について説明します。
ms.openlocfilehash: b2961193bef799742ac3b79a4f421a7aa50c5a03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814207"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Skype for Business Server でのクライアントのポート範囲とサービス品質ポリシーの構成

この記事では、クライアントのポート範囲を構成し、Windows 10 で実行されているクライアントの Skype for Business Server でサービス品質ポリシーを構成する方法について説明します。

## <a name="configure-port-ranges"></a>ポート範囲を構成する

既定では、Skype for Business クライアント アプリケーションは、通信セッションに参加するときにポート 1024 とポート 65535 の間の任意のポートを使用できます。これは、特定のポート範囲がクライアントに対して自動的に有効になっていないためです。 ただし、サービスの品質を使用するには、さまざまなトラフィックの種類 (オーディオ、ビデオ、メディア、アプリケーション共有、ファイル転送) を一連の一意のポート範囲に再割り当てする必要があります。 これは、次のコマンドレットを使用Set-CsConferencingConfigurationできます。

> [!NOTE]  
> エンド ユーザーは、これらの変更を自分で行う必要があります。 ポートの変更は、管理者が Set-CsConferencingConfigurationできます。


Skype for Business Server 管理シェル内から次のコマンドを実行して、通信セッションに現在使用されているポート範囲を確認できます。

    Get-CsConferencingConfiguration

Skype for Business Server のインストール以降に会議設定に変更を加えしていない場合は、次のプロパティ値を含む情報を取得する必要があります。

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

ここに示した出力には、重要な情報が 2 つ含まれています。 1 つ目は、ClientMediaPortRangeEnabled プロパティが False に設定されていることです。

    ClientMediaPortRangeEnabled : False

このプロパティが False に設定されている場合、Skype for Business クライアントは通信セッションに参加するときにポート 1024 から 65535 の間で使用可能なポートを使用するため、これは重要です。これは、その他のポート設定 (ClientMediaPort や ClientVideoPort など) に関係なく true です。 使用を指定したポートのセットに制限する場合 (サービスの品質の実装を計画している場合は、この操作を行う必要があります)、最初にクライアント メディア ポート範囲を有効にする必要があります。 これは、次のコマンドを使用してWindows PowerShellできます。

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

上記のコマンドを実行すると、会議の構成設定のグローバル コレクションに対してクライアントのメディア ポート範囲が有効化されます。ただし、これらの設定は、サイト範囲またはサービスの範囲 (電話会議サーバー サービスのみ) に対しても適用できます。特定のサイトまたはサーバーに対してクライアントのメディア ポート範囲を有効にするには、Set-CsConferencingConfiguration の呼び出し時にそのサイトまたはサーバーの ID を指定します。

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

次のコマンドを使用して、会議のすべての構成設定に対して同時にポート範囲を有効化することもできます。

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

2 つ目の重要な情報は、サンプルの出力では、既定で、各種類のネットワーク トラフィックに対して同じメディア ポート範囲が設定されていることです。

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

QoS を実装するためには、これらの各ポート範囲が一意であることが必要です。たとえば、次のようにポート範囲を構成します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント トラフィックの種類</th>
<th>開始ポート</th>
<th>ポート範囲</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>オーディオ</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>ビデオ</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション共有</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>ファイル送信</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


上記の表では、クライアントのポート範囲はサーバーに構成されたポート範囲のサブセットを表しています。 たとえば、サーバーではアプリケーション共有が 40803 ～ 49151 のポートを使用するように構成されており、クライアント コンピューターではアプリケーション共有が 42000 ～ 42019 のポートを使用するように構成されています。 また、これは主に QoS の管理を容易にするために行われます。クライアント ポートは、サーバーで使用されるポートのサブセットを表す必要がなされません。 (たとえば、クライアント コンピューターでは、ポート 10000 から 10019 までを使用するアプリケーション共有を構成できます)。ただし、クライアント ポート範囲をサーバー ポート範囲のサブセットに設定してください。

さらに、サーバー上のアプリケーション共有用に 8348 個のポートが確保されているが、クライアント上のアプリケーション共有用に確保されたポートは 20 個のみである点に注意してください。 この規則も推奨されますが、高速な規則ではありません。 一般に、使用可能な各ポートを 1 つの通信セッションと見なして、1 つのポート範囲で 100 個のポートを使用できる場合は、問題のコンピューターが一度に最大で 100 個の通信セッションに参加する可能性があります。 サーバーはクライアントよりも多くの会話に参加する可能性が高いので、クライアントよりも多くのポートをサーバーで開くのが理にかなっています。 クライアントでアプリケーション共有用に 20 個のポートを確保すると、ユーザーは指定したデバイスで 20 個のアプリケーション共有セッションに同時に参加できます。 大多数のユーザーにとって十分なことを証明する必要があります。

上のポート範囲を会議構成設定のグローバル コレクションに割り当てるには、次の Skype for Business Server 管理シェル コマンドを使用できます。

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

または、次のコマンドを使用して、この同じポート範囲を会議のすべての構成設定に割り当てます。

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

個々のユーザーは、Skype for Business からログオフしてから、これらの変更を実際に有効にする前にログオンし戻す必要があります。

> [!NOTE]  
> 1 つのコマンドで、クライアントのメディア ポート範囲を有効化し、これらのポート範囲を割り当てることもできます。 次に例を示します。<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Windows 10 で実行されているクライアントのサービス品質ポリシーを構成する

Skype for Business クライアントで使用するポート範囲を指定する以外に、クライアント コンピューターに適用されるサービス品質ポリシーを個別に作成する必要があります。 (会議サーバー、アプリケーション サーバー、および仲介サーバー用に作成されたサービス品質ポリシーは、クライアント コンピューターには適用されません。この情報は、Skype for Business クライアントと Windows 10 を実行しているコンピューターにのみ適用されます。

次の例では、このポート範囲のセットを使用して、オーディオ ポリシーとビデオ ポリシーを作成します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント トラフィックの種類</th>
<th>開始ポート</th>
<th>ポート範囲</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>オーディオ</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>ビデオ</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション共有</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>ファイル送信</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>

Windows 10 コンピューターのサービス品質オーディオ ポリシーを作成するには、まず、グループ ポリシーの管理がインストールされているコンピューターにログオンします。 グループ ポリシーの管理を開き ([スタート] ボタンを **クリック** し、[管理ツール] をポイントし、[グループ ポリシーの管理] をクリックします)、次の手順を実行します。 

1.  [グループ ポリシーの管理] で、新しいポリシーを作成する必要のあるコンテナーを探します。 たとえば、すべてのクライアント コンピューターが Clients という名前の OU にある場合は、新しいポリシーをクライアント OU に作成する必要があります。

2.  適切なコンテナーを右クリックし、[このドメインに GPO を作成する] をクリックし、 **ここにリンクします**。

3.  [新 **しい GPO] ダイアログ** ボックスで、[名前] ボックスに新しいグループ ポリシー オブジェクトの名前を入力し **、[OK]** をクリックします。

4.  新しく作成したポリシーを右クリックし、[編集] をクリック **します**。

5.  グループ ポリシー管理エディターで、[コンピューターの構成] を展開し **、[Windows の** 設定] を展開し、[ポリシー ベース **の QoS]** を右クリックして、[新しいポリシーの作成]**をクリックします**。

6.  [ **ポリシーベースの QoS]** ダイアログ ボックスの開始ページで、[名前] ボックスに新しいポリシーの名前を **入力** します。 [**DSCP 値を指定する**] を選択し、値を **46** に設定します。 [**出力方向のスロットル率を指定する**] をオフのままにして、[**次へ**] をクリックします。

7.  次のページで、[この実行可能ファイル名を持つアプリケーションのみ]を選択し、Lync.exeを入力して、[次へ] をクリック **します**。 この設定は、Skype for Business クライアントからの一致トラフィックのみを優先順位付けするようにポリシーに指示します。

8.  3 番目のページで、[すべての送信元 **IP** アドレス] と [すべての宛先 **IP** アドレス] の両方が選択され、[次へ] **をクリックします**。 この 2 つの設定により、これらのパケットを送信したコンピューター (IP アドレス) やこれらのパケットを受信するコンピューター (IP アドレス) にかかわらず、パケットが管理されます。

9.  4 番目のページで、[**この QoS ポリシーを適用するプロトコルを選択してください**] ドロップダウン リストから [**TCP と UDP**] を選択します。 TCP (伝送制御プロトコル) と UDP (ユーザー データグラム プロトコル) は、Skype for Business Server とそのクライアント アプリケーションで最も一般的に使用される 2 つのネットワーク プロトコルです。

10. [**発信元ポート番号を指定してください**] という見出しの下にある [**次の発信元ポート番号か範囲**] を選択します。付随するテキスト ボックスに、オーディオ送信用に予約されたポート範囲を入力します。たとえば、50020 から 50039 までのポートをオーディオ トラフィック用に予約した場合は、「**50020:50039**」という形式でポート範囲を入力します。[**完了**] をクリックします。

オーディオ用の QoS ポリシーを作成した後で、2 番目にビデオ用のポリシーを作成する必要があります。ビデオ用のポリシーを作成するには、オーディオ ポリシーを作成したときと基本的には同じ手順に従い、次の点を変えます。

  - 別の (および一意の) ポリシー名を使用します。

  - DSCP の値を 46 ではなく「**34**」に設定します。(前に説明したとおり、DSCP の値に 34 を使用する必要はありません。ただ、オーディオに使用したのとは異なる DSCP の値を割り当てる必要があります。)

  - ビデオ トラフィックには、以前に構成したポート範囲を使用します。 たとえば、ポート 58000 ~ 58019 をビデオ用に予約している場合は、ポート範囲を **58000:58019** に設定します。

アプリケーション共有トラフィックを管理するためのポリシーを作成する場合は、次の代替を行います。

  - 別の (および一意の) ポリシー名 **(Skype for Business Server アプリケーション** 共有など) を使用します。

  - DSCP の値を 46 ではなく「**24**」に設定します。(この値も 24 にする必要はありません。ただ、オーディオとビデオに使用した DSCP の値とは別にする必要があります。)

  - ビデオ トラフィックには、以前に構成したポート範囲を使用します。 たとえば、アプリケーション共有用にポート 42000 ~ 42019 を予約している場合、ポート範囲を **42000:42019** に設定します。

ファイル転送ポリシーは次のようにします。

  - 別の (および一意の) ポリシー名 **(Skype for Business Server ファイル** 転送など) を使用します。

  - DSCP 値を **14 に設定します**。 (繰り返しますが、この値は 14 である必要はありません。単に一意の DSCP コードである必要があります)。

  - アプリケーションに対して以前に構成したポート範囲を使用します。 たとえば、アプリケーション共有用にポート 42020 ~ 42039 を予約している場合は、ポート範囲を **42020:42039** に設定します。

新しく作成したポリシーは、クライアント コンピューター上でグループ ポリシーが更新されるまで有効になりません。グループ ポリシーは定期的に自動更新を行いますが、グループ ポリシーの更新が必要な各コンピューター上で次のコマンドを実行することにより、強制的に即時更新できます。

    Gpupdate.exe /force

このコマンドは、管理者の資格情報で実行されていれば、どのコマンド ウィンドウからでも実行できます。コマンド ウィンドウを管理者の資格情報で実行するには、[**スタート**]をクリックして、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。

なお、これらのポリシーが対象とするのはクライアント コンピューターです。 Skype for Business Server を実行しているサーバーには適用できません。

ネットワーク パケットが適切な DSCP 値でマークされるようにするには、次の手順を実行して、各コンピューターに新しいレジストリ エントリを作成する必要もあります。

1.  [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

2.  [ファイル名 **を指定** して実行] ダイアログ ボックスに **「regedit」と** 入力し、Enter キーを押します。

3.  レジストリ エディターで **、HKEY \_ LOCAL \_ MACHINE、****システム****、CurrentControlSet、** サービス、Tcpip の順に **展開します**。 

4.  [**Tcpip**] を右クリックし、[**新規**] をポイントして [**キー**] をクリックします。 新しいレジストリ キーを作成したら **、「QoS」** と入力し、Enter キーを押してキーの名前を変更します。

5.  [**QoS**] を右クリックし、[**新規**] をポイントして [**文字列値**] をクリックします。 新しいレジストリ値を作成したら **、「NLA** を使用しない」と入力し、Enter キーを押して値の名前を変更します。

6.  [**Do no use NLA**] をダブルクリックします。 [文字列の **編集]** ダイアログ ボックスで、[値のデータ] ボックスに **「1」** と **入力し****、[OK]** をクリックします。

7.  レジストリ エディターを閉じて、コンピューターを起動します。

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>複数のネットワーク アダプターを使用するコンピューターでサービスの品質を構成する

複数のネットワーク アダプターを備えるコンピューターがある場合、DSCP 値が構成された値ではなく 0x00 として表示される問題が発生する場合があります。 通常、このような表示になるのは、1 つ以上のネットワーク アダプターが Active Directory ドメインにアクセスできないコンピューターです (たとえば、アダプターがプライベート ネットワークに使用されている場合)。 そのような場合、ドメインへアクセスできるアダプターには DSCP の値がマークされますが、ドメインへアクセスできないアダプターにはマークされません。

ドメインにアクセスできないアダプターを含め、コンピューター内のすべてのネットワーク アダプターの DSCP 値にタグを付けしたい場合は、レジストリに値を追加して構成する必要があります。 このためには、次の手順を実行します。

1.  [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

2.  [ファイル名 **を指定** して実行] ダイアログ ボックスに **「regedit」と** 入力し、Enter キーを押します。

3.  レジストリ エディターで **、HKEY \_ LOCAL \_ MACHINE、****システム****、CurrentControlSet、** サービス、Tcpip の順に **展開します**。 

4.  「**QoS**」というレジストリ キーがない場合は、 [**Tcpip**] 右クリックし、[**新規**] をポイントして、[**キー**] をクリックします。 新しいキーを作成したら **、「QoS」** と入力し、Enter キーを押してキーの名前を変更します。

5.  [**QoS**] を右クリックし、[**新規**] をポイントして [**文字列値**] をクリックします。 新しいレジストリ値を作成したら **、「NLA** を使用しない」と入力し、Enter キーを押して値の名前を変更します。

6.  [**Do no use NLA**] をダブルクリックします。 [文字列の **編集]** ダイアログ ボックスで、[値のデータ] ボックスに **「1」** と **入力し****、[OK]** をクリックします。

新しいレジストリ値を作成して構成した後、変更を有効にするためにコンピューターを再起動する必要があります。

## <a name="see-also"></a>関連項目

[Windows 10 でグループ ポリシー オブジェクトを作成する](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
