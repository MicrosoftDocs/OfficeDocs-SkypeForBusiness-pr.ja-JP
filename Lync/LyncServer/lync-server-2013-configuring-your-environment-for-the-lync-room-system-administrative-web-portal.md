---
title: 'Lync Server 2013: Lync Room System 管理 Web ポータルの環境の構成'
description: 'Lync Server 2013: Lync Room System 管理 Web ポータルの環境の構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c942e1db799a7336a3eafb5571e82584694ddbf3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542203"
---
# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="99ba2-103">Lync Room System 管理 Web ポータル用に Lync Server 2013 環境を構成する</span><span class="sxs-lookup"><span data-stu-id="99ba2-103">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99ba2-104">_**トピックの最終更新日:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="99ba2-104">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="99ba2-105">Lync Room System (LRS) 管理 Web ポータルを使用するには、次の前提条件をインストールまたは構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99ba2-105">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="99ba2-106">サーバーが Kerberos 認証と NTLM 認証の両方を使用して構成されており、ドメインに参加していないコンピューター上で LRS が実行されている場合、Kerberos 認証は失敗し、ユーザーには管理ポータルで LRS の状態が表示されません。</span><span class="sxs-lookup"><span data-stu-id="99ba2-106">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="99ba2-107">この問題を解決するには、サーバーを NTLM 認証または NTLM と DSK 認証 (Kerberos を使用しない) の両方で構成するか、または LRS コンピューターをドメインに参加させます。</span><span class="sxs-lookup"><span data-stu-id="99ba2-107">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="99ba2-108">Lync server 2013 の累積的な更新プログラム (Lync Server トポロジでは2013年7月) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="99ba2-108">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="99ba2-109">更新プログラムを取得するか、またはその内容に含まれているものを確認するには、「 [Lync Server 2013 の更新プログラム](https://go.microsoft.com/fwlink/p/?linkid=323959)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99ba2-109">To get the update or see what’s included with it, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="99ba2-110">SIP 対応の Active Directory ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="99ba2-110">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="99ba2-111">LRS 管理 Web ポータルは、これらの資格情報を使用して Lync Server からの情報を照会します。</span><span class="sxs-lookup"><span data-stu-id="99ba2-111">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="99ba2-112">推奨されるユーザー名は LRSApp です。</span><span class="sxs-lookup"><span data-stu-id="99ba2-112">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="99ba2-113">LRSSupportAdminGroup という名前の Active Directory セキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="99ba2-113">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="99ba2-114">グループスコープを持つグループを [グローバル] および [グループの種類] としてセキュリティとして作成します。</span><span class="sxs-lookup"><span data-stu-id="99ba2-114">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="99ba2-115">このグループに追加される SIP 対応ユーザーは、ルームのリストを確認し、ログの収集などの特定のコマンドを実行することを承認されます。</span><span class="sxs-lookup"><span data-stu-id="99ba2-115">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="99ba2-116">LRSFullAccessAdminGroup という名前の Active Directory セキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="99ba2-116">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="99ba2-117">[グローバル] および [グループの種類] としてグループスコープを持つグループをセキュリティとして作成します。このグループに追加される SIP 対応ユーザーは、すべての管理ポータル機能を使用することを承認されています。</span><span class="sxs-lookup"><span data-stu-id="99ba2-117">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="99ba2-118">![セキュリティグループの役割を持つ管理グループの一覧](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "セキュリティグループの役割を持つ管理グループの一覧")</span><span class="sxs-lookup"><span data-stu-id="99ba2-118">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="99ba2-119">LRSFullAccessAdminGroup を LRSSupportAdminGroup のメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="99ba2-119">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="99ba2-120">![LRSSupportAdminGroup Properties メンバーページ](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties メンバーページ")</span><span class="sxs-lookup"><span data-stu-id="99ba2-120">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="99ba2-121">LRSSupport という名前の SIP 対応 Active Directory ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="99ba2-121">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="99ba2-122">このユーザーを LRSSupportAdminGroup に追加します。</span><span class="sxs-lookup"><span data-stu-id="99ba2-122">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="99ba2-123">![LRSSupportAdminGroup Properties メンバーページ](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties メンバーページ")</span><span class="sxs-lookup"><span data-stu-id="99ba2-123">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="99ba2-124">ASP.NET MVC 4 for Visual Studio 2010 SP1 および Visual Web Developer 2010 SP1 は、Microsoft ダウンロードセンター () から入手でき [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967) ます。</span><span class="sxs-lookup"><span data-stu-id="99ba2-124">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

