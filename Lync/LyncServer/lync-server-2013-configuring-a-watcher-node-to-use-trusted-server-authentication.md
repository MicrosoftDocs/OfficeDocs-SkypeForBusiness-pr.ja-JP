---
title: 信頼されたサーバー認証を使用する監視ノードの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1478e2b2153c1b6834629ab41ccd6cde5b272430
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517704"
---
# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>Lync Server 2013 の監視ノードを構成して、信頼されたサーバー認証を使用する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

監視ノード コンピューターが境界ネットワーク内にある場合、信頼済みサーバー認証によって 1 つの証明書を管理するだけでよくなるので、管理負荷が大幅に軽減されます。膨大な数のユーザー アカウント パスワードを管理する必要はありません。

信頼済みサーバー認証を構成するには、最初のステップとして、まず監視ノード コンピューターをホストする信頼済みアプリケーション プールを作成します。信頼済みアプリケーション プールが作成されたら、その監視ノードで、信頼済みアプリケーションとして実行されるように代理トランザクションを構成する必要があります。

<div>


> [!NOTE]
> 信頼されたアプリケーションとは、Lync Server 2013 の一部として実行される信頼できる状態が与えられているアプリケーションですが、これは製品の組み込みパーツではありません。 信頼済みステータスのアプリケーションは、実行のたびに認証でチャレンジされることはありません。



</div>

信頼されたアプリケーションプールを作成するには、Lync Server 2013 管理シェルを開き、次のようなコマンドを実行します。

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> 上記のコマンドで使用されたパラメーターの詳細については、Lync Server 管理シェルプロンプトで次のように入力します。<BR>Get-Help New-CsTrustedApplicationPool -Full | more



</div>

信頼済みアプリケーション プールの作成後、代理トランザクションが信頼済みアプリケーションアプリケーションとして実行されるように監視ノード コンピューターを構成します。 これを行うには、**New-CsTrustedApplication** コマンドレットと、次のようなコマンドを使用します。

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

上記のコマンドが完了し、信頼済みアプリケーションが作成されたら、Enable-CsTopology を実行して変更を有効にします。

    Enable-CsTopology

Enable-CsTopology の実行後は、コンピューターを再起動することをお勧めします。

新しい信頼済みアプリケーションが作成されたことを確認するには、Lync Server 管理シェルプロンプトで次のように入力します。

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>監視ノードで既定の証明書を構成する

各監視ノードには、Lync Server 展開ウィザードを使用して、既定の証明書が割り当てられている必要があります。

**既定の証明書を割り当てるには**

1.  [ **スタート**]、[ **すべてのプログラム**]、[ **Lync Server**]、[ **lync server 展開ウィザード**] の順にクリックします。

2.  Lync Server 展開ウィザードで、[ **Lync Server システムのインストールまたは更新**] をクリックし、[**要求]、[インストール]、または [証明書の割り当て**] の [**実行**] をクリックします。
    
    <div>
    

    > [!NOTE]
    > [<STRONG>実行</STRONG>] ボタンをが無効になっている場合は、[<STRONG>ローカル構成ストアのインストール</STRONG>] で [<STRONG>実行</STRONG>] を最初にクリックしなければならないことがあります。

    
    </div>

3.  次のどちらかの操作を行います。
    
      - 既定の証明書として使用できる証明書が既にある場合は、証明書ウィザードで [**既定**] をクリックし、[**割り当て**] をクリックします。証明書の割り当てウィザードの手順に従って、証明書を割り当てます。
    
      - 既定の証明書として使用する証明書を要求する必要がある場合は、[**要求**] をクリックし、証明書要求ウィザードの手順に従ってその証明書を要求します。Web サーバー証明書の既定値を使用すると、既定の証明書として割り当てることができる証明書を取得できます。

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>監視ノードをインストールおよび構成する

監視ノードコンピューターを再起動し、証明書を構成した後、ファイル Watchernode.msi を実行する必要があります。 (Operations Manager エージェントファイルと Lync Server 2013 コアコンポーネントの両方がインストールされているコンピューターで Watchernode.msi を実行する必要があります)。

**監視ノードをインストールおよび構成するには**

1.  [ **スタート**]、[ **すべてのプログラム**]、[ **Lync server**]、[ **lync server 管理シェル**] の順にクリックして、Lync server 管理シェルを開きます。

2.  Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します (Watchernode.msi のコピーへの実際のパスを指定します)。
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > コマンド ウィンドウから Watchernode.msi を実行することもできます。コマンド ウィンドウを開くには、[<STRONG>スタート</STRONG>] をクリックし、[<STRONG>コマンド プロンプト</STRONG>] を右クリックして、[<STRONG>管理者として実行</STRONG>] をクリックします。コマンド ウィンドウが開いたら、上記と同じコマンドを入力します。

    
    </div>

上記のコマンドの名前/値ペア Authentication=TrustedServer は大文字と小文字が区別されるので、ここで示すとおりに正確に入力する必要があります。次のコマンドは、大文字と小文字が正しく使用されていないので失敗します。

C: \\ ツール \\Watchernode.msi 認証 = trustedserver

TrustedServer モードは、境界ネットワーク内のコンピューターでのみ使用できます。監視ノードが TrustedServer モードで実行されている場合は、管理者が、コンピューター上のテスト ユーザー パスワードを管理する必要はありません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

