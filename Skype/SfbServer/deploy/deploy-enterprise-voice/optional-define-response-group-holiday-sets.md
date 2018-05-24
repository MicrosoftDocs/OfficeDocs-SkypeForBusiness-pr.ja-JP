---
title: (オプション) Skype for Business 2015 での応答グループ休日セットの定義
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: 作成またはビジネス サーバーのエンタープライズ VoIP の Skype での応答グループ休日セットを変更します。
ms.openlocfilehash: 0ee6ffa0afdff32096845d7450fa92ff6e720022
ms.sourcegitcommit: 68e68c96c18d854afc0158920e6d9d738f276d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business-2015"></a><span data-ttu-id="54d79-103">(オプション) Skype for Business 2015 での応答グループ休日セットの定義</span><span class="sxs-lookup"><span data-stu-id="54d79-103">(Optional) Define Response Group holiday sets in Skype for Business 2015</span></span>
 
<span data-ttu-id="54d79-104">作成またはビジネス サーバーのエンタープライズ VoIP の Skype での応答グループ休日セットを変更します。</span><span class="sxs-lookup"><span data-stu-id="54d79-104">Create or modify Response Group holiday sets, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="54d79-p101">休日設定では、応答グループが営業しない日を定義し、その日に実行するアクションを指定します。休日セットは、応答グループに適用する休日のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="54d79-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="54d79-107">ワークフローが管理ワークフローとして定義されている場合、CsResponseGroupManager の役割に割り当てられたユーザーは、管理するワークフローの休日を設定および変更できます。</span><span class="sxs-lookup"><span data-stu-id="54d79-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span> 
  
### <a name="to-create-a-holiday-set"></a><span data-ttu-id="54d79-108">休日セットを作成するには</span><span class="sxs-lookup"><span data-stu-id="54d79-108">To create a holiday set</span></span>

1. <span data-ttu-id="54d79-109">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="54d79-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="54d79-110">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="54d79-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="54d79-111">定義する休日ごとに、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="54d79-111">For each holiday you want to define, run:</span></span>
    
   ```
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    <span data-ttu-id="54d79-112">定義した休日を含める休日セットを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="54d79-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
   ```
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    <span data-ttu-id="54d79-113">次の例では、2 つの休日を含む休日セットを示します。</span><span class="sxs-lookup"><span data-stu-id="54d79-113">The following example shows a holiday set that includes two holidays:</span></span>
    
   ```
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a><span data-ttu-id="54d79-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="54d79-114">See also</span></span>

[<span data-ttu-id="54d79-115">設計とビジネス 2015年の Skype で応答グループ ワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="54d79-115">Designing and creating response group workflows in Skype for Business 2015</span></span>](designing-and-creating-response-group-workflows.md)

[<span data-ttu-id="54d79-116">新しい-CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="54d79-116">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[<span data-ttu-id="54d79-117">新しい-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="54d79-117">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
