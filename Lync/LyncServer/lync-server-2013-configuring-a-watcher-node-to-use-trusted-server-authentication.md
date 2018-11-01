---
title: 信頼されたサーバー認証を使用する監視ノードの構成
TOCTitle: 信頼されたサーバー認証を使用する監視ノードの構成
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48271915
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 信頼されたサーバー認証を使用する監視ノードの構成

 

_**トピックの最終更新日:** 2012-10-22_

監視ノード コンピューターが境界ネットワーク内にある場合、信頼済みサーバー認証によって 1 つの証明書を管理するだけでよくなるので、管理負荷が大幅に軽減されます。膨大な数のユーザー アカウント パスワードを管理する必要はありません。

信頼済みサーバー認証を構成するには、最初のステップとして、まず監視ノード コンピューターをホストする信頼済みアプリケーション プールを作成します。信頼済みアプリケーション プールが作成されたら、その監視ノードで、信頼済みアプリケーションとして実行されるように代理トランザクションを構成する必要があります。

> [!NOTE]
> 信頼済みアプリケーションとは、信頼済みステータスが付与されたアプリケーションのことで、Lync Server 2013 の一部として実行されますが、製品には組み込まれていません。信頼済みステータスのアプリケーションは、実行のたびに認証でチャレンジされることはありません。


信頼済みアプリケーション プールを作成するには、Lync Server 2013 管理シェルを開き、次のようなコマンドを実行します。

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

> [!NOTE]
> 上記のコマンドで使用されているパラメーターの詳細を確認するには、Lync Server 管理シェル プロンプトで次のように入力します。<br />
> Get-Help New-CsTrustedApplicationPool -Full | more


信頼済みアプリケーション プールの作成後、代理トランザクションが信頼済みアプリケーションアプリケーションとして実行されるように監視ノード コンピューターを構成します。これを行うには、**New-CsTrustedApplication** コマンドレットと、次のようなコマンドを使用します。

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

上記のコマンドが完了し、信頼済みアプリケーションが作成されたら、Enable-CsTopology を実行して変更を有効にします。

    Enable-CsTopology

Enable-CsTopology の実行後は、コンピューターを再起動することをお勧めします。

新しい信頼済みアプリケーションが作成されたことを確認するには、Lync Server 管理シェル プロンプトで次のように入力します。

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

## 監視ノードで既定の証明書を構成する

各監視ノードに、Lync Server 展開ウィザードを使用して割り当てられた既定の証明書が必要です。

**既定の証明書を割り当てるには**

1.  \[**スタート**\]、\[**すべてのプログラム**\]、\[**Lync Server**\]、\[**Lync Server 展開ウィザード**\] の順にクリックします。

2.  Lync Server 展開ウィザードで \[**Lync Server システムのインストールまたは更新**\] をクリックし、\[**証明書の要求、インストール、または割り当て**\] で \[**実行**\] をクリックします。
    
    > [!NOTE]
    > [<strong>実行</strong>] ボタンをが無効になっている場合は、[<strong>ローカル構成ストアのインストール</strong>] で [<strong>実行</strong>] を最初にクリックしなければならないことがあります。


3.  次のどちらかの操作を行います。
    
      - 既定の証明書として使用できる証明書が既にある場合は、証明書ウィザードで \[**既定**\] をクリックし、\[**割り当て**\] をクリックします。証明書の割り当てウィザードの手順に従って、証明書を割り当てます。
    
      - 既定の証明書として使用する証明書を要求する必要がある場合は、\[**要求**\] をクリックし、証明書要求ウィザードの手順に従ってその証明書を要求します。Web サーバー証明書の既定値を使用すると、既定の証明書として割り当てることができる証明書を取得できます。

## 監視ノードをインストールおよび構成する

監視ノード コンピューターを再起動し、証明書を構成したら、Watchernode.msi ファイルを実行する必要があります (Watchernode.msi は、Operations Manager エージェント ファイルと Lync Server 2013 コア コンポーネントの両方がインストールされているコンピューターで実行する必要があります)。

**監視ノードをインストールおよび構成するには**

1.  \[**スタート**\]、\[**すべてのプログラム**\]、\[**Lync Server**\]、\[**Lync Server 管理シェル**\] の順にクリックし、Lync Server 管理シェルを開きます。

2.  Lync Server 管理シェルで、次のコマンドを入力して、Enter キーを押します (Watchernode.msi のコピーへの実際のパスを指定)。
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    > [!NOTE]
    > コマンド ウィンドウから Watchernode.msi を実行することもできます。コマンド ウィンドウを開くには、[<strong>スタート</strong>] をクリックし、[<strong>コマンド プロンプト</strong>] を右クリックして、[<strong>管理者として実行</strong>] をクリックします。コマンド ウィンドウが開いたら、上記と同じコマンドを入力します。


上記のコマンドの名前/値ペア Authentication=TrustedServer は大文字と小文字が区別されるので、ここで示すとおりに正確に入力する必要があります。次のコマンドは、大文字と小文字が正しく使用されていないので失敗します。

C:\\Tools\\Watchernode.msi authentication=trustedserver

TrustedServer モードは、境界ネットワーク内のコンピューターでのみ使用できます。監視ノードが TrustedServer モードで実行されている場合は、管理者が、コンピューター上のテスト ユーザー パスワードを管理する必要はありません。

