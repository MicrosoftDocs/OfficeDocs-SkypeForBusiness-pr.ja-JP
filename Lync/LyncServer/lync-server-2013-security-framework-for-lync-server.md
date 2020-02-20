---
title: 'Lync Server 2013: Lync Server のセキュリティフレームワーク'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 472e15d2206e787abb571885f0155bb0169f7234
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a>Lync Server 2013 のセキュリティフレームワーク

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-08_

このセクションでは、Microsoft Lync Server 2013 のセキュリティフレームワークを形成する基本的な要素の概要を説明します。 これらの要素がどのように連携するかを理解することは、特定の Lync Server 2013 の展開をセキュリティで保護することに関する情報を得ることが重要です。

具体的な要素は次のとおりです。

  - Active Directory ドメイン サービス (AD DS) は、ユーザー アカウントとネットワーク リソースの信頼できる単一のバックエンド リポジトリを提供します。

  - 役割ベースのアクセス制御 (RBAC) を使用すると、高水準のセキュリティを維持しながら管理タスクを委任できます。

  - 公開キー基盤 (PKI) は、信頼された証明機関 (CAs) が発行する証明書を使用してサーバーを認証し、データの整合性を確保します。

  - トランスポート層セキュリティ (TLS)、HTTP over SSL (HTTPS)、および相互 TLS (MTLS) により、エンドポイント認証と IM の暗号化が可能になります。ポイント間の音声、ビデオ、およびアプリケーション共有のストリームは、セキュア リアルタイム転送プロトコル (SRTP) で暗号化されます。

  - ユーザーの認証には、業界標準のプロトコルが可能な限り使用されます。

  - Windows PowerShell には、既定で有効となっているセキュリティ機能があり、ユーザーが簡単には (または知らないうちに) スクリプトを実行できないようになっています。

これらの基本的なセキュリティ要素が連携して、Lync Server 2013 のセキュリティを確保するために、信頼できるユーザー、サーバー、接続、および操作を定義します。

<div>

## <a name="in-this-section"></a>このセクションの内容

このセクションのトピックでは、Lync Server インフラストラクチャのセキュリティを強化するためにこれらの基本的な要素がどのように機能するかについて説明します。

  - [Lync Server 2013 の Active Directory ドメインサービス](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Lync Server 2013 の役割ベースのアクセス制御 (RBAC)](lync-server-2013-role-based-access-control-rbac.md)

  - [Lync Server 2013 の公開キー基盤](lync-server-2013-public-key-infrastructure.md)

  - [Lync Server 2013 の TLS と MTLS](lync-server-2013-tls-and-mtls.md)

  - [Lync Server 2013 の暗号化](lync-server-2013-encryption.md)

  - [Lync Server 2013 のユーザーとクライアントの認証](lync-server-2013-user-and-client-authentication.md)

  - [Windows PowerShell および Lync Server 2013 の管理ツール](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

