---
title: 'Lync Server 2013: Lync Server のセキュリティフレームワーク'
description: 'Lync Server 2013: Lync Server のセキュリティフレームワーク。'
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
ms.openlocfilehash: 7d30c26929ddedbf653abd1fc353b6873ad8f36f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551433"
---
# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="48dd6-103">Lync Server 2013 のセキュリティフレームワーク</span><span class="sxs-lookup"><span data-stu-id="48dd6-103">Security framework for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48dd6-104">_**トピックの最終更新日:** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="48dd6-104">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="48dd6-105">このセクションでは、Microsoft Lync Server 2013 のセキュリティフレームワークを形成する基本的な要素の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="48dd6-105">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="48dd6-106">これらの要素がどのように連携するかを理解することは、特定の Lync Server 2013 の展開をセキュリティで保護することに関する情報を得ることが重要です。</span><span class="sxs-lookup"><span data-stu-id="48dd6-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="48dd6-107">具体的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="48dd6-107">These elements are as follows:</span></span>

  - <span data-ttu-id="48dd6-108">Active Directory ドメイン サービス (AD DS) は、ユーザー アカウントとネットワーク リソースの信頼できる単一のバックエンド リポジトリを提供します。</span><span class="sxs-lookup"><span data-stu-id="48dd6-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="48dd6-109">Role-Based アクセス制御 (RBAC) を使用すると、高水準のセキュリティを維持しながら管理タスクを委任できます。</span><span class="sxs-lookup"><span data-stu-id="48dd6-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="48dd6-110">公開キー基盤 (PKI) は、信頼された証明機関 (CAs) が発行する証明書を使用してサーバーを認証し、データの整合性を確保します。</span><span class="sxs-lookup"><span data-stu-id="48dd6-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="48dd6-p102">トランスポート層セキュリティ (TLS)、HTTP over SSL (HTTPS)、および相互 TLS (MTLS) により、エンドポイント認証と IM の暗号化が可能になります。ポイント間の音声、ビデオ、およびアプリケーション共有のストリームは、セキュア リアルタイム転送プロトコル (SRTP) で暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="48dd6-p102">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="48dd6-113">ユーザーの認証には、業界標準のプロトコルが可能な限り使用されます。</span><span class="sxs-lookup"><span data-stu-id="48dd6-113">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="48dd6-114">Windows PowerShell には、既定で有効となっているセキュリティ機能があり、ユーザーが簡単には (または知らないうちに) スクリプトを実行できないようになっています。</span><span class="sxs-lookup"><span data-stu-id="48dd6-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="48dd6-115">これらの基本的なセキュリティ要素が連携して、Lync Server 2013 のセキュリティを確保するために、信頼できるユーザー、サーバー、接続、および操作を定義します。</span><span class="sxs-lookup"><span data-stu-id="48dd6-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="48dd6-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="48dd6-116">In This Section</span></span>

<span data-ttu-id="48dd6-117">このセクションのトピックでは、Lync Server インフラストラクチャのセキュリティを強化するためにこれらの基本的な要素がどのように機能するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="48dd6-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="48dd6-118">Lync Server 2013 の Active Directory ドメインサービス</span><span class="sxs-lookup"><span data-stu-id="48dd6-118">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="48dd6-119">Lync Server 2013 の役割ベースのアクセス制御 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="48dd6-119">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="48dd6-120">Lync Server 2013 の公開キー基盤</span><span class="sxs-lookup"><span data-stu-id="48dd6-120">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="48dd6-121">Lync Server 2013 の TLS と MTLS</span><span class="sxs-lookup"><span data-stu-id="48dd6-121">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="48dd6-122">Lync Server 2013 の暗号化</span><span class="sxs-lookup"><span data-stu-id="48dd6-122">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="48dd6-123">Lync Server 2013 のユーザーとクライアントの認証</span><span class="sxs-lookup"><span data-stu-id="48dd6-123">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="48dd6-124">Windows PowerShell および Lync Server 2013 の管理ツール</span><span class="sxs-lookup"><span data-stu-id="48dd6-124">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

