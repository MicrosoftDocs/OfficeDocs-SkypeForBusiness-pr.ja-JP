---
title: 学生情報システム (SIS) データを Education Insights と同期する
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 学生情報システム (SIS) データを Microsoft Teams の Education Insights と同期します。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6d8e00bb7dd4ff39bae434f13cdb814d9a40fa7
ms.sourcegitcommit: 7e673b88346e07f7c777710437b19d257ccecb1b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2021
ms.locfileid: "50067122"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a><span data-ttu-id="346f7-103">学生情報システム (SIS) データを Education Insights と同期する</span><span class="sxs-lookup"><span data-stu-id="346f7-103">Sync Student Information System (SIS) data with Education Insights</span></span>
<span data-ttu-id="346f7-104">より多くのデータが [Education Insights](class-insights.md) に提供されるほど、教師はより適切に学生をサポートでき、教育リーダーはより適切に教師をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="346f7-104">The more data is fed into [Education Insights](class-insights.md), the better educators can support their students, and education leaders can support the educators.</span></span>

<span data-ttu-id="346f7-105">組織レベルの Insights を提供するには、[学校データ同期 (SDS)](https://docs.microsoft.com/SchoolDataSync) を使用して学生情報システム (SIS) に接続する必要があります。これは、Insights が教育システムの階層構造を正しくマッピングできるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="346f7-105">To provide organization-level Insights, we must use [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) to connect to the Student Information System (SIS) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span> 

<span data-ttu-id="346f7-106">クラスの教師としてクラス レベルの Insights を表示する場合は、*その必要はありません*。これは、Teams のクラス構造とアクセス許可が使用されるためです。</span><span class="sxs-lookup"><span data-stu-id="346f7-106">Viewing class-level Insights as the class educator *does not* require this because we use Teams' class structure and permissions.</span></span>

## <a name="plan-your-sis-integration"></a><span data-ttu-id="346f7-107">SIS の統合を計画する</span><span class="sxs-lookup"><span data-stu-id="346f7-107">Plan your SIS integration</span></span>
<span data-ttu-id="346f7-108">SIS データは、教育システムの階層構造を提供し、どのユーザーがどこに割り当てられているかをマップします。</span><span class="sxs-lookup"><span data-stu-id="346f7-108">The SIS data provides the hierarchical structure of the educational system and maps which user is assigned where.</span></span>

<span data-ttu-id="346f7-109">Insights は [SDS V2 ファイル形式](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format)を使用する場合に最適に機能しますが、機能が *制限* された [SDS V1 ファイル形式](https://docs.microsoft.com/schooldatasync/school-data-sync-format-csv-files-for-sds)もサポートします。</span><span class="sxs-lookup"><span data-stu-id="346f7-109">Insights works best when using [SDS V2 file format](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format) but also supports [SDS V1 file format](https://docs.microsoft.com/schooldatasync/school-data-sync-format-csv-files-for-sds) with *limited* functionality.</span></span>

### <a name="differences-between-sds-v1-and-v2-file-formats"></a><span data-ttu-id="346f7-110">SDS V1 ファイル形式と SDS V2 ファイル形式の違い</span><span class="sxs-lookup"><span data-stu-id="346f7-110">Differences between SDS V1 and V2 file formats</span></span>

| <span data-ttu-id="346f7-111">データの種類</span><span class="sxs-lookup"><span data-stu-id="346f7-111">Data type</span></span> |   <span data-ttu-id="346f7-112">V1</span><span class="sxs-lookup"><span data-stu-id="346f7-112">V1</span></span> | <span data-ttu-id="346f7-113">V2 (新規のお客様におすすめ)</span><span class="sxs-lookup"><span data-stu-id="346f7-113">V2 (recommended for new customers)</span></span> |
|:--- |:--- |:--- |
| <span data-ttu-id="346f7-114">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="346f7-114">**Users**</span></span> | <span data-ttu-id="346f7-115">V1 ファイル形式には、**教師のみ** が含まれます。そのため、教育リーダーに対して組織レベルのアクセス許可を設定するには、該当者を検索し、それぞれのアクセス許可を手動で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="346f7-115">The V1 format contains **only educators**, so to set org-level permissions for your education leaders, you need to search for them and define each one's permission manually.</span></span> | <span data-ttu-id="346f7-116">V2 ファイル形式には **すべての役割** が含まれます。そのため、役割ベースのアクセス許可を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="346f7-116">The V2 format contains **all the roles** so that you can assign role-based permissions.</span></span> |
| <span data-ttu-id="346f7-117">**組織**</span><span class="sxs-lookup"><span data-stu-id="346f7-117">**Orgs**</span></span> | <span data-ttu-id="346f7-118">V1 ファイル形式には、**学校のみ** が含まれます。したがって、1 つの集計レベル (すべての学校) のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="346f7-118">The V1 format contains **only schools**, so you see only one aggregation level (all your schools).</span></span> <span data-ttu-id="346f7-119">単純なリストを使用して特定の学校にズームインできますが、このリストには多数の学校が含まれている場合や、比較が難しいさまざまな種類の学校 (小学校から中学校、科学系から芸術系の学校など) が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="346f7-119">You can zoom in to a specific school using a flat list, but this list may have a large number of schools or contain different types of schools that are hard to compare (such as primary to secondary school or science to art school).</span></span><br/><br/> <span data-ttu-id="346f7-120">階層が設定されている場合は、科学系や芸術系の学部など、意味のあるレベルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="346f7-120">When there is a hierarchy in place, you can create levels that make sense, such as a science or art department.</span></span>| <span data-ttu-id="346f7-121">V2 ファイル形式には、総合大学、単科大学、学部、キャンパス、地域、プログラムなどを含む、**学区または教育機関の完全な階層** が含まれています。</span><span class="sxs-lookup"><span data-stu-id="346f7-121">The V2 format contains **the full hierarchy of your district or institution**, including universities, colleges, faculties, campuses, regions, programs and so on.</span></span><br/><br/> <span data-ttu-id="346f7-122">階層を使用すると、階層のレベルごとに関連する集計を確認したり、各レベルの組織単位をすばやく比較したり、特定のレベルに権限を割り当てたり、組織レベルごとに目標を設定したりできます。</span><span class="sxs-lookup"><span data-stu-id="346f7-122">With a hierarchy, you can see relevant aggregation by each level of the hierarchy, quickly compare between organizational units at each level, assign permission to specific levels, set goals by org level, and so on.</span></span>|

### <a name="type-of-data-required"></a><span data-ttu-id="346f7-123">必要なデータの種類</span><span class="sxs-lookup"><span data-stu-id="346f7-123">Type of data required</span></span>
<span data-ttu-id="346f7-124">次の表は、Insights を最大限に活用するために必要なデータの種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="346f7-124">The following table provides the type of data required to get the best out of Insights.</span></span>

| <span data-ttu-id="346f7-125">データの種類</span><span class="sxs-lookup"><span data-stu-id="346f7-125">Data type</span></span> | <span data-ttu-id="346f7-126">入力するデータの例</span><span class="sxs-lookup"><span data-stu-id="346f7-126">Examples for what you need to provide</span></span>|<span data-ttu-id="346f7-127">重要な理由</span><span class="sxs-lookup"><span data-stu-id="346f7-127">Why it's important?</span></span>|
|:--- |:--- |:--- |
| <span data-ttu-id="346f7-128">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="346f7-128">**Users**</span></span> |   <span data-ttu-id="346f7-129">役割 (学生など)</span><span class="sxs-lookup"><span data-stu-id="346f7-129">Role (such as student)</span></span><br/> <span data-ttu-id="346f7-130">学年 (10 など)</span><span class="sxs-lookup"><span data-stu-id="346f7-130">Grade/Year level (such as 10)</span></span><br/> <span data-ttu-id="346f7-131">組織 (名前)</span><span class="sxs-lookup"><span data-stu-id="346f7-131">Org (name)</span></span> | <span data-ttu-id="346f7-132">各ユーザーがそれぞれの役割、学年、および組織に正しく割り当てられていれば、要約と集計に間違いが生じません。</span><span class="sxs-lookup"><span data-stu-id="346f7-132">When we correctly assign each person to their role, grade/year level, and organization, we can ensure that the summaries and aggregations are correct.</span></span>|
| <span data-ttu-id="346f7-133">**組織**</span><span class="sxs-lookup"><span data-stu-id="346f7-133">**Orgs**</span></span> | <span data-ttu-id="346f7-134">組織の種類 (単科大学など)</span><span class="sxs-lookup"><span data-stu-id="346f7-134">Org type (such as college)</span></span> |   <span data-ttu-id="346f7-135">ここでは階層が重要です。</span><span class="sxs-lookup"><span data-stu-id="346f7-135">The hierarchy here is important.</span></span> <span data-ttu-id="346f7-136">たとえば、学校がある地区に属し、その地区がある都道府県に属している場合があります。</span><span class="sxs-lookup"><span data-stu-id="346f7-136">For example, schools may belong to a district, and that district may belong to a state.</span></span><br/> <span data-ttu-id="346f7-137">ある地区の教育リーダーがデータの表示を許可されている場合、その地区の学校のみが対象となります。</span><span class="sxs-lookup"><span data-stu-id="346f7-137">When a district education leader is permitted to see data, it's only for the schools in that district.</span></span>|
| <span data-ttu-id="346f7-138">**クラス**</span><span class="sxs-lookup"><span data-stu-id="346f7-138">**Classes**</span></span> | <span data-ttu-id="346f7-139">タイトル (コンピューター サイエンス 101 など)</span><span class="sxs-lookup"><span data-stu-id="346f7-139">Title (such as Computer science 101)</span></span> | <span data-ttu-id="346f7-140">組織内で開講されているクラスの詳細です。</span><span class="sxs-lookup"><span data-stu-id="346f7-140">This details which classes are held in the organization.</span></span> <span data-ttu-id="346f7-141">学生を適切なクラスに割り当てることができるように、正しくマッピングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="346f7-141">This must be correctly mapped so that we can assign the student to the correct class.</span></span> |
| <span data-ttu-id="346f7-142">**登録**</span><span class="sxs-lookup"><span data-stu-id="346f7-142">**Enrollment**</span></span> | <span data-ttu-id="346f7-143">役割 (学生など)</span><span class="sxs-lookup"><span data-stu-id="346f7-143">Role (such as student)</span></span> | <span data-ttu-id="346f7-144">これは学生と教師向けのデータです。学生や教師がどのクラスに登録されているのかを知ることができます。</span><span class="sxs-lookup"><span data-stu-id="346f7-144">This is for students and educators and enables us to know in which class they are registered.</span></span> |

> [!NOTE]
> <span data-ttu-id="346f7-145">展開プロセス中に、Teams のユーザーとクラスのプロビジョニングに SDS を使用するか、Insights にデータを提供するためだけに SDS を使用するかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="346f7-145">During the deployment process, you can decide if you want to use SDS for provisioning users and classes in Teams or to use it only to provide data to Insights.</span></span>

## <a name="best-practices"></a><span data-ttu-id="346f7-146">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="346f7-146">Best practices</span></span>
<span data-ttu-id="346f7-147">階層と、その階層内の全員が属する場所を正確にマッピングすることにより、Insights は、さまざまな種類の教育リーダーに対して、正確なデータと、より詳細かつ重要な分析情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="346f7-147">The accurate mapping of the hierarchy and where everyone belongs within that hierarchy enables Insights to provide accurate data and more precise and relevant insights for the different types of education leaders.</span></span>

<span data-ttu-id="346f7-148">ここで入力するデータがより詳細であるほど、レポートとスポットライトの有用性と重要性が高まります。</span><span class="sxs-lookup"><span data-stu-id="346f7-148">The more detail you provide here, the better and more relevant the reports and spotlights will be.</span></span>
<span data-ttu-id="346f7-149">ユーザーが Insights を最大限に活用できるように、SDS のスムーズな展開を確実にするためのいくつかのベスト プラクティスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="346f7-149">Here are some best practices based to ensure the smooth deployment of SDS so that your users can make the most out of Insights.</span></span>

### <a name="users"></a><span data-ttu-id="346f7-150">ユーザー</span><span class="sxs-lookup"><span data-stu-id="346f7-150">Users</span></span>
*   <span data-ttu-id="346f7-151">提供するファイルに *すべてのユーザー* がリストされ、同期済みであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="346f7-151">Make sure *all users* are listed in the files you provide and synced.</span></span> <span data-ttu-id="346f7-152">これには、対象となる組織単位のデータを確認する必要があるすべての学生とスタッフが含まれます。</span><span class="sxs-lookup"><span data-stu-id="346f7-152">This includes all students and staff that need to see data for the organizational units they cover.</span></span>

    <span data-ttu-id="346f7-153">現在 SIS に教師のみがリストされている場合は、ファイルを SIS にアップロードしてデータを同期する前に、他のユーザーを手動で追加してください。</span><span class="sxs-lookup"><span data-stu-id="346f7-153">If you currently only have educators listed in the SIS, add the other users manually before uploading the files to SIS and syncing the data.</span></span>

    <span data-ttu-id="346f7-154">一部の学生が含まれていない場合、Insights によって収集された統計は登録された学生のみのものであり、データと結論は誤解を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="346f7-154">If some students are missing, the stats gathered by Insights is only from the registered students, and that will make the data and conclusions misleading.</span></span>
    
*   <span data-ttu-id="346f7-155">必ず *各ユーザーの姓と名を入力* してください。</span><span class="sxs-lookup"><span data-stu-id="346f7-155">Make sure to *provide the first and last name of each user*.</span></span> <span data-ttu-id="346f7-156">入力しない場合、ユーザーはメール アドレスによって参照されます。これはレポートとスポットライト (学生のアクティビティやパフォーマンスに関する分析情報を含むカード) において、実用的なエクスペリエンスとは言えません。</span><span class="sxs-lookup"><span data-stu-id="346f7-156">If not, they are referenced by their email address, and this provides a less than positive experience in the reports and spotlights (cards with Insights on student activity or performance).</span></span>

*   <span data-ttu-id="346f7-157">*学年は 2 桁で入力する必要があります* (たとえば、学年が 7 の場合は「07」と入力します)。</span><span class="sxs-lookup"><span data-stu-id="346f7-157">The *grade/year level must be input as 2 digits* (for example, 07 for Year 7).</span></span> <span data-ttu-id="346f7-158">詳しくは、[マッピング リスト](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="346f7-158">Check out the [mapping list](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported).</span></span> 

*   <span data-ttu-id="346f7-159">学年でデータをフィルタ処理できるように、*すべての学生に学年を追加する* ことが重要です。</span><span class="sxs-lookup"><span data-stu-id="346f7-159">It's important to *add the year/grade level to all students* so that a grade/year level can filter the data.</span></span>    

*   <span data-ttu-id="346f7-160">*各ユーザーを関連する組織単位に割り当ててください*。</span><span class="sxs-lookup"><span data-stu-id="346f7-160">Make sure to *assign each user to their relevant organizational unit*.</span></span> <span data-ttu-id="346f7-161">これにより、各組織単位の集計データに基づくスポットライトに誤解を招くデータが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="346f7-161">In this way, we won't show misleading data in our spotlights based on aggregated data for each unit.</span></span>

    *   <span data-ttu-id="346f7-162">学生は、複数の組織単位に関連付けることができます。たとえば、特別なプログラムや 2 つの学部に登録されている学生などです。</span><span class="sxs-lookup"><span data-stu-id="346f7-162">A student can be associated with more than one org unit, for example, students who are registered in a special program or two faculties.</span></span> <span data-ttu-id="346f7-163">このような場合、その学生のユーザー ファイルでは 2 行 (組織ごとに 1 行) に入力します。</span><span class="sxs-lookup"><span data-stu-id="346f7-163">In such a case, provide two lines in the users file for that student – one for each organization.</span></span>
    
    *   <span data-ttu-id="346f7-164">スタッフの組織単位に基づいて、関連するアクセス許可を定義できます。</span><span class="sxs-lookup"><span data-stu-id="346f7-164">Based on the org unit for staff, you will be able to define the relevant permissions.</span></span> <span data-ttu-id="346f7-165">必要なアクセス許可が与えられるように、スタッフが適切な組織単位レベルに関連付けられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="346f7-165">Make sure they are associated with the correct unit level, so they receive the permissions they need.</span></span> <span data-ttu-id="346f7-166">たとえば、4 つの学校に割り当てられているカウンセラーは、それらの学校のすべてのクラスを表示する必要があります。校長は自分の学校のすべてのクラスを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="346f7-166">For example, a counselor assigned to four schools needs to see all the classes in these schools; a principal needs to see all the classes in their school.</span></span> 
    
*   <span data-ttu-id="346f7-167">役割はきわめて重要です。</span><span class="sxs-lookup"><span data-stu-id="346f7-167">The role is vital.</span></span> <span data-ttu-id="346f7-168">これはクローズド リストですが、[このリスト](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)の役割と、アップロードする各ユーザーの実際の役割を一致させるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="346f7-168">Although this is a closed list, try to match the role from [the list](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) to the real role of each user you upload.</span></span> <span data-ttu-id="346f7-169">それにより、役割ベースのアクセス許可を適切に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="346f7-169">In this way, you can assign role-based permissions accordingly.</span></span> <span data-ttu-id="346f7-170">たとえば、すべての校長に対して自分の学校のクラスを表示するアクセス許可を、またはすべての教授に対して自分の学部を表示するアクセス許可を与えます。</span><span class="sxs-lookup"><span data-stu-id="346f7-170">For example, provide permissions for all principals to see the classes in their school, or for all professors to see their faculty.</span></span> 

### <a name="organizations"></a><span data-ttu-id="346f7-171">組織</span><span class="sxs-lookup"><span data-stu-id="346f7-171">Organizations</span></span>

* <span data-ttu-id="346f7-172">*自分の組織の実際の階層を反映するようにしてください*。</span><span class="sxs-lookup"><span data-stu-id="346f7-172">Make sure to *reflect the real hierarchy of your organization*.</span></span> <span data-ttu-id="346f7-173">これは、ファイルを手動で追加することで実現できます。</span><span class="sxs-lookup"><span data-stu-id="346f7-173">This can be achieved by manually adding the file.</span></span> <span data-ttu-id="346f7-174">この階層は SIS に反映されないこともあります。</span><span class="sxs-lookup"><span data-stu-id="346f7-174">In some cases, this hierarchy is not reflected in the SIS.</span></span> <span data-ttu-id="346f7-175">その場合でも、階層のレベルごとに関連する集計を確認したり、特定のレベルにアクセス許可を割り当てたり、組織レベルで目標を設定したりする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="346f7-175">Still, it may be necessary here to see the relevant aggregation by each level of the hierarchy, assign permission to specific levels, set goals by org level, and so on.</span></span> 

* <span data-ttu-id="346f7-176">*組織ツリーの下位にあるすべての組織単位に、学生またはクラスが含まれている* ことを確認して、組織の学生データを集計します。</span><span class="sxs-lookup"><span data-stu-id="346f7-176">Ensure that *all org units down the org tree include students or classes* to aggregate student data for them.</span></span> <span data-ttu-id="346f7-177">学生がツリーの末端の枝に含まれるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="346f7-177">We recommend that students are on the lowest branch of the tree.</span></span>

> [!NOTE]
> <span data-ttu-id="346f7-178">SDS 展開の詳細については、「[SDS の計画](https://docs.microsoft.com/schooldatasync/planning-school-data-sync)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="346f7-178">For more details about SDS deployment, visit [Planning SDS](https://docs.microsoft.com/schooldatasync/planning-school-data-sync).</span></span>

## <a name="integrate-sis-using-sds"></a><span data-ttu-id="346f7-179">SDS を使用して SIS を統合する</span><span class="sxs-lookup"><span data-stu-id="346f7-179">Integrate SIS using SDS</span></span>

<span data-ttu-id="346f7-180">学校データ同期 (SDS) は Office 365 for Education で提供されます。</span><span class="sxs-lookup"><span data-stu-id="346f7-180">School Data Sync (SDS) is provided with Office 365 for Education.</span></span> <span data-ttu-id="346f7-181">SDS は、教育機関の学生情報システム (SIS) からデータを読み取り、それを Teams と統合して、オンライン教室とユーザーの自動作成を可能にします。</span><span class="sxs-lookup"><span data-stu-id="346f7-181">SDS reads the data from an educational institution's Student Information System (SIS) and integrates it with Teams to enable the automatic creation of online classrooms and users.</span></span>

<span data-ttu-id="346f7-182">また、SIS データを Insights と同期します。</span><span class="sxs-lookup"><span data-stu-id="346f7-182">It also synchronizes the SIS data with Insights.</span></span>

### <a name="sync-with-insights"></a><span data-ttu-id="346f7-183">Insights と同期する</span><span class="sxs-lookup"><span data-stu-id="346f7-183">Sync with Insights</span></span>

<span data-ttu-id="346f7-184">まず、同期プロセスを開始するには、Insights トグルをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="346f7-184">First, you need to turn the Insights toggle on to start the sync process.</span></span>

* <span data-ttu-id="346f7-185">[**SDS ポータル**](https://sds.microsoft.com)で **[設定]** に移動し、下にスクロールして **[Collect data for Insights]** (Insights 用のデータを収集する) が有効になっていることを確認します (既定では *オン* になっています)。</span><span class="sxs-lookup"><span data-stu-id="346f7-185">On the [**SDS portal**](https://sds.microsoft.com), go to **Settings**, scroll down to **Collect data for Insights** and check that it's enabled (it's turned *on* by default).</span></span>

* <span data-ttu-id="346f7-186">下にスクロールして、次のスイッチ **[Sync organizational data from SDS (preview)]** (SDS の組織データを同期する (プレビュー)) をオンにします。</span><span class="sxs-lookup"><span data-stu-id="346f7-186">Scroll down to the next switch, **Sync organizational data from SDS (preview)**, and turn on.</span></span>

<span data-ttu-id="346f7-187">[設定] ページに *[Sync organizational data from SDS (preview)]* オプションが表示されない場合は、[サインアップ ページ](https://aka.ms/insights/join) に移動して自分の情報を入力すると、チーム メンバーから連絡があります。</span><span class="sxs-lookup"><span data-stu-id="346f7-187">If you do not see the option for *Sync organizational data from SDS (preview)* on the Settings page, go to the [sign-up page](https://aka.ms/insights/join) to provide your information, and a team member will reach out to you.</span></span>

:::image type="content" source="media/insights-sds-settings.png" alt-text="Insights との同期トグル":::

### <a name="deploy-sds"></a><span data-ttu-id="346f7-189">SDS を展開する</span><span class="sxs-lookup"><span data-stu-id="346f7-189">Deploy SDS</span></span>
<span data-ttu-id="346f7-190">**すでに SDS を使用している場合は**、「[ベスト プラクティス](#best-practices)」に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="346f7-190">**If you already use SDS**, we recommend you follow our [best practices](#best-practices).</span></span> 

<span data-ttu-id="346f7-191">現在のプロファイルを Insights と同期するには、**同期プロファイル** に移動し、**[編集]** をクリックして **[Insights に同期]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="346f7-191">To sync your current profiles with Insights, go to your **Sync Profile(s)**, click **Edit**, and select **Sync to Insights**.</span></span> <span data-ttu-id="346f7-192">初回の同期においては、SIS からデータが更新された後にレポートを利用できるようにするために、24 時間待機することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="346f7-192">For the initial sync, we recommend waiting 24 hours for the reports to be available after the data is refreshed from your SIS.</span></span>  

:::image type="content" source="media/insights-sds-profile-sync.png" alt-text="プロファイルを Insights トグルと同期する":::

<span data-ttu-id="346f7-194">**SDS を使用していない場合は**、[SDS を展開する](https://docs.microsoft.com/schooldatasync/deploying-school-data-sync)必要があります。</span><span class="sxs-lookup"><span data-stu-id="346f7-194">**If you don't use SDS yet**, you now need to [deploy it](https://docs.microsoft.com/schooldatasync/deploying-school-data-sync).</span></span>

<span data-ttu-id="346f7-195">展開プロセス中に、Teams のユーザーとクラスのプロビジョニングに SDS を使用するか、Insights にデータを提供するためだけに SDS を使用するかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="346f7-195">During the deployment process, you can decide if you want to use SDS for provisioning users and classes in Teams or to use it only to provide data to Insights.</span></span>

> [!NOTE]
> <span data-ttu-id="346f7-196">年央で、すでに手動でチームを作成している場合は、Insights にデータを提供するためだけに SDS を使用するとしておき、来年は Teams のユーザーとクラスのプロビジョニングにも SDS を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="346f7-196">If it's the middle of the year and you already created teams manually, use SDS only to provide the data to Insights, and next year consider to use SDS for provisioning users and classes in Teams as well.</span></span>

### <a name="verify-the-sync-process"></a><span data-ttu-id="346f7-197">同期プロセスを確認する</span><span class="sxs-lookup"><span data-stu-id="346f7-197">Verify the sync process</span></span>
<span data-ttu-id="346f7-198">[設定] ページの [SDS から組織データを同期する (プレビュー)] の横に新しい [状態] 領域が表示されます。</span><span class="sxs-lookup"><span data-stu-id="346f7-198">A new status area appears next to Sync organizational data from SDS (preview) on the Settings page.</span></span>
 
*   <span data-ttu-id="346f7-199">状態が "**処理中**" の場合は、SDS プロファイルの展開後、最大で 24 時間お待ちください。</span><span class="sxs-lookup"><span data-stu-id="346f7-199">If the status is **In progress**, please wait up to 24 hours after deployment of the SDS profile.</span></span>

*   <span data-ttu-id="346f7-200">状態が "**完了**" の場合は、組織レベルで Insights を表示することができ、次のステップに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="346f7-200">If the status is **Completed**, congratulations, you can see Insights at the organizational level, and continue to the next step.</span></span>

*   <span data-ttu-id="346f7-201">状態が "**完了 (エラーあり)**"、"**完了 (警告あり)**"、または "**中止**" の場合は、最新の同期のエラーと警告を含むログ ファイルをダウンロードし、それらのエラーを修正できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="346f7-201">If the status is **Completed with errors**, **Completed with warnings**, or **Aborted**, download the log file that contains the errors and warnings for the latest sync and check if you can fix these errors.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="346f7-202">問題が発生した場合は、[カスタマー サポート](https://aka.ms/edusupport)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="346f7-202">If you run into any problems, [customer support](https://aka.ms/edusupport) is there to help you.</span></span>
