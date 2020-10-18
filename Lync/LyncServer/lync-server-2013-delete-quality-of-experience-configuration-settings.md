---
title: 'Lync Server 2013: qoe (Quality of Experience) 構成設定の削除'
description: 'Lync Server 2013: qoe (Quality of Experience) 構成設定を削除します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1894877fe3dbbc758ba02b0e4e5b81c8b7edc4fb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577933"
---
# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="b7955-103">Lync Server 2013 の qoe (Quality of Experience) 構成設定の削除</span><span class="sxs-lookup"><span data-stu-id="b7955-103">Delete Quality of Experience configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7955-104">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b7955-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b7955-p101">QoE (Quality of Experience) 指標は、ネットワーク パケットの損失数、バックグラウンド ノイズ、"ジッター" (パケット遅延のばらつき) の量など、組織内で行われる音声通話およびビデオ通話の品質を追跡します。これらの指標は、他のデータ (詳細な通話の記録など) とは別にデータベースに格納されます。このため、QoE は他のデータ記録と関係なく有効および無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b7955-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="b7955-107">Microsoft Lync Server 2013 をインストールすると、QoE 構成設定のグローバルコレクションが1つ作成されます。</span><span class="sxs-lookup"><span data-stu-id="b7955-107">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="b7955-108">また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b7955-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="b7955-109">設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="b7955-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="b7955-110">サイト スコープの設定を削除すると、サイトの QoE はグローバル設定を使って管理されます。</span><span class="sxs-lookup"><span data-stu-id="b7955-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="b7955-p103">なお、グローバル設置は「削除」することができます。ただし、グローバル設定は実際に削除されるわけではありません。代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。たとえば、QoE 構成設定のコレクションでは削除が既定で有効になっています。仮にグローバル コレクションを変更して削除を無効にしたとします。後にグローバル設定を削除すると、すべてのプロパティは既定の値にリセットされます。この場合、削除が再び有効になることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b7955-p103">Note that you can also “delete” the global settings. However, the global settings will not actually be removed. Instead, all the properties in that collection will be reset to their default values. For example, by default purging is enabled in a collection of QoE configuration settings. Suppose you modify the global collection so that purging is disabled. If you later delete the global settings, all the properties will be reset to their default values. In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="b7955-118">QoE 構成設定を削除するには、Lync Server コントロールパネルを使用するか、または、 [削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b7955-118">You can remove QoE configuration settings by using the Lync Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) cmdlet.</span></span>

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="b7955-119">Lync Server コントロールパネルを使用して QoE 構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="b7955-119">To delete QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b7955-120">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b7955-120">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="b7955-121">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7955-121">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b7955-122">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b7955-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b7955-123">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7955-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b7955-124">左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7955-124">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="b7955-125">[**QoE データ**] ページで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7955-125">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="b7955-126">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7955-126">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b7955-127">Windows PowerShell コマンドレットを使用して QoE 構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="b7955-127">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b7955-128">QoE 構成設定を削除するには、Windows PowerShell および **Remove-CsQoEConfiguration** のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b7955-128">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="b7955-129">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="b7955-129">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b7955-130">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7955-130">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="b7955-131">指定した QoE 構成設定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="b7955-131">To remove a specified collection of QoE configuration settings</span></span>

  - <span data-ttu-id="b7955-132">このコマンドは、Redmond サイトに適用された QoE 構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="b7955-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="b7955-133">サイト スコープに適用されたすべての QoE 構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="b7955-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="b7955-134">このコマンドは、サイト スコープに適用されたすべての QoE 構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="b7955-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="b7955-135">QoE 監視が無効にされたすべての QoE 構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="b7955-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="b7955-136">このコマンドは、QoE 監視が無効にされたすべての QoE 構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="b7955-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

<span data-ttu-id="b7955-137">詳細については、「 [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7955-137">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

