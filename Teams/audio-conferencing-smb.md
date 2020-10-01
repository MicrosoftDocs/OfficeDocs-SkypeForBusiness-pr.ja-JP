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
ms.openlocfilehash: 648a6342adf0fc035dcd33c6eb11efb40b0d4eed
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328437"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="4eaf6-103">中小規模企業向けの電話会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="4eaf6-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="4eaf6-104">電話会議を使用すると、ユーザーは、モバイルデバイスまたは自分のコンピューターから teams アプリを使っていなくても、電話を使用して Teams 会議にコールインすることができます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="4eaf6-105">中小規模企業で、最大300人のユーザーがいて、現在電話会議のライセンスを持っていない場合は、1年間は電話会議を無料で受けることができます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="4eaf6-106">この無料キャンペーンは、2020年10月1日から利用できます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="4eaf6-107">電話会議アドオンライセンスは、Microsoft 365 Business Basic、Business Standard、Business Premium、enterprise E1、Enterprise E3 のライセンスを所有しているユーザーに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="4eaf6-108">詳細については、「 [Teams アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="4eaf6-109">Enterprise E5 または Microsoft 365 ビジネス Voip を使用している場合、これらのライセンスには電話会議が既に含まれているため、無料の電話会議プランは使用できません。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="4eaf6-110">この記事では、電話会議をセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="4eaf6-111">電話会議のセットアップは、ミーティングのスケジュールを設定するユーザーまたはミーティングを主催するユーザーにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="4eaf6-112">会議へのコールインを行う会議出席者は、ライセンスまたはその他の設定を必要としません。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="4eaf6-113">詳細については、「 [電話会議](audio-conferencing-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="4eaf6-114">手順 1: 電話会議ライセンスを取得する</span><span class="sxs-lookup"><span data-stu-id="4eaf6-114">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="4eaf6-115">会議を開催する各ユーザーに対して1つの電話会議ライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-115">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="4eaf6-116">この操作を行うには、Microsoft 365 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-116">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="4eaf6-117">Microsoft 365 管理センターで、[**課金**  >  **サービス**] に移動し、ページの下部にある [**アドオン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-117">In the Microsoft 365 admin center, go to **Billing** > **Purchase services**, and then at the bottom of the page, select **Add-ons**.</span></span> 
2. <span data-ttu-id="4eaf6-118">**Microsoft 365 電話会議の導入プロモーション**  >  の**詳細**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-118">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details**.</span></span>
3. <span data-ttu-id="4eaf6-119">会議の開催者に必要なライセンスの数を入力して、注文を完了します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-119">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

> [!NOTE]
> <span data-ttu-id="4eaf6-120">[このライセンスを持っていないすべてのユーザーに電話会議ライセンスを自動的に割り当てる] のいずれかを選択して、[ **ライセンスのないすべてのユーザーに自動的に割り当てる**] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-120">Clear or select the **Automatically assign to all of your users with no licenses**, depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

## <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="4eaf6-121">手順 2: 会議をリードするユーザーに電話会議ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4eaf6-121">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="4eaf6-122">会議を開催する各ユーザーにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-122">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="4eaf6-123">この操作を行うには、Microsoft 365 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-123">Use the Microsoft 365 admin center to do this.</span></span>

### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="4eaf6-124">1人のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4eaf6-124">Assign a license to one user</span></span>

1. <span data-ttu-id="4eaf6-125">Microsoft 365 管理センターで、[アクティブな**ユーザー**] に移動  >  **Active users**します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-125">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="4eaf6-126">ライセンスを割り当てるユーザーの行を選び、ウィンドウで [ **ライセンスとアプリ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-126">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="4eaf6-127">[ **Microsoft 365 電話会議** ] チェックボックスをオンにして、[ **変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-127">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span> 

### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="4eaf6-128">複数のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4eaf6-128">Assign a license to multiple users</span></span>

1. <span data-ttu-id="4eaf6-129">Microsoft 365 管理センターで、[アクティブな**ユーザー**] に移動  >  **Active users**します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-129">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="4eaf6-130">ライセンスを割り当てるユーザーの横にある円を選択し、[ **製品ライセンスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-130">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="4eaf6-131">[ **製品ライセンスの管理** ] ウィンドウで、[ **その他の割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-131">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="4eaf6-132">[ **Microsoft 365 電話会議** ] チェックボックスをオンにして、[ **変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-132">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="step-3-find-or-get-a-phone-number-for-your-conferencing-bridge"></a><span data-ttu-id="4eaf6-133">手順 3: 会議ブリッジの電話番号を検索または取得する</span><span class="sxs-lookup"><span data-stu-id="4eaf6-133">Step 3: Find or get a phone number for your conferencing bridge</span></span>

<span data-ttu-id="4eaf6-134">会議出席依頼で使うことができるように、会議ブリッジには電話番号 (サービス番号とも呼ばれます) が必要です。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-134">You'll need a phone number (also called a service number) for your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="4eaf6-135">**共有番号**を使用するか、**専用の番号**を使用するかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-135">You can choose to use a **shared number** or a **dedicated number**.</span></span> <span data-ttu-id="4eaf6-136">どちらの番号も、任意の発信者が会議に参加するために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-136">Both types of numbers can be used by any caller to join a meeting.</span></span>

### <a name="use-a-shared-number"></a><span data-ttu-id="4eaf6-137">共有番号を使用する</span><span class="sxs-lookup"><span data-stu-id="4eaf6-137">Use a shared number</span></span>

<span data-ttu-id="4eaf6-138">共有番号は、すべての組織で共有される番号です。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-138">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="4eaf6-139">電話会議をセットアップすると、共有番号が自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-139">Shared numbers are automatically assigned when you set up Audio Conferencing.</span></span> <span data-ttu-id="4eaf6-140">これらの共有番号は有料番号のため、長距離通話料金が適用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-140">These shared numbers are toll numbers, in which long-distance charges may apply.</span></span>

<span data-ttu-id="4eaf6-141">会議ブリッジに割り当てられている既定の電話番号を確認するには、Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**  >  **会議ブリッジ**] に移動して、最寄りの場所の番号を見つけます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-141">To find the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**, and then find the number for the location that's nearest to you.</span></span>

### <a name="get-a-dedicated-number"></a><span data-ttu-id="4eaf6-142">専用番号を取得する</span><span class="sxs-lookup"><span data-stu-id="4eaf6-142">Get a dedicated number</span></span>

<span data-ttu-id="4eaf6-143">専用番号は、ユーザーだけが使用できる番号です。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-143">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="4eaf6-144">専用電話番号には、有料番号または無料電話番号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-144">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="4eaf6-145">専用の電話番号を使用するには、まず電話番号を取得し、それを会議ブリッジに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-145">To use a dedicated number, you'll have to first get the number, and then assign it to your conferencing bridge.</span></span>  

<span data-ttu-id="4eaf6-146">専用の電話番号を取得するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-146">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="4eaf6-147">Microsoft から電話番号を取得するか、現在のサービスプロバイダーから Microsoft に既存の番号を移行 (移植) することができます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-147">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="4eaf6-148">この方法について詳しくは、「 [サービス番号を取得](getting-service-phone-numbers.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-148">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4eaf6-149">無料電話番号を使用している場合は、まず会議を開催する各ユーザーに通信クレジットのライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-149">If you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="4eaf6-150">詳細については、「 [組織のためにコミュニケーションクレジット](set-up-communications-credits-for-your-organization.md)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-150">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="4eaf6-151">番号を取得したら、それを会議ブリッジに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-151">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="4eaf6-152">この操作を行うには、Microsoft Teams 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-152">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="4eaf6-153">Microsoft Teams 管理センターの左のナビゲーションで、[**会議**  >  **会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="4eaf6-154">[ **追加**] を選択し、[ **有料電話番号** ] または [無料 **電話番号**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-154">Select **Add**, and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="4eaf6-155">[ **電話番号の追加** ] ウィンドウで番号を選択し、[ **適用**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-155">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

## <a name="step-4-assign-a-dial-in-number-to-users-who-lead-meetings"></a><span data-ttu-id="4eaf6-156">手順 4: 会議を主催するユーザーにダイヤルイン番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="4eaf6-156">Step 4: Assign a dial-in number to users who lead meetings</span></span>

<span data-ttu-id="4eaf6-157">会議を開催する各ユーザーのダイヤルイン番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-157">Assign a dial-in number for each person who will lead meetings.</span></span> <span data-ttu-id="4eaf6-158">この操作を行うには、Microsoft Teams 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-158">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="4eaf6-159">Microsoft Teams 管理センターの左のナビゲーションで、[ **ユーザー**] を選択し、ユーザーの表示名をクリックして、[ **編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-159">In the left navigation of the Microsoft Teams admin center, select **Users**, click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="4eaf6-160">[電話会議] の横にある [ **編集**] を選択し、[電話会議] ウィンドウで、[有料電話番号] または [無料電話番号] の   一覧から番号を選択し、[ **Audio Conferencing** **Audio Conferencing**    **Toll number**    **Toll-free**   **適用**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-160">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="step-5-schedule-a-teams-meeting-in-outlook"></a><span data-ttu-id="4eaf6-161">手順 5: Outlook で Teams 会議をスケジュールする</span><span class="sxs-lookup"><span data-stu-id="4eaf6-161">Step 5: Schedule a Teams meeting in Outlook</span></span>

<span data-ttu-id="4eaf6-162">Outlook で会議をスケジュールするには、[ **予定表**] に移動し、[ **新しいチーム会議** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-162">To schedule a meeting, in Outlook, go to **Calendar**, and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="4eaf6-163">ユーザーに設定したダイヤルイン番号と会議 ID が、会議出席者に送信された会議出席依頼に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-163">The dial-in numbers that you set for the user and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span>

<span data-ttu-id="4eaf6-164">詳細については、「 [Outlook で Teams 会議のスケジュールを設定](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-164">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="4eaf6-165">必要に応じて、会議出席依頼をカスタマイズして、会社のロゴ、サポート web サイトおよび法的免責事項へのリンク、テキストのみのフッターを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-165">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="4eaf6-166">「[会議への招待状をカスタマイズする](meeting-settings-in-teams.md#customize-meeting-invitations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4eaf6-166">See [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4eaf6-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="4eaf6-167">Related topics</span></span>

- [<span data-ttu-id="4eaf6-168">電話会議</span><span class="sxs-lookup"><span data-stu-id="4eaf6-168">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="4eaf6-169">Teams の電話会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="4eaf6-169">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="4eaf6-170">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="4eaf6-170">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="4eaf6-171">サービス番号の取得</span><span class="sxs-lookup"><span data-stu-id="4eaf6-171">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="4eaf6-172">Teams アドオンライセンス</span><span class="sxs-lookup"><span data-stu-id="4eaf6-172">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="4eaf6-173">ライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4eaf6-173">Assign licenses to users</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
