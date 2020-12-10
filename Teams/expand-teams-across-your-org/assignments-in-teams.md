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
description: 教育担当の Teams で Microsoft Teams 管理センターの課題を管理する方法について説明します。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: f283a4fb2d49778f4b0e8b31f46dada46f900e6f
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616911"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="2170c-103">教育機関向けの Teams の課題 </span><span class="sxs-lookup"><span data-stu-id="2170c-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="2170c-104">学生は、教育機関向けの課題と等級の機能を利用して、学生にタスク、仕事、またはクイズを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2170c-104">The Assignments and Grades features in Teams for Education allow educators to assign tasks, work, or quizzes to their students.</span></span> <span data-ttu-id="2170c-105">教師は、課題のタイムラインや手順を管理したり、リソースを追加したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="2170c-105">Educators can manage assignment timelines, instructions, add resources to turn in, grade with rubrics, and more.</span></span> <span data-ttu-id="2170c-106">また、[成績] タブで、クラスと個々の学生の進捗状況を追跡することもできます。</span><span class="sxs-lookup"><span data-stu-id="2170c-106">They can also track class and individual student progress in the Grades tab.</span></span>

<span data-ttu-id="2170c-107">[トレーニングの Teams での課題と成績の詳細については、こちらを参照](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)してください。</span><span class="sxs-lookup"><span data-stu-id="2170c-107">[Learn more about Assignments and Grades in Teams for Education](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="2170c-108">さまざまなプラットフォームでの Teams の割り当てについて詳しくは、「 [プラットフォームごとの teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2170c-108">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="2170c-109">Microsoft Teams 管理センターでの課題の統合</span><span class="sxs-lookup"><span data-stu-id="2170c-109">Assignments integrations in the Microsoft Teams admin center</span></span>

<span data-ttu-id="2170c-110">Microsoft Teams 管理センターで管理設定を使用すると、組織内の教育者やその学生に対して機能を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2170c-110">Using the admin settings in the Microsoft Teams admin center, you can turn features on or off for educators within your organization and their students.</span></span> <span data-ttu-id="2170c-111">課題に関連する設定を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2170c-111">The following are settings related to Assignments:</span></span>

<span data-ttu-id="2170c-112"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="2170c-112"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="2170c-113">1週間のガーディアンメールダイジェスト</span><span class="sxs-lookup"><span data-stu-id="2170c-113">Weekly guardian email digest</span></span>


<span data-ttu-id="2170c-114">ガーディアンのメールは、各週末に親またはガーディアンに送信されます。</span><span class="sxs-lookup"><span data-stu-id="2170c-114">Guardian emails are sent each weekend to parents or guardians.</span></span> <span data-ttu-id="2170c-115">このメールには、前週と来週の課題に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2170c-115">The email contains information about assignments from the previous week and for the upcoming week.</span></span> <span data-ttu-id="2170c-116">保護者による同期は、 [School Data sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync)を使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="2170c-116">The Parent and Guardian Sync can be setup using [School Data Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync).</span></span>

1. <span data-ttu-id="2170c-117">SDS で親とガーディアンの同期を使って、親の連絡先情報をインポートします。</span><span class="sxs-lookup"><span data-stu-id="2170c-117">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="2170c-118">親とガーディアンの同期を有効にする方法については、「 [親とガーディアンの同期を有効](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2170c-118">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="2170c-119">設定は既定で無効になっているため、Microsoft Teams 管理センターで [ガーディアン] 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="2170c-119">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="2170c-120">これにより、教師が毎週のダイジェストを送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2170c-120">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2170c-121">教師は、独自の個人用クラスチーム内の設定 (**親/ガーディアンメール > の割り当て設定**) の選択を解除することによって、ダイジェストを除外することができます。</span><span class="sxs-lookup"><span data-stu-id="2170c-121">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="2170c-122">親からメールが送信されることを確認するには、次の3つの項目が true である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2170c-122">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="2170c-123">SDS の学生プロファイルに添付され、 _親_ または _ガーディアン_ としてタグ付けされたメールアドレス。</span><span class="sxs-lookup"><span data-stu-id="2170c-123">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="2170c-124">詳細については、「 [親とガーディアンの同期ファイル形式](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2170c-124">For details, see [Parent and Guardian Sync File Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="2170c-125">学生は、[ [割り当ての設定](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)] の教師によって無効にされていない1つ以上のクラスに属しています。</span><span class="sxs-lookup"><span data-stu-id="2170c-125">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="2170c-126">このメールには、先週または来週に期限がある課題に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2170c-126">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="2170c-127">この機能の既定の設定は- **オフ** です。</span><span class="sxs-lookup"><span data-stu-id="2170c-127">Default setting for this feature is - **Off**.</span></span>


<span data-ttu-id="2170c-128"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="2170c-128"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="2170c-129">MakeCode</span><span class="sxs-lookup"><span data-stu-id="2170c-129">MakeCode</span></span>
<span data-ttu-id="2170c-130">Microsoft MakeCode はブロックベースのコーディングプラットフォームであり、すべての学生に対してコンピューターの科学を実現します。</span><span class="sxs-lookup"><span data-stu-id="2170c-130">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="2170c-131">MakeCode は、Microsoft [利用規約](https://go.microsoft.com/fwlink/?LinkID=206977) および [プライバシー](https://go.microsoft.com/fwlink/?LinkId=521839) ポリシーの適用対象となる microsoft 製品です。</span><span class="sxs-lookup"><span data-stu-id="2170c-131">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="2170c-132">この機能の既定の設定は- **オフ** です。</span><span class="sxs-lookup"><span data-stu-id="2170c-132">Default setting for this feature is - **Off**.</span></span>

<span data-ttu-id="2170c-133">Teams で MakeCode の割り当てを有効にするには、 **Teams 管理センター** に移動し、[ **課題** ] セクションに移動して、MakeCode トグルオプションを **[オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="2170c-133">To enable MakeCode assignments in Teams, go to the **Teams Admin Center**, navigate to the **Assignments** section, and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="2170c-134">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2170c-134">Click **Save**.</span></span> <span data-ttu-id="2170c-135">これらの設定を有効にするには、数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="2170c-135">Allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="2170c-136">この機能のしくみについて詳しくは、この [ビデオデモ](https://makecode.com/blog/teams/teams-assignments)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2170c-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="2170c-137">[MakeCode の詳細について](https://aka.ms/makecode)は、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2170c-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="2170c-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="2170c-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="2170c-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="2170c-139">Turnitin</span></span>

<span data-ttu-id="2170c-140">[Turnitin](https://www.turnitin.com/) は、教育機関向けの整合性サービスです。</span><span class="sxs-lookup"><span data-stu-id="2170c-140">[Turnitin](https://www.turnitin.com/) is an academic integrity service.</span></span> <span data-ttu-id="2170c-141">これは、サードパーティの製品またはサービスであり、独自の用語とプライバシーポリシーの適用対象となります。</span><span class="sxs-lookup"><span data-stu-id="2170c-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="2170c-142">お客様は、サードパーティの製品とサービスの使用に関して責任を負います。</span><span class="sxs-lookup"><span data-stu-id="2170c-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="2170c-143">この機能の既定の設定は- **オフ** です。</span><span class="sxs-lookup"><span data-stu-id="2170c-143">Default setting for this feature is - **Off**..</span></span>

<span data-ttu-id="2170c-144">組織で Turnitin を有効にするには、Turnitin サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="2170c-144">To enable Turnitin for your organization, you will need a Turnitin subscription.</span></span> <span data-ttu-id="2170c-145">次に、Turnitin 管理コンソールに含まれる次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="2170c-145">Then you can input the following information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="2170c-146">**TurnitinApiKey**: この32文字の GUID は、[統合] の下の管理コンソールにあります。</span><span class="sxs-lookup"><span data-stu-id="2170c-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="2170c-147">**TurnitinApiUrl**: これは、Turnitin 管理コンソールの HTTPS URL です。</span><span class="sxs-lookup"><span data-stu-id="2170c-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="2170c-148">この情報を取得するための手順をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="2170c-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="2170c-149">**TurnitinApiUrl** は、管理コンソールのホストアドレスです。</span><span class="sxs-lookup"><span data-stu-id="2170c-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="2170c-150">次 `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="2170c-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="2170c-151">管理コンソールでは、統合と関連付けられた API キーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2170c-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="2170c-152">サイド **メニューから [統合] を選択** し、[ **統合の追加** ] を選択して、統合の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2170c-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![新しい統合の追加を示すスクリーンショット](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="2170c-154">プロンプトが表示された後、 **TurnitinApiKey** が提供されます。</span><span class="sxs-lookup"><span data-stu-id="2170c-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="2170c-155">API キーをコピーして、Microsoft Teams 管理センターに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="2170c-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="2170c-156">これは、キーを表示できる唯一の時間です。</span><span class="sxs-lookup"><span data-stu-id="2170c-156">This is the only time you can view the key.</span></span>

![API キーのコピーを示すスクリーンショット](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="2170c-158">この設定のために管理センターで [ **保存** ] ボタンをクリックしたときに、これらの設定が有効になるまで、数時間許可します。</span><span class="sxs-lookup"><span data-stu-id="2170c-158">Upon clicking the **Save** button in the admin center for this setting, allow a few hours for these settings to take effect.</span></span>

