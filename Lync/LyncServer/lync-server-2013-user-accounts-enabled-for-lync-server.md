---
title: 'Lync Server 2013: Lync Server に対して有効になっているユーザーアカウント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d51f72f586ab6d5b5094c61ae09d8ac316350b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a><span data-ttu-id="438a5-102">Lync Server 2013 に対して有効になっているユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="438a5-102">User accounts enabled for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="438a5-103">_**トピックの最終更新日:** 2014-04-18_</span><span class="sxs-lookup"><span data-stu-id="438a5-103">_**Topic Last Modified:** 2014-04-18_</span></span>

<span data-ttu-id="438a5-104">このセクションのトピックでは、Lync Server 2013 コントロールパネルを使用して実行できるユーザー設定を構成するための手順を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="438a5-104">Topics in this section provide step-by-step procedures for configuring user settings that you can perform using the Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="438a5-105">Lync Server コントロールパネルを使用して、Active Directory Domain Admins グループのメンバーであるユーザーを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="438a5-105">You cannot use Lync Server Control Panel to manage users who are members of the Active Directory Domain Admins group.</span></span> <span data-ttu-id="438a5-106">ドメイン管理者ユーザーの場合、Lync Server コントロールパネルのみを使用して読み取り専用の検索操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="438a5-106">For Domain Admins users, you can use Lync Server Control Panel only to perform read-only search operations.</span></span> <span data-ttu-id="438a5-107">ドメイン管理者のユーザーに対して書き込み操作を実行する (たとえば、Lync Server コントロールパネルの有効化または無効化、プールまたはポリシーの割り当ての変更、テレフォニー設定、SIP アドレス) については、ドメイン管理者ユーザーとしてログオンしているときに Windows PowerShell コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="438a5-107">To perform write operations on Domain Admins users (for example, enable or disable for Lync Server Control Panel, change pool or policy assignments, telephony settings, SIP address), you must use Windows PowerShell cmdlets while logged on as a Domain Admins user.</span></span> <span data-ttu-id="438a5-108">Windows PowerShell コマンドレットを使用してユーザーを管理する方法の詳細については、「 <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="438a5-108">For details about using Windows PowerShell cmdlets to manage users, see <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span></span>



</div>

<span data-ttu-id="438a5-109">ユーザーを検索したり、ユーザーの検索結果をフィルター処理したりする Lync Server 2013 の管理タスクを実行すると、Active Directory ドメインサービスに属性として存在するが、グローバルカタログにレプリケートされないユーザープロパティがいくつかあります。Microsoft Exchange Server が展開されるまで。</span><span class="sxs-lookup"><span data-stu-id="438a5-109">When you perform any Lync Server 2013 administrative task that involves searching for a user or filtering user search results, there are some user properties that exist as attributes in Active Directory Domain Services but are not replicated to the global catalog until Microsoft Exchange Server is deployed.</span></span> <span data-ttu-id="438a5-110">Lync Server ではなく、Microsoft Exchange は、次の属性がインストールされているグローバルカタログへのレプリケーションをマークします。</span><span class="sxs-lookup"><span data-stu-id="438a5-110">Microsoft Exchange, not Lync Server, marks the following attributes for replication to the global catalog when it is installed:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="438a5-111">ユーザー情報:</span><span class="sxs-lookup"><span data-stu-id="438a5-111">User Information</span></span></th>
<th><span data-ttu-id="438a5-112">住所と電話番号:</span><span class="sxs-lookup"><span data-stu-id="438a5-112">Address and Phone</span></span></th>
<th><span data-ttu-id="438a5-113">組織</span><span class="sxs-lookup"><span data-stu-id="438a5-113">Organization</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="438a5-114">Initials</span><span class="sxs-lookup"><span data-stu-id="438a5-114">Initials</span></span></p></td>
<td><p><span data-ttu-id="438a5-115">番地</span><span class="sxs-lookup"><span data-stu-id="438a5-115">Street address</span></span></p>
<p><span data-ttu-id="438a5-116">国/地域</span><span class="sxs-lookup"><span data-stu-id="438a5-116">Country/region</span></span></p>
<p><span data-ttu-id="438a5-117">Pager</span><span class="sxs-lookup"><span data-stu-id="438a5-117">Pager</span></span></p>
<p><span data-ttu-id="438a5-118">FAX</span><span class="sxs-lookup"><span data-stu-id="438a5-118">Fax</span></span></p>
<p><span data-ttu-id="438a5-119">Mobile</span><span class="sxs-lookup"><span data-stu-id="438a5-119">Mobile</span></span></p></td>
<td><p><span data-ttu-id="438a5-120">役職</span><span class="sxs-lookup"><span data-stu-id="438a5-120">Title</span></span></p>
<p><span data-ttu-id="438a5-121">Company</span><span class="sxs-lookup"><span data-stu-id="438a5-121">Company</span></span></p>
<p><span data-ttu-id="438a5-122">部署</span><span class="sxs-lookup"><span data-stu-id="438a5-122">Department</span></span></p>
<p><span data-ttu-id="438a5-123">事業所</span><span class="sxs-lookup"><span data-stu-id="438a5-123">Office</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="438a5-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="438a5-124">In This Section</span></span>

  - [<span data-ttu-id="438a5-125">Lync Server 2013 に対して有効になっているユーザーアカウントに関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="438a5-125">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [<span data-ttu-id="438a5-126">Lync Server 2013 のユーザーの有効化および無効化</span><span class="sxs-lookup"><span data-stu-id="438a5-126">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [<span data-ttu-id="438a5-127">Lync Server 2013 でのユーザーのエンタープライズ Voip の管理</span><span class="sxs-lookup"><span data-stu-id="438a5-127">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [<span data-ttu-id="438a5-128">Lync Server 2013 でユーザーアカウントのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="438a5-128">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)

  - [<span data-ttu-id="438a5-129">Lync Server 2013 での外部アクセスポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="438a5-129">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="438a5-130">Lync Server 2013 でのユーザー単位のポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="438a5-130">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="438a5-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="438a5-131">See Also</span></span>


[<span data-ttu-id="438a5-132">Lync Server 2013 でのユーザー管理のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="438a5-132">User management cmdlets in Lync Server 2013</span></span>](lync-server-2013-user-management-cmdlets.md)  


[<span data-ttu-id="438a5-133">Lync Server 2013 でのユーザーの管理</span><span class="sxs-lookup"><span data-stu-id="438a5-133">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

