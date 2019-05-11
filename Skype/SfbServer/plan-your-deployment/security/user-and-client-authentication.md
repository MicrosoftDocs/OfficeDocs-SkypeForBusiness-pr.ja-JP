---
title: ビジネス サーバーの Skype のユーザーとクライアントの認証
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 信頼されたユーザーは、Skype で信頼されたサーバーによってビジネスのサーバーの認証された資格情報を 1 つ。 このサーバーは、通常、Standard Edition サーバー、エンタープライズ版フロント エンド サーバーまたはディレクターです。 Skype ビジネス サーバーは、ユーザーの資格情報、信頼できる単一のバックエンド ・ リポジトリとして、Active Directory ドメイン サービスに依存します。
ms.openlocfilehash: 6d6a796f521ce79fe3c78c7becb48a495eafd473
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885462"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a><span data-ttu-id="f32fa-105">ビジネス サーバーの Skype のユーザーとクライアントの認証</span><span class="sxs-lookup"><span data-stu-id="f32fa-105">User and client authentication for Skype for Business Server</span></span>
 
<span data-ttu-id="f32fa-106">信頼されたユーザーは、Skype で信頼されたサーバーによってビジネスのサーバーの認証された資格情報を 1 つ。</span><span class="sxs-lookup"><span data-stu-id="f32fa-106">A trusted user is one whose credentials have been authenticated by a trusted server in Skype for Business Server.</span></span> <span data-ttu-id="f32fa-107">このサーバーは、通常、Standard Edition サーバー、エンタープライズ版フロント エンド サーバーまたはディレクターです。</span><span class="sxs-lookup"><span data-stu-id="f32fa-107">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="f32fa-108">Skype ビジネス サーバーは、ユーザーの資格情報、信頼できる単一のバックエンド ・ リポジトリとして、Active Directory ドメイン サービスに依存します。</span><span class="sxs-lookup"><span data-stu-id="f32fa-108">Skype for Business Server relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>
  
<span data-ttu-id="f32fa-109">認証では、ユーザーの資格情報が信頼されたサーバーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="f32fa-109">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="f32fa-110">Skype ビジネス サーバーの状態と、ユーザーの場所に応じて、次の認証プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f32fa-110">Skype for Business Server uses the following authentication protocols, depending on the status and location of the user.</span></span>
  
- <span data-ttu-id="f32fa-111">Active Directory の資格情報を持つ内部ユーザーのための**MIT Kerberos バージョン 5 のセキュリティ プロトコル**です。</span><span class="sxs-lookup"><span data-stu-id="f32fa-111">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="f32fa-112">Kerberos では、Active Directory ドメイン サービスは、企業のファイアウォール外のクライアントの認証には使用できません理由へのクライアント接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="f32fa-112">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>
    
- <span data-ttu-id="f32fa-113">企業のファイアウォール外のエンドポイントから接続している Active Directory の資格情報を持つユーザーの**NTLM プロトコル**をします。</span><span class="sxs-lookup"><span data-stu-id="f32fa-113">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="f32fa-114">アクセス エッジ サービスでは、ディレクター、存在する場合、または認証のためのフロント エンド サーバーにログオン要求を渡します。</span><span class="sxs-lookup"><span data-stu-id="f32fa-114">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="f32fa-115">アクセス エッジ サービス自体には、認証は実行されません。</span><span class="sxs-lookup"><span data-stu-id="f32fa-115">The Access Edge service itself performs no authentication.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f32fa-116">NTLM プロトコルは Kerberos ほど攻撃に対して強くないので、NTLM の使用を最小限にしている組織もあります。</span><span class="sxs-lookup"><span data-stu-id="f32fa-116">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="f32fa-117">その結果、内部にビジネス サーバーの Skype へのアクセスを制限することがありますか、クライアントが VPN または DirectAccess 接続を介して接続されています。</span><span class="sxs-lookup"><span data-stu-id="f32fa-117">As a result, access to Skype for Business Server might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span> 
  
- <span data-ttu-id="f32fa-p107">**ダイジェスト プロトコル**: いわゆる匿名ユーザーに対して使用されます。匿名ユーザーは、有効な Active Directory の資格情報は持たないが、社内会議に招待され、有効な会議キーを持つ外部ユーザーです。ダイジェスト認証は、他のクライアント操作には使用されません。</span><span class="sxs-lookup"><span data-stu-id="f32fa-p107">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>
    
<span data-ttu-id="f32fa-121">Skype ビジネス サーバーの認証には、2 つのフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f32fa-121">Skype for Business Server authentication consists of two phases:</span></span>
  
1. <span data-ttu-id="f32fa-122">クライアントとサーバーの間に、セキュリティ アソシエーションが確立されます。</span><span class="sxs-lookup"><span data-stu-id="f32fa-122">A security association is established between the client and the server.</span></span>
    
2. <span data-ttu-id="f32fa-p108">クライアントとサーバーは、既存のセキュリティ アソシエーションを使用して、送信するメッセージに署名し、受信するメッセージを検証します。サーバーで認証が有効になっている場合、クライアントからの認証されていないメッセージは受信されません。</span><span class="sxs-lookup"><span data-stu-id="f32fa-p108">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>
    
