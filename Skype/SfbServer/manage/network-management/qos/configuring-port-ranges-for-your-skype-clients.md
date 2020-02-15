---
title: クライアントのポート範囲とサービス品質ポリシーの構成
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: この記事では、クライアントのポート範囲を構成する方法と、Windows 10 で実行しているクライアントのために Skype for Business Server でサービスの品質 (Qos) ポリシーを構成する方法について説明します。
ms.openlocfilehash: 95fe768333a01aff165e74eec334f14bf23d69dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045890"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Skype for Business Server でのクライアントのポート範囲とサービス品質ポリシーの構成

この記事では、クライアントのポート範囲を構成する方法と、Windows 10 で実行しているクライアントのために Skype for Business Server でサービスの品質 (Qos) ポリシーを構成する方法について説明します。

## <a name="configure-port-ranges"></a>ポート範囲を構成する

既定では、Skype for Business クライアントアプリケーションは、通信セッションに参加するときにポート1024と65535の間の任意のポートを使用できます。これは、特定のポート範囲がクライアントに対して自動的に有効にならないためです。 ただし、サービスの品質を使用するためには、さまざまな種類のトラフィック (オーディオ、ビデオ、メディア、アプリケーション共有、およびファイル転送) を一連の固有のポート範囲に再割り当てする必要があります。 これは、Get-csconferencingconfiguration コマンドレットを使用して行うことができます。

> [!NOTE]  
> エンドユーザーは、これらの変更を行うことはできません。 ポートの変更は、管理者のみが Get-csconferencingconfiguration コマンドレットを使用して行うことができます。


現在通信セッションで使用されているポート範囲を確認するには、Skype for Business Server 管理シェルから次のコマンドを実行します。

    Get-CsConferencingConfiguration

Skype for Business Server をインストールした後に会議の設定を変更していない場合は、次のプロパティ値を含む情報が返されます。

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

このプロパティが False に設定されている場合、Skype for Business クライアントは通信セッションに参加するときにポート1024と65535の間で使用可能なポートを使用します。これは、他のポート設定 (たとえば、ClientMediaPort または ClientVideoPort) に関係なく該当します。 指定したポートセットの使用を制限する場合 (これは、サービスの品質を実装することを計画している場合に実行します)、まずクライアントのメディアポート範囲を有効にする必要があります。 これは、次の Windows PowerShell コマンドを使用して実行できます。

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
<td><p>1280</p></td>
</tr>
<tr class="even">
<td><p>ビデオ</p></td>
<td><p>58000</p></td>
<td><p>1280</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション共有</p></td>
<td><p>42000</p></td>
<td><p>1280</p></td>
</tr>
<tr class="even">
<td><p>ファイル送信</p></td>
<td><p>42020</p></td>
<td><p>1280</p></td>
</tr>
</tbody>
</table>


上記の表では、クライアントのポート範囲はサーバーに構成されたポート範囲のサブセットを表しています。 たとえば、サーバーではアプリケーション共有が 40803 ～ 49151 のポートを使用するように構成されており、クライアント コンピューターではアプリケーション共有が 42000 ～ 42019 のポートを使用するように構成されています。 これも、主に QoS の管理を容易にするために行われています。クライアントポートは、サーバーで使用されるポートのサブセットを表す必要がありません。 (たとえば、クライアントコンピューター上で、ポート 1万 ~ 10019 を使用するようにアプリケーション共有を構成することができます)。ただし、クライアントのポート範囲をサーバーのポート範囲のサブセットにすることをお勧めします。

さらに、サーバー上でのアプリケーション共有のために8348ポートが確保されていても、クライアント上でのアプリケーション共有に関しては20個のポートしか設定されていないことに気付いたかもしれません。 これも、推奨されていますが、ハードおよび高速ルールではありません。 一般に、1つの通信セッションを表すために使用可能な各ポートを考慮することができます。ポート範囲に100のポートを使用できる場合は、そのコンピューターがいつでも最大で100の通信セッションに参加できることを意味します。 サーバーは、多くの場合、クライアントよりも多くの会話に参加しているので、クライアントよりも多くのポートをサーバーで開くことをお勧めします。 クライアントでアプリケーション共有用に20個のポートを設定することは、1人のユーザーが、指定されたデバイスで20個のアプリケーション共有セッションに参加でき、同時にすべて同時に参加できることを意味します。 ユーザーの大部分に十分な証明を提供する必要があります。

会議構成設定のグローバルコレクションに上記のポート範囲を割り当てるには、次の Skype for Business Server 管理シェルコマンドを使用できます。

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

または、次のコマンドを使用して、この同じポート範囲を会議のすべての構成設定に割り当てます。

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

個々のユーザーが Skype for Business からログオフしてから再度ログオンする必要があります。これらの変更は実際に有効になります。

> [!NOTE]  
> 1 つのコマンドで、クライアントのメディア ポート範囲を有効化し、これらのポート範囲を割り当てることもできます。 次に例を示します。<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Windows 10 で実行しているクライアントのサービスの品質ポリシーを構成する

