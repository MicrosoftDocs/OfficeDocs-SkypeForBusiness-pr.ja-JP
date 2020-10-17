---
title: 'Lync Server 2013: Lync Server ユーザーの検索'
description: 'Lync Server 2013: Lync Server ユーザーを検索します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0c4860b7b89ad13b3a0003c5666a320172dad6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557083"
---
# <a name="search-for-lync-server-users-in-lync-server-2013"></a><span data-ttu-id="58201-103">Lync server 2013 での Lync Server ユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="58201-103">Search for Lync Server users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58201-104">_**トピックの最終更新日:** 2014-05-14_</span><span class="sxs-lookup"><span data-stu-id="58201-104">_**Topic Last Modified:** 2014-05-14_</span></span>

<span data-ttu-id="58201-105">検索クエリの結果を使用して、Lync Server 2013 のユーザーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="58201-105">You can use the results of a search query to configure users for Lync Server 2013.</span></span> <span data-ttu-id="58201-106">ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。</span><span class="sxs-lookup"><span data-stu-id="58201-106">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="58201-107">ユーザーの検索には、Lync Server コントロール パネルまたは Active Directory ユーザーおよびコンピューター スナップインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="58201-107">You can search for users by using the Lync Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="58201-108">次の手順では、Lync Server コントロールパネルを使用してユーザーを検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="58201-108">The following procedure describes how to use Lync Server Control Panel to search for users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="58201-109">中央フォレストトポロジを使用している環境では、ユーザーの電子メールアドレスでユーザーを検索すると、検索結果が正確でないことがあります。</span><span class="sxs-lookup"><span data-stu-id="58201-109">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user’s email address.</span></span> <span data-ttu-id="58201-110">代わりに、SIP アドレスプレフィックスを指定してユーザーを検索できます。たとえば、sip: name、検索フィルターを追加して、電子メールアドレスの一部を含む SIP アドレスを選択するか、または <STRONG>Get-help user</STRONG> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="58201-110">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the <STRONG>Get-CSUser</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="58201-111">1 つ以上のユーザーを検索するには</span><span class="sxs-lookup"><span data-stu-id="58201-111">To search for one or more users</span></span>

1.  <span data-ttu-id="58201-112">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="58201-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="58201-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="58201-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="58201-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58201-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="58201-115">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58201-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="58201-116">[**ユーザーの検索**] ボックスに、検索対象のユーザー アカウントの表示名、名、姓、SAM のアカウント名、SIP アドレス、または回線 URI の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58201-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5.  <span data-ttu-id="58201-117">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="58201-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="58201-118">画面の右上隅、[**検索結果**] の上にある展開の矢印ボタンをクリックして、[**フィルターの追加** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58201-118">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="58201-119">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、ユーザーのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="58201-119">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
    3.  <span data-ttu-id="58201-120">[**次の値に等しい**] リストで、[**次の値に等しい**] または [**次の値に等しくない**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58201-120">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
    4.  <span data-ttu-id="58201-121">テキスト ボックスで、検索結果のフィルターに使う検索条件を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58201-121">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6.  <span data-ttu-id="58201-p105">[**検索結果**] に検索結果が表示されます。 リストのユーザーの一部または全部を選択して、選択したユーザーに対して構成タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="58201-p105">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="58201-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="58201-124">See Also</span></span>


[<span data-ttu-id="58201-125">Lync Server 2013 に対して有効になっているユーザーアカウントに関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="58201-125">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[<span data-ttu-id="58201-126">Lync Server 2013 のユーザーの有効化および無効化</span><span class="sxs-lookup"><span data-stu-id="58201-126">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

