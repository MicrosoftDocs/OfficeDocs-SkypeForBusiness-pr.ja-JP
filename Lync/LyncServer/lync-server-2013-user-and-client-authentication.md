---
title: 'Lync Server 2013: ユーザーとクライアントの認証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 052c65bad805dff0d993cbf8533593c1f12915a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="2d2c8-102">Lync Server 2013 のユーザーとクライアントの認証</span><span class="sxs-lookup"><span data-stu-id="2d2c8-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d2c8-103">_**最終更新日:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="2d2c8-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="2d2c8-104">信頼されたユーザーとは、Microsoft Lync Server 2013 の信頼できるサーバーによって資格情報が認証されたユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="2d2c8-105">通常、このサーバーは Standard Edition server、Enterprise Edition のフロントエンドサーバー、またはディレクターです。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="2d2c8-106">Lync Server 2013 は、ユーザー資格情報の単一の信頼できるバックエンドリポジトリとして Active Directory ドメインサービスに依存します。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="2d2c8-107">認証では、ユーザーの資格情報が信頼されたサーバーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="2d2c8-108">Lync Server 2013 では、ユーザーの状態と場所に応じて、次の認証プロトコルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="2d2c8-109">Active Directory 資格情報を持つ内部ユーザー用の**MIT Kerberos バージョン5セキュリティプロトコル**。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-109">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="2d2c8-110">Kerberos には Active Directory ドメインサービスへのクライアント接続が必要です。このため、会社のファイアウォール以外のクライアントを認証するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-110">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="2d2c8-111">企業ファイアウォール外のエンドポイントから接続している Active Directory 資格情報を持つユーザーの**NTLM プロトコル**。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-111">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="2d2c8-112">アクセスエッジサービスは、ログイン要求をディレクター (存在する場合) または認証用のフロントエンドサーバーに渡します。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-112">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="2d2c8-113">アクセスエッジサービス自体では、認証は実行されません。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-113">The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2d2c8-114">NTLM プロトコルは Kerberos ほど攻撃に対して強くないので、NTLM の使用を最小限にしている組織もあります。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="2d2c8-115">その結果、Lync Server 2013 へのアクセスは、VPN または DirectAccess 接続経由で接続されている内部またはクライアントに制限されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="2d2c8-p106">**ダイジェスト プロトコル**: いわゆる匿名ユーザーに対して使用されます。匿名ユーザーは、有効な Active Directory の資格情報は持たないが、社内会議に招待され、有効な会議キーを持つ外部ユーザーです。ダイジェスト認証は、他のクライアント操作には使用されません。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-p106">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="2d2c8-119">Lync Server 2013 認証は、次の2つのフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="2d2c8-120">クライアントとサーバーの間に、セキュリティ アソシエーションが確立されます。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="2d2c8-p107">クライアントとサーバーは、既存のセキュリティ アソシエーションを使用して、送信するメッセージに署名し、受信するメッセージを検証します。サーバーで認証が有効になっている場合、クライアントからの認証されていないメッセージは受信されません。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-p107">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="2d2c8-p108">ユーザーの信用情報は、ユーザー ID 自体ではなく、ユーザーから送信される各メッセージに添付されます。サーバーは、各メッセージについて、送信元ユーザーの資格情報が有効であるかどうか確認します。ユーザーの資格情報が有効な場合、そのメッセージを受け取る最初のサーバーだけでなく、信頼済みサーバー クラウドに属する他のすべてのサーバーで、そのメッセージが受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-p108">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="2d2c8-126">フェデレーション パートナーが発行した有効な資格情報を持つユーザーは信頼されますが、これらのユーザーに対しては、内部ユーザーに与えられる権限のうち一部の使用を、必要に応じて制限できます。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="2d2c8-127">ICE プロトコルおよび TURN プロトコルでも、IETF TURN RFC に記載されているとおり、ダイジェスト認証が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="2d2c8-128">クライアント証明書は、ユーザーが Lync Server 2013 による認証を行うための代替手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="2d2c8-129">ユーザー名とパスワードを提供する代わりに、ユーザーは証明書と、暗号化認証の解決に必要な証明書に対応する秘密キーを持ちます。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="2d2c8-130">(この証明書には、ユーザーを識別するサブジェクト名またはサブジェクトの別名が必要です。また、Lync Server 2013 を実行しているサーバーによって信頼されているルート CA によって発行され、失効していない場合は、証明書の有効期間内に存在する必要があります)。認証するには、個人識別番号 (PIN) を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="2d2c8-131">証明書は、Microsoft Lync 2013 Phone Edition を実行している電話やその他のデバイスで、ユーザー名やパスワードの入力が困難な場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="2d2c8-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

