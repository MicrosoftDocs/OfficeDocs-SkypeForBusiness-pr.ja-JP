---
title: Microsoft Teams での電話会議
ms.reviewer: ''
description: ここに示す展開リソースを使用して、Microsoft Teams のミーティング ワークロードの一部として電話会議を展開してください。
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: f3ed86a8989cc1664d2ff73111b85d2fe30dcad3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240931"
---
# <a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="dfa16-103">Microsoft Teams での電話会議</span><span class="sxs-lookup"><span data-stu-id="dfa16-103">Audio Conferencing in Microsoft Teams</span></span>

<span data-ttu-id="dfa16-104">電話会議とは、通常の電話機から Teams のミーティングに参加することと、ミーティングから電話番号に向けてダイヤルアウトすることができる機能です。</span><span class="sxs-lookup"><span data-stu-id="dfa16-104">Audio Conferencing is the ability to join a Teams meeting from a regular phone and dial out from a meeting to a phone number.</span></span> <span data-ttu-id="dfa16-105">組織に電話会議を展開する際の一環として、[ミーティングの展開](deploy-meetings-microsoft-teams-landing-page.md)を確認しておいてください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-105">Be sure you've reviewed [Meetings rollout](deploy-meetings-microsoft-teams-landing-page.md) as part of rolling out Audio Conferencing in your organization.</span></span>

## <a name="audio-conferencing-deployment-decisions"></a><span data-ttu-id="dfa16-106">電話会議の展開に関する決定事項</span><span class="sxs-lookup"><span data-stu-id="dfa16-106">Audio Conferencing deployment decisions</span></span>

