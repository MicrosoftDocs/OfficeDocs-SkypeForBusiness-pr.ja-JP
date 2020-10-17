---
title: Lync Phone Edition 構成設定の既存コレクションの削除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce796b13ea69296fa72799a13d35cb2046a643b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514634"
---
# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="fc56d-102">Lync Server 2013 の Lync Phone Edition 構成設定の既存コレクションの削除</span><span class="sxs-lookup"><span data-stu-id="fc56d-102">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc56d-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fc56d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fc56d-104">Lync Phone Edition を実行しているデバイスの設定のコレクションを使用する必要がなくなった場合は、それを削除します。</span><span class="sxs-lookup"><span data-stu-id="fc56d-104">If you no longer want to use a collection of settings for devices running Lync Phone Edition, delete it.</span></span> <span data-ttu-id="fc56d-105">サイトのコレクションを削除すると、そのサイト内の電話にはグローバル設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="fc56d-105">If you delete a collection for a site, the global settings will apply to the phones in that site.</span></span> <span data-ttu-id="fc56d-106">グローバル コレクションは削除できません。</span><span class="sxs-lookup"><span data-stu-id="fc56d-106">You cannot delete the global collection.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="fc56d-107">コレクションを削除するのではなく、一部の設定の変更のみ必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="fc56d-107">Instead of deleting a collection, you might just want to change some of the settings.</span></span> <span data-ttu-id="fc56d-108">これを行う方法の詳細については、「 <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Lync Server 2013 の Lync Phone Edition 構成設定のコレクションを作成または変更</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc56d-108">For details about how to do so, see <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="fc56d-109">Lync Phone Edition 構成設定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="fc56d-109">To delete a collection of Lync Phone Edition configuration settings</span></span>

1.  <span data-ttu-id="fc56d-110">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fc56d-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fc56d-111">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fc56d-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fc56d-112">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc56d-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fc56d-113">左側のナビゲーション バーで [**クライアント**] をクリックし、[**デバイスの構成**] 移動ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc56d-113">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="fc56d-114">[**デバイスの構成**] ページで、削除するコレクションをクリックし、[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc56d-114">On the **Device Configuration** page, click the collection you want to delete, click the **Edit** menu, and then click **Delete**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="fc56d-p104">グローバル コレクションを削除すると、設定が既定の設定に戻ります。コレクションがなくなることはありません。</span><span class="sxs-lookup"><span data-stu-id="fc56d-p104">If you delete the global collection, the settings just revert to the default settings. The collection does not go away.</span></span>

    
    </div>

5.  <span data-ttu-id="fc56d-117">確認ボックスで [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc56d-117">In the confirmation box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fc56d-118">Windows PowerShell コマンドレットを使用して Lync Phone Edition の構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="fc56d-118">Removing Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fc56d-119">Lync Phone Edition の構成設定は、Windows PowerShell と **CsUCConfiguration** コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="fc56d-119">You can delete Lync Phone Edition configuration settings by using Windows PowerShell and the **Remove-CsUCConfiguration** cmdlet.</span></span> <span data-ttu-id="fc56d-120">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="fc56d-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fc56d-121">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc56d-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="fc56d-122">指定された Lync Phone Edition 構成設定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="fc56d-122">To remove a specified collection of Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="fc56d-123">次のコマンドは、Redmond サイトに適用される UC 電話の構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="fc56d-123">This command deletes the UC phone configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="fc56d-124">サイトスコープに適用されているすべての Lync Phone Edition 構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="fc56d-124">To remove all of the Lync Phone Edition configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="fc56d-125">次のコマンドは、サービス スコープに適用される UC 電話の構成設定をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="fc56d-125">This command removes all the UC phone configuration settings applied to the service scope:</span></span>
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a><span data-ttu-id="fc56d-126">電話のロックが無効になっているすべての Lync Phone Edition の構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="fc56d-126">To remove all of the Lync Phone Edition configuration settings where phone locking is disabled</span></span>

  - <span data-ttu-id="fc56d-127">次のコマンドは、電話のロックが無効にされている UC 電話の構成設定のコレクションをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="fc56d-127">This command deletes any collection of UC phone configuration settings where phone locking has been disabled:</span></span>
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

<span data-ttu-id="fc56d-128">詳細については、「 [get-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc56d-128">For details, see [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15)).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