Skype for Business クライアントで使用するポート範囲を指定することに加えて、クライアントコンピューターに適用されるサービスの品質を個別に作成する必要もあります。 (会議、アプリケーション、および仲介サーバー用に作成されたサービスの品質をクライアントコンピューターに適用する必要はありません)。この情報は、Skype for Business クライアントと Windows 10 を実行しているコンピューターにのみ適用されます。

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
<td><p>1280</p></td>
</tr>
<tr class="even">
<td><p>ビデオ</p></td>
<td><p>58000</p></td>
<td><p>1280</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション共有</p></td>
<td><p>42000</p></td>
<td><p>1280</p></td>
</tr>
<tr class="even">
<td><p>ファイル送信</p></td>
<td><p>42020</p></td>
<td><p>1280</p></td>
</tr>
</tbody>
</table>

Windows 10 コンピューターのサービス品質のオーディオポリシーを作成するには、まずグループポリシー管理がインストールされているコンピューターにログオンします。 グループポリシーの管理を開きます ([**スタート**] をクリックし、[**管理ツール**] をポイントし、[**グループポリシーの管理**] をクリックします)。次の手順を実行します。

1.  [グループ ポリシーの管理] で、新しいポリシーを作成する必要のあるコンテナーを探します。 たとえば、すべてのクライアントコンピューターがクライアントという名前の OU に配置されている場合は、クライアント OU に新しいポリシーを作成する必要があります。

2.  適切なコンテナーを右クリックし、[**このドメインに GPO を作成し、ここにリンクする**] をクリックします。

3.  [**新しい GPO** ] ダイアログボックスで、[**名前**] ボックスに新しいグループポリシーオブジェクトの名前を入力し、[ **OK**] をクリックします。

4.  新しく作成したポリシーを右クリックし、[**編集**] をクリックします。

5.  グループポリシー管理エディターで、[**コンピューターの構成**]、[ **Windows の設定**] の順に展開し、[**ポリシーベースの QoS**] を右クリックして、[**新規ポリシーの作成**] をクリックします。

6.  [**ポリシーベースの QoS** ] ダイアログボックスの [開始] ページで、[**名前**] ボックスに新しいポリシーの名前を入力します。 [**DSCP 値を指定する**] を選択し、値を **46** に設定します。 [**出力方向のスロットル率を指定する**] をオフのままにして、[**次へ**] をクリックします。

7.  次のページで、[**この実行可能ファイル名を持つアプリケーションのみ**] を選択し、名前として「 **Lync.** 」と入力して、[**次へ**] をクリックします。 この設定では、Skype for Business クライアントからの一致するトラフィックのみに優先順位を付けるようにポリシーに指示します。

8.  3番目のページで、[**送信元 ip アドレス**] と [**宛先 ip アドレス**] の両方が選択されていることを確認し、[**次へ**] をクリックします。 この 2 つの設定により、これらのパケットを送信したコンピューター (IP アドレス) やこれらのパケットを受信するコンピューター (IP アドレス) にかかわらず、パケットが管理されます。

9.  4 番目のページで、[**この QoS ポリシーを適用するプロトコルを選択してください**] ドロップダウン リストから [**TCP と UDP**] を選択します。 TCP (伝送制御プロトコル) と UDP (ユーザーデータグラムプロトコル) は、Skype for Business Server およびそのクライアントアプリケーションで最も一般的に使用される2つのネットワークプロトコルです。

10. [**発信元ポート番号を指定してください**] という見出しの下にある [**次の発信元ポート番号か範囲**] を選択します。付随するテキスト ボックスに、オーディオ送信用に予約されたポート範囲を入力します。たとえば、50020 から 50039 までのポートをオーディオ トラフィック用に予約した場合は、「**50020:50039**」という形式でポート範囲を入力します。[**完了**] をクリックします。

オーディオ用の QoS ポリシーを作成した後で、2 番目にビデオ用のポリシーを作成する必要があります。ビデオ用のポリシーを作成するには、オーディオ ポリシーを作成したときと基本的には同じ手順に従い、次の点を変えます。

  - 異なる (一意の) ポリシー名を使用します。

  - DSCP の値を 46 ではなく「**34**」に設定します。(前に説明したとおり、DSCP の値に 34 を使用する必要はありません。ただ、オーディオに使用したのとは異なる DSCP の値を割り当てる必要があります。)

  - ビデオトラフィックに対して以前に構成されたポート範囲を使用します。 たとえば、ビデオに対してポート 58000 ~ 58019 を予約している場合は、ポート範囲を次のように設定します。 **58000:58019**。

