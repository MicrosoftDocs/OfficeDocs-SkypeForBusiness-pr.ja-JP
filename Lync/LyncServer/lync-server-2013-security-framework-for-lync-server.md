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

# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="96643-102">Lync Server 2013 のセキュリティフレームワーク</span><span class="sxs-lookup"><span data-stu-id="96643-102">Security framework for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96643-103">_**最終更新日:** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="96643-103">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="96643-104">このセクションでは、Microsoft Lync Server 2013 のセキュリティフレームワークを形成する基本的な要素の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="96643-104">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="96643-105">これらの要素がどのように連携するかについて理解することは、特定の Lync Server 2013 の展開をセキュリティで保護することについて、情報に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="96643-105">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="96643-106">具体的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="96643-106">These elements are as follows:</span></span>

  - <span data-ttu-id="96643-107">Active Directory ドメインサービス (AD DS) は、ユーザーアカウントとネットワークリソース用の1つの信頼されたバックエンドリポジトリを提供します。</span><span class="sxs-lookup"><span data-stu-id="96643-107">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="96643-108">役割ベースのアクセス制御 (RBAC) を使用すると、高水準のセキュリティを維持しながら管理操作を委任できます。</span><span class="sxs-lookup"><span data-stu-id="96643-108">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="96643-109">公開キー基盤 (PKI) は、信頼された証明機関 (CA) から発行された証明書を使用してサーバーを認証し、データの整合性を確保します。</span><span class="sxs-lookup"><span data-stu-id="96643-109">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="96643-p102">トランスポート層セキュリティ (TLS)、HTTPS over SSL (HTTPS)、相互 TLS (MTLS) を使用すると、エンドポイント認証と IM の暗号化ができます。ポイント間の音声、ビデオ、アプリケーション共有のストリームは、セキュア リアルタイム転送プロトコル (SRTP) で暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="96643-p102">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="96643-112">ユーザーの認証には、業界標準のプロトコルができる限り使用されます。</span><span class="sxs-lookup"><span data-stu-id="96643-112">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="96643-113">Windows PowerShell には既定で有効になっているセキュリティ機能が用意されているため、ユーザーは簡単にスクリプトを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="96643-113">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="96643-114">これらの基本的なセキュリティ要素は連携して、Lync Server 2013 のセキュリティ保護された基盤を確保するのに役立つ、信頼されたユーザー、サーバー、接続、操作を定義します。</span><span class="sxs-lookup"><span data-stu-id="96643-114">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="96643-115">このセクション中</span><span class="sxs-lookup"><span data-stu-id="96643-115">In This Section</span></span>

<span data-ttu-id="96643-116">このセクションのトピックでは、Lync Server インフラストラクチャのセキュリティを強化するために、これらの各基本的な要素がどのように動作するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="96643-116">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="96643-117">Lync Server 2013 用 Active Directory ドメインサービス</span><span class="sxs-lookup"><span data-stu-id="96643-117">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="96643-118">Lync Server 2013 の役割ベースのアクセス制御 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="96643-118">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="96643-119">Lync Server 2013 用の公開キー基盤</span><span class="sxs-lookup"><span data-stu-id="96643-119">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="96643-120">Lync Server 2013 の TLS と MTLS</span><span class="sxs-lookup"><span data-stu-id="96643-120">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="96643-121">Lync Server 2013 の暗号化</span><span class="sxs-lookup"><span data-stu-id="96643-121">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="96643-122">Lync Server 2013 のユーザーとクライアントの認証</span><span class="sxs-lookup"><span data-stu-id="96643-122">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="96643-123">Windows PowerShell と Lync Server 2013 の管理ツール</span><span class="sxs-lookup"><span data-stu-id="96643-123">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

