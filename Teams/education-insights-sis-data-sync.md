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
ms.openlocfilehash: 5d5ba5c2c5179d5c333472450fd9b2e9c270a4e9
ms.sourcegitcommit: 7579dda8018691eb1a724cb0311b53333dc3ae5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "53142843"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a><span data-ttu-id="ef2eb-103">学生情報システム (SIS) データを Education Insights と同期する</span><span class="sxs-lookup"><span data-stu-id="ef2eb-103">Sync Student Information System (SIS) data with Education Insights</span></span>
<span data-ttu-id="ef2eb-104">より多くのデータが [Education Insights](class-insights.md) に提供されるほど、教師はより適切に学生をサポートでき、教育リーダーはより適切に教師をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-104">The more data is fed into [Education Insights](class-insights.md), the better educators can support their students, and education leaders can support the educators.</span></span>

<span data-ttu-id="ef2eb-105">組織レベルの Insights を提供するには、[学校データ同期 (SDS)](/SchoolDataSync) を使用して学生情報システム (SIS) に接続する必要があります。これは、Insights が教育システムの階層構造を正しくマッピングできるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-105">To provide organization-level Insights, we must use [School Data Sync (SDS)](/SchoolDataSync) to connect to the Student Information System (SIS) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span> 

<span data-ttu-id="ef2eb-106">クラスの教師としてクラス レベルの Insights を表示する場合は、この同期は *必要ありません*。これは、Teams のクラス構造とアクセス許可が使用されるためです。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-106">Viewing class-level Insights as the class educator *does not* require this sync because we use Teams' class structure and permissions.</span></span>

## <a name="plan-your-school-data-sync-integration"></a><span data-ttu-id="ef2eb-107">School Data Sync の統合を計画する</span><span class="sxs-lookup"><span data-stu-id="ef2eb-107">Plan your School Data Sync integration</span></span>
<span data-ttu-id="ef2eb-108">Microsoft School Data Sync (a.k.a SDS) は、学生情報システム (a.k.a SIS) のデータと教育システムの階層構造を提供し、どのユーザーがどこに割り当てられているかをマッピングするとともに、学生や組織の階層に関する追加データを提供します。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-108">The Microsoft School Data Sync (a.k.a SDS) provides the School Information System (a.k.a SIS) data and it’s hierarchical structure of the educational system and maps which user is assigned where, as well as provides additional data on the student and organizational hierarchy.</span></span>

<span data-ttu-id="ef2eb-109">Insights は [SDS V2.1.ファイル形式](/schooldatasync/sds-v2.1-csv-file-format)以上を使用する場合にベストに機能しますが、機能が制限された [SDS V2 ファイル形式](/schooldatasync/sds-v2-csv-file-format) および  [SDS V1 ファイル形式](/schooldatasync/school-data-sync-format-csv-files-for-sds) *もサポートします*。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-109">Insights works best when using [SDS V2.1 file format](/schooldatasync/sds-v2.1-csv-file-format) but also supports [SDS V2 file format](/schooldatasync/sds-v2-csv-file-format) and  [SDS V1 file format](/schooldatasync/school-data-sync-format-csv-files-for-sds) *with limited functionality*.</span></span>


### <a name="differences-between-sds-v1-and-v2-file-formats"></a><span data-ttu-id="ef2eb-110">SDS V1 ファイル形式と SDS V2 ファイル形式の違い</span><span class="sxs-lookup"><span data-stu-id="ef2eb-110">Differences between SDS V1 and V2 file formats</span></span>

