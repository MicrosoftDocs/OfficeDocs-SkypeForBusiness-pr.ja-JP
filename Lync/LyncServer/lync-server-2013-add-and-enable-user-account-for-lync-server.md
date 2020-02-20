---
title: 'Lync Server 2013: Lync Server のユーザーアカウントの追加と有効化'
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
ms.openlocfilehash: bcbea7a081de0f5416f0df1cf6628e66c0998b92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-and-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="6d874-102">Lync Server 2013 のユーザーアカウントを追加して有効にする</span><span class="sxs-lookup"><span data-stu-id="6d874-102">Add and enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d874-103">_**トピックの最終更新日:** 2012-11-02_</span><span class="sxs-lookup"><span data-stu-id="6d874-103">_**Topic Last Modified:** 2012-11-02_</span></span>

<span data-ttu-id="6d874-104">Active Directory ユーザーとコンピューターでユーザーアカウントを有効にした後、lync server コントロールパネルを使用して、lync Server に Active Directory ユーザーを追加することにより、新しい Lync Server 2013 ユーザーアカウントを作成して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6d874-104">After enabling a user account in Active Directory Users and Computers, you can use Lync Server Control Panel to create and enable new Lync Server 2013 user accounts by adding an Active Directory user to Lync Server.</span></span>

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a><span data-ttu-id="6d874-105">新しい Lync Server ユーザーを追加して有効にするには</span><span class="sxs-lookup"><span data-stu-id="6d874-105">To add and enable a new Lync Server user</span></span>

1.  <span data-ttu-id="6d874-106">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6d874-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6d874-107">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6d874-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6d874-108">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d874-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6d874-109">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d874-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="6d874-110">[**ユーザーの有効化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d874-110">Click **Enable users**.</span></span>

5.  <span data-ttu-id="6d874-111">[**新規 Lync Server ユーザー**] ダイアログで [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d874-111">On the **New Lync Server User** dialog, click **Add**.</span></span>

6.  <span data-ttu-id="6d874-112">[**ユーザーの検索**] ボックスに、名前、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、電子メール アドレス、ユーザーのプリンシパル名 (UPN)、または対象の Active Directory ユーザー アカウントの電話番号の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d874-112">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7.  <span data-ttu-id="6d874-113">表で、Lync Server に追加するアカウントを選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d874-113">In the table, select the account you want to add to Lync Server, and then click **OK**.</span></span>

8.  <span data-ttu-id="6d874-114">ユーザーをプールに割り当て、詳細情報を指定し、ポリシーを対象のユーザーに割り当て、[**有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d874-114">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6d874-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d874-115">See Also</span></span>


[<span data-ttu-id="6d874-116">Lync Server 2013 のユーザーアカウントを無効または再度有効にする</span><span class="sxs-lookup"><span data-stu-id="6d874-116">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="6d874-117">Lync Server 2013 からユーザーアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="6d874-117">Remove a user account from Lync Server 2013</span></span>](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[<span data-ttu-id="6d874-118">Lync Server 2013 のユーザーの有効化および無効化</span><span class="sxs-lookup"><span data-stu-id="6d874-118">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

