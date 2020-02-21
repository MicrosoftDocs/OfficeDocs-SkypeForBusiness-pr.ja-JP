---
title: 'Lync Server 2013: アーカイブ構成の削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b864bb96ea7d342dbfd449cc9a151b0d7c2dee6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a><span data-ttu-id="e41cd-102">Lync Server 2013 でのアーカイブ構成の削除</span><span class="sxs-lookup"><span data-stu-id="e41cd-102">Deleting an Archiving configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e41cd-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e41cd-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e41cd-104">サイトまたはプールの構成を削除できます。</span><span class="sxs-lookup"><span data-stu-id="e41cd-104">You can delete a site configuration or pool configuration.</span></span> <span data-ttu-id="e41cd-105">グローバル構成は削除できません。</span><span class="sxs-lookup"><span data-stu-id="e41cd-105">The global configuration cannot be removed.</span></span> <span data-ttu-id="e41cd-106">グローバル構成を削除すると、自動的に既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="e41cd-106">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="e41cd-107">指定できるオプションやアーカイブ構成の階層など、アーカイブ構成の実装方法の詳細については、「計画」のドキュメント、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e41cd-107">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a><span data-ttu-id="e41cd-108">アーカイブ用のサイトまたはプールの構成を削除するには</span><span class="sxs-lookup"><span data-stu-id="e41cd-108">To delete a site or pool configuration for archiving</span></span>

1.  <span data-ttu-id="e41cd-109">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e41cd-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e41cd-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e41cd-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e41cd-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e41cd-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e41cd-112">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41cd-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="e41cd-113">アーカイブ構成のリストで、削除するサイトまたはプールの構成をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41cd-113">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="e41cd-114">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41cd-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e41cd-115">Windows PowerShell コマンドレットを使用してアーカイブ構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="e41cd-115">Removing Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e41cd-116">アーカイブ構成設定は、Windows PowerShell と**set-csarchivingconfiguration**コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="e41cd-116">Archiving configuration settings can be deleted by using Windows PowerShell and the **Remove-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="e41cd-117">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="e41cd-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e41cd-118">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="e41cd-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a><span data-ttu-id="e41cd-119">指定したアーカイブ構成設定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="e41cd-119">To remove a specified collection of archiving configuration settings</span></span>

  - <span data-ttu-id="e41cd-120">次のコマンドを実行すると、レドモンド サイトに適用されているアーカイブ構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="e41cd-120">The following command removes the archiving configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="e41cd-121">サイトスコープに適用されているすべてのアーカイブ構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="e41cd-121">To remove all the archiving configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="e41cd-122">このコマンドを実行すると、サービス スコープに適用されているすべてのアーカイブ構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="e41cd-122">This command removes all the archiving configuration settings applied to the service scope:</span></span>
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a><span data-ttu-id="e41cd-123">指定したプロパティ値に基づいてアーカイブ構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="e41cd-123">To remove archiving configuration settings based on a specified property value</span></span>

  - <span data-ttu-id="e41cd-124">このコマンドを実行すると、Exchange のアーカイブが無効になっているすべてのアーカイブ構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="e41cd-124">This command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

<span data-ttu-id="e41cd-125">詳細については、 [set-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e41cd-125">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e41cd-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="e41cd-126">See Also</span></span>


[<span data-ttu-id="e41cd-127">Lync Server 2013 でのアーカイブのしくみ</span><span class="sxs-lookup"><span data-stu-id="e41cd-127">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="e41cd-128">Lync Server 2013 での内部および外部通信のアーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="e41cd-128">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

