---
title: Teams での割り当て
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Microsoft Teams 管理センターで課題を管理する方法についてMicrosoft Teams for Education。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: abf17b12e8555ce12642627093d856f917dce439
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004149"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="c57a5-103">教育機関向けの Teams の課題 </span><span class="sxs-lookup"><span data-stu-id="c57a5-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="c57a5-104">教師は、Microsoft Teams for Education課題と成績の機能を使用して、タスク、作業、またはテストを学生に割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="c57a5-104">The Assignments and Grades features in Teams for Education allow educators to assign tasks, work, or quizzes to their students.</span></span> <span data-ttu-id="c57a5-105">教師は、課題のタイムラインの管理、手順の管理、リソースの追加、ルーブリックを使用した成績の取得など、その他の操作を行えます。</span><span class="sxs-lookup"><span data-stu-id="c57a5-105">Educators can manage assignment timelines, instructions, add resources to turn in, grade with rubrics, and more.</span></span> <span data-ttu-id="c57a5-106">また、[成績] タブでクラスと個々の学生の進捗状況を追跡することもできます。</span><span class="sxs-lookup"><span data-stu-id="c57a5-106">They can also track class and individual student progress in the Grades tab.</span></span>

<span data-ttu-id="c57a5-107">[課題と成績の詳細については、Microsoft Teams for Education。](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)</span><span class="sxs-lookup"><span data-stu-id="c57a5-107">[Learn more about Assignments and Grades in Teams for Education](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="c57a5-108">さまざまなプラットフォームでの Teamsの割り当ての詳細については、プラットフォーム別のTeams[を参照してください](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="c57a5-108">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="c57a5-109">管理センターでの割りMicrosoft Teams統合</span><span class="sxs-lookup"><span data-stu-id="c57a5-109">Assignments integrations in the Microsoft Teams admin center</span></span>

<span data-ttu-id="c57a5-110">管理センターの管理者設定Microsoft Teams、組織内の教師とその学生の機能を有効またはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="c57a5-110">Using the admin settings in the Microsoft Teams admin center, you can turn features on or off for educators within your organization and their students.</span></span> <span data-ttu-id="c57a5-111">課題に関連する設定を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c57a5-111">The following are settings related to Assignments:</span></span>

<span data-ttu-id="c57a5-112"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="c57a5-112"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="c57a5-113">週 1 回の保護者のメール ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="c57a5-113">Weekly guardian email digest</span></span>


<span data-ttu-id="c57a5-114">保護者のメールは、週末ごとに保護者または保護者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="c57a5-114">Guardian emails are sent each weekend to parents or guardians.</span></span> <span data-ttu-id="c57a5-115">メールには、前の週と今後の週の課題に関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="c57a5-115">The email contains information about assignments from the previous week and for the upcoming week.</span></span> <span data-ttu-id="c57a5-116">親と保護者の同期は、 を使用[して学校データ同期。](/schooldatasync/parent-contact-sync)</span><span class="sxs-lookup"><span data-stu-id="c57a5-116">The Parent and Guardian Sync can be setup using [School Data Sync](/schooldatasync/parent-contact-sync).</span></span>

1. <span data-ttu-id="c57a5-117">SDS で親と保護者の同期を使用して親の連絡先情報をインポートします。</span><span class="sxs-lookup"><span data-stu-id="c57a5-117">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="c57a5-118">親と保護者の同期を有効にする方法については、「親と保護者の同期を有効 [にする」を参照してください](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)。</span><span class="sxs-lookup"><span data-stu-id="c57a5-118">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="c57a5-119">設定が既定でオフになっているMicrosoft Teams管理センターで [保護者の設定] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="c57a5-119">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="c57a5-120">これにより、教師は週刊ダイジェストを送信できます。</span><span class="sxs-lookup"><span data-stu-id="c57a5-120">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c57a5-121">教師は、自分の個人クラス チーム内の設定をオフにすることで、ダイジェストをオプトアウトできます ([割り当て]**設定 >/保護者** のメール)。</span><span class="sxs-lookup"><span data-stu-id="c57a5-121">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="c57a5-122">保護者がメールを受け取るのを確認するには、次の 3 つの項目が true である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c57a5-122">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="c57a5-123">SDS で学生のプロフィールに添付され、親または保護者としてタグ付 _けされた_ メール _アドレス。_</span><span class="sxs-lookup"><span data-stu-id="c57a5-123">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="c57a5-124">詳細については、「親と保護者の [同期ファイル形式」を参照してください](/schooldatasync/parent-contact-sync-file-format)。</span><span class="sxs-lookup"><span data-stu-id="c57a5-124">For details, see [Parent and Guardian Sync File Format](/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="c57a5-125">学生は、課題設定で教師がメールを無効にしていない少なくとも 1 つのクラス [に属しています](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)。</span><span class="sxs-lookup"><span data-stu-id="c57a5-125">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="c57a5-126">メールには、前の週または来週に期限が設定された割り当てに関する情報が含されます。</span><span class="sxs-lookup"><span data-stu-id="c57a5-126">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="c57a5-127">この機能の既定の設定は - **オフです**。</span><span class="sxs-lookup"><span data-stu-id="c57a5-127">Default setting for this feature is - **Off**.</span></span>


<span data-ttu-id="c57a5-128"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="c57a5-128"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="c57a5-129">MakeCode</span><span class="sxs-lookup"><span data-stu-id="c57a5-129">MakeCode</span></span>
<span data-ttu-id="c57a5-130">Microsoft MakeCode は、すべての学生にコンピューター サイエンスを生き生きとさせるブロックベースのコーディング プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="c57a5-130">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="c57a5-131">MakeCode は、Microsoft の使用条件とプライバシー ポリシーの [対象となる](https://go.microsoft.com/fwlink/?LinkID=206977) Microsoft [製品](https://go.microsoft.com/fwlink/?LinkId=521839) です。</span><span class="sxs-lookup"><span data-stu-id="c57a5-131">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="c57a5-132">この機能の既定の設定は - **オフです**。</span><span class="sxs-lookup"><span data-stu-id="c57a5-132">Default setting for this feature is - **Off**.</span></span>

<span data-ttu-id="c57a5-133">Teams で MakeCode の割り当てを有効にするには **、Teams** 管理センター に移動し、[割り当て] セクションに **移動** し、[MakeCode] トグル オプションを [オン] に **切り替します**。</span><span class="sxs-lookup"><span data-stu-id="c57a5-133">To enable MakeCode assignments in Teams, go to the **Teams Admin Center**, navigate to the **Assignments** section, and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="c57a5-134">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c57a5-134">Click **Save**.</span></span> <span data-ttu-id="c57a5-135">これらの設定を有効にするために数時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="c57a5-135">Allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="c57a5-136">この機能のしくみの詳細については、このビデオデモを [参照してください](https://makecode.com/blog/teams/teams-assignments)。</span><span class="sxs-lookup"><span data-stu-id="c57a5-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="c57a5-137">[MakeCode の詳細については、 を参照してください](https://aka.ms/makecode)。</span><span class="sxs-lookup"><span data-stu-id="c57a5-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="c57a5-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="c57a5-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="c57a5-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="c57a5-139">Turnitin</span></span>

<span data-ttu-id="c57a5-140">[Turnitin は](https://www.turnitin.com/) 教育機関向け整合性サービスです。</span><span class="sxs-lookup"><span data-stu-id="c57a5-140">[Turnitin](https://www.turnitin.com/) is an academic integrity service.</span></span> <span data-ttu-id="c57a5-141">これは、独自の使用条件とプライバシー ポリシーの対象となるサード パーティの製品またはサービスです。</span><span class="sxs-lookup"><span data-stu-id="c57a5-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="c57a5-142">お客様は、サード パーティの製品およびサービスを使用する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="c57a5-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="c57a5-143">この機能の既定の設定は - **オフ** です。</span><span class="sxs-lookup"><span data-stu-id="c57a5-143">Default setting for this feature is - **Off**..</span></span>

<span data-ttu-id="c57a5-144">組織で Turnitin を有効にするには、Turnitin サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="c57a5-144">To enable Turnitin for your organization, you will need a Turnitin subscription.</span></span> <span data-ttu-id="c57a5-145">次に、Turnitin 管理コンソールで確認できる次の情報を入力できます。</span><span class="sxs-lookup"><span data-stu-id="c57a5-145">Then you can input the following information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="c57a5-146">**TurnitinApiKey:** 管理コンソールの [統合] にある 32 文字の GUID です。</span><span class="sxs-lookup"><span data-stu-id="c57a5-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="c57a5-147">**TurnitinApiUrl:** これは、Turnitin 管理コンソールの HTTPS URL です。</span><span class="sxs-lookup"><span data-stu-id="c57a5-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="c57a5-148">この情報の取得に役立つ手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c57a5-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="c57a5-149">**TurnitinApiUrl は**、管理コンソールのホスト アドレスです。</span><span class="sxs-lookup"><span data-stu-id="c57a5-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="c57a5-150">例: `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="c57a5-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="c57a5-151">管理コンソールでは、統合と、統合に関連付けられている API キーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c57a5-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="c57a5-152">サイド **メニューから [統合** ] を選択し、[統合の追加] **を選択** し、統合に名前を付きます。</span><span class="sxs-lookup"><span data-stu-id="c57a5-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![新しい統合の追加を示すスクリーンショット](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="c57a5-154">**プロンプトに従った後、TurnitinApiKey** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c57a5-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="c57a5-155">API キーをコピーし、管理センター Microsoft Teams貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c57a5-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="c57a5-156">キーを表示できるのは今回のみです。</span><span class="sxs-lookup"><span data-stu-id="c57a5-156">This is the only time you can view the key.</span></span>

![API キーのコピーを示すスクリーンショット](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="c57a5-158">この設定 **に対して** 管理センターの [保存] ボタンをクリックすると、これらの設定が有効になります。</span><span class="sxs-lookup"><span data-stu-id="c57a5-158">Upon clicking the **Save** button in the admin center for this setting, allow a few hours for these settings to take effect.</span></span>

### <a name="removing-assignments-and-grades"></a><span data-ttu-id="c57a5-159">課題と成績の削除</span><span class="sxs-lookup"><span data-stu-id="c57a5-159">Removing Assignments and Grades</span></span>
<span data-ttu-id="c57a5-160">特定のユーザー Teams割り当てと成績を削除するには、ユーザー ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c57a5-160">You can use Teams policies to remove Assignments and Grades for a specific user or for your entire tenant.</span></span> 

<span data-ttu-id="c57a5-161">個々のユーザーの課題と成績を削除するには **、Teams** 管理センターに移動し **、Teams** アプリ > アクセス許可ポリシーに移動して、新しいアプリのアクセス許可ポリシー定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="c57a5-161">To remove Assignments and Grades for an individual user, go to **Teams Admin Center** and navigate to **Teams apps > Permission policies** to create a new app permission policy definition.</span></span>  <span data-ttu-id="c57a5-162">新しいポリシー定義を作成するときに **、[Microsoft アプリ**]ポリシーを [特定のアプリをブロック] に設定し、他のすべてのアプリを許可し、ブロックされているアプリケーションの一覧に割り当てを追加します。</span><span class="sxs-lookup"><span data-stu-id="c57a5-162">When creating the new policy definition, set the **Microsoft apps** policy to _Block specific apps and allow all others_ and add **Assignments** to the list of blocked applications.</span></span> <span data-ttu-id="c57a5-163">新しいポリシー定義を保存したら、適切なユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c57a5-163">Once your new policy definition is saved, assign it to the appropriate users.</span></span>

<span data-ttu-id="c57a5-164">テナント全体の課題と成績を削除するには **、[Teams** 管理センター] に移動し、[Teamsアプリ> アプリの管理] に移動し、アプリケーションの一覧から[割り当て] を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="c57a5-164">To remove Assignments and Grades for your entire tenant, go to **Teams Admin Center**, navigate to **Teams apps > Manage apps**, and search for and select **Assignments** from the application list.</span></span> <span data-ttu-id="c57a5-165">[アプリケーションの割り当て設定] ページの状態設定を [ブロック] _に変更します_。</span><span class="sxs-lookup"><span data-stu-id="c57a5-165">Change the status setting within the Assignment application settings page to _Blocked_.</span></span> 
