---
title: 音声認識 (音声プロファイル) のテナント管理Teams ミーティング
author: cichur
ms.author: v-cichur
ms.reviewer: parisataheri
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 会議室での音声認識 (音声プロファイル) のテナント管理Teamsします。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 96f82b398ff75cdaf651eb841c412c502c5108d4
ms.sourcegitcommit: 4d2e1328dee2b6c60ba0022976da8dfe5efba2ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53203586"
---
# <a name="manage-voice-recognition-technology-controls-for-an-intelligent-speaker"></a><span data-ttu-id="3d80e-103">インテリジェント スピーカーの音声認識テクノロジ コントロールを管理する</span><span class="sxs-lookup"><span data-stu-id="3d80e-103">Manage voice recognition technology controls for an Intelligent Speaker</span></span>

<span data-ttu-id="3d80e-104">インテリジェント スピーカーは、音声プロファイル情報を使用して、ライブトランスクリプションで何を言ったかを認識します。</span><span class="sxs-lookup"><span data-stu-id="3d80e-104">An Intelligent Speaker uses voice profile information to recognize who said what in live transcription.</span></span> <span data-ttu-id="3d80e-105">会議のMicrosoft Teams ミーティングにWindowsスピーカーが備え付けされている場合、会議中にライブ文字起こしを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-105">When a Microsoft Teams Rooms for Windows meeting room is equipped with an Intelligent Speaker, live transcription can be used during the meeting.</span></span> <span data-ttu-id="3d80e-106">この記事では、テナント管理者が、音声認識でライブトランスクリプションを生成するために使用される音声プロファイリングを制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d80e-106">This article explains how you, a tenant admin, control the voice profiling that's used for voice recognition to generate live transcription.</span></span> <span data-ttu-id="3d80e-107">組織が音声認識を使用している程度と、次の機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-107">You can control to what degree the organization is using voice recognition and the following features:</span></span>

- <span data-ttu-id="3d80e-108">トランスクリプトで話者の名前を編集します。</span><span class="sxs-lookup"><span data-stu-id="3d80e-108">Edit the speaker's name in transcripts.</span></span>
- <span data-ttu-id="3d80e-109">トランスクリプト内の 1 つの発話の話者を変更するか、トランスクリプト内のすべての発話の話者を変更します (ただし、将来のトランスクリプトでは変更されません)。</span><span class="sxs-lookup"><span data-stu-id="3d80e-109">Change the speaker of a single utterance in the transcript or change the speaker in all the utterances in the transcript (but not on future transcripts).</span></span>
- <span data-ttu-id="3d80e-110">会議に一覧表示されているユーザーの発表者 ID を変更します。</span><span class="sxs-lookup"><span data-stu-id="3d80e-110">Change the speaker identification for the people who are listed in the meeting.</span></span>
- <span data-ttu-id="3d80e-111">すべてのトランスクリプトで、その話者として識別された 1 つ以上の発話の識別を削除します。</span><span class="sxs-lookup"><span data-stu-id="3d80e-111">Remove the identification of one or more utterances identified as that speaker, on every transcript.</span></span>

## <a name="review-intelligent-speaker-requirements"></a><span data-ttu-id="3d80e-112">インテリジェント スピーカーの要件を確認する</span><span class="sxs-lookup"><span data-stu-id="3d80e-112">Review Intelligent Speaker requirements</span></span>

<span data-ttu-id="3d80e-113">インテリジェント スピーカーには、特殊な 7 マイク アレイが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d80e-113">An Intelligent Speaker includes a special seven-microphone array.</span></span> <span data-ttu-id="3d80e-114">システムは、音声プロファイル情報を使用して、会議室で最大 10 人の音声を識別します。</span><span class="sxs-lookup"><span data-stu-id="3d80e-114">The system uses voice profile information to identify voices of up to 10 people in meeting rooms.</span></span>

