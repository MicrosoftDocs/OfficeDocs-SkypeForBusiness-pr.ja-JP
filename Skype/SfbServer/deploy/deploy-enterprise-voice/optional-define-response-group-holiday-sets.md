---
title: (省略可能)Skype for Business で応答グループの休日セットを定義する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Skype for Business Server グループの応答グループ休日セットを作成または変更エンタープライズ VoIP。
ms.openlocfilehash: 3a8173964cf32c148146ffc4c501861b35bf6077
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103683"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a><span data-ttu-id="4bee1-103">(省略可能)Skype for Business で応答グループの休日セットを定義する</span><span class="sxs-lookup"><span data-stu-id="4bee1-103">(Optional) Define Response Group holiday sets in Skype for Business</span></span>
 
<span data-ttu-id="4bee1-104">Skype for Business Server グループの応答グループ休日セットを作成または変更エンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="4bee1-104">Create or modify Response Group holiday sets, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="4bee1-p101">休日設定では、応答グループが営業しない日を定義し、その日に実行するアクションを指定します。休日セットは、応答グループに適用する休日のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="4bee1-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4bee1-107">ワークフローが管理ワークフローとして定義されている場合、CsResponseGroupManager の役割に割り当てられたユーザーは、管理するワークフローの休日を設定および変更できます。</span><span class="sxs-lookup"><span data-stu-id="4bee1-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span> 
  
### <a name="to-create-a-holiday-set"></a><span data-ttu-id="4bee1-108">休日セットを作成するには</span><span class="sxs-lookup"><span data-stu-id="4bee1-108">To create a holiday set</span></span>

1. <span data-ttu-id="4bee1-109">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="4bee1-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="4bee1-110">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4bee1-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4bee1-111">定義する休日ごとに、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="4bee1-111">For each holiday you want to define, run:</span></span>
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    <span data-ttu-id="4bee1-112">定義した休日を含める休日セットを作成するには、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="4bee1-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    <span data-ttu-id="4bee1-113">次の例では、2 つの休日を含む休日セットを示します。</span><span class="sxs-lookup"><span data-stu-id="4bee1-113">The following example shows a holiday set that includes two holidays:</span></span>
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a><span data-ttu-id="4bee1-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bee1-114">See also</span></span>

[<span data-ttu-id="4bee1-115">Skype for Business での応答グループ ワークフローの設計と作成</span><span class="sxs-lookup"><span data-stu-id="4bee1-115">Designing and creating response group workflows in Skype for Business</span></span>](designing-and-creating-response-group-workflows.md)

[<span data-ttu-id="4bee1-116">New-CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="4bee1-116">New-CsRgsHoliday</span></span>](/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[<span data-ttu-id="4bee1-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="4bee1-117">New-CsRgsHolidaySet</span></span>](/powershell/module/skype/new-csrgsholidayset?view=skype-ps)