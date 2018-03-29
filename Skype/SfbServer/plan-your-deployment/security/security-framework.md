---
title: Skype for Business Server 2015 のセキュリティ フレームワーク
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: ここでは、Skype のビジネス サーバー 2015 のセキュリティ フレームワークを形成する基本要素の概要を示します。 これらの要素がどのように連携を理解することは、サーバー 2015 のビジネスを展開するための特定、Skype のセキュリティ保護に関する情報に基づいた意思決定を行う必要があります。
ms.openlocfilehash: c29941a3e903b6318db2de0453589b5017e6f51b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="security-framework-for-skype-for-business-server-2015"></a><span data-ttu-id="b1353-104">Skype for Business Server 2015 のセキュリティ フレームワーク</span><span class="sxs-lookup"><span data-stu-id="b1353-104">Security framework for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b1353-105">ここでは、Skype のビジネス サーバー 2015 のセキュリティ フレームワークを形成する基本要素の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="b1353-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server 2015.</span></span> <span data-ttu-id="b1353-106">これらの要素がどのように連携を理解することは、サーバー 2015 のビジネスを展開するための特定、Skype のセキュリティ保護に関する情報に基づいた意思決定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1353-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server 2015 deployment.</span></span>
  
<span data-ttu-id="b1353-107">具体的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b1353-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="b1353-108">Active Directory ドメイン サービス (AD DS) では、ユーザー アカウントとネットワーク リソースの 1 つの信頼されているバックエンド ・ リポジトリを提供します。</span><span class="sxs-lookup"><span data-stu-id="b1353-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="b1353-109">役割ベースのアクセス制御 (RBAC) を使用すると、高水準のセキュリティを維持しながら管理操作を委任できます。</span><span class="sxs-lookup"><span data-stu-id="b1353-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="b1353-110">公開キー基盤 (PKI) は、信頼された証明機関 (CA) から発行された証明書を使用してサーバーを認証し、データの整合性を確保します。</span><span class="sxs-lookup"><span data-stu-id="b1353-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="b1353-p103">トランスポート層セキュリティ (TLS)、HTTPS over SSL (HTTPS)、相互 TLS (MTLS) を使用すると、エンドポイント認証と IM の暗号化ができます。ポイント間の音声、ビデオ、アプリケーション共有のストリームは、セキュア リアルタイム転送プロトコル (SRTP) で暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="b1353-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="b1353-113">ユーザーの認証には、業界標準のプロトコルができる限り使用されます。</span><span class="sxs-lookup"><span data-stu-id="b1353-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="b1353-114">Windows PowerShell には、ユーザーことはできませんか知らないうちに、簡単にスクリプトを実行するために既定で有効になっているセキュリティ機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="b1353-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="b1353-115">確保する基盤をセキュリティで保護された Skype のビジネス サーバー 2015 の信頼されるユーザー、サーバー、接続、および操作を定義するのにはこれらの基本的なセキュリティ要素が連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="b1353-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server 2015.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b1353-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b1353-116">In this section</span></span>

<span data-ttu-id="b1353-117">このセクションのトピックでは、ビジネスのサーバー インフラストラクチャを Skype のセキュリティを強化するためにこれらの基本的な要素の動作方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1353-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="b1353-118">ビジネス サーバー 2015 の Skype の active Directory ドメイン サービス</span><span class="sxs-lookup"><span data-stu-id="b1353-118">Active Directory Domain Services for Skype for Business Server 2015</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="b1353-119">ビジネス サーバー 2015 の Skype の役割に基づくアクセス制御 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="b1353-119">Role-based access control (RBAC) for Skype for Business Server 2015</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="b1353-120">ビジネス サーバー 2015 の Skype 用の公開キー基盤</span><span class="sxs-lookup"><span data-stu-id="b1353-120">Public Key Infrastructure for Skype for Business Server 2015</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="b1353-121">TLS とビジネス サーバー 2015 の Skype の MTLS</span><span class="sxs-lookup"><span data-stu-id="b1353-121">TLS and MTLS for Skype for Business Server 2015</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="b1353-122">ビジネス サーバー 2015 の Skype の暗号化</span><span class="sxs-lookup"><span data-stu-id="b1353-122">Encryption for Skype for Business Server 2015</span></span>](encryption.md)
    
- [<span data-ttu-id="b1353-123">ビジネス サーバー 2015 の Skype のユーザーとクライアントの認証</span><span class="sxs-lookup"><span data-stu-id="b1353-123">User and client authentication for Skype for Business Server 2015</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="b1353-124">Windows PowerShell およびサーバー 2015 のビジネス管理ツールの Skype</span><span class="sxs-lookup"><span data-stu-id="b1353-124">Windows PowerShell and Skype for Business Server 2015 management tools</span></span>](management-tools.md)
    

