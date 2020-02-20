---
title: 'Lync Server 2013: (オプション) 応答グループの営業時間の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group business hours
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205291(v=OCS.15)
ms:contentKeyID: 48185504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac232fa40e4fd9a276dd7e96e8565e0dcf0b3940
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-business-hours-in-lync-server-2013"></a><span data-ttu-id="02ec9-102">オプションLync Server 2013 で応答グループの営業時間を定義する</span><span class="sxs-lookup"><span data-stu-id="02ec9-102">(Optional) Define Response Group business hours in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02ec9-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="02ec9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<div>

## <a name="defining-business-hours"></a><span data-ttu-id="02ec9-104">営業時間の定義</span><span class="sxs-lookup"><span data-stu-id="02ec9-104">Defining Business Hours</span></span>

<span data-ttu-id="02ec9-105">営業時間設定では、ワークフローが通話に応答できる時間を定義し、営業時間外の通話に対するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="02ec9-105">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="02ec9-106">応答グループ管理者は、**New-CsRgsHoursOfBusiness** コマンドレットを使用して、使用できる応答グループの数に制限がない事前設定スケジュールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="02ec9-106">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="02ec9-107">ワークフローを作成または変更するときに、そのワークフローのみに適用されるカスタム スケジュールを指定できます。</span><span class="sxs-lookup"><span data-stu-id="02ec9-107">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="02ec9-108">詳細については、「 <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Lync server 2013 でハントグループワークフローを作成または変更する</A>」または「 <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">lync server 2013 で対話ワークフローを作成または変更</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02ec9-108">For details, see <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Create or modify a hunt group workflow in Lync Server 2013</A> or <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">Create or modify an interactive workflow in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="02ec9-109">ワークフローが管理ワークフローとして定義されている場合、CsResponseGroupManager の役割を割り当てられているすべてのユーザーは、管理するワークフローのカスタム営業時間を設定および変更できます。</span><span class="sxs-lookup"><span data-stu-id="02ec9-109">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="02ec9-110">次のコマンドレットのパラメーターの時刻表記は、24 時間形式で入力する必要があります (例: 20:00 は午後 8:00 を表します)。</span><span class="sxs-lookup"><span data-stu-id="02ec9-110">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span>



</div>

<div>

## <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="02ec9-111">事前設定された営業時間コレクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="02ec9-111">To create a predefined business hours collection</span></span>

1.  <span data-ttu-id="02ec9-112">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="02ec9-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="02ec9-113">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="02ec9-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="02ec9-114">定義する一意の時間の範囲ごとに、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="02ec9-114">For each unique range of hours you want to define, run:</span></span>
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    <span data-ttu-id="02ec9-115">定義した範囲を使用する営業時間コレクションを作成するには、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="02ec9-115">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    <span data-ttu-id="02ec9-p103">次の例では、平日の営業時間を午前 9:00 から午後 5:00 に、土曜日の営業時間を午前 8:00 から午前 10:00 と午後 2:00 から午後 6:00 に、日曜日は営業時間なしに指定します。</span><span class="sxs-lookup"><span data-stu-id="02ec9-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="02ec9-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="02ec9-123">See Also</span></span>


[<span data-ttu-id="02ec9-124">Lync Server 2013 でハントグループワークフローを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="02ec9-124">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="02ec9-125">Lync Server 2013 での対話ワークフローの作成または変更</span><span class="sxs-lookup"><span data-stu-id="02ec9-125">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="02ec9-126">New-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="02ec9-126">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsTimeRange)  
[<span data-ttu-id="02ec9-127">New-CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="02ec9-127">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoursOfBusiness)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