<span data-ttu-id="3d80e-115">インテリジェント スピーカーの要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3d80e-115">The following items are Intelligent Speaker requirements:</span></span>

- <span data-ttu-id="3d80e-116">顧客テナントは米国 (北米) にある必要があります。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3d80e-116">The customer tenant must be located in the U.S. (North America).<sup>1</sup></span></span>
- <span data-ttu-id="3d80e-117">会議室には、最大 10 人の人が出席する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d80e-117">The meeting room should have a maximum of 10 people present in person.</span></span>
- <span data-ttu-id="3d80e-118">会議室には、7 Mbps 以上のアップロード リンクがあります。</span><span class="sxs-lookup"><span data-stu-id="3d80e-118">The meeting room has an upload link of minimum 7 Mbps.</span></span>

 <span data-ttu-id="3d80e-119"><sup>1</sup> インテリジェント スピーカーおよび関連する音声プロファイルと使用状況は、EN-US 言語および米国 (NA-US リージョン) テナントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-119"><sup>1</sup> An Intelligent Speaker and associated voice profile and usage will only be available in EN-US language and for US (NA-US region) tenants.</span></span> <span data-ttu-id="3d80e-120">テナント ユーザーが属性付き文字起こしにインテリジェント スピーカーを登録して使用するには、両方の条件が満たされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d80e-120">Both conditions must be true for a tenant user to enroll and use an Intelligent Speaker for attributed transcription.</span></span>

## <a name="set-up-an-intelligent-speaker"></a><span data-ttu-id="3d80e-121">インテリジェント スピーカーを設定する</span><span class="sxs-lookup"><span data-stu-id="3d80e-121">Set up an Intelligent Speaker</span></span>

<span data-ttu-id="3d80e-122">インテリジェント スピーカーは、USB を使用して本体に直接接続Teams ミーティングします。</span><span class="sxs-lookup"><span data-stu-id="3d80e-122">An Intelligent Speaker connects directly using USB to the Teams Rooms console.</span></span> <span data-ttu-id="3d80e-123">最良の結果を得る場合は、Yealink ブランドの本体で Yealink ブランドのインテリジェント スピーカーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d80e-123">For best results, a Yealink brand Intelligent Speaker should be used with a Yealink brand console.</span></span>

> [!NOTE]
> <span data-ttu-id="3d80e-124">Yealink インテリジェントスピーカーは、Yealink 本体と一緒に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d80e-124">A Yealink Intelligent Speaker **must** be used with a Yealink console.</span></span>

> [!NOTE]
> <span data-ttu-id="3d80e-125">Logitech Surface Pro Microsoft Teams ミーティング に接続されたインテリジェント スピーカーはサポートSurface Pro Microsoft Teams ミーティング。</span><span class="sxs-lookup"><span data-stu-id="3d80e-125">We don't support an Intelligent Speaker connected to Logitech Surface Pro Microsoft Teams Rooms.</span></span> <span data-ttu-id="3d80e-126">ドックを介してインテリジェント スピーカー Teams ミーティング認識できないという既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="3d80e-126">There is a known issue that Teams Rooms can't recognize the Intelligent Speaker through the dock.</span></span>

<span data-ttu-id="3d80e-127">インテリジェント スピーカーは、壁やノート PC などの大きなオブジェクトから少なくとも 8 インチ (20 cm) 離れた場所に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d80e-127">An Intelligent Speaker should be placed at least 8 inches (20 cm) away from walls and large objects, such as laptops.</span></span> <span data-ttu-id="3d80e-128">インテリジェント スピーカー USB ケーブルがセットアップに十分な長みではない場合は、ケーブル 拡張器を使用します。</span><span class="sxs-lookup"><span data-stu-id="3d80e-128">If the Intelligent Speaker USB cable isn't long enough for your setup, use cable extenders.</span></span>