アプリケーション共有トラフィックを管理するポリシーを作成する場合は、次のように置き換えます。

  - 別の (一意の) ポリシー名 (たとえば、 **Skype For Business Server アプリケーション共有**) を使用します。

  - DSCP の値を 46 ではなく「**24**」に設定します。(この値も 24 にする必要はありません。ただ、オーディオとビデオに使用した DSCP の値とは別にする必要があります。)

  - ビデオトラフィックに対して以前に構成されたポート範囲を使用します。 たとえば、アプリケーション共有用にポート 42000 ~ 42019 を予約している場合は、ポート範囲を次のように設定します。 **42000:42019**。

ファイル転送ポリシーは次のようにします。

  - 別の (一意の) ポリシー名 (たとえば、 **Skype For Business Server ファイル転送**) を使用します。

  - DSCP 値を**14**に設定します。 (この値は、14にする必要はありません。また、単に一意の DSCP コードでなければなりません)。

  - アプリケーションに対して以前に構成したポート範囲を使用します。 たとえば、アプリケーション共有用にポート 42020 ~ 42039 を予約している場合は、ポート範囲を次のように設定します。 **42020:42039**。

新しく作成したポリシーは、クライアント コンピューター上でグループ ポリシーが更新されるまで有効になりません。グループ ポリシーは定期的に自動更新を行いますが、グループ ポリシーの更新が必要な各コンピューター上で次のコマンドを実行することにより、強制的に即時更新できます。

    Gpupdate.exe /force

このコマンドは、管理者の資格情報で実行されていれば、どのコマンド ウィンドウからでも実行できます。コマンド ウィンドウを管理者の資格情報で実行するには、[**スタート**]をクリックして、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。

なお、これらのポリシーが対象とするのはクライアント コンピューターです。 これらは、Skype for Business Server を実行しているサーバーには適用されません。

ネットワーク パケットが適切な DSCP 値でマークされるようにするには、次の手順を実行して、各コンピューターに新しいレジストリ エントリを作成する必要もあります。

1.  **[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** をクリックします。

2.  [**実行**] ダイアログボックスで、「 **regedit**」と入力し、enter キーを押します。

3.  レジストリエディターで、[ **HKEY\_LOCAL\_MACHINE**] を展開し、[**システム**] を展開し、[ **CurrentControlSet**] を展開し、[**サービス**] を展開して、[ **Tcpip**] を展開します。

4.  [**Tcpip**] を右クリックし、[**新規**] をポイントして [**キー**] をクリックします。 新しいレジストリキーを作成したら、「 **QoS**」と入力し、enter キーを押してキーの名前を変更します。

5.  [**QoS**] を右クリックし、[**新規**] をポイントして [**文字列値**] をクリックします。 新しいレジストリ値が作成されたら、 **NLA を使用しない**と入力し、enter キーを押して値の名前を変更します。

6.  [**Do no use NLA**] をダブルクリックします。 [**文字列の編集**] ダイアログボックスで、[**値のデータ**] ボックスに「 **1** 」と入力し、[ **OK**] をクリックします。

7.  レジストリエディターを閉じ、コンピューターを起動します。

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>複数のネットワークアダプターがあるコンピューターでサービスの品質を構成する

複数のネットワークアダプターを備えたコンピューターがある場合は、構成された値ではなく0x00 として DSCP 値が表示される問題が発生することがあります。 通常、このような表示になるのは、1 つ以上のネットワーク アダプターが Active Directory ドメインにアクセスできないコンピューターです (たとえば、アダプターがプライベート ネットワークに使用されている場合)。 そのような場合、ドメインへアクセスできるアダプターには DSCP の値がマークされますが、ドメインへアクセスできないアダプターにはマークされません。

ドメインにアクセスできないアダプターを含む、コンピューター内のすべてのネットワークアダプターの DSCP 値にタグを付ける場合は、レジストリに値を追加して構成する必要があります。 このためには、次の手順を実行します。

1.  **[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** をクリックします。

2.  [**実行**] ダイアログボックスで、「 **regedit**」と入力し、enter キーを押します。

3.  レジストリエディターで、[ **HKEY\_LOCAL\_MACHINE**] を展開し、[**システム**] を展開し、[ **CurrentControlSet**] を展開し、[**サービス**] を展開して、[ **Tcpip**] を展開します。

4.  「**QoS**」というレジストリ キーがない場合は、 [**Tcpip**] 右クリックし、[**新規**] をポイントして、[**キー**] をクリックします。 新しいキーを作成したら、「 **QoS**」と入力し、enter キーを押してキーの名前を変更します。

5.  [**QoS**] を右クリックし、[**新規**] をポイントして [**文字列値**] をクリックします。 新しいレジストリ値が作成されたら、 **NLA を使用しない**と入力し、enter キーを押して値の名前を変更します。

6.  [**Do no use NLA**] をダブルクリックします。 [**文字列の編集**] ダイアログボックスで、[**値のデータ**] ボックスに「 **1** 」と入力し、[ **OK**] をクリックします。

新しいレジストリ値を作成して構成した後、変更を有効にするためにコンピューターを再起動する必要があります。

## <a name="see-also"></a>関連項目

[Windows 10 でグループポリシーオブジェクトを作成する](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
