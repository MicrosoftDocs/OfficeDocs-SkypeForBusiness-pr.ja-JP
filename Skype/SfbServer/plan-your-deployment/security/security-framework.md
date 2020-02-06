---
title: Skype for Business Server のセキュリティフレームワーク
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: このセクションでは、Skype for Business Server のセキュリティフレームワークを形成する基本的な要素の概要について説明します。 これらの要素がどのように連携するかを理解することは、特定の Skype for Business Server の展開をセキュリティで保護することに関する意思決定を行うために不可欠です。
ms.openlocfilehash: 432d4cda013e5bdec2613e3c9052f10b7d619302
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815615"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="fc56a-104">Skype for Business Server のセキュリティフレームワーク</span><span class="sxs-lookup"><span data-stu-id="fc56a-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="fc56a-105">このセクションでは、Skype for Business Server のセキュリティフレームワークを形成する基本的な要素の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc56a-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="fc56a-106">これらの要素がどのように連携するかを理解することは、特定の Skype for Business Server の展開をセキュリティで保護することに関する意思決定を行うために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="fc56a-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="fc56a-107">具体的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fc56a-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="fc56a-108">Active Directory ドメインサービス (AD DS) は、ユーザーアカウントとネットワークリソース用の1つの信頼されたバックエンドリポジトリを提供します。</span><span class="sxs-lookup"><span data-stu-id="fc56a-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="fc56a-109">役割ベースのアクセス制御 (RBAC) を使用すると、高水準のセキュリティを維持しながら管理操作を委任できます。</span><span class="sxs-lookup"><span data-stu-id="fc56a-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="fc56a-110">公開キー基盤 (PKI) は、信頼された証明機関 (CA) から発行された証明書を使用してサーバーを認証し、データの整合性を確保します。</span><span class="sxs-lookup"><span data-stu-id="fc56a-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="fc56a-p103">トランスポート層セキュリティ (TLS)、HTTPS over SSL (HTTPS)、相互 TLS (MTLS) を使用すると、エンドポイント認証と IM の暗号化ができます。ポイント間の音声、ビデオ、アプリケーション共有のストリームは、セキュア リアルタイム転送プロトコル (SRTP) で暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="fc56a-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="fc56a-113">ユーザーの認証には、業界標準のプロトコルができる限り使用されます。</span><span class="sxs-lookup"><span data-stu-id="fc56a-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="fc56a-114">Windows PowerShell には既定で有効になっているセキュリティ機能が用意されているため、ユーザーは簡単にスクリプトを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="fc56a-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="fc56a-115">これらの基本的なセキュリティ要素は連携して、Skype for Business Server のセキュリティ保護された基盤を確保するのに役立つ、信頼されたユーザー、サーバー、接続、操作を定義します。</span><span class="sxs-lookup"><span data-stu-id="fc56a-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="fc56a-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fc56a-116">In this section</span></span>

<span data-ttu-id="fc56a-117">このセクションのトピックでは、Skype for Business Server インフラストラクチャのセキュリティを強化するために、これらの各基本的な要素がどのように動作するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fc56a-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="fc56a-118">Skype for Business Server の Active Directory ドメインサービス</span><span class="sxs-lookup"><span data-stu-id="fc56a-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="fc56a-119">Skype for Business Server の役割ベースのアクセス制御 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="fc56a-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="fc56a-120">Skype for Business Server の公開キー基盤</span><span class="sxs-lookup"><span data-stu-id="fc56a-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="fc56a-121">Skype for Business Server の TLS と MTLS</span><span class="sxs-lookup"><span data-stu-id="fc56a-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="fc56a-122">Skype for Business Server の暗号化</span><span class="sxs-lookup"><span data-stu-id="fc56a-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="fc56a-123">Skype for Business Server のユーザーとクライアントの認証</span><span class="sxs-lookup"><span data-stu-id="fc56a-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="fc56a-124">Windows PowerShell と Skype for Business Server 管理ツール</span><span class="sxs-lookup"><span data-stu-id="fc56a-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

