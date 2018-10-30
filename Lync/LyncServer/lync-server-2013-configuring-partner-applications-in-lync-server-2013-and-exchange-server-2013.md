---
title: "Lync Server 2013 と Exchange Server 2013 のパートナー アプリケーションの構成"
TOCTitle: "Lync Server 2013 と Exchange Server 2013 のパートナー アプリケーションの構成"
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49887070
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 のパートナー アプリケーションの構成

 

_**トピックの最終更新日:** 2016-12-08_

サーバー間認証には、通常、3 つのエンティティが関与します。相互に通信する必要がある 2 つのサーバーと、サードパーティのセキュリティ トークン サーバーです。通信する必要がある 2 つのサーバー (サーバー A とサーバー B など) は、通常、最初にトークン サーバーに接続して、相互に信頼されたセキュリティ トークンを取得します。そのセキュリティ トークンが、サーバーが本物であり、信頼できることを保証するための手段として、一方のサーバーからもう一方のサーバー (サーバー A からサーバー B、またはサーバー B からサーバー A) に提示されます。

ただし、それは一般的な場合です。Lync Server 2013、Microsoft Exchange Server 2013、および Microsoft SharePoint Server 2013 では、相互に通信する際にサードパーティのトークン サーバーを使用する必要はありません。これらのサーバー製品では、独立したトークン サーバーを使用せずに相互に受け入れ可能なセキュリティ トークンを作成できるからです (この機能を使用できるのは、Lync Server 2013、Exchange 2013、および SharePoint Server 2013 のみです。その他のサーバー (マイクロソフトのその他のサーバー製品を含む) とのサーバー間認証を設定する必要がある場合は、サードパーティのトークン サーバーを使用する必要があります)。

Lync Server と Exchange の間でサーバー間認証を設定するには、次の 2 つの作業を行う必要があります。1) 各サーバーに適切な証明書を割り当てる必要があります。2) 各サーバーをもう一方のサーバーのパートナー アプリケーションとして構成する必要があります (つまり、Lync Server 2013 を Exchange 2013 のパートナー アプリケーションとして構成し、Exchange 2013 を Lync Server 2013 のパートナー アプリケーションとして構成する必要があります)。

## Lync Server 2013 を Exchange 2013 のパートナー アプリケーションとして構成する

Lync Server 2013 を Exchange 2013 のパートナー アプリケーションとして構成するには、Configure-EnterprisePartnerApplication.ps1 スクリプトを実行するのが最も簡単です。これは、Exchange 2013 に付属の Windows PowerShell スクリプトです。このスクリプトを実行するには、Lync Server の認証メタデータ ドキュメントの URL を指定する必要があります。これは通常、SharePoint プールの完全修飾ドメイン名に /metadata/json/1 というサフィックスを追加したものになります。次に例を示します。

    https://atl-cs-001.litwareinc.com/metadata/json/1

Lync Server をパートナー アプリケーションとして構成するには、Exchange 管理シェルを開いて次のようなコマンドを実行します (Exchange がドライブ C: にインストールされていて既定のフォルダー パスが使用されている場合)。

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

パートナー アプリケーションの構成が完了したら、Exchange のメールボックス サーバーとクライアント アクセス サーバーでインターネット インフォメーション サービス (IIS) を停止して再起動することをお勧めします。IIS を再起動するには次のようなコマンドを使用します。このコマンドは、コンピューター atl-exchange-001 でこのサービスを再起動します。

    iisreset atl-exchange-001

このコマンドは、Exchange 管理シェルから実行することも、管理者特権で実行されている他の任意のコマンド ウィンドウから実行することもできます。

## Exchange 2013 を Lync Server 2013 のパートナー アプリケーションとして構成する

Lync Server 2013 を Exchange 2013 のパートナー アプリケーションとして構成したら、次に、Exchange を Lync Server のパートナー アプリケーションとして構成する必要があります。そのためには、Lync Server 管理シェルを使用して、Exchange の認証メタデータ ドキュメントを指定します。これは通常、Exchange 自動検出サービスの URI にサフィックス /metadata/json/1 を追加したものになります。次に例を示します。

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

Lync Server では、[New-CsPartnerApplication](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsPartnerApplication) コマンドレットを使用してパートナー アプリケーションを構成します。メタデータの URI を指定するほかに、アプリケーションの信頼レベルを Full に設定する必要もあります。これにより、Exchange が領域内で自身と承認済みユーザーの両方を表すことができるようになります。次に例を示します。

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

また、Lync Server 2013 のサーバー間認証のドキュメントに含まれているスクリプト コードをコピーして変更することによってパートナー アプリケーションを作成することもできます。詳細については、「[Lync Server 2013 でのサーバー間認証 (Oauth) およびパートナー アプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。

Lync Server と Exchange の両方のパートナー アプリケーションの構成が完了したら、この 2 つの製品間のサーバー間認証の構成が完了したことになります。Lync Server 2013 に含まれている [Test-CsExStorageConnectivity](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExStorageConnectivity) という Windows PowerShell コマンドレットを使用すると、サーバー間認証が正しく構成されているかどうかと、Lync Server ストレージ サービスが Exchange 2013 に接続できるかどうかを確認できます。これは、Exchange 2013 ユーザーのメールボックスに接続し、そのユーザーの会話履歴フォルダーに項目を書き込むことによって行われます。必要に応じてその項目を削除することもできます。

Lync Server 2013 と Exchange 2013 の統合をテストするには、Lync Server 管理シェルから次のようなコマンドを実行します。

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

上のコマンドの SipUri は、Exchange 2013 のアカウントを持つユーザーの SIP アドレスを表します。これが有効なユーザー アカウントでない場合、このコマンドは失敗します。

テストが成功して、接続が確立されたら、オプション機能 (アーカイブの統合、統合連絡先ストアなど) を構成できます。

