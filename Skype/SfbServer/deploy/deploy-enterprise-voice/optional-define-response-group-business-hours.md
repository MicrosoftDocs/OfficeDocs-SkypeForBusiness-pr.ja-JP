---
title: (省略可能)ビジネス用の Skype を定義する応答グループの営業時間
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: 作成または応答グループのビジネス サーバーのエンタープライズ VoIP の Skype での営業時間を変更します。
ms.openlocfilehash: e98bfcf07b48811957c659fc865edda930f33da7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894641"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a><span data-ttu-id="330a5-103">(省略可能)ビジネス用の Skype を定義する応答グループの営業時間</span><span class="sxs-lookup"><span data-stu-id="330a5-103">(Optional) Define Response Group business hours in Skype for Business</span></span> 
 
<span data-ttu-id="330a5-104">作成または応答グループのビジネス サーバーのエンタープライズ VoIP の Skype での営業時間を変更します。</span><span class="sxs-lookup"><span data-stu-id="330a5-104">Create or modify Response Group business hours, in Skype for Business Server Enterprise Voice.</span></span>
  
## <a name="defining-business-hours"></a><span data-ttu-id="330a5-105">営業時間の定義</span><span class="sxs-lookup"><span data-stu-id="330a5-105">Defining Business Hours</span></span>

<span data-ttu-id="330a5-106">営業時間設定では、ワークフローが通話に応答できる時間を定義し、営業時間外の通話に対するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="330a5-106">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="330a5-107">応答グループ管理者は、**New-CsRgsHoursOfBusiness** コマンドレットを使用して、使用できる応答グループの数に制限がない事前設定スケジュールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="330a5-107">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>
  
> [!TIP]
> <span data-ttu-id="330a5-108">ワークフローを作成または変更するときに、そのワークフローのみに適用されるカスタム スケジュールを指定できます。</span><span class="sxs-lookup"><span data-stu-id="330a5-108">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="330a5-109">詳細については、[設計と応答のビジネス用の Skype でのグループのワークフローを作成する](designing-and-creating-response-group-workflows.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="330a5-109">For details, see [Designing and creating response group workflows in Skype for Business](designing-and-creating-response-group-workflows.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="330a5-110">ワークフローが管理ワークフローとして定義されている場合、CsResponseGroupManager の役割を割り当てられているすべてのユーザーは、管理するワークフローのカスタム営業時間を設定および変更できます。</span><span class="sxs-lookup"><span data-stu-id="330a5-110">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="330a5-111">次のコマンドレットのパラメーターの時刻表記は、24 時間形式で入力する必要があります (例: 20:00 は午後 8:00 を表します)。</span><span class="sxs-lookup"><span data-stu-id="330a5-111">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span> 
  
### <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="330a5-112">事前設定された営業時間コレクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="330a5-112">To create a predefined business hours collection</span></span>

1. <span data-ttu-id="330a5-113">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="330a5-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="330a5-114">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="330a5-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="330a5-115">定義する一意の時間の範囲ごとに、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="330a5-115">For each unique range of hours you want to define, run:</span></span>
    
   ```
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    <span data-ttu-id="330a5-116">定義した範囲を使用する営業時間コレクションを作成するには、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="330a5-116">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
   ```
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    <span data-ttu-id="330a5-p103">次の例では、平日の営業時間を午前 9:00 から午後 5:00 に、土曜日の営業時間を午前 8:00 から午前 10:00 と午後 2:00 から午後 6:00 に、日曜日は営業時間なしに指定します。</span><span class="sxs-lookup"><span data-stu-id="330a5-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
   ```
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a><span data-ttu-id="330a5-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="330a5-124">See also</span></span>

[<span data-ttu-id="330a5-125">新しい-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="330a5-125">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[<span data-ttu-id="330a5-126">新しい-CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="330a5-126">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
