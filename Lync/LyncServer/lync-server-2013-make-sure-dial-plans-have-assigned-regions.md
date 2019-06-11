---
title: 'Lync Server 2013: ダイヤル プランに地域が割り当てられていることの確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75c5aa91470accf0f25478b9233e1efb90357251
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a><span data-ttu-id="8a7aa-102">「ダイヤルプラン Lync Server 2013 に地域が割り当てられていることを確認する」</span><span class="sxs-lookup"><span data-stu-id="8a7aa-102">Make sure dial plans Lync Server 2013 have assigned regions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a7aa-103">_**最終更新日:** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="8a7aa-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="8a7aa-104">ダイヤルイン会議に使用するダイヤルプランには、ダイヤルイン会議アクセス番号と適切なダイヤルプランを関連付けるために、**ダイヤルイン会議領域**が指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-104">Dial plans that are used for dial-in conferencing need to have a **Dial-in conferencing region** specified to associate dial-in conferencing access numbers with the appropriate dial plan.</span></span> <span data-ttu-id="8a7aa-105">ダイヤル プランをセットアップするときに、そのダイヤル プランに適用されるダイヤルイン会議の地域を指定します。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-105">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan.</span></span> <span data-ttu-id="8a7aa-106">次に、ダイヤルインアクセス番号を作成するときに、アクセス番号を適切なダイヤルプランに関連付ける地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-106">Then, when you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="8a7aa-107">すべてのダイヤルプランの地域を指定することが重要であるため、この手順を使用して、すべてのダイヤルプランに地域が設定されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-107">Because it important to specify a region for all dial plans, we recommend that you use this procedure to verify that all dial plans have regions.</span></span> <span data-ttu-id="8a7aa-108">この手順は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-108">This step is optional.</span></span>

<span data-ttu-id="8a7aa-109">**Get-CsDialPlan**コマンドレットを使用して、地域がすべてのダイヤルイン会議ダイヤルプランに設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-109">Use the **Get-CsDialPlan** cmdlet to verify whether the region is set for all dial-in conferencing dial plans.</span></span> <span data-ttu-id="8a7aa-110">ダイヤル プランに地域がない場合は、**Set-CsDialPlan** コマンドレットを使用して地域を設定できます。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-110">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="8a7aa-111">Lync Server コントロールパネルを使用して、既存のダイヤルプランの領域を更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-111">You can also use Lync Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="8a7aa-112">Lync Server コントロールパネルの使用について詳しくは、「 [Lync server 2013 でダイヤルプランを変更](lync-server-2013-modify-a-dial-plan.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-112">For details about using Lync Server Control Panel, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="8a7aa-113">ダイヤル プランで地域プロパティが設定されているかどうかを確認するには</span><span class="sxs-lookup"><span data-stu-id="8a7aa-113">To verify whether dial plans have the region property set</span></span>

1.  <span data-ttu-id="8a7aa-114">RTCUniversalServerAdmins グループのメンバーか、**Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="8a7aa-115">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8a7aa-116">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-116">Run the following at the command prompt:</span></span>
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    <span data-ttu-id="8a7aa-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-117">For example:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="8a7aa-118">この例では、組織で構成されているすべてのダイヤル プランが戻されます。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-118">In this example, all the dial plans configured for your organization are returned.</span></span>

4.  <span data-ttu-id="8a7aa-119">戻されたダイヤル プランを確認して、ダイヤルイン会議の地域が含まれていないものを識別します。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-119">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> <span data-ttu-id="8a7aa-120">詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-120">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="8a7aa-121">ダイヤル プランの地域プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="8a7aa-121">To set the region property for a dial plan</span></span>

1.  <span data-ttu-id="8a7aa-122">RTCUniversalServerAdmins グループのメンバーか、**Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="8a7aa-123">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8a7aa-124">ダイヤルイン会議の地域が含まれていないダイヤル プランで、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-124">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    <span data-ttu-id="8a7aa-125">例:</span><span class="sxs-lookup"><span data-stu-id="8a7aa-125">For example:</span></span>
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    <span data-ttu-id="8a7aa-126">この例では、Redmond という Identity を持つダイヤル プランを変更して、DialinConferencingRegion プロパティを "US West Coast" に設定します。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-126">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> <span data-ttu-id="8a7aa-127">詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a7aa-127">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

