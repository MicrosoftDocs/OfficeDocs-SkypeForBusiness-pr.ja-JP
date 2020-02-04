---
title: 'Lync Server 2013: Lync Server のユーザーアカウントを追加して有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add and enable user account for Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48183578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a04a798a69279ebef6c4917938ead2fd88a49805
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-and-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="52dfe-102">Lync Server 2013 のユーザーアカウントを追加して有効にする</span><span class="sxs-lookup"><span data-stu-id="52dfe-102">Add and enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52dfe-103">_**最終更新日:** 2012-11-02_</span><span class="sxs-lookup"><span data-stu-id="52dfe-103">_**Topic Last Modified:** 2012-11-02_</span></span>

<span data-ttu-id="52dfe-104">Active Directory ユーザーとコンピューターでユーザーアカウントを有効にした後、Lync Server コントロールパネルを使用して、Active Directory ユーザーを Lync Server に追加することで、新しい Lync Server 2013 ユーザーアカウントを作成して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="52dfe-104">After enabling a user account in Active Directory Users and Computers, you can use Lync Server Control Panel to create and enable new Lync Server 2013 user accounts by adding an Active Directory user to Lync Server.</span></span>

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a><span data-ttu-id="52dfe-105">新しい Lync Server ユーザーを追加して有効にするには</span><span class="sxs-lookup"><span data-stu-id="52dfe-105">To add and enable a new Lync Server user</span></span>

1.  <span data-ttu-id="52dfe-106">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="52dfe-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="52dfe-107">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="52dfe-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="52dfe-108">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="52dfe-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="52dfe-109">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52dfe-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="52dfe-110">[**ユーザーを有効にする] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="52dfe-110">Click **Enable users**.</span></span>

5.  <span data-ttu-id="52dfe-111">[**新しい Lync Server ユーザー** ] ダイアログボックスで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52dfe-111">On the **New Lync Server User** dialog, click **Add**.</span></span>

6.  <span data-ttu-id="52dfe-112">[**ユーザーの検索**] ボックスで、名前、表示名、姓、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、メールアドレス、ユーザープリンシパル名 (UPN)、または必要な Active Directory ユーザーアカウントの電話番号のすべてまたは最初の部分を入力し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52dfe-112">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7.  <span data-ttu-id="52dfe-113">表で、Lync Server に追加するアカウントを選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52dfe-113">In the table, select the account you want to add to Lync Server, and then click **OK**.</span></span>

8.  <span data-ttu-id="52dfe-114">プールにユーザーを割り当て、追加の詳細を指定して、ポリシーを目的のユーザーに割り当て、[**有効に**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52dfe-114">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="52dfe-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="52dfe-115">See Also</span></span>


[<span data-ttu-id="52dfe-116">Lync Server 2013 のユーザーアカウントを無効にするか、再び有効にする</span><span class="sxs-lookup"><span data-stu-id="52dfe-116">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="52dfe-117">Lync Server 2013 からユーザーアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="52dfe-117">Remove a user account from Lync Server 2013</span></span>](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[<span data-ttu-id="52dfe-118">Lync Server 2013 のユーザーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="52dfe-118">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

