---
title: 'Lync Server 2013: Lync Room System 管理 Web ポータルの環境の構成'
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
ms.openlocfilehash: 5c42b5541fb28646e4c01d9d070b67f6fe103234
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="1a9d7-102">Lync Room System 管理 Web ポータル用に Lync Server 2013 環境を構成する</span><span class="sxs-lookup"><span data-stu-id="1a9d7-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a9d7-103">_**トピックの最終更新日:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="1a9d7-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="1a9d7-104">Lync Room System (LRS) 管理 Web ポータルを使用するには、次の前提条件をインストールまたは構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-104">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1a9d7-105">サーバーが Kerberos 認証と NTLM 認証の両方を使用して構成されており、ドメインに参加していないコンピューター上で LRS が実行されている場合、Kerberos 認証は失敗し、ユーザーには管理ポータルで LRS の状態が表示されません。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-105">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="1a9d7-106">この問題を解決するには、サーバーを NTLM 認証または NTLM と DSK 認証 (Kerberos を使用しない) の両方で構成するか、または LRS コンピューターをドメインに参加させます。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-106">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="1a9d7-107">Lync server 2013 の累積的な更新プログラム (Lync Server トポロジでは2013年7月) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-107">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="1a9d7-108">更新プログラムを取得するか、またはその内容に含まれているものを確認するには、「 [Lync Server 2013 の更新プログラム](http://go.microsoft.com/fwlink/p/?linkid=323959)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-108">To get the update or see what’s included with it, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="1a9d7-109">SIP 対応の Active Directory ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-109">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="1a9d7-110">LRS 管理 Web ポータルは、これらの資格情報を使用して Lync Server からの情報を照会します。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-110">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="1a9d7-111">推奨されるユーザー名は LRSApp です。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-111">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="1a9d7-112">LRSSupportAdminGroup という名前の Active Directory セキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-112">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="1a9d7-113">グループスコープを持つグループを [グローバル] および [グループの種類] としてセキュリティとして作成します。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-113">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="1a9d7-114">このグループに追加される SIP 対応ユーザーは、ルームのリストを確認し、ログの収集などの特定のコマンドを実行することを承認されます。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-114">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="1a9d7-115">LRSFullAccessAdminGroup という名前の Active Directory セキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-115">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="1a9d7-116">[グローバル] および [グループの種類] としてグループスコープを持つグループをセキュリティとして作成します。このグループに追加される SIP 対応ユーザーは、すべての管理ポータル機能を使用することを承認されています。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-116">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="1a9d7-117">![セキュリティグループの役割を持つ管理グループの一覧](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "セキュリティグループの役割を持つ管理グループの一覧")</span><span class="sxs-lookup"><span data-stu-id="1a9d7-117">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="1a9d7-118">LRSFullAccessAdminGroup を LRSSupportAdminGroup のメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-118">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="1a9d7-119">![LRSSupportAdminGroup Properties メンバーページ](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties メンバーページ")</span><span class="sxs-lookup"><span data-stu-id="1a9d7-119">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="1a9d7-120">LRSSupport という名前の SIP 対応 Active Directory ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-120">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="1a9d7-121">このユーザーを LRSSupportAdminGroup に追加します。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-121">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="1a9d7-122">![LRSSupportAdminGroup Properties メンバーページ](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties メンバーページ")</span><span class="sxs-lookup"><span data-stu-id="1a9d7-122">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="1a9d7-123">ASP.NET MVC 4 for Visual Studio 2010 SP1 および Visual Web Developer 2010 SP1 は、Microsoft ダウンロードセンター () から入手[http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)できます。</span><span class="sxs-lookup"><span data-stu-id="1a9d7-123">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

