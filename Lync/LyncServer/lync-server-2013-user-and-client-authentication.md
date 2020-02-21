---
title: 'Lync Server 2013: ユーザーとクライアントの認証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dbddb0dab36a8ad805691196a00a3dc8bf6f9d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="3cd57-102">Lync Server 2013 のユーザーとクライアントの認証</span><span class="sxs-lookup"><span data-stu-id="3cd57-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cd57-103">_**トピックの最終更新日:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="3cd57-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="3cd57-104">信頼されたユーザーとは、Microsoft Lync Server 2013 の信頼されたサーバーによって認証された資格情報を持つユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="3cd57-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="3cd57-105">このサーバーは、通常、Standard Edition サーバー、Enterprise Edition フロント エンド サーバー、またはディレクターです。</span><span class="sxs-lookup"><span data-stu-id="3cd57-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="3cd57-106">Lync Server 2013 は、Active Directory ドメインサービスを、ユーザー資格情報の単一の信頼されたバックエンドリポジトリとして利用します。</span><span class="sxs-lookup"><span data-stu-id="3cd57-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="3cd57-107">認証では、ユーザーの資格情報が信頼されたサーバーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="3cd57-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="3cd57-108">Lync Server 2013 は、ユーザーの状態と場所に応じて、次の認証プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cd57-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="3cd57-p103">**MIT Kerberos Version 5 セキュリティ プロトコル**: Active Directory の資格情報を持つ内部ユーザーに対して使用されます。Kerberos では、クライアントが Active Directory ドメイン サービスに接続できる状態であることが必要です。このため、Kerberos は企業のファイアウォールの外側にいるクライアントの認証には使用できません。</span><span class="sxs-lookup"><span data-stu-id="3cd57-p103">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials. Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="3cd57-p104">**NTLM プロトコル**: Active Directory の資格情報を持ち、企業のファイアウォールの外側にあるエンドポイントから接続しているユーザーに対して使用されます。アクセス エッジ サービスによってログオン要求がディレクター (ある場合) またはフロントエンド サーバーに渡され、そこで認証が行われます。アクセス エッジ サービス自体では認証は行われません。</span><span class="sxs-lookup"><span data-stu-id="3cd57-p104">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall. The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication. The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3cd57-114">NTLM プロトコルは Kerberos ほど攻撃に対して強くないので、NTLM の使用を最小限にしている組織もあります。</span><span class="sxs-lookup"><span data-stu-id="3cd57-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="3cd57-115">そのため、Lync Server 2013 へのアクセスは、VPN または DirectAccess 接続を介して接続された内部またはクライアントに制限される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3cd57-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="3cd57-p106">**ダイジェスト プロトコル**: いわゆる匿名ユーザーに対して使用されます。匿名ユーザーは、有効な Active Directory の資格情報は持たないが、社内会議に招待され、有効な会議キーを持つ外部ユーザーです。ダイジェスト認証は、他のクライアント操作には使用されません。</span><span class="sxs-lookup"><span data-stu-id="3cd57-p106">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="3cd57-119">Lync Server 2013 認証は、次の2つのフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3cd57-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="3cd57-120">クライアントとサーバーの間に、セキュリティ アソシエーションが確立されます。</span><span class="sxs-lookup"><span data-stu-id="3cd57-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="3cd57-p107">クライアントとサーバーは、既存のセキュリティ アソシエーションを使用して、送信するメッセージに署名し、受信するメッセージを検証します。サーバーで認証が有効になっている場合、クライアントからの認証されていないメッセージは受信されません。</span><span class="sxs-lookup"><span data-stu-id="3cd57-p107">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="3cd57-p108">ユーザーの信用情報は、ユーザー ID 自体ではなく、ユーザーから送信される各メッセージに添付されます。サーバーは、各メッセージについて、送信元ユーザーの資格情報が有効であるかどうか確認します。ユーザーの資格情報が有効な場合、そのメッセージを受け取る最初のサーバーだけでなく、信頼済みサーバー クラウドに属する他のすべてのサーバーで、そのメッセージが受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3cd57-p108">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="3cd57-126">フェデレーション パートナーが発行した有効な資格情報を持つユーザーは信頼されますが、これらのユーザーに対しては、内部ユーザーに与えられる権限のうち一部の使用を、必要に応じて制限できます。</span><span class="sxs-lookup"><span data-stu-id="3cd57-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="3cd57-127">ICE プロトコルおよび TURN プロトコルでも、IETF TURN RFC に記載されているとおり、ダイジェスト認証が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3cd57-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="3cd57-128">クライアント証明書は、Lync Server 2013 によってユーザーを認証するための代替方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="3cd57-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="3cd57-129">ユーザー名とパスワードを指定する代わりに、ユーザーは、証明書と、暗号化のチャレンジを解決するために必要な証明書に対応する秘密キーを持っています。</span><span class="sxs-lookup"><span data-stu-id="3cd57-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="3cd57-130">(この証明書には、ユーザーを識別し、Lync Server 2013 を実行しているサーバーによって信頼されていて、失効されていないルート CA によって発行される必要があります)。認証のためには、ユーザーは暗証番号 (PIN) だけを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cd57-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="3cd57-131">証明書は、ユーザー名やパスワードの入力が困難な Microsoft Lync 2013 Phone Edition を実行している電話機やその他のデバイスに特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3cd57-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

