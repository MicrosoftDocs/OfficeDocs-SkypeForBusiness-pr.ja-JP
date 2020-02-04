---
title: 'Lync Server 2013: (オプション) 応答グループの休日セットを定義する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group holiday sets
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49733657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e6751a5f5915e73d181efba40976640c65e0909
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-holiday-sets-in-lync-server-2013"></a><span data-ttu-id="33391-102">省略Lync Server 2013 で回答グループの休日セットを定義する</span><span class="sxs-lookup"><span data-stu-id="33391-102">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33391-103">_**最終更新日:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="33391-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="33391-p101">休日設定では、応答グループが営業しない日を定義し、その日に実行するアクションを指定します。休日セットは、応答グループに適用する休日のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="33391-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="33391-106">ワークフローが管理ワークフローとして定義されている場合、CsResponseGroupManager の役割に割り当てられたユーザーは、管理するワークフローの休日を設定および変更できます。</span><span class="sxs-lookup"><span data-stu-id="33391-106">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span>



</div>

<div>

## <a name="to-create-a-holiday-set"></a><span data-ttu-id="33391-107">休日セットを作成するには</span><span class="sxs-lookup"><span data-stu-id="33391-107">To create a holiday set</span></span>

1.  <span data-ttu-id="33391-108">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="33391-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="33391-109">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="33391-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="33391-110">定義する休日ごとに、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="33391-110">For each holiday you want to define, run:</span></span>
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    <span data-ttu-id="33391-111">定義した休日を含める休日セットを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="33391-111">To create the holiday set that contains the holidays you defined, run:</span></span>
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    <span data-ttu-id="33391-112">次の例では、2 つの休日を含む休日セットを示します。</span><span class="sxs-lookup"><span data-stu-id="33391-112">The following example shows a holiday set that includes two holidays:</span></span>
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33391-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="33391-113">See Also</span></span>


[<span data-ttu-id="33391-114">Lync Server 2013 でハントグループワークフローを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="33391-114">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="33391-115">Lync Server 2013 での対話ワークフローの作成または変更</span><span class="sxs-lookup"><span data-stu-id="33391-115">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="33391-116">New-CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="33391-116">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoliday)  
[<span data-ttu-id="33391-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="33391-117">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHolidaySet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