1. <span data-ttu-id="3d80e-129">管理者として本体にサインインします。</span><span class="sxs-lookup"><span data-stu-id="3d80e-129">Sign in to the console as administrator.</span></span>
2. <span data-ttu-id="3d80e-130">インテリジェント スピーカー Teamsスピーカーに合わせて、デバイスの設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="3d80e-130">Set the Teams device settings to match the Intelligent Speaker microphone and speaker.</span></span>
   <span data-ttu-id="3d80e-131">この操作は、ルーム コンソールではなく TAC ポータルから行う方法です。</span><span class="sxs-lookup"><span data-stu-id="3d80e-131">You can also do this through the TAC portal instead of at the room console.</span></span>

   <span data-ttu-id="3d80e-132">この図は、デバイスにデータ ボックスが含まれる場合にインテリジェント スピーカーがデバイスに接続される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3d80e-132">The diagram shows how the Intelligent Speaker is connected to the device if the device includes a data box.</span></span>

   ![<span data-ttu-id="3d80e-133">スピーカー、電源、データ ボックスを使用してインテリジェント スピーカーをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="3d80e-133">The Intelligent Speaker setup with the speaker, the power and data box.</span></span> <span data-ttu-id="3d80e-134">一方の行は本体の USB ポートに接続され、もう一方の行は電源に接続されます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-134">One line goes to the USB port of the console, and the other line goes to power.</span></span> ](../media/intelligent-speakers1.png)

   <span data-ttu-id="3d80e-135">この図は、デバイスにデータ ボックスが含されていない場合にインテリジェント スピーカーがデバイスに接続される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3d80e-135">The diagram shows how the Intelligent Speaker is connected to the device if the device doesn't include a data box.</span></span>

   ![<span data-ttu-id="3d80e-136">インテリジェント スピーカーは、スピーカーを本体に直接接続してセットアップします。</span><span class="sxs-lookup"><span data-stu-id="3d80e-136">The Intelligent Speaker setup with the speaker connecting directly to the console.</span></span> ](../media/intelligent-speakers2.png)

> [!Note]
> <span data-ttu-id="3d80e-137">EPOS デバイスと Yealink デバイスは、"EPOS" または "Yealink" プレフィックスを持ち、スピーカー名に "UAC2_RENDER" を、マイク名に "UAC2_TEAMS" を含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d80e-137">EPOS and Yealink devices should have "EPOS" or "Yealink" prefix and contain "UAC2_RENDER" in the speaker name and "UAC2_TEAMS" in the microphone name.</span></span> <span data-ttu-id="3d80e-138">これらのマイクとスピーカーの名前がドロップダウン メニューに見当たらない場合は、インテリジェント スピーカー デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="3d80e-138">If you don't find these microphone and speaker names in the dropdown menu, restart the Intelligent Speaker device.</span></span>

## <a name="enable-an-intelligent-speaker-user-recognition"></a><span data-ttu-id="3d80e-139">インテリジェント スピーカーのユーザー認識を有効にする</span><span class="sxs-lookup"><span data-stu-id="3d80e-139">Enable an Intelligent Speaker user recognition</span></span>

<span data-ttu-id="3d80e-140">音声プロファイル データは、インテリジェント スピーカーとの任意の会議で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-140">Voice profile data can be used in any meeting with an Intelligent Speaker.</span></span> <span data-ttu-id="3d80e-141">会議[Teams設定の詳細については、「会議ポリシー](../meeting-policies-in-teams.md#allow-transcription)と[PowerShell](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)会議コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d80e-141">See [Teams meetings policies](../meeting-policies-in-teams.md#allow-transcription) and the [PowerShell meeting cmdlets](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) for information on the meeting settings.</span></span>

<span data-ttu-id="3d80e-142">ユーザーの音声プロファイル データは、会議中にポリシーが区別または非会議の招待者のウォークインに設定されている場合に作成されます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-142">The voice profile data of the user is created when the policy is set to distinguish or a non-meeting invitee walks in during the meeting.</span></span> <span data-ttu-id="3d80e-143">音声プロファイル データは、会議の最後に閉じ込めされます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-143">The voice profile data is dismissed at the end of the meeting.</span></span>

<span data-ttu-id="3d80e-144">インテリジェント スピーカーとユーザー認識を設定するために必要なポリシーを次に示します。</span><span class="sxs-lookup"><span data-stu-id="3d80e-144">The following are the required policies to set an Intelligent Speaker and user recognition.</span></span>

|<span data-ttu-id="3d80e-145">ポリシー</span><span class="sxs-lookup"><span data-stu-id="3d80e-145">Policy</span></span>|<span data-ttu-id="3d80e-146">説明</span><span class="sxs-lookup"><span data-stu-id="3d80e-146">Description</span></span>|<span data-ttu-id="3d80e-147">値と動作</span><span class="sxs-lookup"><span data-stu-id="3d80e-147">Values and Behavior</span></span>|
|-|-|-|
|<span data-ttu-id="3d80e-148">enrollUserOverride</span><span class="sxs-lookup"><span data-stu-id="3d80e-148">enrollUserOverride</span></span>|<span data-ttu-id="3d80e-149">を使用して、テナントの音声プロファイルキャプチャまたは登録Teams設定を行います。</span><span class="sxs-lookup"><span data-stu-id="3d80e-149">Use to set voice profile capture, or enrollment, in Teams settings for a tenant.</span></span> |<span data-ttu-id="3d80e-150">**無効**</span><span class="sxs-lookup"><span data-stu-id="3d80e-150">**Disabled**</span></span><br><ul><li> <span data-ttu-id="3d80e-151">登録したことがないユーザーは、表示、登録、または再登録を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d80e-151">Users who have never enrolled can't view, enroll, or re-enroll.</span></span><li><span data-ttu-id="3d80e-152">登録フローへのエントリ ポイントは非表示になります。</span><span class="sxs-lookup"><span data-stu-id="3d80e-152">The entry point to the enrollment flow will be hidden.</span></span><li><span data-ttu-id="3d80e-153">ユーザーが登録ページへのリンクを選択すると、組織でこの機能が有効になっていないというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-153">If users select a link to the enrollment page, they'll see a message that states this feature isn't enabled for their organization.</span></span>  <li><span data-ttu-id="3d80e-154">登録したユーザーは、ユーザー設定で自分の音声プロファイルを表示およびTeamsできます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-154">Users who have enrolled can view and remove their voice profile in the Teams settings.</span></span> <span data-ttu-id="3d80e-155">音声プロファイルを削除すると、登録フローを表示、アクセス、または完了する機能は使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-155">Once they remove their voice profile, they won't be able to view, access, or complete the enrollment flow.</span></span></li></ul><br><span data-ttu-id="3d80e-156">**有効**</span><span class="sxs-lookup"><span data-stu-id="3d80e-156">**Enabled**</span></span><br><ul><li> <span data-ttu-id="3d80e-157">ユーザーは登録フローを表示、アクセス、完了できます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-157">Users can view, access, and complete the enrollment flow.</span></span><li><span data-ttu-id="3d80e-158">エントリ ポイントは、[認識] タブTeams設定ページに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-158">The entry point will show on Teams settings page under the **Recognition** tab.</span></span></li></ul>|
|<span data-ttu-id="3d80e-159">roomAttributeUserOverride</span><span class="sxs-lookup"><span data-stu-id="3d80e-159">roomAttributeUserOverride</span></span>|<span data-ttu-id="3d80e-160">会議室で音声ベースのユーザー ID を制御します。</span><span class="sxs-lookup"><span data-stu-id="3d80e-160">Control the voice-based user identification in meeting rooms.</span></span> <span data-ttu-id="3d80e-161">この設定は、アカウントのTeams ミーティングです。</span><span class="sxs-lookup"><span data-stu-id="3d80e-161">This setting is required for Teams Rooms accounts.</span></span>| <span data-ttu-id="3d80e-162">**オフ**</span><span class="sxs-lookup"><span data-stu-id="3d80e-162">**Off**</span></span><br><ul><li><span data-ttu-id="3d80e-163">デバイスTeams ミーティング、部屋からオーディオ ストリームを節約する帯域幅を送信しない。</span><span class="sxs-lookup"><span data-stu-id="3d80e-163">The Teams Rooms device won't send audio stream-saving bandwidth from the room.</span></span> <li><span data-ttu-id="3d80e-164">会議室のユーザーは属性付けも区別もされません。また、音声署名を取得したり使用したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3d80e-164">Meeting room users won't be attributed or distinguished, and their voice signatures won't be retrieved or used at all.</span></span><li><span data-ttu-id="3d80e-165">会議室のユーザーは不明です。</span><span class="sxs-lookup"><span data-stu-id="3d80e-165">Meeting room users are unknown.</span></span></li></ul> <br><span data-ttu-id="3d80e-166">**属性**</span><span class="sxs-lookup"><span data-stu-id="3d80e-166">**Attribute**</span></span><br><ul><li><span data-ttu-id="3d80e-167">ルームユーザーは、登録状態に基づいて属性付けされます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-167">Rooms users will be attributed based on their enrollment status.</span></span><li><span data-ttu-id="3d80e-168">登録されているユーザーは、文字起こしに自分の名前で表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-168">Users who are enrolled are shown with their name in the transcription.</span></span>  <li><span data-ttu-id="3d80e-169">登録されていないユーザーは、Speaker n として表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-169">Users who aren't enrolled show as Speaker n.</span></span><li><span data-ttu-id="3d80e-170">デバイスTeams ミーティング、部屋から 7 つのオーディオ ストリームを送信します。</span><span class="sxs-lookup"><span data-stu-id="3d80e-170">The Teams Rooms device will send seven audio streams from the room.</span></span></ul> <br><span data-ttu-id="3d80e-171">**識別**</span><span class="sxs-lookup"><span data-stu-id="3d80e-171">**Distinguish**</span></span><br> <span data-ttu-id="3d80e-172">*この設定は、後日使用できます。*</span><span class="sxs-lookup"><span data-stu-id="3d80e-172">*This setting will be available at a later date.*</span></span>|
|<span data-ttu-id="3d80e-173">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="3d80e-173">AllowTranscription</span></span>|<span data-ttu-id="3d80e-174">ユーザー アカウントと会議室アカウントTeams必要です。</span><span class="sxs-lookup"><span data-stu-id="3d80e-174">Required for user and Teams rooms accounts.</span></span>|<span data-ttu-id="3d80e-175">**True** と **False**</span><span class="sxs-lookup"><span data-stu-id="3d80e-175">**True** and **False**</span></span>|
||||

<span data-ttu-id="3d80e-176">[Teamsセンターで、[文字起こしを許可する **] ポリシーを設定** します。</span><span class="sxs-lookup"><span data-stu-id="3d80e-176">In the Teams admin center, set the **Allow transcription** policy.</span></span> <span data-ttu-id="3d80e-177">設定既定 **ではオフ** になっています。</span><span class="sxs-lookup"><span data-stu-id="3d80e-177">Settings are **Off** by default.</span></span>

![[会議ポリシー] が強調表示され、[文字起こしを許可する] が選択されている管理センター](../media/allow-transcription1.png)

## <a name="frequently-asked-questions-faq"></a><span data-ttu-id="3d80e-179">よく寄せられる質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="3d80e-179">Frequently asked questions (FAQ)</span></span>

<span data-ttu-id="3d80e-180">**音声プロファイル データはどこに保存されますか。**</span><span class="sxs-lookup"><span data-stu-id="3d80e-180">**Where is the voice profile data stored?**</span></span>

<span data-ttu-id="3d80e-181">音声プロファイル データは、ユーザー コンテンツOffice 365クラウドに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-181">Voice profile data is stored in Office 365 cloud with user content.</span></span>

<span data-ttu-id="3d80e-182">**リテンション期間のタイムラインとポリシーは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="3d80e-182">**What is the retention timeline and policy?**</span></span>

<span data-ttu-id="3d80e-183">一般的なリテンション期間ポリシーについては、「データリテンション期間の概要 [」を参照してください](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)。</span><span class="sxs-lookup"><span data-stu-id="3d80e-183">General retention policy is stated in the [Data retention overview](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).</span></span> <span data-ttu-id="3d80e-184">さらに、ユーザーの音声プロファイル データは、その 3 年間のインテリジェント スピーカーとの会議にユーザーが招待されていない場合、3 年後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-184">In addition, a user's voice profile data will be deleted after 3 years  if the user isn't invited to any meetings with an Intelligent Speaker within that 3-year period.</span></span> <span data-ttu-id="3d80e-185">既存の従業員の会議では、データは使用されません。</span><span class="sxs-lookup"><span data-stu-id="3d80e-185">Data isn't used in any meetings for existing employees.</span></span> <span data-ttu-id="3d80e-186">従業員が会社を離した場合、音声プロファイル データはユーザー コンテンツと見なされ、データ保持の概要 に記載されている Office 365 データ保持ポリシーに従って処理[されます](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)。</span><span class="sxs-lookup"><span data-stu-id="3d80e-186">If an employee has left the company, voice profile data is considered user content and is treated as such per Office 365 data retention policy described in the [Data retention overview](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="3d80e-187">**音声プロファイル データは、複数のネットワークでMicrosoft サービス。**</span><span class="sxs-lookup"><span data-stu-id="3d80e-187">**Is voice profile data used across Microsoft services?**</span></span>

<span data-ttu-id="3d80e-188">いいえ。音声プロファイル データは、ユーザーが同意した目的でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-188">No, voice profile data is only used for the purpose for which the user has provided consent.</span></span> <span data-ttu-id="3d80e-189">Microsoft では、音声プロファイル データは、音声認識シナリオ以外Teams使用しません。</span><span class="sxs-lookup"><span data-stu-id="3d80e-189">Microsoft will not use the voice profile data except within Teams voice recognition scenarios.</span></span>

<span data-ttu-id="3d80e-190">たとえば、次のような状況では、Microsoft はデータを使用しません。</span><span class="sxs-lookup"><span data-stu-id="3d80e-190">For example, Microsoft won't use the data in the following situations:</span></span>

<span data-ttu-id="3d80e-191">**音声プロファイル データは、別の組織の会議に参加するときに使用されますか?**</span><span class="sxs-lookup"><span data-stu-id="3d80e-191">**Is my voice profile data used when I join a meeting in another organization?**</span></span>

<span data-ttu-id="3d80e-192">組織内のユーザーが開催した会議でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-192">No only in meetings organized by a user in your organization.</span></span>

<span data-ttu-id="3d80e-193">**音声プロファイルをエクスポートする方法**</span><span class="sxs-lookup"><span data-stu-id="3d80e-193">**How can I export my voice profile?**</span></span>

<span data-ttu-id="3d80e-194">IT 管理者は、いつでもオーディオ データをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="3d80e-194">Your IT admin can export your audio data at any time.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3d80e-195">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3d80e-195">Related topics</span></span>

[<span data-ttu-id="3d80e-196">サポート記事: インテリジェント スピーカーを使用して部屋の参加者を識別する </span><span class="sxs-lookup"><span data-stu-id="3d80e-196">Support article: Use Intelligent Speakers to Identify in-room participants </span></span>](https://support.microsoft.com/office/use-teams-intelligent-speakers-to-identify-in-room-participants-in-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00)