<span data-ttu-id="dfa16-107">この記事では、自分の組織のプロファイルとビジネスの要件に基づいて既定の電話会議の設定に変更が必要かどうかを判断する際のガイダンスを示し、それぞれの変更の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="dfa16-107">This article helps you decide whether to change any of the default Audio Conferencing settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="dfa16-108">設定については 2 つのグループに分けて、まず、[変更する可能性が高いと考えられる](#core-deployment-decisions)中心的な部分について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfa16-108">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="dfa16-109">2 番目のグループには、組織のニーズ応じた構成が求められる可能性がある[追加の設定](#additional-deployment-decisions)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfa16-109">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="dfa16-110">電話会議のセットアップは、ミーティングのスケジュールを設定するユーザーまたはミーティングを主催するユーザーにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="dfa16-110">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="dfa16-111">ダイヤルインするミーティングの参加者には、ライセンスの割り当てなど一切のセットアップが不要です。</span><span class="sxs-lookup"><span data-stu-id="dfa16-111">Meeting attendees who dial in don't need any licenses assigned to them or any other setup.</span></span> <span data-ttu-id="dfa16-112">ミーティングへのダイヤルイン (通話) は、外出先でラップトップやモバイル デバイスの Skype for Business または Teams アプリを使用してミーティングに参加できないユーザーにとって便利なものです。</span><span class="sxs-lookup"><span data-stu-id="dfa16-112">Dialing in (calling in) to meetings is very useful for users who are on the road and can't attend a meeting using the Skype for Business or Teams app on their laptops or mobile devices.</span></span> 


## <a name="audio-conferencing-prerequisites"></a><span data-ttu-id="dfa16-113">電話会議の前提条件</span><span class="sxs-lookup"><span data-stu-id="dfa16-113">Audio Conferencing prerequisites</span></span> 

<span data-ttu-id="dfa16-114">Teams の電話会議を展開する前に、次の事項について検討してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-114">Before you can roll out Audio Conferencing for Teams, consider the following:</span></span>

|<span data-ttu-id="dfa16-115">確認事項</span><span class="sxs-lookup"><span data-stu-id="dfa16-115">Ask yourself</span></span>|<span data-ttu-id="dfa16-116">アクション</span><span class="sxs-lookup"><span data-stu-id="dfa16-116">Action</span></span> |
|------------|-------|
|<span data-ttu-id="dfa16-117">自分の国/地域で電話会議が使用できるか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-117">Is Audio Conferencing available for my country/region?</span></span>|<span data-ttu-id="dfa16-118">自分の国/地域で電話会議が使用できるかどうかを調べるには、「[電話会議および通話プランを利用可能な国と地域](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-118">To find out if Audio Conferencing is available for your country/region, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>|
|<span data-ttu-id="dfa16-119">ユーザーは Teams の電話会議に対応したライセンスを所持しているか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-119">Do my users have the proper licensing for Teams Audio Conferencing?</span></span>|<span data-ttu-id="dfa16-120">電話会議のライセンスは、Office 365 E5 サブスクリプションの一部として入手できます。また、Office 365 Business Premium、Office 365 E1 または E3 サブスクリプションのアドオン サービスとしても入手できます。</span><span class="sxs-lookup"><span data-stu-id="dfa16-120">Audio Conferencing licenses are available as part of an Office 365 E5 subscription or as an add-on service for an Office 365 E1 or Office 365 E3 subscription.</span></span> <ul><li><span data-ttu-id="dfa16-121">ライセンスを取得して割り当てる場合は、「[Office 365 の電話会議を試用または購入する](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)」および「[一般法人向け Office 365 のライセンスを割り当てまたは削除する](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-121">To get and assign licenses, see [Try or purchase Audio Conferencing in Office 365](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365) and [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span></li><li> <span data-ttu-id="dfa16-122">詳細は、[Microsoft Teamsアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-122">To learn more, read [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span> </li><li><span data-ttu-id="dfa16-123">それぞれの Office 365 プランに含まれているクラウド機能を確認するには、「[プランに応じたライセンス オプション](teams-add-on-licensing/office-365-business-premium.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-123">To see what cloud features are included in each Office 365 plan, see the [License options based on your plan](teams-add-on-licensing/office-365-business-premium.md) articles.</span></span></li></ul>|
|<span data-ttu-id="dfa16-124">電話会議のライセンスを割り当てたユーザーにコミュニケーション クレジットを購入する必要があるか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-124">Do I need to purchase Communications Credits for the users who are assigned Audio Conferencing licenses?</span></span>|<span data-ttu-id="dfa16-125">詳細については、「[コミュニケーション クレジットについて](what-are-communications-credits.md)」を参照してから、この後のセクション「[コミュニケーション クレジット](#communications-credits)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-125">To learn more, read [What are Communications Credits](what-are-communications-credits.md), then check out the [Communications Credits](#communications-credits) section below.</span></span>|
|||


## <a name="core-deployment-decisions"></a><span data-ttu-id="dfa16-126">展開に関する重要な決定事項</span><span class="sxs-lookup"><span data-stu-id="dfa16-126">Core deployment decisions</span></span>

<span data-ttu-id="dfa16-127">電話会議の前提条件を満たしたら、次の作業を実行してユーザーの電話会議を構成します。</span><span class="sxs-lookup"><span data-stu-id="dfa16-127">After you meet the Audio Conferencing prerequisites, complete the following tasks to configure Audio Conferencing for your users.</span></span>


### <a name="teams-administrators"></a><span data-ttu-id="dfa16-128">Teams の管理者</span><span class="sxs-lookup"><span data-stu-id="dfa16-128">Teams administrators</span></span>

<span data-ttu-id="dfa16-129">Teams には、組織に適した Teams の管理に使用できる、カスタムの管理者の役割のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="dfa16-129">Teams provides a set of custom administrator roles that can be used to manage Teams for your organization.</span></span> <span data-ttu-id="dfa16-130">この役割によって、さまざまな機能が管理者に提供されます。</span><span class="sxs-lookup"><span data-stu-id="dfa16-130">The roles provide various capabilities to administrators.</span></span> 

| <span data-ttu-id="dfa16-131">確認事項</span><span class="sxs-lookup"><span data-stu-id="dfa16-131">Ask yourself</span></span> | <span data-ttu-id="dfa16-132">アクション</span><span class="sxs-lookup"><span data-stu-id="dfa16-132">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="dfa16-133">Teams 通信管理者の役割を誰に割り当てるか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-133">Who will be assigned the Teams Communications Administrator role?</span></span>|<span data-ttu-id="dfa16-134">Teams 管理者の役割の詳細については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-134">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|<span data-ttu-id="dfa16-135">Teams 通信サポート エンジニアの役割を誰に割り当てるか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-135">Who will be assigned the Teams Communications Support Engineer role?</span></span>|<span data-ttu-id="dfa16-136">管理者の役割を割り当てるには、「[Active Directory で管理者の役割と管理者以外の役割をユーザーに割り当てる](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-136">To assign admin roles, see [Assign administrator and non-administrator roles to users with Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>|
|<span data-ttu-id="dfa16-137">Teams 通信サポート スペシャリストの役割を誰に割り当てるか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-137">Who will be assigned the Teams Communications Support Specialist role?</span></span>||
|||

### <a name="conferencing-bridges-and-phone-numbers"></a><span data-ttu-id="dfa16-138">会議ブリッジと電話番号</span><span class="sxs-lookup"><span data-stu-id="dfa16-138">Conferencing bridges and phone numbers</span></span>

<span data-ttu-id="dfa16-139">会議ブリッジにより、ユーザーは電話機を使用してミーティングにダイヤルインできるようになります。</span><span class="sxs-lookup"><span data-stu-id="dfa16-139">Conferencing bridges let people dial into meetings using a phone.</span></span> <span data-ttu-id="dfa16-140">会議ブリッジの既定の設定を使用することも、電話番号 (有料ダイヤル/無料ダイヤル) およびその他の設定 (PIN や使用言語など) を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="dfa16-140">You can use the default settings for a conferencing bridge or change the phone numbers (toll and toll-free) and other settings, such as the PIN or the languages that are used.</span></span>

<span data-ttu-id="dfa16-141">詳細については、「[Office 365 の電話会議](audio-conferencing-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-141">See [Audio Conferencing in Office 365](audio-conferencing-in-office-365.md) to learn more.</span></span>

|<span data-ttu-id="dfa16-142">確認事項</span><span class="sxs-lookup"><span data-stu-id="dfa16-142">Ask yourself</span></span>|<span data-ttu-id="dfa16-143">アクション</span><span class="sxs-lookup"><span data-stu-id="dfa16-143">Action</span></span> |
|------------|-------|
|<span data-ttu-id="dfa16-144">新しい会議ブリッジ番号を追加する必要があるか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-144">Do I need to add new conferencing bridge numbers?</span></span>| <span data-ttu-id="dfa16-145">新しい番号を追加する場合は、「[サービスの電話番号を取得する](/microsoftteams/getting-service-phone-numbers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-145">To add new numbers, see [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>|
|<span data-ttu-id="dfa16-146">ブリッジの設定を変更する必要があるか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-146">Will I need to modify the bridge settings?</span></span>|<span data-ttu-id="dfa16-147">ブリッジの設定を変更する場合は、「[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-147">To modify the bridge settings, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>|
|<span data-ttu-id="dfa16-148">電話会議で使用する番号を移行する必要があるか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-148">Do I need to port numbers to use with audio conferencing?</span></span>|<span data-ttu-id="dfa16-149">電話番号の移行の詳細は、「[Office 365 に電話番号を転送する](transfer-phone-numbers-to-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-149">To learn about porting phone numbers, read [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>|
|||


### <a name="default-and-alternate-languages"></a><span data-ttu-id="dfa16-150">既定の言語と第 2 言語</span><span class="sxs-lookup"><span data-stu-id="dfa16-150">Default and alternate languages</span></span>

<span data-ttu-id="dfa16-151">Teams の電話会議では、会議ブリッジの既定の言語と第 2 言語を設定できます。</span><span class="sxs-lookup"><span data-stu-id="dfa16-151">Teams Audio Conferencing lets you set up default and alternate languages for a conferencing bridge.</span></span>

|<span data-ttu-id="dfa16-152">確認事項</span><span class="sxs-lookup"><span data-stu-id="dfa16-152">Ask yourself</span></span>|<span data-ttu-id="dfa16-153">アクション</span><span class="sxs-lookup"><span data-stu-id="dfa16-153">Action</span></span> |
|------------|-------|
| <span data-ttu-id="dfa16-154">どの言語を自動応答案内に選択する必要があるか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-154">Which languages should I choose for auto attendant greetings?</span></span> | <span data-ttu-id="dfa16-155">言語を選択する場合は、「[電話会議の自動案内の言語を設定する](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-155">To choose languages, see [Set auto attendant languages for Audio Conferencing](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>|
|||

### <a name="conferencing-bridge-settings"></a><span data-ttu-id="dfa16-156">会議ブリッジの設定</span><span class="sxs-lookup"><span data-stu-id="dfa16-156">Conferencing bridge settings</span></span> 

<span data-ttu-id="dfa16-157">会議ブリッジのセットアップ後 (既定および第 2 言語のセットアップを含む)、参加/退出の通知と使用する PIN の長さが適切かなど、既定の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="dfa16-157">After setting up your conferencing bridge, including default and alternate languages, you should verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use.</span></span> <span data-ttu-id="dfa16-158">適切でない場合は変更できます。</span><span class="sxs-lookup"><span data-stu-id="dfa16-158">If they're not, you can change them.</span></span> 

|<span data-ttu-id="dfa16-159">確認事項</span><span class="sxs-lookup"><span data-stu-id="dfa16-159">Ask yourself</span></span>|<span data-ttu-id="dfa16-160">アクション</span><span class="sxs-lookup"><span data-stu-id="dfa16-160">Action</span></span> |
|------------|-------|
| <span data-ttu-id="dfa16-161">ユーザーがミーティングに参加または退出したときに参加者に通知するか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-161">Will attendees hear a notification when a user joins or exits a meeting?</span></span> | <span data-ttu-id="dfa16-162">これに該当する設定を変更する場合は、「[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-162">To change these settings, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>|
|<span data-ttu-id="dfa16-163">ミーティングの主催者がミーティングを開始するために使用する PIN に要求される長さは?</span><span class="sxs-lookup"><span data-stu-id="dfa16-163">What is the required length of the PIN that a meeting organizer uses to start the meeting?</span></span>||
|||

### <a name="dial-in-phone-number-settings-for-users-who-lead-meetings"></a><span data-ttu-id="dfa16-164">ミーティングを主催するユーザーのダイヤルイン電話番号の設定</span><span class="sxs-lookup"><span data-stu-id="dfa16-164">Dial-in phone number settings for users who lead meetings</span></span>

<span data-ttu-id="dfa16-165">電話会議ブリッジの作成後、ミーティングの主催者が使用する有料ダイヤル番号や無料ダイヤル番号を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfa16-165">After you create your Audio Conferencing bridge, you need to set the toll and/or toll-free numbers that users who lead meetings will use.</span></span>

|<span data-ttu-id="dfa16-166">確認事項</span><span class="sxs-lookup"><span data-stu-id="dfa16-166">Ask yourself</span></span>|<span data-ttu-id="dfa16-167">アクション</span><span class="sxs-lookup"><span data-stu-id="dfa16-167">Action</span></span> |
|------------|-------|
| <span data-ttu-id="dfa16-168">ミーティングを主催するユーザーごとに、どの会議ブリッジ番号を割り当てるか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-168">Which conference bridge numbers will I assign to each user who leads meetings?</span></span> | <span data-ttu-id="dfa16-169">ダイヤルイン電話番号をユーザーに割り当てる場合は、「[手順 7: 会議を主催するユーザーにダイヤルイン電話番号を割り当てる](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-169">To assign a dial-in phone number to a user, see [Step 7: Assign dial-in phone numbers for users who lead meetings](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings).</span></span> |
|||

### <a name="communications-credits"></a><span data-ttu-id="dfa16-170">コミュニケーション クレジット</span><span class="sxs-lookup"><span data-stu-id="dfa16-170">Communications Credits</span></span>

<span data-ttu-id="dfa16-171">無料ダイヤルの会議ブリッジ電話番号を提供したり、国際電話番号への会議ダイヤルアウトをサポートするには、組織の通信クレジットをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfa16-171">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to international phone numbers, you must set up Communications Credits for your organization.</span></span> <span data-ttu-id="dfa16-172">コミュニケーション クレジットの詳細については、「[コミュニケーション クレジットについて](what-are-communications-credits.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-172">To learn more about Communications Credits, see [What are Communications Credits?](what-are-communications-credits.md).</span></span>

|<span data-ttu-id="dfa16-173">確認事項</span><span class="sxs-lookup"><span data-stu-id="dfa16-173">Ask yourself</span></span>|<span data-ttu-id="dfa16-174">アクション</span><span class="sxs-lookup"><span data-stu-id="dfa16-174">Action</span></span> |
|------------|-------|
|<span data-ttu-id="dfa16-175">電話会議の実装にコミュニケーション クレジットが必要か?</span><span class="sxs-lookup"><span data-stu-id="dfa16-175">Are Communications Credits required for my Audio Conferencing implementation?</span></span> |<span data-ttu-id="dfa16-176">コミュニケーション クレジットのセットアップが必要かどうかを調べるには、「[組織向けにコミュニケーション クレジットをセットアップする](set-up-communications-credits-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-176">To find out if you need to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>|
|<span data-ttu-id="dfa16-177">必要な場合、購入金額はいくらにするか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-177">If they're required, how much should I purchase?</span></span>|<span data-ttu-id="dfa16-178">コミュニケーション クレジットの金額を判断する場合は、「[推奨される資金額](what-are-communications-credits.md#recommended-funding-amounts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-178">To determine the Communications Credits amount, see [Recommended funding amounts](what-are-communications-credits.md#recommended-funding-amounts).</span></span>|
|<span data-ttu-id="dfa16-179">自動リチャージする金額を構成できるか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-179">Do I want to configure an auto-recharge amount?</span></span>|<span data-ttu-id="dfa16-180">自動リチャージする金額を設定する場合は、「[組織のコミュニケーション クレジットをセットアップする](set-up-communications-credits-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-180">To configure an auto-recharge amount, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>|
|||



## <a name="additional-deployment-decisions"></a><span data-ttu-id="dfa16-181">その他の展開に関する決定事項</span><span class="sxs-lookup"><span data-stu-id="dfa16-181">Additional deployment decisions</span></span>

<span data-ttu-id="dfa16-182">次の設定は、組織のニーズと構成に基づいて変更できます。</span><span class="sxs-lookup"><span data-stu-id="dfa16-182">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="outbound-calling-restriction-policies"></a><span data-ttu-id="dfa16-183">発信通話の制限ポリシー</span><span class="sxs-lookup"><span data-stu-id="dfa16-183">Outbound calling restriction policies</span></span> 

<span data-ttu-id="dfa16-184">管理者は、発信通話の制御を使用して、組織内のユーザーが発信できる電話会議の種類とエンド ユーザーの PSTN 通話を制限できます。</span><span class="sxs-lookup"><span data-stu-id="dfa16-184">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span>

|<span data-ttu-id="dfa16-185">確認事項</span><span class="sxs-lookup"><span data-stu-id="dfa16-185">Ask yourself</span></span>|<span data-ttu-id="dfa16-186">アクション</span><span class="sxs-lookup"><span data-stu-id="dfa16-186">Action</span></span> |
|------------|-------|
| <span data-ttu-id="dfa16-187">許可する発信通話の種類を制限するか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-187">Will I limit the type of outbound calls that are allowed?</span></span> | <span data-ttu-id="dfa16-188">発信通話を制限する場合は、「[電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー](outbound-calling-restriction-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-188">To restrict outbound calls, see [Outbound calling restriction policies for Audio Conferencing and user PSTN calls](outbound-calling-restriction-policies.md).</span></span>|
|||


### <a name="dial-plans"></a><span data-ttu-id="dfa16-189">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="dfa16-189">Dial plans</span></span>

<span data-ttu-id="dfa16-190">Office 365 の電話システムの一部であるダイヤル プランは、通話の認証およびルーティングの目的で、ダイヤルされた電話番号を代替形式 (通常、E.164 形式) に変換する正規化ルールです。</span><span class="sxs-lookup"><span data-stu-id="dfa16-190">A dial plan, as part of Phone System in Office 365, is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="dfa16-191">ダイヤル プランの詳細については、「[ダイヤル プランについて](what-are-dial-plans.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-191">For more information about dial plans, see [What are dial plans?](what-are-dial-plans.md)</span></span>

|<span data-ttu-id="dfa16-192">確認事項</span><span class="sxs-lookup"><span data-stu-id="dfa16-192">Ask yourself</span></span>|<span data-ttu-id="dfa16-193">アクション</span><span class="sxs-lookup"><span data-stu-id="dfa16-193">Action</span></span> |
|------------|-------|
|<span data-ttu-id="dfa16-194">組織はダイヤル プランのカスタマイズを必要としているか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-194">Does my organization need a customized dial plan?</span></span>|<span data-ttu-id="dfa16-195">カスタムのダイヤル プランが必要かどうかを判断する場合は、「[テナント ダイヤル プランの計画](what-are-dial-plans.md#planning-for-tenant-dial-plans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-195">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans).</span></span> |
|<span data-ttu-id="dfa16-196">どのユーザーがダイヤル プランのカスタマイズを要求していて、どのテナント ダイヤル プランを各ユーザーに割り当てる必要があるか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-196">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span>|<span data-ttu-id="dfa16-197">PowerShell を使用して、カスタマイズしたダイヤル プランにユーザーを追加するには、「[ダイヤル プランの作成と管理](create-and-manage-dial-plans.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-197">To add users to a customized dial plan using PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>|
|||

### <a name="troubleshoot-meeting-and-call-quality"></a><span data-ttu-id="dfa16-198">ミーティングと通話の品質に関するトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="dfa16-198">Troubleshoot meeting and call quality</span></span> 

<span data-ttu-id="dfa16-199">Teams では、通話品質の問題を監視してトラブルシューティングするために、[通話分析と通話品質ダッシュボード](difference-between-call-analytics-and-call-quality-dashboard.md)という 2 つの方法を利用できます。</span><span class="sxs-lookup"><span data-stu-id="dfa16-199">Teams gives you two ways to monitor and troubleshoot call quality problems: [Call Analytics and Call Quality Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md).</span></span> <span data-ttu-id="dfa16-200">通話分析は、各ユーザーの特定の通話および会議に関連するデバイス、ネットワーク、および接続性についての詳細情報を示します。</span><span class="sxs-lookup"><span data-stu-id="dfa16-200">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user.</span></span> <span data-ttu-id="dfa16-201">通話分析は特定の通話の品質にかかわる問題を管理者やヘルプデスク エージェントがトラブルシューティングする際の支援を目的として設計されていますが、通話品質ダッシュボードは管理者やネットワーク エンジニアがネットワークを最適化する際の支援を目的として設計されています。</span><span class="sxs-lookup"><span data-stu-id="dfa16-201">Call Analytics is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, whereas the Call Quality Dashboard is designed to help admins and network engineers optimize a network.</span></span> <span data-ttu-id="dfa16-202">通話品質ダッシュボードは、特定のユーザーに焦点を合わせるのではなく、Teams 組織全体についての集計情報に注目します。</span><span class="sxs-lookup"><span data-stu-id="dfa16-202">Call Quality Dashboard shifts focus from specific users and instead looks at aggregate information for an entire Teams organization.</span></span> 

|<span data-ttu-id="dfa16-203">確認事項</span><span class="sxs-lookup"><span data-stu-id="dfa16-203">Ask yourself</span></span>|<span data-ttu-id="dfa16-204">アクション</span><span class="sxs-lookup"><span data-stu-id="dfa16-204">Action</span></span> |
|------------|-------|
| <span data-ttu-id="dfa16-205">通話品質の問題についての監視およびトラブルシューティングを誰が担当するか?</span><span class="sxs-lookup"><span data-stu-id="dfa16-205">Who will be responsible for monitoring and troubleshooting call quality issues?</span></span> | <span data-ttu-id="dfa16-206">通話品質の問題をトラブルシューティングするために必要なアクセス許可レベルの詳細については、「[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-206">See [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md) for information about permission levels required to troubleshoot call quality issues.</span></span>|
|||


## <a name="next-steps"></a><span data-ttu-id="dfa16-207">次のステップ</span><span class="sxs-lookup"><span data-stu-id="dfa16-207">Next steps</span></span>
- <span data-ttu-id="dfa16-208">組織での電話会議の[導入を推進する](adopt-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="dfa16-208">[Drive adoption](adopt-microsoft-teams-landing-page.md) of audio conferencing in your organization.</span></span>
- [<span data-ttu-id="dfa16-209">クラウド ボイスを展開する</span><span class="sxs-lookup"><span data-stu-id="dfa16-209">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)
- <span data-ttu-id="dfa16-210">お勧めのアプリ (Planner など) を Teams の初期ロールアウトに組み込む。</span><span class="sxs-lookup"><span data-stu-id="dfa16-210">Include featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="dfa16-211">Teams 導入の進行に応じて、その他の[アプリ、ボット、およびコネクタ](deploy-apps-microsoft-teams-landing-page.md)を追加してください。</span><span class="sxs-lookup"><span data-stu-id="dfa16-211">Add other [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>
