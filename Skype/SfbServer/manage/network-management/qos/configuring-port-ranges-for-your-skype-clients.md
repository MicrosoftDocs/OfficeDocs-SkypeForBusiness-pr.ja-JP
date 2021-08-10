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
description: この記事では、クライアントのポート範囲を構成する方法と、Skype for Business Server で実行されているクライアントのサービス品質ポリシーを構成する方法についてWindows 10。
ms.openlocfilehash: d2d38ff777322aa952efd427c7e528afbb0e333252aabec2a943b1a9007d0ca7
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2021
ms.locfileid: "54591141"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>クライアントのポート範囲とサービス品質ポリシーの構成Skype for Business Server

この記事では、クライアントのポート範囲を構成する方法と、Skype for Business Server で実行されているクライアントのサービス品質ポリシーを構成する方法についてWindows 10。

## <a name="configure-port-ranges"></a>ポート範囲の構成

既定では、Skype for Business クライアント アプリケーションは、通信セッションに参加するときにポート 1024 と 65535 の間の任意のポートを使用できます。これは、特定のポート範囲がクライアントに対して自動的に有効になっていないためです。 ただし、サービス品質を使用するには、さまざまなトラフィックの種類 (オーディオ、ビデオ、メディア、アプリケーション共有、ファイル転送) を一連の一意のポート範囲に再割り当てする必要があります。 これは、このコマンドレットを使用してSet-CsConferencingConfigurationできます。

> [!NOTE]  
> エンド ユーザーは、これらの変更自体を行う必要があります。 ポートの変更は、管理者が Set-CsConferencingConfigurationコマンドレットを使用して行う必要があります。


現在通信セッションに使用されているポート範囲は、管理シェル内から次のコマンドを実行Skype for Business Serverできます。

**Get-CsConferencingConfiguration**

電話会議のインストール後に会議の設定に変更を加えSkype for Business Server、次のプロパティ値を含む情報を取得する必要があります。

ClientMediaPortRangeEnabled : False<br/>
ClientAudioPort : 5350<br/>
ClientAudioPortRange : 40<br/>
ClientVideoPort : 5350<br/>
ClientVideoPortRange : 40<br/>
ClientAppSharingPort : 5350<br/>
ClientAppSharingPortRange : 40<br/>
ClientFileTransferPort : 5350<br/>
ClientTransferPortRange : 40<br/>

ここに示した出力には、重要な情報が 2 つ含まれています。1 つ目は、ClientMediaPortRangeEnabled プロパティが False に設定されていることです。

**ClientMediaPortRangeEnabled : False**

このプロパティが False に設定されている場合、Skype for Business クライアントは通信セッションに関与するときにポート 1024 から 65535 の間で使用可能なポートを使用するため、重要です。これは、他のポート設定 (ClientMediaPort や ClientVideoPort など) に関係なく当てはまる。 使用を指定したポートのセットに制限する場合 (また、サービス品質の実装を計画している場合はこれを行う必要がある場合)、最初にクライアント メディア ポート範囲を有効にする必要があります。 これは、次のコマンドを使用Windows PowerShellできます。

**Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True**

上記のコマンドを実行すると、会議の構成設定のグローバル コレクションに対してクライアントのメディア ポート範囲が有効化されます。ただし、これらの設定は、サイト範囲またはサービスの範囲 (電話会議サーバー サービスのみ) に対しても適用できます。特定のサイトまたはサーバーに対してクライアントのメディア ポート範囲を有効にするには、Set-CsConferencingConfiguration の呼び出し時にそのサイトまたはサーバーの ID を指定します。

**Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True**

次のコマンドを使用して、会議のすべての構成設定に対して同時にポート範囲を有効化することもできます。

**Get-CsConferencingConfiguration |Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True**

2 つ目の重要な情報は、サンプルの出力では、既定で、各種類のネットワーク トラフィックに対して同じメディア ポート範囲が設定されていることです。

ClientAudioPort : 5350<br/>
ClientVideoPort : 5350<br/>
ClientAppSharingPort : 5350<br/>
ClientFileTransferPort : 5350<br/>