| <span data-ttu-id="ef2eb-111">データの種類</span><span class="sxs-lookup"><span data-stu-id="ef2eb-111">Data type</span></span> | <span data-ttu-id="ef2eb-112">V1</span><span class="sxs-lookup"><span data-stu-id="ef2eb-112">V1</span></span> | <span data-ttu-id="ef2eb-113">V2 および V2.1</span><span class="sxs-lookup"><span data-stu-id="ef2eb-113">V2 and V2.1</span></span> |
|:--- |:--- |:--- |
| <span data-ttu-id="ef2eb-114">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="ef2eb-114">**Users**</span></span> |<span data-ttu-id="ef2eb-115">"教師" ロールのみをサポートするため、教育リーダーの組織レベルのアクセス許可を手動で設定する必要があります</span><span class="sxs-lookup"><span data-stu-id="ef2eb-115">Supports only ‘educator’ role, as a result org-level permissions for your education leaders need to be set manually</span></span>|<span data-ttu-id="ef2eb-116">ロールベースのアクセス許可を設定できるように、複数のロールをサポートします</span><span class="sxs-lookup"><span data-stu-id="ef2eb-116">Supports multiple roles so that role-based permissions can be set</span></span>|
| <span data-ttu-id="ef2eb-117">**組織**</span><span class="sxs-lookup"><span data-stu-id="ef2eb-117">**Orgs**</span></span> | <span data-ttu-id="ef2eb-118">'schools'、集計レベルのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-118">Supports only ‘schools’, aggregation level.</span></span><br><br><span data-ttu-id="ef2eb-119">その結果、複数の集計レベルが提供されず、異なる種類の学校 (小学校と中学校、サイエンス スクール、アート スクールなど) を比較する機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-119">As a result, does not provide multiple aggregation levels and provide limited ability to compare different types of schools (e.g primary vs. secondary school, science vs. art school)</span></span>|<span data-ttu-id="ef2eb-120">学区/機関、大学、カレッジ、学部、キャンパス、地域、プログラムなどの多層階層をサポートします。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-120">Supports multi-layer hierarchy, including district/institution, universities, colleges, faculties, campuses, regions, programs, etc.</span></span><br><br><span data-ttu-id="ef2eb-121">複数の集計レベルを使用でき、各レベルの組織単位間の比較、特定のレベルへのアクセス許可の割り当て、組織レベル別の目標の設定などを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-121">Allows for multiple aggregation levels and to easily compare between organizational units at each level, assign permissions to specific levels, set goals by org level, etc.</span></span>|
| <span data-ttu-id="ef2eb-122">**追加のオプション情報**</span><span class="sxs-lookup"><span data-stu-id="ef2eb-122">**Additional optional information**</span></span> |<span data-ttu-id="ef2eb-123">なし</span><span class="sxs-lookup"><span data-stu-id="ef2eb-123">None</span></span>|<span data-ttu-id="ef2eb-124">**V2.1 ファイル形式のみ**</span><span class="sxs-lookup"><span data-stu-id="ef2eb-124">**V2.1 file format only**</span></span><br><br><span data-ttu-id="ef2eb-125">*学期* - セッションの時間枠 (半期、学年など)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-125">*Academic Sessions* - timeframes of sessions (semesters, school years etc.)</span></span><br><br><span data-ttu-id="ef2eb-126">人口統計と学生のフラグ\* - 人種、民族、性別などのデータだけでなく、特別なプログラム (IEP、504)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-126">Demographics and student flags\* - data like race, ethnicity, and gender, as well as special programs (IEP, 504)</span></span>|

> [!NOTE]
> <span data-ttu-id="ef2eb-127">2021 年 7 月 15 日以降、ファイル形式 v2 をオンボードすることができなくなり、代わりに v2.1 形式を使用する必要があります。今後のアップグレードや新しい機能はすべて v2.1 形式で行われ、ファイル形式 v1 との完全な下位互換性があります。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-127">Customers will not be able on onboard file format v2 starting July 15th 2021, and will need to use the v2.1 format instead, all future upgrades and new capabilitie will be done on the v2.1 format and it will be fully backward compatible to file format v1.</span></span>

### <a name="best-practices"></a><span data-ttu-id="ef2eb-128">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="ef2eb-128">Best practices</span></span>

<span data-ttu-id="ef2eb-129">階層と、その階層内の全員が属する場所を正確にマッピングすることにより、Insights は、さまざまな種類の教育リーダーに対して、正確なデータと、より詳細かつ重要な分析情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-129">The accurate mapping of the hierarchy and where everyone belongs within that hierarchy, enables Insights to provide accurate data and more precise and relevant insights for the different types of education leaders.</span></span>

<span data-ttu-id="ef2eb-130">入力するデータがより詳細であるほど、レポートとスポットライトの有用性と重要性が高まります。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-130">The more detail you provide, the better and more relevant the reports and spotlights will be.</span></span>

