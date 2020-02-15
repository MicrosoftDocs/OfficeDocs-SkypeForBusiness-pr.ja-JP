---
title: 'Lync Server 2013: Lync Server からユーザーアカウントを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0699733bdfeb860aafa2b56086bf62988f18bbf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a><span data-ttu-id="3e5eb-102">Lync Server 2013 からユーザーアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="3e5eb-102">Remove a user account from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e5eb-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="3e5eb-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="3e5eb-104">次の手順を使用して、Lync Server 2013 で以前に追加したユーザーアカウントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-104">You can use the following procedure to remove a previously added user account in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3e5eb-105">ユーザーを削除すると、そのユーザー アカウントに対して構成したすべての設定が失われます。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-105">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="3e5eb-106">代わりにユーザーアカウントを一時的に無効にする場合は、「 <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013 のユーザーアカウントの無効化または再有効化</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-106">If you would like to temporarily disable a user account instead, see the topic <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a><span data-ttu-id="3e5eb-107">Lync Server 管理シェルを使用してユーザーアカウントを削除するには</span><span class="sxs-lookup"><span data-stu-id="3e5eb-107">To remove a user account by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="3e5eb-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3e5eb-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e5eb-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3e5eb-111">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-111">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3e5eb-112">[**ユーザーの検索**] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="3e5eb-113">表で、削除するユーザー アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-113">In the table, click the user account that you want to remove.</span></span>

6.  <span data-ttu-id="3e5eb-114">[**操作**] メニューの [**Lync Server から削除**] をクリックします。ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-114">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7.  <span data-ttu-id="3e5eb-115">ダイアログ ボックスで、ユーザーを削除するかどうかを確認するメッセージが表示されます。[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-115">From the dialog box, select **OK** to remove the user.</span></span>

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3e5eb-116">Windows PowerShell コマンドレットを使用してユーザーアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="3e5eb-116">Removing User Accounts by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3e5eb-117">ユーザーアカウントを削除するには、Disable-CsUser コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-117">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="3e5eb-118">このコマンドレットは、Lync Server 2013 管理シェルまたはリモートセッション Windows PowerShell から実行できます。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="3e5eb-119">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-user-account"></a><span data-ttu-id="3e5eb-120">ユーザーアカウントを削除するには</span><span class="sxs-lookup"><span data-stu-id="3e5eb-120">To remove a user account</span></span>

  - <span data-ttu-id="3e5eb-p104">ユーザー アカウントを削除するには、Disable-CsUser コマンドレットを使用します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-p104">To remove a user account, use the Disable-CsUser cmdlet. For example:</span></span>
    
        Disable-CsUser -Identity "Ken Myer"
    
    <span data-ttu-id="3e5eb-p105">このコマンドを実行した後、削除したアカウントおよびその以前の設定を再度有効化することはできません。Enable-CsUser コマンドレットを使用して、Ken Myer の新規アカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-p105">After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.</span></span>

</div>

<span data-ttu-id="3e5eb-125">詳細については、「 [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e5eb-125">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3e5eb-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e5eb-126">See Also</span></span>


[<span data-ttu-id="3e5eb-127">Lync Server 2013 のユーザーアカウントを無効または再度有効にする</span><span class="sxs-lookup"><span data-stu-id="3e5eb-127">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="3e5eb-128">Lync Server 2013 のユーザーの有効化および無効化</span><span class="sxs-lookup"><span data-stu-id="3e5eb-128">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

