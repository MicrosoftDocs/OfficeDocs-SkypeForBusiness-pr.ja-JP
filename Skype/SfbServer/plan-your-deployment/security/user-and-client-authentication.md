---
title: Skype for Business Server のユーザーとクライアントの認証
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
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 信頼されたユーザーとは、資格情報が Skype for Business Server の信頼されたサーバーによって認証されたユーザーのことです。 通常、このサーバーは Standard Edition server、Enterprise Edition のフロントエンドサーバー、またはディレクターです。 Skype for Business Server は、ユーザー資格情報の単一の信頼できるバックエンドリポジトリとして Active Directory ドメインサービスに依存します。
ms.openlocfilehash: 2ffabce6546bf8b542503f8c80fe5cb2b952c568
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815585"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a><span data-ttu-id="a7c4f-105">Skype for Business Server のユーザーとクライアントの認証</span><span class="sxs-lookup"><span data-stu-id="a7c4f-105">User and client authentication for Skype for Business Server</span></span>
 
<span data-ttu-id="a7c4f-106">信頼されたユーザーとは、資格情報が Skype for Business Server の信頼されたサーバーによって認証されたユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-106">A trusted user is one whose credentials have been authenticated by a trusted server in Skype for Business Server.</span></span> <span data-ttu-id="a7c4f-107">通常、このサーバーは Standard Edition server、Enterprise Edition のフロントエンドサーバー、またはディレクターです。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-107">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="a7c4f-108">Skype for Business Server は、ユーザー資格情報の単一の信頼できるバックエンドリポジトリとして Active Directory ドメインサービスに依存します。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-108">Skype for Business Server relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>
  
<span data-ttu-id="a7c4f-109">認証では、ユーザーの資格情報が信頼されたサーバーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-109">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="a7c4f-110">Skype for Business Server では、ユーザーの状態と場所に応じて、次の認証プロトコルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-110">Skype for Business Server uses the following authentication protocols, depending on the status and location of the user.</span></span>
  
- <span data-ttu-id="a7c4f-111">Active Directory 資格情報を持つ内部ユーザー用の**MIT Kerberos バージョン5セキュリティプロトコル**。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-111">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="a7c4f-112">Kerberos には Active Directory ドメインサービスへのクライアント接続が必要です。このため、会社のファイアウォール以外のクライアントを認証するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-112">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>
    
- <span data-ttu-id="a7c4f-113">企業ファイアウォール外のエンドポイントから接続している Active Directory 資格情報を持つユーザーの**NTLM プロトコル**。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-113">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="a7c4f-114">アクセスエッジサービスは、ログイン要求をディレクター (存在する場合) または認証用のフロントエンドサーバーに渡します。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-114">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="a7c4f-115">アクセスエッジサービス自体では、認証は実行されません。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-115">The Access Edge service itself performs no authentication.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a7c4f-116">NTLM プロトコルは Kerberos ほど攻撃に対して強くないので、NTLM の使用を最小限にしている組織もあります。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-116">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="a7c4f-117">その結果、Skype for Business Server へのアクセスが、VPN または DirectAccess 接続経由で接続されている内部またはクライアントに制限されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-117">As a result, access to Skype for Business Server might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span> 
  
- <span data-ttu-id="a7c4f-p107">**ダイジェスト プロトコル**: いわゆる匿名ユーザーに対して使用されます。匿名ユーザーは、有効な Active Directory の資格情報は持たないが、社内会議に招待され、有効な会議キーを持つ外部ユーザーです。ダイジェスト認証は、他のクライアント操作には使用されません。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-p107">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>
    
<span data-ttu-id="a7c4f-121">Skype for Business Server 認証は、次の2つのフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-121">Skype for Business Server authentication consists of two phases:</span></span>
  
1. <span data-ttu-id="a7c4f-122">クライアントとサーバーの間に、セキュリティ アソシエーションが確立されます。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-122">A security association is established between the client and the server.</span></span>
    
2. <span data-ttu-id="a7c4f-p108">クライアントとサーバーは、既存のセキュリティ アソシエーションを使用して、送信するメッセージに署名し、受信するメッセージを検証します。サーバーで認証が有効になっている場合、クライアントからの認証されていないメッセージは受信されません。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-p108">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>
    
