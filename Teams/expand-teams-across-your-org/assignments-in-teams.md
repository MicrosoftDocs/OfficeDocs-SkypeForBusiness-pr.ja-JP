---
title: Teams での割り当て
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: e3a0bf0dd0141679dc89ed1d5ecc0cfc542854c8
ms.sourcegitcommit: 3eb5820b279fc904f34ac4259deeb419e02d832a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561053"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="67a3d-103">教育機関向けの Teams の課題 </span><span class="sxs-lookup"><span data-stu-id="67a3d-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="67a3d-104">割り当ては、学生またはチームメンバーに対して、調査の一環として、クラス内で割り当てられているタスクまたは作業単位数です。</span><span class="sxs-lookup"><span data-stu-id="67a3d-104">Assignments are tasks or units of work assigned to a student or team member in a class as part of their study.</span></span> <span data-ttu-id="67a3d-105">Teams クラス内で課題を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="67a3d-105">You can create assignments within your Teams class.</span></span>

<span data-ttu-id="67a3d-106">[割り当ての詳細について](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)は、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67a3d-106">[Learn more about Assignments](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="67a3d-107">さまざまなプラットフォームでの Teams の割り当てについて詳しくは、「 [プラットフォームごとの teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="67a3d-107">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="67a3d-108">Microsoft Teams 管理センターでの課題</span><span class="sxs-lookup"><span data-stu-id="67a3d-108">Assignments in the Microsoft Teams admin center</span></span>

<span data-ttu-id="67a3d-109">Microsoft Teams 管理センターの管理設定を使用すると、組織内の学生と教師が、次の機能を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="67a3d-109">With the admin settings in Microsoft Teams admin center, you can turn the following features on or off to be available for students and teachers within your organization.</span></span> <span data-ttu-id="67a3d-110">課題に関連する設定を次に示します。</span><span class="sxs-lookup"><span data-stu-id="67a3d-110">The following are settings related to Assignments:</span></span>

<span data-ttu-id="67a3d-111"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="67a3d-111"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="67a3d-112">1週間のガーディアンメールダイジェスト</span><span class="sxs-lookup"><span data-stu-id="67a3d-112">Weekly guardian email digest</span></span>

