---
title: 中小規模企業向けの電話会議をセットアップする
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: '会議へのコールインに電話を使用する必要があるユーザー向けに、中小規模企業で電話会議を設定する方法について説明します。 '
ms.openlocfilehash: b692654a0a874ea0c07f074daefe203aef2f80bc
ms.sourcegitcommit: 764605e226bc7d9cf45e9833c758d30da29132c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2020
ms.locfileid: "48594648"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="be98d-103">中小規模企業向けの電話会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="be98d-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="be98d-104">電話会議を使用すると、ユーザーは、モバイルデバイスまたは自分のコンピューターから teams アプリを使っていなくても、電話を使用して Teams 会議にコールインすることができます。</span><span class="sxs-lookup"><span data-stu-id="be98d-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="be98d-105">中小規模企業で、最大300人のユーザーがいて、現在電話会議のライセンスを持っていない場合は、1年間は電話会議を無料で受けることができます。</span><span class="sxs-lookup"><span data-stu-id="be98d-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="be98d-106">この無料キャンペーンは、2020年10月1日から利用できます。</span><span class="sxs-lookup"><span data-stu-id="be98d-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="be98d-107">電話会議アドオンライセンスは、Microsoft 365 Business Basic、Business Standard、Business Premium、enterprise E1、Enterprise E3 のライセンスを所有しているユーザーに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="be98d-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="be98d-108">詳細については、「 [Teams アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be98d-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="be98d-109">Enterprise E5 または Microsoft 365 ビジネス Voip を使用している場合、これらのライセンスには電話会議が既に含まれているため、無料の電話会議プランは使用できません。</span><span class="sxs-lookup"><span data-stu-id="be98d-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="be98d-110">この記事では、電話会議をセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="be98d-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="be98d-111">電話会議のセットアップは、ミーティングのスケジュールを設定するユーザーまたはミーティングを主催するユーザーにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="be98d-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="be98d-112">会議へのコールインを行う会議出席者は、ライセンスまたはその他の設定を必要としません。</span><span class="sxs-lookup"><span data-stu-id="be98d-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="be98d-113">詳細については、「 [電話会議](audio-conferencing-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be98d-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="set-up-audio-conferencing"></a><span data-ttu-id="be98d-114">電話会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="be98d-114">Set up Audio Conferencing</span></span>

<span data-ttu-id="be98d-115">電話会議をセットアップすると、電話番号が会議の出席依頼で使用できるように、会議ブリッジに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="be98d-115">When you set up Audio Conferencing, a phone number is automatically assigned to your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="be98d-116">会議ブリッジの既定の番号として割り当てられている電話番号は、組織の国または地域のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="be98d-116">The phone number that's assigned as the default number of your conferencing bridge will be one from the country or region of your organization.</span></span> <span data-ttu-id="be98d-117">この電話番号は有料番号であり、長距離通話料金が適用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="be98d-117">This phone number is a toll number, in which long-distance charges may apply.</span></span>