<span data-ttu-id="f32fa-p109">ユーザーの信用情報は、ユーザー ID 自体ではなく、ユーザーから送信される各メッセージに添付されます。サーバーは、各メッセージについて、送信元ユーザーの資格情報が有効であるかどうか確認します。ユーザーの資格情報が有効な場合、そのメッセージを受け取る最初のサーバーだけでなく、信頼済みサーバー クラウドに属する他のすべてのサーバーで、そのメッセージが受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f32fa-p109">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>
  
<span data-ttu-id="f32fa-128">フェデレーション パートナーが発行した有効な資格情報を持つユーザーは信頼されますが、これらのユーザーに対しては、内部ユーザーに与えられる権限のうち一部の使用を、必要に応じて制限できます。</span><span class="sxs-lookup"><span data-stu-id="f32fa-128">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>
  
<span data-ttu-id="f32fa-129">ICE プロトコルおよび TURN プロトコルでも、IETF TURN RFC に記載されているとおり、ダイジェスト認証が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f32fa-129">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>
  
<span data-ttu-id="f32fa-130">クライアント証明書は、Skype でビジネスのサーバーの認証を受けるユーザーの代替の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="f32fa-130">Client certificates provide an alternate way for users to be authenticated by Skype for Business Server.</span></span> <span data-ttu-id="f32fa-131">ユーザー名とパスワードを提供する代わりに、ユーザーは証明書と、暗号化認証の解決に必要な証明書に対応する秘密キーを持ちます。</span><span class="sxs-lookup"><span data-stu-id="f32fa-131">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="f32fa-132">(この証明書は、サブジェクト名またはサブジェクトの別名ユーザーを識別し、ビジネス サーバーの Skype を実行しているサーバーによって信頼されているルート CA が発行する必要がありますと、証明書の有効期間内であるし、失効していないをいる必要があります)認証を受けるには、ユーザーは暗証番号 (PIN) を入力するだけが必要です。</span><span class="sxs-lookup"><span data-stu-id="f32fa-132">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Skype for Business Server, be within the certificate's validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="f32fa-133">証明書は、ユーザー名とパスワードを入力するが難しい、電話、携帯電話、およびその他のデバイスの場合に特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f32fa-133">Certificates are particularly useful for telephones, mobile phones, and other devices where it is difficult to enter a user name and password.</span></span>
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a><span data-ttu-id="f32fa-134">ASP .NET 4.5 のための暗号化の要件</span><span class="sxs-lookup"><span data-stu-id="f32fa-134">Cryptographic requirements due to ASP .NET 4.5</span></span> 

<span data-ttu-id="f32fa-135">ビジネス サーバー 2015 CU5 の Skype は、現在 ASP.NET 4.6 では、AES はサポートされていませんし、Skype の会議アプリケーション起動に失敗が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f32fa-135">As of Skype for Business Server 2015 CU5, AES is not supported for ASP.NET 4.6 and this may cause Skype Meetings App to fail to start.</span></span> <span data-ttu-id="f32fa-136">クライアントがコンピューターのキーの検証値として AES を使用している場合は、sha-1、または IIS で Skype 会議アプリケーションのサイト レベルでサポートされている別のアルゴリズムをコンピューターのキーの値をリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f32fa-136">If a client is using AES as the machine key validation value you will need to reset the machine key value to SHA-1 or another supported algorithm on the Skype Meetings App site level on IIS.</span></span> <span data-ttu-id="f32fa-137">必要に応じて、手順については[IIS 8.0 の ASP.NET 構成の管理](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f32fa-137">If necessary, see [IIS 8.0 ASP.NET Configuration Management](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) for instructions.</span></span>
  
<span data-ttu-id="f32fa-138">その他に次の値がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f32fa-138">Other supported values are:</span></span>
  
- <span data-ttu-id="f32fa-139">HMACSHA256</span><span class="sxs-lookup"><span data-stu-id="f32fa-139">HMACSHA256</span></span>
    
- <span data-ttu-id="f32fa-140">HMACSHA384</span><span class="sxs-lookup"><span data-stu-id="f32fa-140">HMACSHA384</span></span>
    
- <span data-ttu-id="f32fa-141">HMACSHA512</span><span class="sxs-lookup"><span data-stu-id="f32fa-141">HMACSHA512</span></span>
    
  <span data-ttu-id="f32fa-142">ASP.NET 4 ではサポートされていた AES、3DES、MD5 の値は使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f32fa-142">The values AES, 3DES, and MD5 are no longer allowed, as they once were in ASP.NET 4.</span></span> <span data-ttu-id="f32fa-143">[ASP.NET 4.5、2 pt. で暗号化の機能強化](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/)の詳細があります。</span><span class="sxs-lookup"><span data-stu-id="f32fa-143">[Cryptographic Improvements in ASP.NET 4.5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) has more details.</span></span>
  
