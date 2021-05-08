---
title: 中小企業向けに音声会議を設定する
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: '電話を使って会議にコールインする必要があるユーザーのために、中小企業で電話会議を設定する方法について説明します。 '
ms.openlocfilehash: e7a3461453255a7a61f6a1095e9cb9697070771c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122351"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="526c8-103">中小企業向けに音声会議を設定する</span><span class="sxs-lookup"><span data-stu-id="526c8-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="526c8-104">電話会議では、モバイル デバイスやコンピューターで Teams アプリを使用する代わりに、電話を使って Teams 会議にコールインできます。</span><span class="sxs-lookup"><span data-stu-id="526c8-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="526c8-105">最大 300 人のユーザーを含む中小企業で、現在電話会議ライセンスを持ってない場合は、電話会議を 1 年間無料で利用できます。</span><span class="sxs-lookup"><span data-stu-id="526c8-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="526c8-106">この無料オファーは、2020 年 10 月 1 日から利用できます。</span><span class="sxs-lookup"><span data-stu-id="526c8-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="526c8-107">電話会議アドオン ライセンスは、Microsoft 365 Business Basic、Business Standard、Business プレミアム、Enterprise E1、または Enterprise E3 ライセンスを持つユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="526c8-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="526c8-108">詳細については、「Teams[ライセンス」を参照してください。](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="526c8-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="526c8-109">E5 または EnterpriseをMicrosoft 365 Business Voice場合、これらのライセンスには既に電話会議が含まれるため、無料の電話会議オファーを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="526c8-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="526c8-110">この記事では、電話会議を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="526c8-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="526c8-111">電話会議のセットアップは、ミーティングのスケジュールを設定するユーザーまたはミーティングを主催するユーザーにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="526c8-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="526c8-112">会議にコールインする会議出席者は、ライセンスや他のセットアップを必要としません。</span><span class="sxs-lookup"><span data-stu-id="526c8-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="526c8-113">詳細については、「電話会議」 [を参照してください](audio-conferencing-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="526c8-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="set-up-audio-conferencing"></a><span data-ttu-id="526c8-114">電話会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="526c8-114">Set up Audio Conferencing</span></span>

<span data-ttu-id="526c8-115">電話会議を設定すると、電話番号が会議ブリッジに自動的に割り当てられるので、会議出席依頼で使用できます。</span><span class="sxs-lookup"><span data-stu-id="526c8-115">When you set up Audio Conferencing, a phone number is automatically assigned to your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="526c8-116">会議ブリッジの既定の番号として割り当てられている電話番号は、組織の国または地域の電話番号になります。</span><span class="sxs-lookup"><span data-stu-id="526c8-116">The phone number that's assigned as the default number of your conferencing bridge will be one from the country or region of your organization.</span></span> <span data-ttu-id="526c8-117">この電話番号は有料電話番号で、長距離料金が適用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="526c8-117">This phone number is a toll number, in which long-distance charges may apply.</span></span>

> [!NOTE]
> <span data-ttu-id="526c8-118">無料電話番号を使用する場合も、いくつかの追加の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="526c8-118">You can also use a toll-free number, which requires a few additional steps.</span></span> <span data-ttu-id="526c8-119">会議ブリッジの電話番号の詳細については、この記事の後半の [「電話会議の電話番号](#audio-conferencing-phone-numbers) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="526c8-119">To learn more about phone numbers for your conferencing bridge, see [Audio Conferencing phone numbers](#audio-conferencing-phone-numbers) later in this article.</span></span>

### <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="526c8-120">手順 1: 電話会議ライセンスを取得する</span><span class="sxs-lookup"><span data-stu-id="526c8-120">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="526c8-121">会議を開催するユーザーごとに 1 つの電話会議ライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="526c8-121">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="526c8-122">これを行うにはMicrosoft 365管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="526c8-122">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="526c8-123">管理センター Microsoft 365、[**課金** 購入サービス] に移動し、ページの下部にある [アドオン  >  ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="526c8-123">In the Microsoft 365 admin center, go to **Billing** > **Purchase services**, and then at the bottom of the page, select **Add-ons**.</span></span>
2. <span data-ttu-id="526c8-124">[**電話Microsoft 365導入プロモーション** の詳細] を  >  **選択し**、[今すぐ取得]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="526c8-124">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details**, and then select **Get now**.</span></span>
3. <span data-ttu-id="526c8-125">会議の開催者に必要なライセンス数を入力し、注文を完了します。</span><span class="sxs-lookup"><span data-stu-id="526c8-125">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="電話会議導入プロモーション ライセンスのスクリーンショット":::

    > [!NOTE]
    > <span data-ttu-id="526c8-127">このライセンスを持たなかったすべてのユーザーに電話会議ライセンスを自動的に割り当てるかどうかに応じて、[ライセンスを持たなかったすべてのユーザーに自動的に割り当てる] をオフまたは選択します。</span><span class="sxs-lookup"><span data-stu-id="526c8-127">Clear or select the **Automatically assign to all of your users with no licenses**, depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="526c8-128">手順 2: 会議を開催するユーザーに電話会議ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="526c8-128">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="526c8-129">会議を開催する各ユーザーにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="526c8-129">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="526c8-130">これを行うにはMicrosoft 365管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="526c8-130">Use the Microsoft 365 admin center to do this.</span></span>

#### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="526c8-131">1 人のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="526c8-131">Assign a license to one user</span></span>

1. <span data-ttu-id="526c8-132">管理センター Microsoft 365、[ユーザー] [アクティブなユーザー]  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="526c8-132">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="526c8-133">ライセンスを割り当てるユーザーの行を選択し、ウィンドウで [ライセンスとアプリ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="526c8-133">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="526c8-134">[電話会議 **Microsoft 365] チェック ボックス** をオンにし、[変更の保存]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="526c8-134">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>

#### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="526c8-135">複数のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="526c8-135">Assign a license to multiple users</span></span>

1. <span data-ttu-id="526c8-136">管理センター Microsoft 365、[ユーザー] [アクティブなユーザー]  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="526c8-136">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="526c8-137">ライセンスを割り当てるユーザーの横にある円を選択し、[製品ライセンスの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="526c8-137">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="526c8-138">[製品ライセンス **の管理] ウィンドウで、[** さらに割り当てる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="526c8-138">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="526c8-139">[電話会議 **Microsoft 365] チェック ボックス** をオンにし、[変更の保存]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="526c8-139">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="schedule-teams-meetings-in-outlook"></a><span data-ttu-id="526c8-140">会議Teamsスケジュールを設定Outlook</span><span class="sxs-lookup"><span data-stu-id="526c8-140">Schedule Teams meetings in Outlook</span></span>

<span data-ttu-id="526c8-141">会議の開催者は、会議のスケジュールを設定Outlook。</span><span class="sxs-lookup"><span data-stu-id="526c8-141">Your meeting organizers can now schedule meetings in Outlook.</span></span> <span data-ttu-id="526c8-142">[Outlook] に移動 **し**、[会議の新規Teams **選択** します。</span><span class="sxs-lookup"><span data-stu-id="526c8-142">In Outlook, go to **Calendar**, and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="526c8-143">会議のダイヤルイン番号と会議 ID は、会議の出席者に送信される会議出席依頼に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="526c8-143">The meeting dial-in numbers and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span> <span data-ttu-id="526c8-144">詳細については、「会議のスケジュール[を設定する」Teamsを参照Outlook。](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)</span><span class="sxs-lookup"><span data-stu-id="526c8-144">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="526c8-145">必要に応じて、会議出席依頼をカスタマイズして、会社のロゴ、サポート Web サイトへのリンク、免責事項、テキストのみフッターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="526c8-145">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="526c8-146">詳細については、「会議出席依頼を [カスタマイズする」を参照してください](meeting-settings-in-teams.md#customize-meeting-invitations)。</span><span class="sxs-lookup"><span data-stu-id="526c8-146">To learn more, see [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="audio-conferencing-phone-numbers"></a><span data-ttu-id="526c8-147">電話会議の電話番号</span><span class="sxs-lookup"><span data-stu-id="526c8-147">Audio Conferencing phone numbers</span></span>

<span data-ttu-id="526c8-148">会議ブリッジに使用できる番号には、2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="526c8-148">There are two types of numbers that you can use for your conferencing bridge.</span></span> <span data-ttu-id="526c8-149">共有番号 (この記事 **の**「電話会議 [](#set-up-audio-conferencing)の設定」セクションで説明したように) または専用の番号を **使用できます**。</span><span class="sxs-lookup"><span data-stu-id="526c8-149">You can use either **shared numbers** (as in the [Set up Audio Conferencing](#set-up-audio-conferencing) section earlier in this article) or **dedicated numbers**.</span></span> <span data-ttu-id="526c8-150">それぞれの詳細を次に示します。</span><span class="sxs-lookup"><span data-stu-id="526c8-150">Here's more information about each.</span></span>

### <a name="shared-numbers"></a><span data-ttu-id="526c8-151">共有番号</span><span class="sxs-lookup"><span data-stu-id="526c8-151">Shared numbers</span></span>

<span data-ttu-id="526c8-152">共有番号は、すべての組織で共有される番号です。</span><span class="sxs-lookup"><span data-stu-id="526c8-152">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="526c8-153">共有番号は有料電話番号であり、電話会議を設定すると自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="526c8-153">Shared numbers are toll numbers and are automatically assigned when you set up Audio Conferencing.</span></span>

<span data-ttu-id="526c8-154">会議ブリッジに割り当てられている既定の番号を表示するには、Microsoft Teams 管理センターの左側のナビゲーションで、[会議会議ブリッジ] に移動し、最も近い場所の番号を見つけて確認します。  >  </span><span class="sxs-lookup"><span data-stu-id="526c8-154">To see the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**, and then find the number for the location that's nearest to you.</span></span>

### <a name="dedicated-numbers"></a><span data-ttu-id="526c8-155">専用番号</span><span class="sxs-lookup"><span data-stu-id="526c8-155">Dedicated numbers</span></span>

<span data-ttu-id="526c8-156">専用の番号は、ユーザーだけが使用できる数値です。</span><span class="sxs-lookup"><span data-stu-id="526c8-156">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="526c8-157">専用の番号には、有料電話番号または無料電話番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="526c8-157">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="526c8-158">専用の番号を使用するには、まず番号を取得し、会議ブリッジに割り当て、会議を開催する各ユーザーに番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="526c8-158">To use a dedicated number, you'll have to first get the number, assign it to your conferencing bridge, and then assign the number to each person who will lead meetings.</span></span>

<span data-ttu-id="526c8-159">専用の番号を取得するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="526c8-159">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="526c8-160">Microsoft から番号を取得するか、既存の番号を現在のサービス プロバイダーから Microsoft に転送 (ポート) することができます。</span><span class="sxs-lookup"><span data-stu-id="526c8-160">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="526c8-161">これを行う方法の詳細については、サービス番号の取得 [に関するページを参照してください](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="526c8-161">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="526c8-162">無料電話番号を使用する場合は、会議を開催する各ユーザーにコミュニケーション クレジット ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="526c8-162">Keep in mind that if you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="526c8-163">詳細については、「組織の通信 [クレジットを設定する」を参照してください](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="526c8-163">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="526c8-164">番号を作成した後、それを会議ブリッジに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="526c8-164">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="526c8-165">これを行うにはMicrosoft Teams管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="526c8-165">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="526c8-166">管理センターの左側のナビゲーションMicrosoft Teams会議ブリッジ]**に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="526c8-166">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="526c8-167">[追加 **]** を選択し、[有料電話番号] **または [** 無料電話番号] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="526c8-167">Select **Add**, and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="526c8-168">[電話番号 **の追加] ウィンドウで** 番号を選択し、[適用] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="526c8-168">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

<span data-ttu-id="526c8-169">次に、会議を開催する各ユーザーに番号を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="526c8-169">Then, assign the number to each person who will lead meetings.</span></span> <span data-ttu-id="526c8-170">これを行うにはMicrosoft Teams管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="526c8-170">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="526c8-171">管理センターの左側のナビゲーションMicrosoft Teams、[ユーザー] を選択し、ユーザーの表示名をクリックして、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="526c8-171">In the left navigation of the Microsoft Teams admin center, select **Users**, click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="526c8-172">[**電話会議**]**の横** にある [編集] を選択し、[電話会議] ウィンドウで [有料電話番号] または [無料電話番号] リストで番号を選択し、[適用] を **選択します**。 </span><span class="sxs-lookup"><span data-stu-id="526c8-172">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="526c8-173">関連トピック</span><span class="sxs-lookup"><span data-stu-id="526c8-173">Related topics</span></span>

- [<span data-ttu-id="526c8-174">電話会議</span><span class="sxs-lookup"><span data-stu-id="526c8-174">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="526c8-175">会議の電話会議を設定Teams</span><span class="sxs-lookup"><span data-stu-id="526c8-175">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="526c8-176">電話会議の電話番号</span><span class="sxs-lookup"><span data-stu-id="526c8-176">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
- [<span data-ttu-id="526c8-177">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="526c8-177">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="526c8-178">サービス番号の取得</span><span class="sxs-lookup"><span data-stu-id="526c8-178">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="526c8-179">Teams アドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="526c8-179">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="526c8-180">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="526c8-180">Assign licenses to users</span></span>](/microsoft-365/admin/manage/assign-licenses-to-users)