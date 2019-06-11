---
title: 信頼されたサーバー認証を使用するためのウォッチャーノードの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6634fa55424190d2e0a05aece38d88977d2f6bca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>Lync Server 2013 で監視ノードを構成して、信頼されたサーバー認証を使用する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

ウォッチャーノードコンピューターが境界ネットワーク内にある場合、信頼されたサーバー認証を使用すると、多数のユーザーアカウントパスワードではなく1つの証明書を管理するために管理税が大幅に減少する可能性があります。

信頼されたサーバー認証を構成するための最初の手順は、監視ノードコンピューターをホストする信頼されたアプリケーションプールを作成することです。 信頼されたアプリケーションプールを作成した後で、そのウォッチャーノードの代理トランザクションを、信頼されたアプリケーションとして実行されるように構成する必要があります。

<div>


> [!NOTE]
> 信頼されたアプリケーションとは、Lync Server 2013 の一部として実行される信頼された状態を提供するアプリケーションですが、製品の組み込みの部分ではありません。 Trusted status means that the application will not be challenged for authentication each time it runs.



</div>

信頼されたアプリケーションプールを作成するには、Lync Server 2013 管理シェルを開き、次のようなコマンドを実行します。

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> 上記のコマンドで使用されるパラメーターの詳細については、「Lync Server 管理シェルのプロンプトで次のように入力します。<BR>CsTrustedApplicationPool---------------------もっとその



</div>

信頼されたアプリケーションプールを作成したら、信頼されたアプリケーションとして代理トランザクションを実行するようにウォッチャーノードのコンピューターを構成します。 これを行うには、 **CsTrustedApplication**コマンドレットと次のようなコマンドを使用します。

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

上記のコマンドが完了し、信頼されたアプリケーションが作成されたら、Enable-CsTopology ツールを実行して、変更が反映されるようにします。

    Enable-CsTopology

Enable-CsTopology ツールを実行した後、コンピューターを再起動することをお勧めします。

新しい信頼済みアプリケーションが作成されたことを確認するには、Lync Server 管理シェルのプロンプトで次のように入力します。

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>ウォッチャーノードでの既定の証明書の構成

各ウォッチャーノードには、Lync Server 展開ウィザードを使用して、既定の証明書を割り当てる必要があります。

**既定の証明書を割り当てるには**

1.  [**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[ **lync server**] をクリックして、[ **lync server Deployment Wizard**] をクリックします。

2.  Lync Server 展開ウィザードで、[ **Lync Server System をインストールまたは更新**する] をクリックし、[**要求]、[インストール]、または [証明書の割り当て**] の [**実行**] をクリックします。
    
    <div>
    

    > [!NOTE]
    > [<STRONG>実行</STRONG>] ボタンが無効になっている場合は、最初に [<STRONG>ローカル構成ストアのインストール</STRONG>] の [<STRONG>実行</STRONG>] をクリックする必要があります。

    
    </div>

3.  次のいずれかの操作を行います。
    
      - 既定の証明書として使用できる証明書が既にある場合は、証明書ウィザードで [**既定**] をクリックし、[**割り当て**] をクリックします。 証明書の割り当てウィザードの手順に従って、証明書を割り当てます。
    
      - 既定の証明書を使用するために証明書を要求する必要がある場合は、[**要求**] をクリックし、証明書の要求ウィザードの手順に従って証明書を要求します。 Web サーバー証明書の既定値を使用すると、既定の証明書として割り当てることができる証明書を取得できます。

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>ウォッチャーノードのインストールと構成

ウォッチャーノードのコンピューターを再起動して証明書を構成したら、Watchernode ファイルを実行する必要があります。 (Operations Manager エージェントファイルと Lync Server 2013 コアコンポーネントの両方がインストールされているコンピューターで Watchernode を実行する必要があります)。

**ウォッチャーノードをインストールして構成するには**

1.  [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Lync Server**]、[ **lync server 管理シェル**] の順にクリックして、lync server 管理シェルを開きます。

2.  Lync Server 管理シェルで、次のコマンドを入力し、enter キーを押します (Watchernode のコピーの実際のパスを指定します)。
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > コマンドウィンドウから Watchernode を実行することもできます。 コマンド ウィンドウを開くには、[<STRONG>スタート</STRONG>] メニューをクリックし、[<STRONG>コマンド プロンプト</STRONG>] を右クリックして、[<STRONG>管理者として実行</STRONG>] をクリックします。 コマンドウィンドウが開いたら、上記と同じコマンドを入力します。

    
    </div>

上のコマンド Authentication = TrustedServer では、名前/値のペアは大文字と小文字が区別されることに注意してください。 示されているとおりに入力する必要があります。 次のコマンドは、正しい文字の大文字と小文字を区別しないために失敗します。

C:\\ツール\\Watchernode 認証 = trustedserver

TrustedServer モードは、境界ネットワーク内に配置されているコンピューターでのみ使うことができます。 Watcher ノードが TrustedServer モードで実行されている場合、管理者は、コンピューター上のテストユーザーパスワードを管理する必要はありません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