#### <a name="file-format-version-to-use-adn-data-to-sync"></a><span data-ttu-id="ef2eb-131">使用するファイル形式のバージョンと同期するデータ</span><span class="sxs-lookup"><span data-stu-id="ef2eb-131">File format version to use adn data to sync</span></span>
*   <span data-ttu-id="ef2eb-132">ファイル形式 V2.1 を使用し、[ここ](/schooldatasync/sds-for-insights-overview#education-insights-capabilities-matrix-and-sds-v21-csv)に記載してある Education Insights が使用するオプションデータを同期します。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-132">Use file format V2.1 and sync the optional data used by Education Insights as described [here](/schooldatasync/sds-for-insights-overview#education-insights-capabilities-matrix-and-sds-v21-csv).</span></span>

#### <a name="users-and-roles"></a><span data-ttu-id="ef2eb-133">ユーザーおよび役割</span><span class="sxs-lookup"><span data-stu-id="ef2eb-133">Users and Roles</span></span>
*   <span data-ttu-id="ef2eb-134">提供するファイルに **すべてのユーザー** がリストされ、同期済みであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-134">Make sure **all users are listed in the files** you provide and synced.</span></span> <span data-ttu-id="ef2eb-135">これには、対象となる組織単位のデータを確認する必要があるすべての学生とスタッフが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-135">This includes all students and staff that need to see data for the organizational units they cover.</span></span>
*   <span data-ttu-id="ef2eb-136">現在 SIS に教師のみがリストされている場合は、ファイルを SDS にアップロードしてデータを同期する前に、他のユーザーを手動で追加してください。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-136">If you currently only have educators listed in your SIS, add all other users manually before uploading the files to SDS and syncing the data.</span></span> <span data-ttu-id="ef2eb-137">Insights によって収集された統計は登録された学生のみからであり、一部の学生が含まれず、データと結論は誤解を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-137">The stats gathered by Insights will onlybe  from the registered students, if some students are missing, that will make the data and conclusions misleading.</span></span>
    
*   <span data-ttu-id="ef2eb-138">プロビジョニングにも SDS を使用する場合は、**各ユーザーの姓と名を提供** してください。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-138">If you use SDS for provisioning as well, make sure to **provide the first and last name of each user**.</span></span> <span data-ttu-id="ef2eb-139">それ以外の場合、学生は自分のメール アドレスで参照されるため、最適ではないエクスペリエンスが得られます。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-139">Otherwise, students will be referenced by their email address, resulting in a non-optimal experience.</span></span>

*   <span data-ttu-id="ef2eb-140">級/学年は、この[マッピング リスト](#supported-grade-level-values)に基づいている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-140">The grade/year level must be based on this [mapping list](#supported-grade-level-values).</span></span> 

*   <span data-ttu-id="ef2eb-141">確実に **すべての学生に級/学年レベルを追加** してください。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-141">Make sure to **add the year/grade level to all students** .</span></span>    

*   <span data-ttu-id="ef2eb-142">確実に **各ユーザーを関連する組織単位に割り当ててください**。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-142">Make sure to **assign each user to their relevant organizational unit**.</span></span>

    *   <span data-ttu-id="ef2eb-143">学生は、複数の組織単位に関連付けることができます。たとえば、特別なプログラムや 2 つの学部に登録されている学生などです。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-143">A student can be associated to more than one organizational unit, for example, students who are registered in a special program or two faculties.</span></span> <span data-ttu-id="ef2eb-144">学生が複数の組織単位を持っている場合は、その学生のユーザー　ファイルにそれぞれの行を指定します。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-144">In case the student has more then one organizational unit, provide a line for each in the users file for that student.</span></span>
    
    *   <span data-ttu-id="ef2eb-145">IT 管理者は、スタッフの組織単位に基づいてアクセス許可を付与することができます。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-145">IT admin can grant permissions based on organizational unit for staff.</span></span> <span data-ttu-id="ef2eb-146">必要なアクセス許可が与えられるように、**スタッフ メンバーが適切な組織単位レベルに関連付けられていることを確認してください**。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-146">**Make sure staff members are associated with the correct unit level**, so they receive the permissions they need.</span></span> <span data-ttu-id="ef2eb-147">たとえば、4 つの学校に割り当てられているカウンセラーは、それらの学校のすべての学年を表示する必要があります。校長は自分の学校のすべてのクラスを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-147">For example, a counselor assigned to four schools needs to see all the grades in those schools; a principal needs to see all the classes in their school.</span></span> 
    
*   <span data-ttu-id="ef2eb-148">**役割はきわめて重要です**。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-148">**The role is vital**.</span></span> <span data-ttu-id="ef2eb-149">このリストは閉じられていますが、[こちらのリスト](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)の役割と、アップロードする各ユーザーの実際の役割を一致させるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-149">Although this list is closed, try to match the role from [the list](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) to the real role of each user you upload.</span></span> <span data-ttu-id="ef2eb-150">これにより、役割ベースのアクセス許可を適切に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-150">This will enable you to assign role-based permissions accordingly.</span></span> <span data-ttu-id="ef2eb-151">たとえば、すべての校長に対して自分の学校のクラスを表示するアクセス許可を、またはすべての教授に対して自分の学部を表示するアクセス許可を与えます。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-151">For example, provide permissions for all principals to see the classes in their school, or for all professors to see their faculty.</span></span> 

#### <a name="organizations"></a><span data-ttu-id="ef2eb-152">組織</span><span class="sxs-lookup"><span data-stu-id="ef2eb-152">Organizations</span></span>

* <span data-ttu-id="ef2eb-153">**自分の組織の実際の完全な階層を反映するようにしてください**。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-153">Make sure to **reflect the real and full hierarchy of your organization**.</span></span> <span data-ttu-id="ef2eb-154">場合によっては、この階層は SIS に反映されません。その場合は、CSV ファイルの同期前に手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-154">In some cases, this hierarchy is not reflected in the SIS, in which case it needs to be added manually to the CSV file efore syncing.</span></span>

* <span data-ttu-id="ef2eb-155">**組織ツリーの下にあるすべての組織単位に、学生またはクラスが含まれている** ことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-155">Make sure that **all organization units down the organization tree include students or classes**.</span></span> <span data-ttu-id="ef2eb-156">学生がツリーの末端の枝に含まれるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-156">We recommend that students are on the lowest branch of the tree.</span></span>

> [!NOTE]
> <span data-ttu-id="ef2eb-157">SDS 展開の詳細については、「[SDS の計画](/schooldatasync/planning-school-data-sync)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-157">For more details about SDS deployment, visit [Planning SDS](/schooldatasync/planning-school-data-sync).</span></span>

## <a name="integrate-sis-data-using-sds"></a><span data-ttu-id="ef2eb-158">SDS を使用して SIS データを統合する</span><span class="sxs-lookup"><span data-stu-id="ef2eb-158">Integrate SIS data using SDS</span></span>

<span data-ttu-id="ef2eb-p109">School Data Sync (SDS) には、Office 365 for Education が提供されており、教育機関の学生情報システム (SIS) からデータを読み取り、それを Teams などの Microsoft アプリケーションと統合して、オンライン教室とユーザーの自動作成を可能にします。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-p109">School Data Sync (SDS) is provided with Office 365 for Education. SDS reads the data from an educational institution's Student Information System (SIS) and integrates it with Microsoft applications like Teams to enable the automatic creation of online classrooms and users.</span></span>

<span data-ttu-id="ef2eb-161">また、SIS データを Insights と同期します。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-161">It also synchronizes the SIS data with Insights.</span></span>

<span data-ttu-id="ef2eb-162">IT 管理者としては、SDS をプロビジョニングのみ、Insights のみ、またはその両方に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-162">As an IT Admin, you can choose to use SDS for provisioning only, Insights only or for both.</span></span>

<span data-ttu-id="ef2eb-163">SIS の情報を Educations Insights と同期するには、[Insights 用 SDS の展開方法](/schooldatasync/how-to-deploy-sds-for-insights)の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-163">To Sync your SIS information with Educations Insights follow the instructions in [How to deploy SDS for Insights](/schooldatasync/how-to-deploy-sds-for-insights).</span></span>

### <a name="deploy-sds"></a><span data-ttu-id="ef2eb-164">SDS を展開する</span><span class="sxs-lookup"><span data-stu-id="ef2eb-164">Deploy SDS</span></span>
<span data-ttu-id="ef2eb-165">**すでに SDS を使用している場合は**、「[ベスト プラクティス](#best-practices)」に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-165">**If you already use SDS**, we recommend you follow our [best practices](#best-practices).</span></span> 

<span data-ttu-id="ef2eb-166">**SDS を使用していない場合は**、[SDS を展開する](/schooldatasync/deploying-school-data-sync)必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-166">**If you don't use SDS yet**, you now need to [deploy it](/schooldatasync/deploying-school-data-sync).</span></span>

<span data-ttu-id="ef2eb-167">展開プロセス中に、Teams のユーザーとクラスのプロビジョニングに SDS を使用するか、Insights にもユーザーと組織の階層を提供するためにのみ使用するかを決めることができます。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-167">During the deployment process, you can decide if you want to use SDS for provisioning users and classes to Teams or to use it only to provide user and organizational hierarchy to Insights as well.</span></span>

> [!NOTE]
> <span data-ttu-id="ef2eb-168">年央で、すでに手動でチームを作成している場合は、Insights にユーザーと組織階層のデータを提供するためだけに SDS を使用するとしておき、来年は Teams のユーザーとクラスのプロビジョニングにも SDS を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-168">If it's the middle of the year and you already created teams manually, use SDS only to provide the user and organizational hierarchy data to Insights, and next year consider using SDS for provisioning users and classes for Teams as well.</span></span>

### <a name="verify-the-sync-process"></a><span data-ttu-id="ef2eb-169">同期プロセスを確認する</span><span class="sxs-lookup"><span data-stu-id="ef2eb-169">Verify the sync process</span></span>
<span data-ttu-id="ef2eb-170">同期状態の進捗状況を確認するには、[Insights データの正常性と監視向け SDS](/schooldatasync/sds-for-insights-data-health-and-monitoring) の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-170">To verify the sync status progress follow the instructions in [SDS for Insights Data Health and Monitoring](/schooldatasync/sds-for-insights-data-health-and-monitoring).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef2eb-171">問題が発生した場合は、[カスタマー サポート](https://aka.ms/edusupport)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-171">If you run into any problems, [customer support](https://aka.ms/edusupport) is there to help you.</span></span>

## <a name="supported-grade-level-values"></a><span data-ttu-id="ef2eb-172">サポートされている学年の値</span><span class="sxs-lookup"><span data-stu-id="ef2eb-172">Supported grade level values</span></span>

<span data-ttu-id="ef2eb-173">SDS ファイルでは、学年は列挙値として定義されています。つまり、CSV ファイル内で指定されている値のセットのみを入力できます。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-173">In the SDS files, grade/year level defined as Enumerated values, which means you can only provide a selected set of values within the CSV file.</span></span> <span data-ttu-id="ef2eb-174">指定されている値以外の値を入力すると、同期処理中にエラーとなります。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-174">Anything other than values specified will result in an error during sync processing.</span></span>

<span data-ttu-id="ef2eb-175">以下のセクションでは、users ファイルでサポートされている値を定義します。</span><span class="sxs-lookup"><span data-stu-id="ef2eb-175">The section below defines the supported values in the users file.</span></span>

### <a name="united-states--worldwide-grade-levels"></a><span data-ttu-id="ef2eb-176">米国 / 世界的に用いられる学年</span><span class="sxs-lookup"><span data-stu-id="ef2eb-176">United States / worldwide grade levels</span></span>
|<span data-ttu-id="ef2eb-177">ファイル内の値 (Grade 列)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-177">Value in file (Grade column)</span></span> | <span data-ttu-id="ef2eb-178">Insights のラベル</span><span class="sxs-lookup"><span data-stu-id="ef2eb-178">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="ef2eb-179">IT</span><span class="sxs-lookup"><span data-stu-id="ef2eb-179">IT</span></span>|<span data-ttu-id="ef2eb-180">Infant (保育園)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-180">Infant</span></span>|
|<span data-ttu-id="ef2eb-181">PR</span><span class="sxs-lookup"><span data-stu-id="ef2eb-181">PR</span></span>|<span data-ttu-id="ef2eb-182">Pre-school (保育園)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-182">Pre-school</span></span>|
|<span data-ttu-id="ef2eb-183">PK</span><span class="sxs-lookup"><span data-stu-id="ef2eb-183">PK</span></span>|<span data-ttu-id="ef2eb-184">Pre-kindergarten (保育園)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-184">Pre-kindergarten</span></span>|
|<span data-ttu-id="ef2eb-185">TK</span><span class="sxs-lookup"><span data-stu-id="ef2eb-185">TK</span></span>|<span data-ttu-id="ef2eb-186">Transitional Kindergarten (幼稚園 - 年少)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-186">Transitional Kindergarten</span></span>|
|<span data-ttu-id="ef2eb-187">KG</span><span class="sxs-lookup"><span data-stu-id="ef2eb-187">KG</span></span>|<span data-ttu-id="ef2eb-188">Kindergarten (幼稚園)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-188">Kindergarten</span></span>|
|<span data-ttu-id="ef2eb-189">01 または 1</span><span class="sxs-lookup"><span data-stu-id="ef2eb-189">01 or 1</span></span>|<span data-ttu-id="ef2eb-190">First grade (1 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-190">First grade</span></span>|
|<span data-ttu-id="ef2eb-191">02 または 2</span><span class="sxs-lookup"><span data-stu-id="ef2eb-191">02 or 2</span></span>|<span data-ttu-id="ef2eb-192">Second grade (2 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-192">Second grade</span></span>|
|<span data-ttu-id="ef2eb-193">03 または 3</span><span class="sxs-lookup"><span data-stu-id="ef2eb-193">03 or 3</span></span>|<span data-ttu-id="ef2eb-194">Third grade (3 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-194">Third grade</span></span>|
|<span data-ttu-id="ef2eb-195">04 または 4</span><span class="sxs-lookup"><span data-stu-id="ef2eb-195">04 or 4</span></span>|<span data-ttu-id="ef2eb-196">Fourth Grade (4 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-196">Fourth grade</span></span>|
|<span data-ttu-id="ef2eb-197">05 または 5</span><span class="sxs-lookup"><span data-stu-id="ef2eb-197">05 or 5</span></span>|<span data-ttu-id="ef2eb-198">Fifth grade (5 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-198">Fifth grade</span></span>|
|<span data-ttu-id="ef2eb-199">06 または 6</span><span class="sxs-lookup"><span data-stu-id="ef2eb-199">06 or 6</span></span>|<span data-ttu-id="ef2eb-200">Sixth grade (6 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-200">Sixth grade</span></span>|
|<span data-ttu-id="ef2eb-201">07 または 7</span><span class="sxs-lookup"><span data-stu-id="ef2eb-201">07 or 7</span></span>|<span data-ttu-id="ef2eb-202">Seventh grade (7 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-202">Seventh grade</span></span>|
|<span data-ttu-id="ef2eb-203">08 または 8</span><span class="sxs-lookup"><span data-stu-id="ef2eb-203">08 or 8</span></span>|<span data-ttu-id="ef2eb-204">Eighth grade (8 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-204">Eighth grade</span></span>|
|<span data-ttu-id="ef2eb-205">09 または 9</span><span class="sxs-lookup"><span data-stu-id="ef2eb-205">09 or 9</span></span>|<span data-ttu-id="ef2eb-206">Ninth grade (9 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-206">Ninth grade</span></span>|
|<span data-ttu-id="ef2eb-207">10</span><span class="sxs-lookup"><span data-stu-id="ef2eb-207">10</span></span>|<span data-ttu-id="ef2eb-208">Tenth grade (10 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-208">Tenth grade</span></span>|
|<span data-ttu-id="ef2eb-209">11</span><span class="sxs-lookup"><span data-stu-id="ef2eb-209">11</span></span>|<span data-ttu-id="ef2eb-210">Eleventh grade (11 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-210">Eleventh grade</span></span>|
|<span data-ttu-id="ef2eb-211">12</span><span class="sxs-lookup"><span data-stu-id="ef2eb-211">12</span></span>|<span data-ttu-id="ef2eb-212">Twelfth grade (12 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-212">Twelfth grade</span></span>|
|<span data-ttu-id="ef2eb-213">PS</span><span class="sxs-lookup"><span data-stu-id="ef2eb-213">PS</span></span>|<span data-ttu-id="ef2eb-214">Postsecondary (高等教育)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-214">Postsecondary</span></span>|
|<span data-ttu-id="ef2eb-215">PS1</span><span class="sxs-lookup"><span data-stu-id="ef2eb-215">PS1</span></span>|<span data-ttu-id="ef2eb-216">Postsecondary freshman (大学 1 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-216">Postsecondary freshman</span></span>|
|<span data-ttu-id="ef2eb-217">PS2</span><span class="sxs-lookup"><span data-stu-id="ef2eb-217">PS2</span></span>|<span data-ttu-id="ef2eb-218">Postsecondary sophomore (大学 2 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-218">Postsecondary sophomore</span></span>|
|<span data-ttu-id="ef2eb-219">PS3</span><span class="sxs-lookup"><span data-stu-id="ef2eb-219">PS3</span></span>|<span data-ttu-id="ef2eb-220">Postsecondary junior (大学 3 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-220">Postsecondary junior</span></span>|
|<span data-ttu-id="ef2eb-221">PS4</span><span class="sxs-lookup"><span data-stu-id="ef2eb-221">PS4</span></span>|<span data-ttu-id="ef2eb-222">Postsecondary senior (大学 4 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-222">Postsecondary senior</span></span>|
|<span data-ttu-id="ef2eb-223">undergraduate</span><span class="sxs-lookup"><span data-stu-id="ef2eb-223">undergraduate</span></span>|<span data-ttu-id="ef2eb-224">Undergraduate (大学)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-224">Undergraduate</span></span>|
|<span data-ttu-id="ef2eb-225">graduate</span><span class="sxs-lookup"><span data-stu-id="ef2eb-225">graduate</span></span>|<span data-ttu-id="ef2eb-226">Graduate (大学院)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-226">Graduate</span></span>|
|<span data-ttu-id="ef2eb-227">postgraduate</span><span class="sxs-lookup"><span data-stu-id="ef2eb-227">postgraduate</span></span>|<span data-ttu-id="ef2eb-228">Postgraduate (研究科)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-228">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="ef2eb-229">alumni</span><span class="sxs-lookup"><span data-stu-id="ef2eb-229">alumni</span></span>|<span data-ttu-id="ef2eb-230">Alumni (卒業生)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-230">Alumni</span></span>|
|<span data-ttu-id="ef2eb-231">adultEducation</span><span class="sxs-lookup"><span data-stu-id="ef2eb-231">adultEducation</span></span>|<span data-ttu-id="ef2eb-232">Adult Education (社会人教育)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-232">Adult Education</span></span>|
|<span data-ttu-id="ef2eb-233">UG</span><span class="sxs-lookup"><span data-stu-id="ef2eb-233">UG</span></span>|<span data-ttu-id="ef2eb-234">Ungraded (特殊教育)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-234">Ungraded</span></span>|
|<span data-ttu-id="ef2eb-235">Other (その他)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-235">Other</span></span>|<span data-ttu-id="ef2eb-236">Other (その他)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-236">Other</span></span>|

### <a name="united-kingdom-year-groups"></a><span data-ttu-id="ef2eb-237">英国の学年グループ</span><span class="sxs-lookup"><span data-stu-id="ef2eb-237">United Kingdom year groups</span></span>
|<span data-ttu-id="ef2eb-238">ファイル内の値 (Grade 列)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-238">Value in file (Grade column)</span></span> | <span data-ttu-id="ef2eb-239">Insights のラベル</span><span class="sxs-lookup"><span data-stu-id="ef2eb-239">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="ef2eb-240">IT</span><span class="sxs-lookup"><span data-stu-id="ef2eb-240">IT</span></span>|<span data-ttu-id="ef2eb-241">Nursery (保育園)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-241">Nursery</span></span>|
|<span data-ttu-id="ef2eb-242">PR</span><span class="sxs-lookup"><span data-stu-id="ef2eb-242">PR</span></span>|<span data-ttu-id="ef2eb-243">Pre-school (保育園)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-243">Pre-school</span></span>|
|<span data-ttu-id="ef2eb-244">PK</span><span class="sxs-lookup"><span data-stu-id="ef2eb-244">PK</span></span>|<span data-ttu-id="ef2eb-245">Reception (幼稚園)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-245">Reception</span></span>|
|<span data-ttu-id="ef2eb-246">01 または 1</span><span class="sxs-lookup"><span data-stu-id="ef2eb-246">01 or 1</span></span>|<span data-ttu-id="ef2eb-247">Year 1 (1 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-247">Year 1</span></span>|
|<span data-ttu-id="ef2eb-248">02 または 2</span><span class="sxs-lookup"><span data-stu-id="ef2eb-248">02 or 2</span></span>|<span data-ttu-id="ef2eb-249">Year 2 (2 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-249">Year 2</span></span>|
|<span data-ttu-id="ef2eb-250">03 または 3</span><span class="sxs-lookup"><span data-stu-id="ef2eb-250">03 or 3</span></span>|<span data-ttu-id="ef2eb-251">Year 3 (3 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-251">Year 3</span></span>|
|<span data-ttu-id="ef2eb-252">04 または 4</span><span class="sxs-lookup"><span data-stu-id="ef2eb-252">04 or 4</span></span>|<span data-ttu-id="ef2eb-253">Year 4 (4 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-253">Year 4</span></span>|
|<span data-ttu-id="ef2eb-254">05 または 5</span><span class="sxs-lookup"><span data-stu-id="ef2eb-254">05 or 5</span></span>|<span data-ttu-id="ef2eb-255">Year 5 (5 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-255">Year 5</span></span>|
|<span data-ttu-id="ef2eb-256">06 または 6</span><span class="sxs-lookup"><span data-stu-id="ef2eb-256">06 or 6</span></span>|<span data-ttu-id="ef2eb-257">Year 6 (6 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-257">Year 6</span></span>|
|<span data-ttu-id="ef2eb-258">07 または 7</span><span class="sxs-lookup"><span data-stu-id="ef2eb-258">07 or 7</span></span>|<span data-ttu-id="ef2eb-259">Year 7 (7 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-259">Year 7</span></span>|
|<span data-ttu-id="ef2eb-260">08 または 8</span><span class="sxs-lookup"><span data-stu-id="ef2eb-260">08 or 8</span></span>|<span data-ttu-id="ef2eb-261">Year 8 (8 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-261">Year 8</span></span>|
|<span data-ttu-id="ef2eb-262">09 または 9</span><span class="sxs-lookup"><span data-stu-id="ef2eb-262">09 or 9</span></span>|<span data-ttu-id="ef2eb-263">Year 9 (9 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-263">Year 9</span></span>|
|<span data-ttu-id="ef2eb-264">10</span><span class="sxs-lookup"><span data-stu-id="ef2eb-264">10</span></span>|<span data-ttu-id="ef2eb-265">Year 10 (10 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-265">Year 10</span></span>|
|<span data-ttu-id="ef2eb-266">11</span><span class="sxs-lookup"><span data-stu-id="ef2eb-266">11</span></span>|<span data-ttu-id="ef2eb-267">Year 11 (11 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-267">Year 11</span></span>|
|<span data-ttu-id="ef2eb-268">12</span><span class="sxs-lookup"><span data-stu-id="ef2eb-268">12</span></span>|<span data-ttu-id="ef2eb-269">Year 12 (12 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-269">Year 12</span></span>|
|<span data-ttu-id="ef2eb-270">13</span><span class="sxs-lookup"><span data-stu-id="ef2eb-270">13</span></span>|<span data-ttu-id="ef2eb-271">Year 13 (13 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-271">Year 13</span></span>|
|<span data-ttu-id="ef2eb-272">PS</span><span class="sxs-lookup"><span data-stu-id="ef2eb-272">PS</span></span>|<span data-ttu-id="ef2eb-273">Postsecondary (高等教育)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-273">Postsecondary</span></span>|
|<span data-ttu-id="ef2eb-274">PS1</span><span class="sxs-lookup"><span data-stu-id="ef2eb-274">PS1</span></span>|<span data-ttu-id="ef2eb-275">Postsecondary Year 1 (大学 1 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-275">Postsecondary Year 1</span></span>|
|<span data-ttu-id="ef2eb-276">PS2</span><span class="sxs-lookup"><span data-stu-id="ef2eb-276">PS2</span></span>|<span data-ttu-id="ef2eb-277">Postsecondary Year 2 (大学 2 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-277">Postsecondary Year 2</span></span>|
|<span data-ttu-id="ef2eb-278">PS3</span><span class="sxs-lookup"><span data-stu-id="ef2eb-278">PS3</span></span>|<span data-ttu-id="ef2eb-279">Postsecondary Year 3 (大学 3 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-279">Postsecondary Year 3</span></span>|
|<span data-ttu-id="ef2eb-280">PS4</span><span class="sxs-lookup"><span data-stu-id="ef2eb-280">PS4</span></span>|<span data-ttu-id="ef2eb-281">Postsecondary Year 4 (大学 4 年)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-281">Postsecondary Year 4</span></span>|
|<span data-ttu-id="ef2eb-282">undergraduate</span><span class="sxs-lookup"><span data-stu-id="ef2eb-282">undergraduate</span></span>|<span data-ttu-id="ef2eb-283">Undergraduate (大学)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-283">Undergraduate</span></span>|
|<span data-ttu-id="ef2eb-284">graduate</span><span class="sxs-lookup"><span data-stu-id="ef2eb-284">graduate</span></span>|<span data-ttu-id="ef2eb-285">Graduate (大学院)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-285">Graduate</span></span>|
|<span data-ttu-id="ef2eb-286">postgraduate</span><span class="sxs-lookup"><span data-stu-id="ef2eb-286">postgraduate</span></span>|<span data-ttu-id="ef2eb-287">Postgraduate (研究科)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-287">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="ef2eb-288">alumni</span><span class="sxs-lookup"><span data-stu-id="ef2eb-288">alumni</span></span>|<span data-ttu-id="ef2eb-289">Alumni (卒業生)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-289">Alumni</span></span>|
|<span data-ttu-id="ef2eb-290">adultEducation</span><span class="sxs-lookup"><span data-stu-id="ef2eb-290">adultEducation</span></span>|<span data-ttu-id="ef2eb-291">Adult Education (社会人教育)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-291">Adult Education</span></span>|
|<span data-ttu-id="ef2eb-292">UG</span><span class="sxs-lookup"><span data-stu-id="ef2eb-292">UG</span></span>|<span data-ttu-id="ef2eb-293">Ungraded (特殊教育)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-293">Ungraded</span></span>|
|<span data-ttu-id="ef2eb-294">Other (その他)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-294">Other</span></span>|<span data-ttu-id="ef2eb-295">Other (その他)</span><span class="sxs-lookup"><span data-stu-id="ef2eb-295">Other</span></span>|

