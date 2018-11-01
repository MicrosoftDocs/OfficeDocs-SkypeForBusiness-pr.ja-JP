---
title: Lync Server 2013 の証明書インフラストラクチャのサポート
TOCTitle: 証明書インフラストラクチャのサポート
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48271965
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での証明書インフラストラクチャのサポート

 

_**トピックの最終更新日:** 2013-11-07_

Lync Server 2013 では、トランスポート層セキュリティ (TLS) 接続および相互 TLS (MTLS) 接続をサポートするための公開キー基盤 (PKI) が必要です。既定では、Lync Server 2013 はクライアントとサーバー間の接続に TLS を使用するように構成されています。MTLS は、サーバー間の接続に使用されます。

MTLS 証明書は、Lync Server 2013 の信頼された証明機関 (CA) によって発行される必要があります。Lync Server は、次の CA から発行される証明書をサポートしています。

  - 内部 CA から発行される証明書:
    
      - Windows Server 2003 オペレーティング システムの CA
    
      - Windows Server 2008 オペレーティング システムの CA
    
      - Windows Server 2008 R2 オペレーティング システムの CA
    
      - Windows Server 2012 オペレーティング システムの CA
    
      - Windows Server 2012 R2 オペレーティング システムの CA

  - パブリック CA から発行される証明書

Exchange 2013 など、他のアプリケーションやサーバーとの通信には、その他のアプリケーションや製品でサポートされている証明書が必要です。2013 リリースの場合、Lync Server 2013 をはじめとする Microsoft サーバー製品 (Exchange 2013 や SharePoint Server を含む) は、サーバー間の認証および承認で OAuth (Open Authorization) プロトコルをサポートしています。詳細については、「展開」または「操作」のドキュメントの「[Lync Server 2013 でのサーバー間認証 (Oauth) およびパートナー アプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。

Windows 7 オペレーティング システム、Windows Server 2008 R2 オペレーティング システム、Microsoft Office Communicator 2007 Phone Edition を実行するクライアントから接続する場合、Lync Server 2013 は SHA-256 暗号ハッシュ関数を使用して署名した証明書も (必要はありませんが) サポートします。SHA-256 を使用する外部アクセスをサポートするには、SHA-256 を使用するパブリック CA が外部証明書を発行する必要があります。

証明書要件の詳細については、「計画」のドキュメントの「[Lync Server 2013 の証明書インフラストラクチャの要件](lync-server-2013-certificate-infrastructure-requirements.md)」を参照してください。証明書におけるワイルドカードの使用の詳細については、「サポート」のドキュメントの「[Lync Server 2013 のワイルドカード証明書のサポート](lync-server-2013-wildcard-certificate-support.md)」を参照してください。

