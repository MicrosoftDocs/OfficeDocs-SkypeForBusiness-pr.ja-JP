---
title: 'Lync Server 2013: Lync Server ユーザーを検索する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068fe07bf14894d22f929291514854360d6d0465
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a><span data-ttu-id="ce7ce-102">Lync server 2013 で Lync Server ユーザーを検索する</span><span class="sxs-lookup"><span data-stu-id="ce7ce-102">Search for Lync Server users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce7ce-103">_**最終更新日:** 2014-05-14_</span><span class="sxs-lookup"><span data-stu-id="ce7ce-103">_**Topic Last Modified:** 2014-05-14_</span></span>

<span data-ttu-id="ce7ce-104">検索クエリの結果を使用して、Lync Server 2013 のユーザーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-104">You can use the results of a search query to configure users for Lync Server 2013.</span></span> <span data-ttu-id="ce7ce-105">ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-105">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="ce7ce-106">Lync Server コントロールパネル、または Active Directory ユーザーとコンピュータースナップインを使用して、ユーザーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-106">You can search for users by using the Lync Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="ce7ce-107">次の手順では、Lync Server コントロールパネルを使用してユーザーを検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-107">The following procedure describes how to use Lync Server Control Panel to search for users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce7ce-108">中央フォレストトポロジを持つ環境では、ユーザーのメールアドレスでユーザーを検索すると、検索結果が正確でない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-108">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user’s email address.</span></span> <span data-ttu-id="ce7ce-109">代わりに、SIP アドレスプレフィックスを指定してユーザーを検索することもできます。たとえば、sip: name、検索フィルターを追加して、メールアドレスの一部を含む SIP アドレスを選ぶか、または、<STRONG>ユーザー</STRONG>コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-109">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the <STRONG>Get-CSUser</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="ce7ce-110">1人以上のユーザーを検索するには</span><span class="sxs-lookup"><span data-stu-id="ce7ce-110">To search for one or more users</span></span>

1.  <span data-ttu-id="ce7ce-111">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ce7ce-112">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ce7ce-113">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ce7ce-114">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="ce7ce-115">[**ユーザーの検索**] ボックスに、検索するユーザーアカウントの表示名、姓、名、SAM アカウント名、SIP アドレス、またはライン URI のすべてまたは最初の部分を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5.  <span data-ttu-id="ce7ce-116">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="ce7ce-117">**検索結果**の上にある画面の右上隅にある展開矢印ボタンをクリックし、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-117">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="ce7ce-118">[ユーザー] プロパティを入力するか、ドロップダウンリストの矢印をクリックして、ユーザープロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-118">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
    3.  <span data-ttu-id="ce7ce-119">[指定の**値**に等しい] \*\*\*\* または [ \*\*\*\* 指定の値に等しい] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-119">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
    4.  <span data-ttu-id="ce7ce-120">検索結果をフィルター処理するために使用する検索条件をテキストボックスに入力し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-120">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6.  <span data-ttu-id="ce7ce-121">検索結果が [**検索結果**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-121">The search results appear under **Search Results**.</span></span> <span data-ttu-id="ce7ce-122">リスト内の任意またはすべてのユーザーを選択し、選択したユーザーに対して構成タスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="ce7ce-122">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce7ce-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce7ce-123">See Also</span></span>


[<span data-ttu-id="ce7ce-124">Lync Server 2013 で有効になっているユーザーアカウントに関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="ce7ce-124">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[<span data-ttu-id="ce7ce-125">Lync Server 2013 のユーザーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="ce7ce-125">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

