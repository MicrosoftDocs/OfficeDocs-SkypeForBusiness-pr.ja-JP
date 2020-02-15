---
title: 'Lync Server 2013: 外部ユーザーアクセスのサイトポリシーまたはユーザーポリシーの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c21b58715814b5bf08023662bff61b004b51896
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="d5edf-102">Lync Server 2013 で外部ユーザーアクセスのサイトポリシーまたはユーザーポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="d5edf-102">Delete a site or user policy for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5edf-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="d5edf-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="d5edf-104">[**外部アクセスポリシー** ] ページの [Lync Server コントロールパネル] に表示されているすべてのサイトポリシーまたはユーザーポリシーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d5edf-104">You can delete any site or user policy that is listed in Lync Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="d5edf-105">グローバル ポリシーを削除すると、実際には削除されず、外部ユーザー アクセス オプションのサポートが含まれていない既定の設定にリセットされるだけです。</span><span class="sxs-lookup"><span data-stu-id="d5edf-105">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="d5edf-106">グローバルポリシーのリセットの詳細については、「 [Lync Server 2013 での外部ユーザーアクセスに関するグローバルポリシーのリセット](lync-server-2013-reset-the-global-policy-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5edf-106">For details about resetting the global policy, see [Reset the global policy for external user access in Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).</span></span>

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="d5edf-107">外部ユーザー アクセスのサイト ポリシーまたはユーザー ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="d5edf-107">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="d5edf-108">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d5edf-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d5edf-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d5edf-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d5edf-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5edf-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d5edf-111">[**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5edf-111">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="d5edf-112">[**外部アクセス ポリシー**] タブで、削除するサイト ポリシーまたはユーザー ポリシーをクリックして [**編集**] をクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5edf-112">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="d5edf-113">削除について確認するメッセージが表示されたら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5edf-113">When prompted to confirm the deletion, click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d5edf-114">Windows PowerShell コマンドレットを使用して PIN ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="d5edf-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d5edf-115">外部アクセスポリシーは、Windows PowerShell と Get-csexternalaccesspolicy コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="d5edf-115">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="d5edf-116">このコマンドレットは、Lync Server 2013 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="d5edf-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d5edf-117">リモート Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Microsoft Lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)を使用したリモート PowerShell の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5edf-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="d5edf-118">特定の外部アクセスポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="d5edf-118">To remove a specific external access policy</span></span>

  - <span data-ttu-id="d5edf-119">次のコマンドでは、Redmond サイトに適用されている外部アクセス ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="d5edf-119">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="d5edf-120">ユーザーごとのスコープに適用されているすべての外部アクセスポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="d5edf-120">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="d5edf-121">次のコマンドでは、ユーザーごとのスコープで構成されているすべての外部アクセス ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="d5edf-121">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="d5edf-122">外部ユーザーアクセスが無効になっているすべての外部アクセスポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="d5edf-122">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="d5edf-123">次のコマンドでは、外部ユーザー アクセス ポリシーが無効になっているすべての外部アクセス ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="d5edf-123">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

<span data-ttu-id="d5edf-124">詳細については、 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5edf-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

