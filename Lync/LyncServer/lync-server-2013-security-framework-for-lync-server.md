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
ms.openlocfilehash: 1a2b58d34c1ed1f899e0daac8c1bb0132b1a22d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a>Lync Server 2013 のセキュリティフレームワーク

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-08_

このセクションでは、Microsoft Lync Server 2013 のセキュリティフレームワークを形成する基本的な要素の概要について説明します。 これらの要素がどのように連携するかについて理解することは、特定の Lync Server 2013 の展開をセキュリティで保護することについて、情報に基づいて決定する

具体的な要素は次のとおりです。

  - Active Directory ドメインサービス (AD DS) は、ユーザーアカウントとネットワークリソース用の1つの信頼されたバックエンドリポジトリを提供します。

  - 役割ベースのアクセス制御 (RBAC) を使用すると、高水準のセキュリティを維持しながら管理操作を委任できます。

  - 公開キー基盤 (PKI) は、信頼された証明機関 (CA) から発行された証明書を使用してサーバーを認証し、データの整合性を確保します。

  - トランスポート層セキュリティ (TLS)、HTTPS over SSL (HTTPS)、相互 TLS (MTLS) を使用すると、エンドポイント認証と IM の暗号化ができます。ポイント間の音声、ビデオ、アプリケーション共有のストリームは、セキュア リアルタイム転送プロトコル (SRTP) で暗号化されます。

  - ユーザーの認証には、業界標準のプロトコルができる限り使用されます。

  - Windows PowerShell には既定で有効になっているセキュリティ機能が用意されているため、ユーザーは簡単にスクリプトを実行することはできません。

これらの基本的なセキュリティ要素は連携して、Lync Server 2013 のセキュリティ保護された基盤を確保するのに役立つ、信頼されたユーザー、サーバー、接続、操作を定義します。

<div>

## <a name="in-this-section"></a>このセクション中

このセクションのトピックでは、Lync Server インフラストラクチャのセキュリティを強化するために、これらの各基本的な要素がどのように動作するかについて説明します。

  - [Lync Server 2013 用 Active Directory ドメインサービス](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Lync Server 2013 の役割ベースのアクセス制御 (RBAC)](lync-server-2013-role-based-access-control-rbac.md)

  - [Lync Server 2013 用の公開キー基盤](lync-server-2013-public-key-infrastructure.md)

  - [Lync Server 2013 の TLS と MTLS](lync-server-2013-tls-and-mtls.md)

  - [Lync Server 2013 の暗号化](lync-server-2013-encryption.md)

  - [Lync Server 2013 のユーザーとクライアントの認証](lync-server-2013-user-and-client-authentication.md)

  - [Windows PowerShell と Lync Server 2013 の管理ツール](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