> [!NOTE]
> <span data-ttu-id="be98d-118">また、無料番号を使用して、いくつかの手順を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be98d-118">You can also use a toll-free number, which requires a few additional steps.</span></span> <span data-ttu-id="be98d-119">会議ブリッジの電話番号の詳細については、この記事の後半の「 [電話会議の電話番号](#audio-conferencing-phone-numbers) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be98d-119">To learn more about phone numbers for your conferencing bridge, see [Audio Conferencing phone numbers](#audio-conferencing-phone-numbers) later in this article.</span></span>

### <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="be98d-120">手順 1: 電話会議ライセンスを取得する</span><span class="sxs-lookup"><span data-stu-id="be98d-120">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="be98d-121">会議を開催する各ユーザーに対して1つの電話会議ライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="be98d-121">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="be98d-122">この操作を行うには、Microsoft 365 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="be98d-122">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="be98d-123">Microsoft 365 管理センターで、[**課金**  >  **サービス**] に移動し、ページの下部にある [**アドオン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be98d-123">In the Microsoft 365 admin center, go to **Billing** > **Purchase services**, and then at the bottom of the page, select **Add-ons**.</span></span>
2. <span data-ttu-id="be98d-124">[ **Microsoft 365 電話会議の導入キャンペーン**の詳細] を選択し  >  **Details**、[**今すぐ取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be98d-124">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details**, and then select **Get now**.</span></span>
3. <span data-ttu-id="be98d-125">会議の開催者に必要なライセンスの数を入力して、注文を完了します。</span><span class="sxs-lookup"><span data-stu-id="be98d-125">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="電話会議の採用プロモーションライセンスのスクリーンショット":::

    > [!NOTE]
    > <span data-ttu-id="be98d-127">[このライセンスを持っていないすべてのユーザーに電話会議ライセンスを自動的に割り当てる] のいずれかを選択して、[ **ライセンスのないすべてのユーザーに自動的に割り当てる**] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="be98d-127">Clear or select the **Automatically assign to all of your users with no licenses**, depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="be98d-128">手順 2: 会議をリードするユーザーに電話会議ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="be98d-128">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="be98d-129">会議を開催する各ユーザーにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="be98d-129">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="be98d-130">この操作を行うには、Microsoft 365 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="be98d-130">Use the Microsoft 365 admin center to do this.</span></span>

#### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="be98d-131">1人のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="be98d-131">Assign a license to one user</span></span>

1. <span data-ttu-id="be98d-132">Microsoft 365 管理センターで、[アクティブな**ユーザー**] に移動  >  **Active users**します。</span><span class="sxs-lookup"><span data-stu-id="be98d-132">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="be98d-133">ライセンスを割り当てるユーザーの行を選び、ウィンドウで [ **ライセンスとアプリ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="be98d-133">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="be98d-134">[ **Microsoft 365 電話会議** ] チェックボックスをオンにして、[ **変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be98d-134">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>

#### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="be98d-135">複数のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="be98d-135">Assign a license to multiple users</span></span>

1. <span data-ttu-id="be98d-136">Microsoft 365 管理センターで、[アクティブな**ユーザー**] に移動  >  **Active users**します。</span><span class="sxs-lookup"><span data-stu-id="be98d-136">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="be98d-137">ライセンスを割り当てるユーザーの横にある円を選択し、[ **製品ライセンスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be98d-137">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="be98d-138">[ **製品ライセンスの管理** ] ウィンドウで、[ **その他の割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be98d-138">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="be98d-139">[ **Microsoft 365 電話会議** ] チェックボックスをオンにして、[ **変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be98d-139">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="schedule-teams-meetings-in-outlook"></a><span data-ttu-id="be98d-140">Outlook で Teams の会議をスケジュールする</span><span class="sxs-lookup"><span data-stu-id="be98d-140">Schedule Teams meetings in Outlook</span></span>

<span data-ttu-id="be98d-141">会議の開催者が Outlook で会議をスケジュールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="be98d-141">Your meeting organizers can now schedule meetings in Outlook.</span></span> <span data-ttu-id="be98d-142">Outlook で [ **予定表**] に移動し、[ **新しいチーム会議** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="be98d-142">In Outlook, go to **Calendar**, and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="be98d-143">会議のダイヤルイン番号と会議 ID が、会議出席者に送信された会議出席依頼に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="be98d-143">The meeting dial-in numbers and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span> <span data-ttu-id="be98d-144">詳細については、「 [Outlook で Teams 会議のスケジュールを設定](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be98d-144">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="be98d-145">必要に応じて、会議出席依頼をカスタマイズして、会社のロゴ、サポート web サイトおよび法的免責事項へのリンク、テキストのみのフッターを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="be98d-145">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="be98d-146">詳細については、「 [会議出席依頼をカスタマイズ](meeting-settings-in-teams.md#customize-meeting-invitations)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be98d-146">To learn more, see [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="audio-conferencing-phone-numbers"></a><span data-ttu-id="be98d-147">電話会議の電話番号</span><span class="sxs-lookup"><span data-stu-id="be98d-147">Audio Conferencing phone numbers</span></span>

<span data-ttu-id="be98d-148">電話会議ブリッジに使用できる番号には2種類あります。</span><span class="sxs-lookup"><span data-stu-id="be98d-148">There are two types of numbers that you can use for your conferencing bridge.</span></span> <span data-ttu-id="be98d-149">**共有番号**(この記事の前半の「[電話会議の設定](#set-up-audio-conferencing)」のセクションの場合)、または**専用の番号**を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="be98d-149">You can use either **shared numbers** (as in the [Set up Audio Conferencing](#set-up-audio-conferencing) section earlier in this article) or **dedicated numbers**.</span></span> <span data-ttu-id="be98d-150">それぞれの詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="be98d-150">Here's more information about each.</span></span>

### <a name="shared-numbers"></a><span data-ttu-id="be98d-151">共有番号</span><span class="sxs-lookup"><span data-stu-id="be98d-151">Shared numbers</span></span>

<span data-ttu-id="be98d-152">共有番号は、すべての組織で共有される番号です。</span><span class="sxs-lookup"><span data-stu-id="be98d-152">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="be98d-153">共有番号は有料番号で、電話会議のセットアップ時に自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="be98d-153">Shared numbers are toll numbers and are automatically assigned when you set up Audio Conferencing.</span></span>

<span data-ttu-id="be98d-154">会議ブリッジに割り当てられている既定の電話番号を確認するには、Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**  >  **会議ブリッジ**] に移動して、最寄りの場所の番号を見つけます。</span><span class="sxs-lookup"><span data-stu-id="be98d-154">To see the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**, and then find the number for the location that's nearest to you.</span></span>

### <a name="dedicated-numbers"></a><span data-ttu-id="be98d-155">専用電話番号</span><span class="sxs-lookup"><span data-stu-id="be98d-155">Dedicated numbers</span></span>

<span data-ttu-id="be98d-156">専用番号は、ユーザーだけが使用できる番号です。</span><span class="sxs-lookup"><span data-stu-id="be98d-156">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="be98d-157">専用電話番号には、有料番号または無料電話番号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="be98d-157">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="be98d-158">専用の番号を使用するには、最初に番号を取得し、それを会議ブリッジに割り当てる必要があります。その後、会議を開催する各ユーザーに番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="be98d-158">To use a dedicated number, you'll have to first get the number, assign it to your conferencing bridge, and then assign the number to each person who will lead meetings.</span></span>

<span data-ttu-id="be98d-159">専用の電話番号を取得するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="be98d-159">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="be98d-160">Microsoft から電話番号を取得するか、現在のサービスプロバイダーから Microsoft に既存の番号を移行 (移植) することができます。</span><span class="sxs-lookup"><span data-stu-id="be98d-160">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="be98d-161">この方法について詳しくは、「 [サービス番号を取得](getting-service-phone-numbers.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="be98d-161">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="be98d-162">無料電話番号を使用する場合は、まず会議を開催する各ユーザーに通信クレジットのライセンスを割り当てる必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="be98d-162">Keep in mind that if you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="be98d-163">詳細については、「 [組織のためにコミュニケーションクレジット](set-up-communications-credits-for-your-organization.md)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be98d-163">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="be98d-164">番号を取得したら、それを会議ブリッジに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="be98d-164">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="be98d-165">この操作を行うには、Microsoft Teams 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="be98d-165">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="be98d-166">Microsoft Teams 管理センターの左のナビゲーションで、[**会議**  >  **会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="be98d-166">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="be98d-167">[ **追加**] を選択し、[ **有料電話番号** ] または [無料 **電話番号**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be98d-167">Select **Add**, and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="be98d-168">[ **電話番号の追加** ] ウィンドウで番号を選択し、[ **適用**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be98d-168">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

<span data-ttu-id="be98d-169">次に、会議を開催する各ユーザーに番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="be98d-169">Then, assign the number to each person who will lead meetings.</span></span> <span data-ttu-id="be98d-170">この操作を行うには、Microsoft Teams 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="be98d-170">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="be98d-171">Microsoft Teams 管理センターの左のナビゲーションで、[ **ユーザー**] を選択し、ユーザーの表示名をクリックして、[ **編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be98d-171">In the left navigation of the Microsoft Teams admin center, select **Users**, click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="be98d-172">[電話会議] の横にある [ **編集**] を選択し、[電話会議] ウィンドウで、[有料電話番号] または [無料電話番号] の   一覧から番号を選択し、[ **Audio Conferencing** **Audio Conferencing**    **Toll number**    **Toll-free**   **適用**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be98d-172">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="be98d-173">関連トピック</span><span class="sxs-lookup"><span data-stu-id="be98d-173">Related topics</span></span>

- [<span data-ttu-id="be98d-174">電話会議</span><span class="sxs-lookup"><span data-stu-id="be98d-174">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="be98d-175">Teams の電話会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="be98d-175">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="be98d-176">電話会議の電話番号</span><span class="sxs-lookup"><span data-stu-id="be98d-176">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
- [<span data-ttu-id="be98d-177">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="be98d-177">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="be98d-178">サービス番号の取得</span><span class="sxs-lookup"><span data-stu-id="be98d-178">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="be98d-179">Teams アドオンライセンス</span><span class="sxs-lookup"><span data-stu-id="be98d-179">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="be98d-180">ライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="be98d-180">Assign licenses to users</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