<span data-ttu-id="a7c4f-p109">ユーザーの信用情報は、ユーザー ID 自体ではなく、ユーザーから送信される各メッセージに添付されます。サーバーは、各メッセージについて、送信元ユーザーの資格情報が有効であるかどうか確認します。ユーザーの資格情報が有効な場合、そのメッセージを受け取る最初のサーバーだけでなく、信頼済みサーバー クラウドに属する他のすべてのサーバーで、そのメッセージが受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-p109">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>
  
<span data-ttu-id="a7c4f-128">フェデレーション パートナーが発行した有効な資格情報を持つユーザーは信頼されますが、これらのユーザーに対しては、内部ユーザーに与えられる権限のうち一部の使用を、必要に応じて制限できます。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-128">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>
  
<span data-ttu-id="a7c4f-129">ICE プロトコルおよび TURN プロトコルでも、IETF TURN RFC に記載されているとおり、ダイジェスト認証が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-129">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>
  
<span data-ttu-id="a7c4f-130">クライアント証明書は、ユーザーが Skype for Business Server による認証を行うための代替手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-130">Client certificates provide an alternate way for users to be authenticated by Skype for Business Server.</span></span> <span data-ttu-id="a7c4f-131">ユーザー名とパスワードを提供する代わりに、ユーザーは証明書と、暗号化認証の解決に必要な証明書に対応する秘密キーを持ちます。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-131">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="a7c4f-132">(この証明書には、ユーザーを識別するサブジェクト名またはサブジェクトの別名が必要です。また、Skype for Business Server を実行しているサーバーによって信頼され、証明書の有効期間内であり、失効していないルート CA によって発行されている必要があります)。認証するには、個人識別番号 (PIN) を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-132">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Skype for Business Server, be within the certificate's validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="a7c4f-133">証明書は、ユーザー名とパスワードを入力することが難しい電話、携帯電話、その他のデバイスで特に便利です。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-133">Certificates are particularly useful for telephones, mobile phones, and other devices where it is difficult to enter a user name and password.</span></span>
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a><span data-ttu-id="a7c4f-134">ASP .NET 4.5 に基づく暗号化要件</span><span class="sxs-lookup"><span data-stu-id="a7c4f-134">Cryptographic requirements due to ASP .NET 4.5</span></span> 

<span data-ttu-id="a7c4f-135">Skype for Business Server 2015 CU5 以降の場合、AES は ASP.NET 4.6 ではサポートされていないため、Skype 会議アプリの起動が失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-135">As of Skype for Business Server 2015 CU5, AES is not supported for ASP.NET 4.6 and this may cause Skype Meetings App to fail to start.</span></span> <span data-ttu-id="a7c4f-136">クライアントがマシンキーの検証値として AES を使用している場合は、コンピューターのキー値を SHA-1 にリセットするか、IIS の Skype 会議アプリのサイトレベルでサポートされている別のアルゴリズムに再設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-136">If a client is using AES as the machine key validation value you will need to reset the machine key value to SHA-1 or another supported algorithm on the Skype Meetings App site level on IIS.</span></span> <span data-ttu-id="a7c4f-137">必要に応じて、「 [IIS 8.0 ASP.NET 構成管理](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management)の手順」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-137">If necessary, see [IIS 8.0 ASP.NET Configuration Management](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) for instructions.</span></span>
  
<span data-ttu-id="a7c4f-138">その他に次の値がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-138">Other supported values are:</span></span>
  
- <span data-ttu-id="a7c4f-139">HMACSHA256</span><span class="sxs-lookup"><span data-stu-id="a7c4f-139">HMACSHA256</span></span>
    
- <span data-ttu-id="a7c4f-140">HMACSHA384</span><span class="sxs-lookup"><span data-stu-id="a7c4f-140">HMACSHA384</span></span>
    
- <span data-ttu-id="a7c4f-141">HMACSHA512</span><span class="sxs-lookup"><span data-stu-id="a7c4f-141">HMACSHA512</span></span>
    
  <span data-ttu-id="a7c4f-142">ASP.NET 4 ではサポートされていた AES、3DES、MD5 の値は使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-142">The values AES, 3DES, and MD5 are no longer allowed, as they once were in ASP.NET 4.</span></span> <span data-ttu-id="a7c4f-143">[ASP.NET 4.5 での暗号化の改善](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/)の詳細については、こちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a7c4f-143">[Cryptographic Improvements in ASP.NET 4.5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) has more details.</span></span>
  
