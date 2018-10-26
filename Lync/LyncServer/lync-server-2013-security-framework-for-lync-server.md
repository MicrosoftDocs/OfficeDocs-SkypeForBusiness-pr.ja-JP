---
title: Lync Server 2013 のセキュリティ フレームワーク
TOCTitle: Lync Server 2013 のセキュリティ フレームワーク
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59682884
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のセキュリティ フレームワーク

 

_**トピックの最終更新日:** 2013-11-08_

ここでは、Microsoft Lync Server 2013 のセキュリティ フレームワークを形成する基本要素の概要を示します。これらの要素が連携するしくみを理解することは、実際に使う Lync Server 2013 展開のセキュリティ保護について十分な情報に基づいた決断を行うために不可欠です。

具体的な要素は次のとおりです。

  - Active Directory ドメイン サービス (AD DS) は、ユーザー アカウントとネットワーク リソースの信頼できる単一のバックエンド リポジトリを提供します。

  - 役割ベースのアクセス制御 (RBAC) では、高水準のセキュリティを維持しながら管理タスクを委任できます。

  - 公開キー基盤 (PKI) は、信頼された証明機関 (CA) によって発行された証明書を使用してサーバーを認証し、データの整合性を確保します。

  - トランスポート層セキュリティ (TLS)、HTTP over SSL (HTTPS)、および相互 TLS (MTLS) により、エンドポイント認証と IM の暗号化が可能になります。ポイント間の音声、ビデオ、およびアプリケーション共有のストリームは、セキュア リアルタイム転送プロトコル (SRTP) で暗号化されます。

  - ユーザーの認証には、業界標準のプロトコルが可能な限り使用されます。

  - Windows PowerShell には、既定で有効となっているセキュリティ機能があり、ユーザーが簡単には (または知らないうちに) スクリプトを実行できないようになっています。

これらの基本的なセキュリティ要素が連携することで、信頼の置けるユーザー、サーバー、接続、および操作が定められ、Lync Server 2013 の安全な基盤が確立されます。

## このセクション中

このセクションのトピックでは、Lync Server インフラストラクチャのセキュリティを高めるために、これらの各基本要素が機能するしくみについて説明します。

  - [Lync Server 2013 用の Active Directory ドメイン サービス](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Lync Server 2013 の役割ベースのアクセス制御 (RBAC)](lync-server-2013-role-based-access-control-rbac.md)

  - [Lync Server 2013 の公開キー基盤](lync-server-2013-public-key-infrastructure.md)

  - [Lync Server 2013 の TLS と MTLS](lync-server-2013-tls-and-mtls.md)

  - [Lync Server 2013 の暗号化](lync-server-2013-encryption.md)

  - [Lync Server 2013 でのユーザーとクライアントの認証](lync-server-2013-user-and-client-authentication.md)

  - [Windows PowerShell と Lync Server 2013 の管理ツール](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

