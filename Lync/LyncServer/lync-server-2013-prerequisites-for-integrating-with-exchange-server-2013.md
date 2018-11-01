---
title: Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 の統合の前提条件
TOCTitle: Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 の統合の前提条件
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49887197
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 の統合の前提条件

 

_**トピックの最終更新日:** 2016-12-08_

Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 を統合する前に、必要な手順がすべて完了していることを確認する必要があります。当然ながら、Exchange 2013 と Lync Server 2013 の両方が完全にインストールされ、稼働されるまで、統合はできません。Exchange のインストールの詳細については、Exchange 2013 の「計画と展開」のドキュメント ([http://go.microsoft.com/fwlink/?linkid=268539\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268539%26clcid=0x411)) を参照してください。Lync Server 2013 のインストールの詳細については、「計画と展開」のドキュメント ([http://go.microsoft.com/fwlink/?linkid=254806\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=254806%26clcid=0x411)) を参照してください。

サーバーが稼働した後で、サーバー間認証の証明書を Lync Server 2013 と Exchange 2013 の両方に割り当てる必要があります。これらの証明書によって、Lync Server と Exchange は情報の交換や相互の通信ができるようになります。Exchange 2013 をインストールする場合、Microsoft Exchange Server Auth Certificate という名前で自己署名証明書が作成されます。この証明書はローカル コンピューターの証明書ストアに格納され、Exchange 2013 のサーバー間認証に使用されます。Exchange 2013 における証明書の割り当ての詳細については、「メール フローとクライアント アクセスの構成」([http://go.microsoft.com/fwlink/?linkid=268540\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268540%26clcid=0x411)) を参照してください。

Lync Server 2013 には、既存の Lync Server 証明書をサーバー間認証の証明書として使用できます。たとえば、既定の証明書は OAuthTokenIssuer 証明書としても使用できます。Lync Server 2013 によって、任意の Web サーバー証明書をサーバー間認証の証明書として使用できるようになります。ただし次の条件があります。

  - 証明書の \[Subject\] (サブジェクト) フィールドに SIP ドメインの名前が含まれている。

  - これと同じ証明書がすべてのフロントエンド サーバーで OAuthTokenIssuer 証明書として構成されている。

  - 証明書の長さが 2,048 ビット以上。

Microsoft Lync Server 2013 のサーバー間認証の証明書の詳細については、「[サーバー間の認証証明書の Microsoft Lync Server 2013 への割り当て](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md) を参照してください。」

証明書が割り当てられた後で、Exchange 2013 上で autodiscover サービスを構成する必要があります。Exchange 2013 では、ユーザーがシステムにログオンしたときに autodiscover サービスがユーザー プロファイルを構成し、Exchange サービスへのアクセスを提供します。ユーザーが autodiscover サービスに電子メール アドレスとパスワードを入力すると、このサービスからユーザーへ次の情報が提供されます。

  - Exchange 2013 への内部接続および外部接続のための接続情報。

  - ユーザーのメールボックス サーバーの場所。

  - 空き時間情報、ユニファイド メッセージング、およびオフライン アドレス帳などの Outlook 機能の URL。

  - Outlook Anywhere のサーバー設定。

Lync Server 2013 と Exchange 2013 を統合するためには、autodiscover サービスを構成しておく必要があります。autodiscover サービスが構成されているかどうかは、Exchange の管理シェルから次のコマンドを入力し、AutoDiscoverServiceInternalUri プロパティの値をチェックすることによって確認できます。

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

この値が空白の場合、autodiscover サービスに URI を割り当てる必要があります。通常、この URI は次のようになります。

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

autodiscover の URI は、次のようなコマンドを実行することによって割り当てられます。

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

autodiscover サービスの詳細については、「自動検出サービスについて」([http://go.microsoft.com/fwlink/?linkid=268542\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268542%26clcid=0x411)) を参照してください。

autodiscover サービスを構成した後で、Lync Server の OAuth 構成設定を変更する必要があります。これにより、Lync Server は autodiscover サービスの場所を知ることができます。Lync Server 2013 の OAuth 構成設定を変更するには、Lync Server 管理シェル 内から次のコマンドを実行します。このコマンドを実行するときは、必ず Exchange サーバー上で実行されている autodiscover サービスの URI を指定し、**autodiscover.xml** (サービスが使用する XML ファイルを指定) ではなく **autodiscover.svc** を使用してこのサービスの場所を指定してください。

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc

> [!NOTE]  
> 上記のコマンドの Identity パラメーターは省略可能です。Lync Server では 1 つのグローバルな OAuth 構成設定しかできないためです。つまり、より単純な次のコマンドを使用して autodiscover の URL を構成できるということです。<br />
> Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl &quot;https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc&quot;<br />
> OAuth というテクノロジは、多くの大手 Web サイトで使用されている標準的な認証プロトコルです。OAuth では、ユーザーの資格情報とパスワードがコンピューター間で渡されることはありません。その代わりに、セキュリティ トークンの交換に基づいて認証と承認が行われます。これらのトークンによって、特定のリソースのセットに対する特定の時間のアクセスが許可されます。

autodiscover サービスの構成に加えて、このサービスのために Exchange サーバーを示す DNS レコードを作成する必要があります。たとえば、autodiscover サービスが autodiscover.litwareinc.com にある場合、autodiscover.litwareinc.com のために Exchange サーバーの完全修飾ドメイン名 (たとえば atl-exchange-001.litwareinc.com) に解決される DNS レコードを作成する必要があります。

