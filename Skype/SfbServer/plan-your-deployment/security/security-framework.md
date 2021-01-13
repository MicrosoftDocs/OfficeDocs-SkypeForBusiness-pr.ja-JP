---
title: Skype for Business Server のセキュリティ フレームワーク
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: このセクションでは、Skype for Business Server のセキュリティ フレームワークを形成する基本的な要素の概要について説明します。 これらの要素がどのように機能し合うのかは、特定の Skype for Business Server 展開のセキュリティ保護に関する情報に基づいた決定を行う上で不可欠です。
ms.openlocfilehash: 94d2ffac30e029ab6631557a69d6da3ec108657f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832097"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="8683a-104">Skype for Business Server のセキュリティ フレームワーク</span><span class="sxs-lookup"><span data-stu-id="8683a-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="8683a-105">このセクションでは、Skype for Business Server のセキュリティ フレームワークを形成する基本的な要素の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="8683a-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="8683a-106">これらの要素がどのように組み合うのか理解は、特定の Skype for Business Server 展開をセキュリティで保護するための情報に基づいた決定を行う上で不可欠です。</span><span class="sxs-lookup"><span data-stu-id="8683a-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="8683a-107">具体的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8683a-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="8683a-108">Active Directory ドメイン サービス (AD DS) は、ユーザー アカウントとネットワーク リソースの信頼できる単一のバックエンド リポジトリを提供します。</span><span class="sxs-lookup"><span data-stu-id="8683a-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="8683a-109">Role-Based (RBAC) を使用すると、高レベルのセキュリティを維持しながら管理タスクを委任できます。</span><span class="sxs-lookup"><span data-stu-id="8683a-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="8683a-110">公開キー基盤 (PKI) は、信頼された証明機関 (CA) によって発行された証明書を使用して、サーバーを認証し、データの整合性を確保します。</span><span class="sxs-lookup"><span data-stu-id="8683a-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="8683a-p103">トランスポート層セキュリティ (TLS)、HTTP over SSL (HTTPS)、および相互 TLS (MTLS) により、エンドポイント認証と IM の暗号化が可能になります。ポイント間の音声、ビデオ、およびアプリケーション共有のストリームは、セキュア リアルタイム転送プロトコル (SRTP) で暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="8683a-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="8683a-113">ユーザーの認証には、業界標準のプロトコルが可能な限り使用されます。</span><span class="sxs-lookup"><span data-stu-id="8683a-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="8683a-114">Windows PowerShell には、既定で有効となっているセキュリティ機能があり、ユーザーが簡単には (または知らないうちに) スクリプトを実行できないようになっています。</span><span class="sxs-lookup"><span data-stu-id="8683a-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="8683a-115">これらの基本的なセキュリティ要素は、信頼できるユーザー、サーバー、接続、および操作を定義して、Skype for Business Server のセキュリティで保護された基盤を確保するために機能します。</span><span class="sxs-lookup"><span data-stu-id="8683a-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8683a-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8683a-116">In this section</span></span>

<span data-ttu-id="8683a-117">このセクションのトピックでは、Skype for Business Server インフラストラクチャのセキュリティを強化するために、これらの各基本要素がどのように機能するのかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8683a-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="8683a-118">Skype for Business Server の Active Directory ドメイン サービス</span><span class="sxs-lookup"><span data-stu-id="8683a-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="8683a-119">Skype for Business Server の役割ベースのアクセス制御 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="8683a-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="8683a-120">Skype for Business Server の公開キー基盤</span><span class="sxs-lookup"><span data-stu-id="8683a-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="8683a-121">Skype for Business Server の TLS と MTLS</span><span class="sxs-lookup"><span data-stu-id="8683a-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="8683a-122">Skype for Business Server の暗号化</span><span class="sxs-lookup"><span data-stu-id="8683a-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="8683a-123">Skype for Business Server のユーザー認証とクライアント認証</span><span class="sxs-lookup"><span data-stu-id="8683a-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="8683a-124">Windows PowerShell Skype for Business Server 管理ツール</span><span class="sxs-lookup"><span data-stu-id="8683a-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

