---
title: Skype for Business Server 2015 のユーザーとクライアントの認証
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 信頼されたユーザーは、ビジネス サーバー 2015 の Skype 内の信頼されたサーバーが資格情報を認証されています。 このサーバーは、通常、Standard Edition サーバー、エンタープライズ版フロント エンド サーバーまたはディレクターです。 Skype ビジネス サーバーは、ユーザーの資格情報、信頼できる単一のバックエンド ・ リポジトリとして、Active Directory ドメイン サービスに依存します。
ms.openlocfilehash: d8fa9265a4c27432dd4c2dba6e15c07e39f348b8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="user-and-client-authentication-for-skype-for-business-server-2015"></a><span data-ttu-id="5d46c-105">Skype for Business Server 2015 のユーザーとクライアントの認証</span><span class="sxs-lookup"><span data-stu-id="5d46c-105">User and client authentication for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5d46c-106">信頼されたユーザーは、ビジネス サーバー 2015 の Skype 内の信頼されたサーバーが資格情報を認証されています。</span><span class="sxs-lookup"><span data-stu-id="5d46c-106">A trusted user is one whose credentials have been authenticated by a trusted server in Skype for Business Server 2015.</span></span> <span data-ttu-id="5d46c-107">このサーバーは、通常、Standard Edition サーバー、エンタープライズ版フロント エンド サーバーまたはディレクターです。</span><span class="sxs-lookup"><span data-stu-id="5d46c-107">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="5d46c-108">Skype ビジネス サーバーは、ユーザーの資格情報、信頼できる単一のバックエンド ・ リポジトリとして、Active Directory ドメイン サービスに依存します。</span><span class="sxs-lookup"><span data-stu-id="5d46c-108">Skype for Business Server relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>
  
<span data-ttu-id="5d46c-109">認証では、ユーザーの資格情報が信頼されたサーバーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="5d46c-109">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="5d46c-110">Skype ビジネス サーバーの状態と、ユーザーの場所に応じて、次の認証プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d46c-110">Skype for Business Server uses the following authentication protocols, depending on the status and location of the user.</span></span>
  
- <span data-ttu-id="5d46c-111">Active Directory の資格情報を持つ内部ユーザーのための**MIT Kerberos バージョン 5 のセキュリティ プロトコル**です。</span><span class="sxs-lookup"><span data-stu-id="5d46c-111">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="5d46c-112">Kerberos では、Active Directory ドメイン サービスは、企業のファイアウォール外のクライアントの認証には使用できません理由へのクライアント接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="5d46c-112">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>
    
- <span data-ttu-id="5d46c-113">企業のファイアウォール外のエンドポイントから接続している Active Directory の資格情報を持つユーザーの**NTLM プロトコル**をします。</span><span class="sxs-lookup"><span data-stu-id="5d46c-113">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="5d46c-114">アクセス エッジ サービスでは、ディレクター、存在する場合、または認証のためのフロント エンド サーバーにログオン要求を渡します。</span><span class="sxs-lookup"><span data-stu-id="5d46c-114">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="5d46c-115">アクセス エッジ サービス自体には、認証は実行されません。</span><span class="sxs-lookup"><span data-stu-id="5d46c-115">The Access Edge service itself performs no authentication.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5d46c-116">NTLM プロトコルは Kerberos ほど攻撃に対して強くないので、NTLM の使用を最小限にしている組織もあります。</span><span class="sxs-lookup"><span data-stu-id="5d46c-116">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="5d46c-117">その結果、内部にビジネス サーバー 2015 の Skype へのアクセスを制限することがありますか、クライアントが VPN または DirectAccess 接続を介して接続されています。</span><span class="sxs-lookup"><span data-stu-id="5d46c-117">As a result, access to Skype for Business Server 2015 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span> 
  
- <span data-ttu-id="5d46c-p107">**ダイジェスト プロトコル**: いわゆる匿名ユーザーに対して使用されます。匿名ユーザーは、有効な Active Directory の資格情報は持たないが、社内会議に招待され、有効な会議キーを持つ外部ユーザーです。ダイジェスト認証は、他のクライアント操作には使用されません。</span><span class="sxs-lookup"><span data-stu-id="5d46c-p107">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>
    
<span data-ttu-id="5d46c-121">ビジネス サーバー 2015 の認証のための Skype は、2 つのフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="5d46c-121">Skype for Business Server 2015 authentication consists of two phases:</span></span>
  
1. <span data-ttu-id="5d46c-122">クライアントとサーバーの間に、セキュリティ アソシエーションが確立されます。</span><span class="sxs-lookup"><span data-stu-id="5d46c-122">A security association is established between the client and the server.</span></span>
    
2. <span data-ttu-id="5d46c-p108">クライアントとサーバーは、既存のセキュリティ アソシエーションを使用して、送信するメッセージに署名し、受信するメッセージを検証します。サーバーで認証が有効になっている場合、クライアントからの認証されていないメッセージは受信されません。</span><span class="sxs-lookup"><span data-stu-id="5d46c-p108">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>
    
<span data-ttu-id="5d46c-p109">ユーザーの信用情報は、ユーザー ID 自体ではなく、ユーザーから送信される各メッセージに添付されます。サーバーは、各メッセージについて、送信元ユーザーの資格情報が有効であるかどうか確認します。ユーザーの資格情報が有効な場合、そのメッセージを受け取る最初のサーバーだけでなく、信頼済みサーバー クラウドに属する他のすべてのサーバーで、そのメッセージが受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5d46c-p109">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>
  
<span data-ttu-id="5d46c-128">フェデレーション パートナーが発行した有効な資格情報を持つユーザーは信頼されますが、これらのユーザーに対しては、内部ユーザーに与えられる権限のうち一部の使用を、必要に応じて制限できます。</span><span class="sxs-lookup"><span data-stu-id="5d46c-128">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>
  
<span data-ttu-id="5d46c-129">ICE プロトコルおよび TURN プロトコルでも、IETF TURN RFC に記載されているとおり、ダイジェスト認証が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d46c-129">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>
  
<span data-ttu-id="5d46c-130">クライアント証明書は、ビジネス サーバー 2015 の Skype によって認証されるユーザーに対して別の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="5d46c-130">Client certificates provide an alternate way for users to be authenticated by Skype for Business Server 2015.</span></span> <span data-ttu-id="5d46c-131">ユーザーでは、ユーザー名とパスワードを提供することではなく証明書と暗号化の課題を解決するために必要な証明書に対応する秘密キーがあります。</span><span class="sxs-lookup"><span data-stu-id="5d46c-131">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="5d46c-132">(この証明書は、サブジェクト名またはサブジェクトの別名ユーザーを識別し、ビジネス サーバー 2015 の Skype を実行しているサーバーによって信頼されているルート CA が発行する必要があります、証明書の有効期間内であるし、失効していないことをいる必要があります)認証を受けるには、ユーザーは暗証番号 (PIN) を入力するだけが必要です。</span><span class="sxs-lookup"><span data-stu-id="5d46c-132">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Skype for Business Server 2015, be within the certificate's validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="5d46c-133">証明書は、ユーザー名とパスワードを入力するが難しい、電話、携帯電話、およびその他のデバイスの場合に特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5d46c-133">Certificates are particularly useful for telephones, mobile phones, and other devices where it is difficult to enter a user name and password.</span></span>
  

