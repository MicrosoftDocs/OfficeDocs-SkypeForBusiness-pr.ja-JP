---
title: Lync Phone Edition の構成設定の既存のコレクションを削除する
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
ms.openlocfilehash: dbf7d49a14ce45550777c6c122cd799f6a511f76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="99373-102">Lync Server 2013 で既存の Lync Phone エディション構成の設定を削除する</span><span class="sxs-lookup"><span data-stu-id="99373-102">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99373-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="99373-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="99373-104">Lync Phone Edition を実行しているデバイスの設定のコレクションを使用する必要がなくなった場合は、削除します。</span><span class="sxs-lookup"><span data-stu-id="99373-104">If you no longer want to use a collection of settings for devices running Lync Phone Edition, delete it.</span></span> <span data-ttu-id="99373-105">サイトのコレクションを削除すると、そのサイトの電話にグローバル設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="99373-105">If you delete a collection for a site, the global settings will apply to the phones in that site.</span></span> <span data-ttu-id="99373-106">グローバルコレクションは削除できません。</span><span class="sxs-lookup"><span data-stu-id="99373-106">You cannot delete the global collection.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="99373-107">コレクションを削除する代わりに、設定の一部を変更することが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="99373-107">Instead of deleting a collection, you might just want to change some of the settings.</span></span> <span data-ttu-id="99373-108">その方法の詳細については、「lync <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Server 2013 で Lync Phone Edition 構成設定のコレクションを作成または変更</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99373-108">For details about how to do so, see <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="99373-109">Lync Phone エディション構成設定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="99373-109">To delete a collection of Lync Phone Edition configuration settings</span></span>

1.  <span data-ttu-id="99373-110">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="99373-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99373-111">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="99373-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="99373-112">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="99373-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="99373-113">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイス構成**] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="99373-113">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="99373-114">[**デバイスの構成**] ページで、削除するコレクションをクリックし、[**編集**] メニューをクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99373-114">On the **Device Configuration** page, click the collection you want to delete, click the **Edit** menu, and then click **Delete**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="99373-115">グローバルコレクションを削除した場合、設定は既定の設定に戻ります。</span><span class="sxs-lookup"><span data-stu-id="99373-115">If you delete the global collection, the settings just revert to the default settings.</span></span> <span data-ttu-id="99373-116">コレクションは移動しません。</span><span class="sxs-lookup"><span data-stu-id="99373-116">The collection does not go away.</span></span>

    
    </div>

5.  <span data-ttu-id="99373-117">確認ボックスで [ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99373-117">In the confirmation box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="99373-118">Windows PowerShell コマンドレットを使用した、Lync Phone Edition 構成設定の削除</span><span class="sxs-lookup"><span data-stu-id="99373-118">Removing Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="99373-119">Lync Phone Edition の構成設定は、Windows PowerShell と**CsUCConfiguration**コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="99373-119">You can delete Lync Phone Edition configuration settings by using Windows PowerShell and the **Remove-CsUCConfiguration** cmdlet.</span></span> <span data-ttu-id="99373-120">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="99373-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="99373-121">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="99373-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="99373-122">指定した Lync Phone エディション構成設定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="99373-122">To remove a specified collection of Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="99373-123">このコマンドは、Redmond サイトに適用されている UC 電話構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="99373-123">This command deletes the UC phone configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="99373-124">サイトの範囲に適用されているすべての Lync Phone エディション構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="99373-124">To remove all of the Lync Phone Edition configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="99373-125">このコマンドにより、サービスの範囲に適用されているすべての UC 電話構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="99373-125">This command removes all the UC phone configuration settings applied to the service scope:</span></span>
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a><span data-ttu-id="99373-126">電話のロックが無効になっている Lync Phone エディションの構成設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="99373-126">To remove all of the Lync Phone Edition configuration settings where phone locking is disabled</span></span>

  - <span data-ttu-id="99373-127">このコマンドは、電話のロックが無効になっている UC 電話構成設定のコレクションをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="99373-127">This command deletes any collection of UC phone configuration settings where phone locking has been disabled:</span></span>
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

<span data-ttu-id="99373-128">詳細については、「 [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99373-128">For details, see [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

