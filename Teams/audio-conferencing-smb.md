---
title: 中小企業向け電話会議をセットアップする
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
ms.openlocfilehash: 80e372e62ffdac9907521eb9426b465c9d0b6e92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821287"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="c9f1e-103">中小企業向け電話会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="c9f1e-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="c9f1e-104">電話会議では、モバイル デバイスやコンピューターから Teams アプリを使用する代わりに、電話を使って Teams 会議にコールインできます。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="c9f1e-105">最大 300 人のユーザーを持つ中小企業で、現在電話会議のライセンスを持っている場合は、電話会議を 1 年間無料で利用できます。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="c9f1e-106">この無料特典は、2020 年 10 月 1 日から利用できます。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="c9f1e-107">電話会議アドオン ライセンスは、Microsoft 365 Business Basic、Business Standard、Business Premium、Enterprise E1、または Enterprise E3 のライセンスを持つユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="c9f1e-108">詳細については、「Teams アドオン ライセンス [」を参照してください。](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="c9f1e-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="c9f1e-109">Enterprise E5 または Microsoft 365 Business Voice を使用している場合、これらのライセンスには電話会議が既に含まれるため、無料の電話会議サービスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="c9f1e-110">この記事では、電話会議のセットアップ方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="c9f1e-111">電話会議のセットアップは、ミーティングのスケジュールを設定するユーザーまたはミーティングを主催するユーザーにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="c9f1e-112">会議にコールインする会議の出席者は、ライセンスや他のセットアップを必要としません。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="c9f1e-113">詳細については、「電話会議 [」を参照してください](audio-conferencing-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="set-up-audio-conferencing"></a><span data-ttu-id="c9f1e-114">電話会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="c9f1e-114">Set up Audio Conferencing</span></span>

<span data-ttu-id="c9f1e-115">電話会議をセットアップすると、電話番号が会議ブリッジに自動的に割り当てられるので、会議出席依頼で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-115">When you set up Audio Conferencing, a phone number is automatically assigned to your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="c9f1e-116">会議ブリッジの既定の番号として割り当てられている電話番号は、組織の国または地域の電話番号になります。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-116">The phone number that's assigned as the default number of your conferencing bridge will be one from the country or region of your organization.</span></span> <span data-ttu-id="c9f1e-117">この電話番号は有料電話番号で、長距離料金が適用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-117">This phone number is a toll number, in which long-distance charges may apply.</span></span>

> [!NOTE]
> <span data-ttu-id="c9f1e-118">無料電話番号を使用する場合も、いくつかの追加手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-118">You can also use a toll-free number, which requires a few additional steps.</span></span> <span data-ttu-id="c9f1e-119">会議ブリッジの電話番号の詳細については、この記事の後半にある [電話会議の](#audio-conferencing-phone-numbers) 電話番号を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-119">To learn more about phone numbers for your conferencing bridge, see [Audio Conferencing phone numbers](#audio-conferencing-phone-numbers) later in this article.</span></span>

### <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="c9f1e-120">手順 1: 電話会議ライセンスを取得する</span><span class="sxs-lookup"><span data-stu-id="c9f1e-120">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="c9f1e-121">会議を開催するユーザーごとに 1 つの電話会議ライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-121">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="c9f1e-122">これを行うには、Microsoft 365 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-122">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="c9f1e-123">Microsoft 365 管理センターで、[課金購入サービス] に移動し、ページの下部にある [アドオン]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-123">In the Microsoft 365 admin center, go to **Billing** > **Purchase services**, and then at the bottom of the page, select **Add-ons**.</span></span>
2. <span data-ttu-id="c9f1e-124">**Microsoft 365 電話会議導入プロモーション** の詳細を選択し、[今すぐ取得]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-124">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details**, and then select **Get now**.</span></span>
3. <span data-ttu-id="c9f1e-125">会議の開催者に必要なライセンスの数を入力し、注文を完了します。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-125">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="電話会議導入プロモーション ライセンスのスクリーンショット":::

    > [!NOTE]
    > <span data-ttu-id="c9f1e-127">このライセンスを持たなかったすべてのユーザーに電話会議ライセンスを自動的に割り当てるかどうかに応じて、[ライセンスを持たなかったすべてのユーザーに自動的に割り当てる] をオフまたは選択します。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-127">Clear or select the **Automatically assign to all of your users with no licenses**, depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="c9f1e-128">手順 2: 会議を開催するユーザーに電話会議ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c9f1e-128">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="c9f1e-129">会議を開催する各ユーザーにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-129">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="c9f1e-130">これを行うには、Microsoft 365 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-130">Use the Microsoft 365 admin center to do this.</span></span>

#### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="c9f1e-131">1 人のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c9f1e-131">Assign a license to one user</span></span>

1. <span data-ttu-id="c9f1e-132">Microsoft 365 管理センターで、[アクティブなユーザー]**に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-132">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="c9f1e-133">ライセンスを割り当てるユーザーの行を選択し、ウィンドウで [ライセンスとアプリ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-133">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="c9f1e-134">**[Microsoft 365 電話会議] チェック** ボックスをオンにし、[変更の保存]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-134">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>

#### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="c9f1e-135">複数のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c9f1e-135">Assign a license to multiple users</span></span>

1. <span data-ttu-id="c9f1e-136">Microsoft 365 管理センターで、[アクティブなユーザー]**に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-136">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="c9f1e-137">ライセンスを割り当てるユーザーの横にある円を選択し、[製品ライセンスの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-137">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="c9f1e-138">[製品ライセンス **の管理] ウィンドウで、[** 追加の割り当 **て] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-138">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="c9f1e-139">**[Microsoft 365 電話会議] チェック** ボックスをオンにし、[変更の保存]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-139">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="schedule-teams-meetings-in-outlook"></a><span data-ttu-id="c9f1e-140">Outlook で Teams 会議をスケジュールする</span><span class="sxs-lookup"><span data-stu-id="c9f1e-140">Schedule Teams meetings in Outlook</span></span>

<span data-ttu-id="c9f1e-141">会議の開催者は、Outlook で会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-141">Your meeting organizers can now schedule meetings in Outlook.</span></span> <span data-ttu-id="c9f1e-142">Outlook で [予定表] に **移動** し、[新しい Teams 会議] **ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-142">In Outlook, go to **Calendar**, and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="c9f1e-143">会議のダイヤルイン番号と会議 ID は、会議の出席者に送信される会議出席依頼に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-143">The meeting dial-in numbers and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span> <span data-ttu-id="c9f1e-144">詳細については、「Outlook で [Teams 会議をスケジュールする」を参照してください](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-144">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="c9f1e-145">必要に応じて、会議出席依頼をカスタマイズして、会社のロゴ、サポート Web サイトへのリンク、法的免責事項、テキストのみフッターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-145">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="c9f1e-146">詳細については、「会議出席依頼を [カスタマイズする」を参照してください](meeting-settings-in-teams.md#customize-meeting-invitations)。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-146">To learn more, see [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="audio-conferencing-phone-numbers"></a><span data-ttu-id="c9f1e-147">電話会議の電話番号</span><span class="sxs-lookup"><span data-stu-id="c9f1e-147">Audio Conferencing phone numbers</span></span>

<span data-ttu-id="c9f1e-148">会議ブリッジに使用できる番号には、2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-148">There are two types of numbers that you can use for your conferencing bridge.</span></span> <span data-ttu-id="c9f1e-149">共有番号 **(この** 記事の「電話会議 [](#set-up-audio-conferencing)の設定」セクションに示す) または専用の **番号を使用できます**。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-149">You can use either **shared numbers** (as in the [Set up Audio Conferencing](#set-up-audio-conferencing) section earlier in this article) or **dedicated numbers**.</span></span> <span data-ttu-id="c9f1e-150">それぞれの詳細を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-150">Here's more information about each.</span></span>

### <a name="shared-numbers"></a><span data-ttu-id="c9f1e-151">共有番号</span><span class="sxs-lookup"><span data-stu-id="c9f1e-151">Shared numbers</span></span>

<span data-ttu-id="c9f1e-152">共有番号は、すべての組織で共有されている番号です。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-152">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="c9f1e-153">共有電話番号は有料電話番号で、電話会議を設定すると自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-153">Shared numbers are toll numbers and are automatically assigned when you set up Audio Conferencing.</span></span>

<span data-ttu-id="c9f1e-154">会議ブリッジに割り当てられている既定の番号を表示するには、Microsoft Teams 管理センターの左側のナビゲーションで [会議会議ブリッジ] に移動し、最も近い場所の番号を検索します。  >  </span><span class="sxs-lookup"><span data-stu-id="c9f1e-154">To see the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**, and then find the number for the location that's nearest to you.</span></span>

### <a name="dedicated-numbers"></a><span data-ttu-id="c9f1e-155">専用の番号</span><span class="sxs-lookup"><span data-stu-id="c9f1e-155">Dedicated numbers</span></span>

<span data-ttu-id="c9f1e-156">専用の番号は、ユーザーだけが利用できる数値です。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-156">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="c9f1e-157">専用の番号には、有料電話番号またはフリーダイヤル番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-157">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="c9f1e-158">専用の番号を使用するには、まず番号を取得し、それを会議ブリッジに割り当て、その番号を会議の開催者ごとに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-158">To use a dedicated number, you'll have to first get the number, assign it to your conferencing bridge, and then assign the number to each person who will lead meetings.</span></span>

<span data-ttu-id="c9f1e-159">専用の番号を取得するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-159">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="c9f1e-160">Microsoft から番号を取得するか、既存の番号を現在のサービス プロバイダーから Microsoft に転送 (ポート) することができます。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-160">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="c9f1e-161">この方法の詳細については、「サービス番号を取得する [」を参照してください](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-161">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="c9f1e-162">無料電話番号を使用する場合は、会議を開催する各ユーザーにコミュニケーション クレジット のライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-162">Keep in mind that if you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="c9f1e-163">詳細については、組織の [コミュニケーション クレジットのセットアップに関するページを参照してください](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-163">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="c9f1e-164">番号を作成した後、それを会議ブリッジに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-164">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="c9f1e-165">これを行うには、Microsoft Teams 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-165">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="c9f1e-166">Microsoft Teams 管理センターの左側のナビゲーションで、会議ブリッジ **に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-166">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="c9f1e-167">[追加 **]** を選択し、有料電話番号 **または** フリー **ダイヤル番号を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-167">Select **Add**, and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="c9f1e-168">[電話番号 **の追加] ウィンドウで** 番号を選択し、[適用] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-168">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

<span data-ttu-id="c9f1e-169">次に、会議を開催する各ユーザーに番号を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-169">Then, assign the number to each person who will lead meetings.</span></span> <span data-ttu-id="c9f1e-170">これを行うには、Microsoft Teams 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-170">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="c9f1e-171">Microsoft Teams 管理センターの左側のナビゲーションで、[ユーザー] を選択し、ユーザーの表示名をクリックして、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-171">In the left navigation of the Microsoft Teams admin center, select **Users**, click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="c9f1e-172">[**電話会議**]**の横** にある [編集]を選択し、[電話会議] ウィンドウで、有料電話番号または無料電話番号の一覧から番号を選択し、[適用] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1e-172">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c9f1e-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9f1e-173">Related topics</span></span>

- [<span data-ttu-id="c9f1e-174">電話会議</span><span class="sxs-lookup"><span data-stu-id="c9f1e-174">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="c9f1e-175">Teams の電話会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="c9f1e-175">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="c9f1e-176">電話会議の電話番号</span><span class="sxs-lookup"><span data-stu-id="c9f1e-176">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
- [<span data-ttu-id="c9f1e-177">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="c9f1e-177">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="c9f1e-178">サービス番号の取得</span><span class="sxs-lookup"><span data-stu-id="c9f1e-178">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="c9f1e-179">Teams アドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="c9f1e-179">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="c9f1e-180">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c9f1e-180">Assign licenses to users</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