<span data-ttu-id="67a3d-113">このメールには、前週と来週の課題に関する情報が含まれており、週末に送信されます。</span><span class="sxs-lookup"><span data-stu-id="67a3d-113">The emails will contain information about assignments from the previous week and for the upcoming week, and will be sent over the weekend.</span></span> <span data-ttu-id="67a3d-114">メールコンテンツに関する情報については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67a3d-114">Information about the email content can be found here.</span></span> <span data-ttu-id="67a3d-115">メールは、 [School Data Sync (SDS)](https://docs.microsoft.com/schooldatasync/)を使用して管理者がセットアップおよび更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67a3d-115">The emails need to be set up and updated by the admins by using [School Data Sync (SDS)](https://docs.microsoft.com/schooldatasync/).</span></span> <span data-ttu-id="67a3d-116">この機能は、学校の学生情報システム (SIS) を使用して、学生の選手名簿で Teams のクラスを自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="67a3d-116">This feature automatically populates classes for Teams with student rosters from the school's student information system (SIS).</span></span> <span data-ttu-id="67a3d-117">この機能を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="67a3d-117">The steps to enable this feature are:</span></span>

1. <span data-ttu-id="67a3d-118">SDS で親とガーディアンの同期を使って、親の連絡先情報をインポートします。</span><span class="sxs-lookup"><span data-stu-id="67a3d-118">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="67a3d-119">親とガーディアンの同期を有効にする方法については、「 [親とガーディアンの同期を有効](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67a3d-119">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="67a3d-120">設定は既定で無効になっているため、Microsoft Teams 管理センターで [ガーディアン] 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="67a3d-120">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="67a3d-121">これにより、教師が毎週のダイジェストを送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="67a3d-121">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="67a3d-122">教師は、独自の個人用クラスチーム内の設定 (**親/ガーディアンメール > の割り当て設定**) の選択を解除することによって、ダイジェストを除外することができます。</span><span class="sxs-lookup"><span data-stu-id="67a3d-122">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="67a3d-123">親からメールが送信されることを確認するには、次の3つの項目が true である必要があります。</span><span class="sxs-lookup"><span data-stu-id="67a3d-123">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="67a3d-124">SDS の学生プロファイルに添付され、 _親_ または _ガーディアン_ としてタグ付けされたメールアドレス。</span><span class="sxs-lookup"><span data-stu-id="67a3d-124">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="67a3d-125">詳細については、「 [親とガーディアンの同期ファイル形式](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67a3d-125">For details, see [Parent and Guardian Sync File Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="67a3d-126">学生は、[ [割り当ての設定](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)] の教師によって無効にされていない1つ以上のクラスに属しています。</span><span class="sxs-lookup"><span data-stu-id="67a3d-126">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="67a3d-127">このメールには、先週または来週に期限がある課題に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67a3d-127">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="67a3d-128">この設定は、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="67a3d-128">This setting is off by default.</span></span>


<span data-ttu-id="67a3d-129"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="67a3d-129"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="67a3d-130">MakeCode</span><span class="sxs-lookup"><span data-stu-id="67a3d-130">MakeCode</span></span>
<span data-ttu-id="67a3d-131">Microsoft MakeCode はブロックベースのコーディングプラットフォームであり、すべての学生に対してコンピューターの科学を実現します。</span><span class="sxs-lookup"><span data-stu-id="67a3d-131">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="67a3d-132">MakeCode は、Microsoft [利用規約](https://go.microsoft.com/fwlink/?LinkID=206977) および [プライバシー](https://go.microsoft.com/fwlink/?LinkId=521839) ポリシーの適用対象となる microsoft 製品です。</span><span class="sxs-lookup"><span data-stu-id="67a3d-132">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="67a3d-133">この設定は、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="67a3d-133">This setting is off by default.</span></span> <span data-ttu-id="67a3d-134">Teams で MakeCode の割り当てを有効にするには、 **Teams 管理センター** で、[ **課題** ] セクションに移動し、MakeCode トグルオプションを **[オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="67a3d-134">To enable MakeCode assignments in Teams, in the **Teams Admin Center**, navigate to the **Assignments** section and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="67a3d-135">[ **保存** ] をクリックして、これらの設定が有効になるまで数時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="67a3d-135">Click **Save** and allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="67a3d-136">この機能のしくみについて詳しくは、この [ビデオデモ](https://makecode.com/blog/teams/teams-assignments)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="67a3d-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="67a3d-137">[MakeCode の詳細について](https://aka.ms/makecode)は、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67a3d-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="67a3d-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="67a3d-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="67a3d-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="67a3d-139">Turnitin</span></span>

<span data-ttu-id="67a3d-140">Turnitin は、plagiarism の検出サービスです。</span><span class="sxs-lookup"><span data-stu-id="67a3d-140">Turnitin is a plagiarism detection service.</span></span> <span data-ttu-id="67a3d-141">これは、サードパーティの製品またはサービスであり、独自の用語とプライバシーポリシーの適用対象となります。</span><span class="sxs-lookup"><span data-stu-id="67a3d-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="67a3d-142">お客様は、サードパーティの製品とサービスの使用に関して責任を負います。</span><span class="sxs-lookup"><span data-stu-id="67a3d-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="67a3d-143">この設定は、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="67a3d-143">This setting is off by default.</span></span>

<span data-ttu-id="67a3d-144">組織の Turnitin を正常に有効にするには、Turnitin サブスクリプションが既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="67a3d-144">In order to successfully enable Turnitin for your organization, you will need to already have a Turnitin subscription.</span></span> <span data-ttu-id="67a3d-145">次の追加情報を入力する必要があります。これは、Turnitin の管理コンソールにあります。</span><span class="sxs-lookup"><span data-stu-id="67a3d-145">You will need to enter the following additional information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="67a3d-146">**TurnitinApiKey**: この32文字の GUID は、[統合] の下の管理コンソールにあります。</span><span class="sxs-lookup"><span data-stu-id="67a3d-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="67a3d-147">**TurnitinApiUrl**: これは、Turnitin 管理コンソールの HTTPS URL です。</span><span class="sxs-lookup"><span data-stu-id="67a3d-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="67a3d-148">この情報を取得するための手順をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="67a3d-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="67a3d-149">**TurnitinApiUrl** は、管理コンソールのホストアドレスです。</span><span class="sxs-lookup"><span data-stu-id="67a3d-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="67a3d-150">次 `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="67a3d-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="67a3d-151">管理コンソールでは、統合と関連付けられた API キーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="67a3d-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="67a3d-152">サイド **メニューから [統合] を選択** し、[ **統合の追加** ] を選択して、統合の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="67a3d-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![新しい統合の追加を示すスクリーンショット](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="67a3d-154">プロンプトが表示された後、 **TurnitinApiKey** が提供されます。</span><span class="sxs-lookup"><span data-stu-id="67a3d-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="67a3d-155">API キーをコピーして、Microsoft Teams 管理センターに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="67a3d-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="67a3d-156">これは、キーを表示できる唯一の時間です。</span><span class="sxs-lookup"><span data-stu-id="67a3d-156">This is the only time you can view the key.</span></span>

![API キーのコピーを示すスクリーンショット](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="67a3d-158">この設定のために管理センターで [ **保存** ] ボタンをクリックしたときに、これらの設定が有効になるまで、数時間許可してください。</span><span class="sxs-lookup"><span data-stu-id="67a3d-158">Upon clicking the **Save** button in the admin center for this setting, please allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="67a3d-159">Teams で Turnitin 統合の使用を開始する準備ができましたか?</span><span class="sxs-lookup"><span data-stu-id="67a3d-159">Ready to start using the Turnitin integration in Teams?</span></span> <span data-ttu-id="67a3d-160">[以前のアクセスプログラム](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="67a3d-160">Sign up for the [early access program](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).</span></span>