QoS を実装するためには、これらの各ポート範囲が一意であることが必要です。たとえば、次のようにポート範囲を構成します。


<table>
<colgroup>
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


上記の表では、クライアントのポート範囲はサーバーに構成されたポート範囲のサブセットを表しています。 たとえば、サーバーではアプリケーション共有が 40803 ～ 49151 のポートを使用するように構成されており、クライアント コンピューターではアプリケーション共有が 42000 ～ 42019 のポートを使用するように構成されています。 これは、主に QoS の管理を容易にするために行われます。クライアント ポートは、サーバーで使用されるポートのサブセットを表す必要があります。 (たとえば、クライアント コンピューターでは、ポート 10000 ~ 10019 など、使用するアプリケーション共有を構成できます。ただし、クライアント ポート範囲をサーバー ポート範囲のサブセットに設定してください。

さらに、サーバー上のアプリケーション共有用に 8348 ポートが確保されているが、クライアントでのアプリケーション共有には 20 個のポートしか取り除かれておかない場合があります。 このルールも推奨されますが、ハードアンドファストルールではありません。 一般に、使用可能な各ポートが 1 つの通信セッションを表すと考えます。ポート範囲に 100 個のポートがある場合は、問題のコンピューターが任意の時点で最大で 100 個の通信セッションに参加できる可能性があります。 サーバーはクライアントよりも多くの会話に参加する可能性が高いので、クライアントよりも多くのポートをサーバーで開くのが理にかなっています。 クライアントでアプリケーション共有用に 20 個のポートを設定すると、ユーザーは指定したデバイス上で 20 のアプリケーション共有セッションに同時に参加できます。 これは、大多数のユーザーにとって十分なことを証明する必要があります。

会議構成設定のグローバル コレクションに前のポート範囲を割り当てるには、次の管理シェル コマンドSkype for Business Server使用できます。

**Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20**

または、次のコマンドを使用して、この同じポート範囲を会議のすべての構成設定に割り当てます。

**Get-CsConferencingConfiguration |Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20**

個々のユーザーは、これらの変更が実際に有効Skype for Business前に、ユーザーからログオフしてからログオンし戻す必要があります。

> [!NOTE]  
> 1 つのコマンドで、クライアントのメディア ポート範囲を有効化し、これらのポート範囲を割り当てることもできます。次に例を示します。<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>クライアントで実行されているクライアントのサービス品質ポリシーを構成Windows 10

Skype for Business クライアントで使用するポート範囲の指定に加えて、クライアント コンピューターに適用される個別のサービス品質ポリシーも作成する必要があります。 (会議サーバー、アプリケーション サーバー、仲介サーバー用に作成されたサービス品質ポリシーは、クライアント コンピューターには適用できません)。この情報は、クライアントとクライアントを実行しているSkype for BusinessにのみWindows 10。

次の例では、このポート範囲のセットを使用して、オーディオ ポリシーとビデオ ポリシーを作成します。


<table>
<colgroup>
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

コンピューターにサービス品質オーディオ ポリシーをWindows 10、グループ ポリシー管理がインストールされているコンピューターに最初にログオンします。 [グループ ポリシーの管理] を開きます ([スタート] をクリックし、[管理ツール] をポイントし、[グループ ポリシーの **管理**] をクリックします)、次の手順を実行します。

1.  [グループ ポリシーの管理] で、新しいポリシーを作成する必要のあるコンテナーを探します。 たとえば、すべてのクライアント コンピューターが Client という名前の OU 内にある場合、新しいポリシーをクライアント OU に作成する必要があります。

2.  適切なコンテナーを右クリックし、[このドメインに GPO を作成する] をクリックし、 **ここにリンクします**。

3.  [新しい **GPO]** ダイアログ ボックスで、[名前] ボックスに新しいグループ ポリシー オブジェクトの名前を入力し **、[OK] をクリックします**。

4.  新しく作成したポリシーを右クリックし、[編集] を **クリックします**。

5.  グループ ポリシー管理エディターで、[コンピューターの構成] を展開し、[Windows 設定]**を** 展開し、[ポリシー ベース **の QoS]** を右クリックし、[新しいポリシーの作成]**をクリックします**。

6.  [ポリシー ベース **の QoS]** ダイアログ ボックスの開始ページで、[名前] ボックスに新しいポリシーの名前を **入力** します。 [**DSCP 値を指定する**] を選択し、値を **46** に設定します。 [**出力方向のスロットル率を指定する**] をオフのままにして、[**次へ**] をクリックします。

7.  次のページで、[この実行可能ファイル名を持つアプリケーションのみ]を選択し、Lync.exeを入力し、[次へ] を **クリックします**。 この設定は、ポリシーに対して、クライアントからの一致するトラフィックにのみ優先順位をSkype for Businessします。

8.  3 番目のページで、[すべての送信元 IP アドレス] と **[** 任意の宛先 **IP** アドレス] の両方が選択され、[次へ] **をクリックします**。 この 2 つの設定により、これらのパケットを送信したコンピューター (IP アドレス) やこれらのパケットを受信するコンピューター (IP アドレス) にかかわらず、パケットが管理されます。

9.  4 番目のページで、[**この QoS ポリシーを適用するプロトコルを選択してください**] ドロップダウン リストから [**TCP と UDP**] を選択します。 TCP (伝送制御プロトコル) と UDP (User Datagram Protocol) は、ネットワーク アプリケーションとそのクライアント アプリケーションで最も一般的に使用される 2 つのネットワーク プロトコルSkype for Business Serverです。

10. [**発信元ポート番号を指定してください**] という見出しの下にある [**次の発信元ポート番号か範囲**] を選択します。付随するテキスト ボックスに、オーディオ送信用に予約されたポート範囲を入力します。たとえば、50020 から 50039 までのポートをオーディオ トラフィック用に予約した場合は、「**50020:50039**」という形式でポート範囲を入力します。[**完了**] をクリックします。

オーディオ用の QoS ポリシーを作成した後で、2 番目にビデオ用のポリシーを作成する必要があります。ビデオ用のポリシーを作成するには、オーディオ ポリシーを作成したときと基本的には同じ手順に従い、次の点を変えます。

  - 別の (および一意の) ポリシー名を使用します。

  - DSCP の値を 46 ではなく「**34**」に設定します。(前に説明したとおり、DSCP の値に 34 を使用する必要はありません。ただ、オーディオに使用したのとは異なる DSCP の値を割り当てる必要があります。)

  - ビデオ トラフィックには、以前に構成したポート範囲を使用します。 たとえば、ビデオ用に予約ポート 58000 ~ 58019 がある場合、ポート範囲を **58000:58019** に設定します。

アプリケーション共有トラフィックを管理するためのポリシーを作成する場合は、次の置換を行います。

  - 別の (および一意の) ポリシー名を使用します (たとえば、Skype for Business Server **共有)。**

  - DSCP の値を 46 ではなく「**24**」に設定します。(この値も 24 にする必要はありません。ただ、オーディオとビデオに使用した DSCP の値とは別にする必要があります。)

  - ビデオ トラフィックには、以前に構成したポート範囲を使用します。 たとえば、アプリケーション共有用に予約ポート 42000 ~ 42019 がある場合は、ポート範囲を **42000:42019** に設定します。

ファイル転送ポリシーは次のようにします。

  - 別の (および一意の) ポリシー名 (たとえば、ファイル **転送Skype for Business Server使用します**)。

  - DSCP の値を「**14**」に設定します。(この値も 14 にする必要はありません。ただ、一意の DSCP にする必要があります。)

  - 以前に構成したポート範囲をアプリケーションに使用します。 たとえば、アプリケーション共有用に予約ポート 42020 ~ 42039 がある場合は、ポート範囲を **42020:42039** に設定します。

新しく作成したポリシーは、クライアント コンピューター上でグループ ポリシーが更新されるまで有効になりません。グループ ポリシーは定期的に自動更新を行いますが、グループ ポリシーの更新が必要な各コンピューター上で次のコマンドを実行することにより、強制的に即時更新できます。

**Gpupdate.exe /force**

このコマンドは、管理者の資格情報で実行されていれば、どのコマンド ウィンドウからでも実行できます。コマンド ウィンドウを管理者の資格情報で実行するには、[**スタート**]をクリックして、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。

なお、これらのポリシーが対象とするのはクライアント コンピューターです。 これらは、サーバーを実行しているサーバー Skype for Business Server。

ネットワーク パケットが適切な DSCP 値でマークされるようにするには、次の手順を実行して、各コンピューターに新しいレジストリ エントリを作成する必要もあります。

1.  [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

2.  [実行 **] ダイアログ** ボックスに **「regedit」と入力し**、Enter キーを押します。

3.  レジストリ エディターで **、[HKEY \_ LOCAL \_ MACHINE]** を展開し **、[SYSTEM]** を展開し **、[CurrentControlSet]** を展開し、[サービス] を展開し **、[Tcpip] を展開します**。

4.  [**Tcpip**] を右クリックし、[**新規**] をポイントして [**キー**] をクリックします。 新しいレジストリ キーを作成したら **、「QoS」と入力し**、Enter キーを押してキーの名前を変更します。

5.  [**QoS**] を右クリックし、[**新規**] をポイントして [**文字列値**] をクリックします。 新しいレジストリ値を作成したら **、「NLA** を使用しない」と入力し、Enter キーを押して値の名前を変更します。

6.  [**Do no use NLA**] をダブルクリックします。 [文字列 **の編集]** ダイアログ ボックスで、[値のデータ] ボックスに **「1」** と **入力** し **、[OK] をクリックします**。

7.  レジストリ エディターを閉じて、コンピューターを起動します。

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>複数のネットワーク アダプターを使用するコンピューターでサービス品質を構成する

複数のネットワーク アダプターを持つコンピューターがある場合は、構成された値ではなく、DSCP 値が 0x00 として表示される問題に実行される場合があります。 通常、このような表示になるのは、1 つ以上のネットワーク アダプターが Active Directory ドメインにアクセスできないコンピューターです (たとえば、アダプターがプライベート ネットワークに使用されている場合)。 そのような場合、ドメインへアクセスできるアダプターには DSCP の値がマークされますが、ドメインへアクセスできないアダプターにはマークされません。

ドメインにアクセスできないアダプターを含む、コンピューター内のすべてのネットワーク アダプターに DSCP 値をタグ付けする場合は、レジストリに値を追加して構成する必要があります。 このためには、次の手順を実行します。

1.  [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

2.  [実行 **] ダイアログ** ボックスに **「regedit」と入力し**、Enter キーを押します。

3.  レジストリ エディターで **、[HKEY \_ LOCAL \_ MACHINE]** を展開し **、[SYSTEM]** を展開し **、[CurrentControlSet]** を展開し、[サービス] を展開し **、[Tcpip] を展開します**。

4.  「**QoS**」というレジストリ キーがない場合は、 [**Tcpip**] 右クリックし、[**新規**] をポイントして、[**キー**] をクリックします。 新しいキーを作成したら **、「QoS」と入力し**、Enter キーを押してキーの名前を変更します。

5.  [**QoS**] を右クリックし、[**新規**] をポイントして [**文字列値**] をクリックします。 新しいレジストリ値を作成したら **、「NLA** を使用しない」と入力し、Enter キーを押して値の名前を変更します。

6.  [**Do no use NLA**] をダブルクリックします。 [文字列 **の編集]** ダイアログ ボックスで、[値のデータ] ボックスに **「1」** と **入力** し **、[OK] をクリックします**。

新しいレジストリ値を作成して構成した後、変更を有効にするためにコンピューターを再起動する必要があります。

## <a name="see-also"></a>関連項目

[グループ ポリシー オブジェクトを作成Windows 10](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
