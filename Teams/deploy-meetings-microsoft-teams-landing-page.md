---
title: Microsoft Teams でのミーティングと会議
ms.reviewer: ''
description: ここに示す展開のリソースを使用して、Microsoft Teams でのミーティングを展開します。
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/28/2019
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 585e857ff6edf89880ed29d9a434747a0af3d127
ms.sourcegitcommit: 2453f87088fc2f8034726c14699aacb65d859b1b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "36436356"
---
# <a name="meetings-and-conferencing-in-microsoft-teams"></a><span data-ttu-id="559d4-103">Microsoft Teams でのミーティングと会議</span><span class="sxs-lookup"><span data-stu-id="559d4-103">Meetings & conferencing in Microsoft Teams</span></span>

<span data-ttu-id="559d4-104">[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。</span><span class="sxs-lookup"><span data-stu-id="559d4-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="559d4-105">Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。</span><span class="sxs-lookup"><span data-stu-id="559d4-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="559d4-106">この時点で、[電話会議](deploy-audio-conferencing-teams-landing-page.md)、ビデオ、および共有を含むミーティング ワークロードを追加する準備が整っています。</span><span class="sxs-lookup"><span data-stu-id="559d4-106">Now you're ready to add the meetings workload, including [audio conferencing](deploy-audio-conferencing-teams-landing-page.md), video, and sharing.</span></span> <span data-ttu-id="559d4-107">これを行うには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="559d4-107">Here's how.</span></span> 


## <a name="meetings-and-conferencing-deployment-decisions"></a><span data-ttu-id="559d4-108">ミーティングと会議の展開に関する決定事項</span><span class="sxs-lookup"><span data-stu-id="559d4-108">Meetings & conferencing deployment decisions</span></span>

<span data-ttu-id="559d4-109">Teams は、すぐに使用できる優れたエクスペリエンスを組織に提供します。既定の設定は、ほとんどの組織の業務に通用します。</span><span class="sxs-lookup"><span data-stu-id="559d4-109">Teams provides a great out-of-the-box experience for your organization, and most organizations find that the default settings work for them.</span></span> <span data-ttu-id="559d4-110">この記事では、自分の組織のプロファイルとビジネスの要件に基づいて既定の設定に変更が必要かどうかを判断する際のガイダンスを示し、それぞれの変更の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="559d4-110">This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="559d4-111">設定については 2 つのグループに分けて、まず、[変更する可能性が高いと考えられる](#core-deployment-decisions)中心的な部分について説明します。</span><span class="sxs-lookup"><span data-stu-id="559d4-111">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="559d4-112">2 番目のグループには、組織のニーズ応じた構成が求められる可能性がある[追加の設定](#additional-deployment-decisions)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="559d4-112">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

> [!Tip]
> <span data-ttu-id="559d4-113">ミーティングの詳細については、セッション「[Microsoft Teams でのミーティングの概要 (IT プロフェッショナル向け)](https://aka.ms/teams-meetings-intro)」を視聴してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-113">Watch the following session to learn more about Meetings: [Introduction to Meetings in Microsoft Teams for IT Pros](https://aka.ms/teams-meetings-intro)</span></span>


## <a name="meetings-and-conferencing-prerequisites"></a><span data-ttu-id="559d4-114">ミーティングと会議の前提条件</span><span class="sxs-lookup"><span data-stu-id="559d4-114">Meetings & conferencing prerequisites</span></span> 

<span data-ttu-id="559d4-115">組織全体にミーティングの展開を広げる前に、できる限り最高のエクスペリエンスをユーザーに提供する環境が整っているかどうかを再確認するための時間を割いてください。</span><span class="sxs-lookup"><span data-stu-id="559d4-115">Before scaling your meetings deployment across your organization, take time to review and confirm that your environment is ready to provide users with the best possible experience.</span></span> <span data-ttu-id="559d4-116">次の情報を確認して、環境に必要に応じた変更を実行します。</span><span class="sxs-lookup"><span data-stu-id="559d4-116">Review the following information and make any required changes to your environment as needed.</span></span>

<span data-ttu-id="559d4-117">Teams の最高のエクスペリエンスを実現する場合、組織は Exchange Online および SharePoint Online を展開している必要があり、ユーザーには O365 の確認済みドメイン (*contoso.com* など) が必要になります。</span><span class="sxs-lookup"><span data-stu-id="559d4-117">To get the best experience on Teams, your organization must have deployed Exchange Online and SharePoint Online, and you must have a verified domain for O365 such as *contoso.com*.</span></span>

<span data-ttu-id="559d4-118">組織全体にミーティングを組織全体に広げるには、すべてのユーザーの場所に Office 365 サービスへのインターネット アクセスが必要になります。</span><span class="sxs-lookup"><span data-stu-id="559d4-118">To scale meetings across your organization you should ensure that all user locations have internet access to connect to the Office 365 Services.</span></span> <span data-ttu-id="559d4-119">少なくとも、次に示す共通のポートがユーザーの場所からインターネットに対して開かれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="559d4-119">At a minimum you should make sure that the following common ports are open to the internet from your user’s locations:-</span></span>

- <span data-ttu-id="559d4-120">Teams で使用するクライアントからの送信 TCP 80 および 443</span><span class="sxs-lookup"><span data-stu-id="559d4-120">TCP ports 80 and 443 outgoing from clients that will use Teams</span></span>
- <span data-ttu-id="559d4-121">Teams で使用するクライアントからの送信 UDP ポート 3478 から 3481</span><span class="sxs-lookup"><span data-stu-id="559d4-121">UDP ports 3478 through 3481 outgoing from clients that will use Teams</span></span>

<span data-ttu-id="559d4-122">[Network Testing Companion](https://www.powershellgallery.com/packages/NetworkTestingCompanion/1.5.2) を使用すると、ネットワークの場所でミーティング エクスペリエンスをサポートする音声とビデオのトラフィックを利用するための準備が整っているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="559d4-122">You can use the [Network Testing Companion](https://www.powershellgallery.com/packages/NetworkTestingCompanion/1.5.2) to confirm that your network locations are ready for the voice and video traffic that will support your meetings experience.</span></span>

| <span data-ttu-id="559d4-123">確認事項</span><span class="sxs-lookup"><span data-stu-id="559d4-123">Ask yourself</span></span> | <span data-ttu-id="559d4-124">アクション</span><span class="sxs-lookup"><span data-stu-id="559d4-124">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="559d4-125">Teams のミーティングの展開にネットワークが対応しているか?</span><span class="sxs-lookup"><span data-stu-id="559d4-125">Is my network ready for Teams meetings deployment?</span></span> | <span data-ttu-id="559d4-126">ネットワークの対応状況を確認するには、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-126">To verify that your network is ready, see:</span></span><ul><li>[<span data-ttu-id="559d4-127">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="559d4-127">Prepare your organization's network for Microsoft Teams</span></span>](https://docs.microsoft.com/ja-JP/MicrosoftTeams/prepare-network)</li><li>[<span data-ttu-id="559d4-128">Office 365 の URL と IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="559d4-128">Office 365 URLs and IP address ranges</span></span>](https://docs.microsoft.com/ja-JP/MicrosoftTeams/office-365-urls-ip-address-ranges)</li></ul> |
|||

## <a name="core-deployment-decisions"></a><span data-ttu-id="559d4-129">展開に関する重要な決定事項</span><span class="sxs-lookup"><span data-stu-id="559d4-129">Core deployment decisions</span></span>

<span data-ttu-id="559d4-130">次に示す設定は、ほとんどの組織が変更を必要とするものです (Teams の既定の設定では、組織に適した動作にならない場合)。</span><span class="sxs-lookup"><span data-stu-id="559d4-130">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

### <a name="teams-administrators"></a><span data-ttu-id="559d4-131">Teams の管理者</span><span class="sxs-lookup"><span data-stu-id="559d4-131">Teams administrators</span></span>

<span data-ttu-id="559d4-132">Teams には、組織に適した Teams の管理に使用できる、カスタムの管理者の役割のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="559d4-132">Teams provides a set of custom administrator roles that can be used to manage Teams for your organization.</span></span> <span data-ttu-id="559d4-133">この役割によって、さまざまな機能が管理者に提供されます。</span><span class="sxs-lookup"><span data-stu-id="559d4-133">The roles provide various capabilities to administrators.</span></span> 

| <span data-ttu-id="559d4-134">確認事項</span><span class="sxs-lookup"><span data-stu-id="559d4-134">Ask yourself</span></span> | <span data-ttu-id="559d4-135">アクション</span><span class="sxs-lookup"><span data-stu-id="559d4-135">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="559d4-136">Teams 通信管理者の役割を誰に割り当てるか?</span><span class="sxs-lookup"><span data-stu-id="559d4-136">Who will be assigned the Teams Communications Administrator role?</span></span>|<span data-ttu-id="559d4-137">Teams 管理者の役割の詳細については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-137">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|<span data-ttu-id="559d4-138">Teams 通信サポート エンジニアの役割を誰に割り当てるか?</span><span class="sxs-lookup"><span data-stu-id="559d4-138">Who will be assigned the Teams Communications Support Engineer role?</span></span>|<span data-ttu-id="559d4-139">管理者の役割を割り当てるには、「[Active Directory で管理者の役割と管理者以外の役割をユーザーに割り当てる](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-139">To assign admin roles, see [Assign administrator and non-administrator roles to users with Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>|
|<span data-ttu-id="559d4-140">Teams 通信サポート スペシャリストの役割を誰に割り当てるか?</span><span class="sxs-lookup"><span data-stu-id="559d4-140">Who will be assigned the Teams Communications Support Specialist role?</span></span>||
|||

### <a name="meetings-settings"></a><span data-ttu-id="559d4-141">ミーティングの設定</span><span class="sxs-lookup"><span data-stu-id="559d4-141">Meetings settings</span></span> 

<span data-ttu-id="559d4-142">ミーティングの設定は、匿名ユーザーが Teams のミーティングに参加できるようにするかどうかを制御する場合、ミーティングの出席依頼をセットアップする場合、およびサービスの品質 (QoS) をオンにするときにリアルタイム トラフィック用のポートを設定する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="559d4-142">Meetings settings are used to control whether anonymous users can join Teams meetings, set up meeting invitations, and if you want to turn on Quality of Service (QoS), set the ports for real-time traffic.</span></span> <span data-ttu-id="559d4-143">これらの設定は、組織のユーザーがスケジュール設定するすべての Teams のミーティングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="559d4-143">These settings will be used for all of the Teams meetings that users schedule in your organization.</span></span> 

| <span data-ttu-id="559d4-144">確認事項</span><span class="sxs-lookup"><span data-stu-id="559d4-144">Ask yourself</span></span> | <span data-ttu-id="559d4-145">アクション</span><span class="sxs-lookup"><span data-stu-id="559d4-145">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="559d4-146">初期のミーティングの設定をカスタマイズするか?</span><span class="sxs-lookup"><span data-stu-id="559d4-146">Will I customize the initial meeting settings?</span></span> |<span data-ttu-id="559d4-147">ミーティングの設定の詳細については、[Teams のミーティングのチュートリアル](tutorial-meetings-in-teams.yml)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-147">See the [Meetings in Teams tutorial](tutorial-meetings-in-teams.yml) to learn more about meetings settings.</span></span>|
|<span data-ttu-id="559d4-148">QoS を実装するか?</span><span class="sxs-lookup"><span data-stu-id="559d4-148">Will I implement QoS?</span></span>|<span data-ttu-id="559d4-149">QoS の概念、シナリオ、および実装の詳細は、「[Microsoft Teams でのサービスの品質](qos-in-teams.md)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="559d4-149">See [Quality of Service in Microsoft Teams](qos-in-teams.md) for information about QoS concepts.</span></span> <span data-ttu-id="559d4-150">。</span><span class="sxs-lookup"><span data-stu-id="559d4-150">scenarios, and implementation.</span></span>|
|||

### <a name="meeting-policies"></a><span data-ttu-id="559d4-151">ミーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="559d4-151">Meeting policies</span></span>

<span data-ttu-id="559d4-152">ミーティングのポリシーは、Teams のミーティングに参加するときにユーザーが使用できる機能を制御するために使用します。</span><span class="sxs-lookup"><span data-stu-id="559d4-152">Meeting policies are used to control what features are available to users when they join Teams meetings.</span></span> <span data-ttu-id="559d4-153">既定のポリシーを使用することも、ミーティングをホストする組織内のユーザーに応じた 1 つ以上のポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="559d4-153">You can use the default policy or create one or more custom meeting policies for people that host meetings in your organization.</span></span> <span data-ttu-id="559d4-154">詳細については、[Microsoft Team のミーティングのチュートリアル](tutorial-meetings-in-teams.yml)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-154">To learn more, see the [Meetings in Microsoft Team tutorial](tutorial-meetings-in-teams.yml).</span></span>

| <span data-ttu-id="559d4-155">確認事項</span><span class="sxs-lookup"><span data-stu-id="559d4-155">Ask yourself</span></span> | <span data-ttu-id="559d4-156">アクション</span><span class="sxs-lookup"><span data-stu-id="559d4-156">Action</span></span> |
|--------------|--------|
|<ul><li><span data-ttu-id="559d4-157">初期のミーティング ポリシーをカスタマイズするか?</span><span class="sxs-lookup"><span data-stu-id="559d4-157">Will I customize the initial meeting policies?</span></span></li><li><span data-ttu-id="559d4-158">複数のミーティング ポリシーが必要か?</span><span class="sxs-lookup"><span data-stu-id="559d4-158">Do I require multiple meeting policies?</span></span></li><li><span data-ttu-id="559d4-159">どのユーザーのグループにどのミーティング ポリシーを適用するかについて判断する方法は?</span><span class="sxs-lookup"><span data-stu-id="559d4-159">How will I determine which groups of users get which meetings policy applied?</span></span></li></ul>|<br><span data-ttu-id="559d4-160">「[Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-160">Read [Manage meeting policies in Teams](meeting-policies-in-teams.md).</span></span>|
|||

### <a name="audio-conferencing"></a><span data-ttu-id="559d4-161">電話会議</span><span class="sxs-lookup"><span data-stu-id="559d4-161">Audio Conferencing</span></span>

<span data-ttu-id="559d4-162">電話会議により、組織はあらゆる (臨時またはスケジュールされた) ミーティングへの追加のエントリ ポイントを得られます。会議の参加者は従来の固定電話回線、構内電話交換機 (PBX)、または携帯電話を使用して電話することで、公衆交換電話網 (PSTN) を通じてミーティングに参加できます。</span><span class="sxs-lookup"><span data-stu-id="559d4-162">Audio Conferencing provides organizations with additional entry points to any meeting (ad hoc or scheduled) by allowing meeting participants to join via public switched telephone network (PSTN) by dialing in using a traditional land line, private branch exchange (PBX), or mobile phone.</span></span> 

<span data-ttu-id="559d4-163">電話会議を展開する準備が整っている場合は、詳細な[電話会議の展開](deploy-audio-conferencing-teams-landing-page.md)ガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-163">When you're ready to roll out Audio Conferencing, see the in-depth [Audio Conferencing rollout](deploy-audio-conferencing-teams-landing-page.md) guidance.</span></span>

### <a name="meeting-room-and-personal-devices"></a><span data-ttu-id="559d4-164">会議室と個人用デバイス</span><span class="sxs-lookup"><span data-stu-id="559d4-164">Meeting room and personal devices</span></span>

<span data-ttu-id="559d4-165">Teams のミーティング エクスペリエンスを最適なものにするために、Teams のデバイス (会議室システム、電話機、ヘッドセット、カメラなど) の使用について検討してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-165">For an optimal meeting experience in Teams, consider using Teams devices such as room systems, phones, headsets, and cameras.</span></span> <span data-ttu-id="559d4-166">詳細については、[インテリジェントなコミュニケーションのための Teams のデバイス](https://products.office.com/microsoft-teams/across-devices)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-166">To learn more, see [Teams devices for intelligent communications](https://products.office.com/microsoft-teams/across-devices).</span></span>

| <span data-ttu-id="559d4-167">確認事項</span><span class="sxs-lookup"><span data-stu-id="559d4-167">Ask yourself</span></span> | <span data-ttu-id="559d4-168">アクション</span><span class="sxs-lookup"><span data-stu-id="559d4-168">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="559d4-169">ユーザーのために個人用デバイスを購入するか?</span><span class="sxs-lookup"><span data-stu-id="559d4-169">Will I purchase personal devices for my users?</span></span> |<span data-ttu-id="559d4-170">「[Teams でのデバイスを管理する](device-management.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-170">Read [Manage your devices in Teams](device-management.md).</span></span> |
|<span data-ttu-id="559d4-171">会議室に会議室システムのデバイスを購入して配備するか?</span><span class="sxs-lookup"><span data-stu-id="559d4-171">Will I purchase and deploy room system devices for my conference rooms?</span></span>|<span data-ttu-id="559d4-172">「[会議室のデバイスとソリューション](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-172">Read [Meeting room devices and solutions](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>|
|||

### <a name="reporting"></a><span data-ttu-id="559d4-173">レポート</span><span class="sxs-lookup"><span data-stu-id="559d4-173">Reporting</span></span>

<span data-ttu-id="559d4-174">アクティビティ レポートを使用して、組織内のユーザーがどのように Teams を使用しているかを調べます。</span><span class="sxs-lookup"><span data-stu-id="559d4-174">Use activity reports to see how users in your organization are using Teams.</span></span> <span data-ttu-id="559d4-175">たとえば、まだ Teams を使用していないユーザーがいる場合、そのユーザーは使用の開始方法を知らないか、Teams を使用して生産性と共同作業の効率を向上させる方法を理解していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="559d4-175">For example, if some don’t use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative.</span></span> <span data-ttu-id="559d4-176">組織では、アクティビティ レポートを使用して、トレーニングとコミュニケーションに関する優先項目を判断できます。</span><span class="sxs-lookup"><span data-stu-id="559d4-176">Your organization can use the activity reports to decide where to prioritize training and communication efforts.</span></span> 


| <span data-ttu-id="559d4-177">確認事項</span><span class="sxs-lookup"><span data-stu-id="559d4-177">Ask yourself</span></span> | <span data-ttu-id="559d4-178">アクション</span><span class="sxs-lookup"><span data-stu-id="559d4-178">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="559d4-179">レポート作成の担当者を誰にするか?</span><span class="sxs-lookup"><span data-stu-id="559d4-179">Who will be responsible for reporting?</span></span>|<span data-ttu-id="559d4-180">「[Teams のアクティビティ レポートを使用する](teams-activity-reports.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-180">Read [Use activity reports for Teams](teams-activity-reports.md).</span></span>  |
|<span data-ttu-id="559d4-181">使用状況の監視の担当者を誰にするか?</span><span class="sxs-lookup"><span data-stu-id="559d4-181">Who will be responsible for monitoring usage?</span></span>|<span data-ttu-id="559d4-182">「[Teams での使用状況とフィードバックを監視する](get-started-with-teams-monitor-usage-and-feedback.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-182">Read [Monitor usage and feedback in Teams](get-started-with-teams-monitor-usage-and-feedback.md).</span></span>|
|||

## <a name="additional-deployment-decisions"></a><span data-ttu-id="559d4-183">その他の展開に関する決定事項</span><span class="sxs-lookup"><span data-stu-id="559d4-183">Additional deployment decisions</span></span>

<span data-ttu-id="559d4-184">次の設定は、組織のニーズと構成に基づいて変更できます。</span><span class="sxs-lookup"><span data-stu-id="559d4-184">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="bandwidth-planning"></a><span data-ttu-id="559d4-185">帯域幅の計画</span><span class="sxs-lookup"><span data-stu-id="559d4-185">Bandwidth planning</span></span> 

<span data-ttu-id="559d4-186">帯域の計画により、組織は組織のワイド エリア ネットワークとインターネットのリンク全体でミーティングをサポートするために必要な帯域幅の推定が可能になり、ミーティング サービスの拡大をサポートするためにネットワークが適切にプロビジョニングされていることを確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="559d4-186">Bandwidth planning lets organizations estimate the bandwidth that will be required to support meetings across their wide area networks and internet links so they can confirm that the network is correctly provisioned to support a scaled out meeting service.</span></span> 

| <span data-ttu-id="559d4-187">確認事項</span><span class="sxs-lookup"><span data-stu-id="559d4-187">Ask yourself</span></span> | <span data-ttu-id="559d4-188">アクション</span><span class="sxs-lookup"><span data-stu-id="559d4-188">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="559d4-189">ミーティングの展開前および展開時に帯域幅の計画を実行する必要があるか?</span><span class="sxs-lookup"><span data-stu-id="559d4-189">Do I need to do bandwidth planning prior to and during my Meetings rollout?</span></span> |<span data-ttu-id="559d4-190">詳細および計画プロセスを簡単にするツールへのリンクについては、「[ネットワークの準備](3-envision-evaluate-my-environment.md#network-readiness)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-190">See [Network Readiness](3-envision-evaluate-my-environment.md#network-readiness) for more information and links to tools to simplify your planning process.</span></span>|
|||

### <a name="meeting-recording-and-archiving"></a><span data-ttu-id="559d4-191">ミーティングの記録とアーカイブ</span><span class="sxs-lookup"><span data-stu-id="559d4-191">Meeting recording and archiving</span></span>

<span data-ttu-id="559d4-192">ユーザーは音声、ビデオ、および画面共有のアクティビティをキャプチャするために、ミーティングとグループの通話を記録できます。</span><span class="sxs-lookup"><span data-stu-id="559d4-192">Users can record their meetings and group calls to capture audio, video, and screen sharing activity.</span></span> <span data-ttu-id="559d4-193">自動的に文字起こしする記録のオプションもあるため、ユーザーはミーティングの記録を字幕付きで再生して、会議内容の重要な議題を検索できます。</span><span class="sxs-lookup"><span data-stu-id="559d4-193">There is also an option for recordings to have automatic transcription, so that users can play back meeting recordings with closed captions and search for important discussion items in the transcript.</span></span> <span data-ttu-id="559d4-194">記録はクラウドで実施され Microsoft Stream に保存されるため、ユーザーは組織全体で安全に議事録を共有できます。</span><span class="sxs-lookup"><span data-stu-id="559d4-194">The recording happens in the cloud and is saved in Microsoft Stream, so users can share it securely across their organization.</span></span> <span data-ttu-id="559d4-195">ミーティングの記録を検索するには、ミーティングの会話に移動します。</span><span class="sxs-lookup"><span data-stu-id="559d4-195">To find the recording for a meeting, go to the meeting conversation.</span></span>

<span data-ttu-id="559d4-196">詳細については、「[Teams のクラウド会議の記録](cloud-recording.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-196">To learn more, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

| <span data-ttu-id="559d4-197">確認事項</span><span class="sxs-lookup"><span data-stu-id="559d4-197">Ask yourself</span></span> | <span data-ttu-id="559d4-198">アクション</span><span class="sxs-lookup"><span data-stu-id="559d4-198">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="559d4-199">ミーティングの文字起こしサービスをオンにするか?</span><span class="sxs-lookup"><span data-stu-id="559d4-199">Will I turn on the meeting transcription service?</span></span>|<span data-ttu-id="559d4-200">「[記録の文字起こしをオンまたはオフにする](cloud-recording.md#turn-on-or-turn-off-recording-transcription)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-200">See [Turn on or turn off recording transcription](cloud-recording.md#turn-on-or-turn-off-recording-transcription)</span></span>|
|||


### <a name="live-events-policies"></a><span data-ttu-id="559d4-201">ライブ イベント ポリシー</span><span class="sxs-lookup"><span data-stu-id="559d4-201">Live events policies</span></span>

<span data-ttu-id="559d4-202">Teams のライブ イベント ポリシーは、ユーザー グループのイベント設定を管理するために使用します。</span><span class="sxs-lookup"><span data-stu-id="559d4-202">Teams live events policies are used to manage event settings for groups of users.</span></span> <span data-ttu-id="559d4-203">既定のポリシーを使用することも、ライブ イベントを保持する組織内のユーザーに割り当て可能な追加のポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="559d4-203">You can use the default policy or create additional policies that can be assigned to users who hold live events within your organization.</span></span> 

| <span data-ttu-id="559d4-204">確認事項</span><span class="sxs-lookup"><span data-stu-id="559d4-204">Ask yourself</span></span> | <span data-ttu-id="559d4-205">アクション</span><span class="sxs-lookup"><span data-stu-id="559d4-205">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="559d4-206">自分の組織は Teams のライブ イベントを使用するか?</span><span class="sxs-lookup"><span data-stu-id="559d4-206">Will my organization use Teams live events?</span></span>| <span data-ttu-id="559d4-207">Teams のライブ イベントの計画、設定、および構成に関する詳細については、[ライブ イベントの記事](teams-live-events/what-are-teams-live-events.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-207">See the [live events articles](teams-live-events/what-are-teams-live-events.md) for more information about planning for, setting up, and configuring Teams live events.</span></span>|
|||

### <a name="conference-room-systems-rollout"></a><span data-ttu-id="559d4-208">会議室システムの展開</span><span class="sxs-lookup"><span data-stu-id="559d4-208">Conference room systems rollout</span></span>

<span data-ttu-id="559d4-209">多数の会議室を使用する組織は、会議室の一覧を作成して、適切なデバイスを特定し、それらを展開するための構造化された方法について検討することがあります。</span><span class="sxs-lookup"><span data-stu-id="559d4-209">Organizations with many conference rooms may want to consider a structured approach to inventorying their rooms, identifying the appropriate devices, and then rolling them out.</span></span> 



| <span data-ttu-id="559d4-210">確認事項</span><span class="sxs-lookup"><span data-stu-id="559d4-210">Ask yourself</span></span> | <span data-ttu-id="559d4-211">アクション</span><span class="sxs-lookup"><span data-stu-id="559d4-211">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="559d4-212">会議室システムを展開するために何を実行する必要があるか?</span><span class="sxs-lookup"><span data-stu-id="559d4-212">What do I need to do to roll out conference room systems?</span></span>|<span data-ttu-id="559d4-213">[Plan Microsoft Teams ルーム](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)の記事をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="559d4-213">Check out the [Plan Microsoft Teams Rooms](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) articles.</span></span>|
|||

### <a name="cloud-video-interop"></a><span data-ttu-id="559d4-214">クラウド ビデオ相互運用性</span><span class="sxs-lookup"><span data-stu-id="559d4-214">Cloud video interop</span></span>

<span data-ttu-id="559d4-215">クラウド ビデオ相互運用性により、サード パーティ製の会議室デバイスで Teams のミーティングに参加することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="559d4-215">Cloud video interop makes it possible for third-party meeting room devices to join Teams meetings.</span></span> 

<span data-ttu-id="559d4-216">コンテンツの共同作業にかかわるビデオ会議では、会議を最大限に活用できます。</span><span class="sxs-lookup"><span data-stu-id="559d4-216">Video teleconferencing with content collaboration helps you make the most out of meetings.</span></span> <span data-ttu-id="559d4-217">ただし、会議室システムとデバイスのアップグレードには高価な費用がかかります。</span><span class="sxs-lookup"><span data-stu-id="559d4-217">However, meeting room systems and devices are expensive to upgrade.</span></span> <span data-ttu-id="559d4-218">Teams のクラウド ビデオ相互運用性は、サード パーティ製のシステムと連動して、会議室または Teams のクライアントで、すべての参加者にネイティブなミーティング エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="559d4-218">Cloud video interop for Teams works with third-party systems and delivers a native meeting experience for all participants – in meeting rooms or inside Teams clients.</span></span> 

| <span data-ttu-id="559d4-219">確認事項</span><span class="sxs-lookup"><span data-stu-id="559d4-219">Ask yourself</span></span> | <span data-ttu-id="559d4-220">アクション</span><span class="sxs-lookup"><span data-stu-id="559d4-220">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="559d4-221">会議室システムの展開の一部としてクラウド ビデオ相互運用性ソリューションを使用するか?</span><span class="sxs-lookup"><span data-stu-id="559d4-221">Will I use a cloud video interop solution as part of my room systems deployment?</span></span> | <span data-ttu-id="559d4-222">「[Teams のクラウド ビデオ相互運用性](cloud-video-interop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-222">Read [Cloud Video Interop for Teams](cloud-video-interop.md).</span></span>|
|||


### <a name="personal-device-rollout"></a><span data-ttu-id="559d4-223">個人用デバイスの展開</span><span class="sxs-lookup"><span data-stu-id="559d4-223">Personal device rollout</span></span>

<span data-ttu-id="559d4-224">ミーティングや音声通話の展開をサポートするために個人用デバイスの大規模な展開を計画するときには、再現可能な品質を提供する繰り返し可能なサイトごとの展開プロセスの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-224">When planning a larger rollout of personal devices to support meetings or voice deployments, consider using a repeatable site-by-site rollout process that delivers repeatable quality.</span></span>

| <span data-ttu-id="559d4-225">確認事項</span><span class="sxs-lookup"><span data-stu-id="559d4-225">Ask yourself</span></span> | <span data-ttu-id="559d4-226">アクション</span><span class="sxs-lookup"><span data-stu-id="559d4-226">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="559d4-227">ミーティングの展開にサイトごとのアプローチを使用するか?</span><span class="sxs-lookup"><span data-stu-id="559d4-227">Will I use a site-by-site approach to roll out Meetings?</span></span> |  <span data-ttu-id="559d4-228">「[Teams のサイト有効化プレイブック](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads)」は、独自の展開に使用できる優れた基礎知識を提供しています。</span><span class="sxs-lookup"><span data-stu-id="559d4-228">The [Site enablement playbook for Teams](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads) provides a good foundation that you can use for your own deployments.</span></span> <span data-ttu-id="559d4-229">このガイドは、音声通話に焦点を合わせていますが、デバイスの配布、アカウントの準備、導入、およびトレーニングに関する一般的な概念は、大規模なミーティングの展開に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="559d4-229">The guide is focused on voice, but the general principles of device delivery, account readiness, adoption, and training apply to a large meeting deployment.</span></span> |
|||

### <a name="troubleshoot-meeting-and-call-quality"></a><span data-ttu-id="559d4-230">ミーティングと通話の品質に関するトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="559d4-230">Troubleshoot meeting and call quality</span></span> 

<span data-ttu-id="559d4-231">Teams では、通話品質の問題を監視してトラブルシューティングするために、[通話分析と通話品質ダッシュボード](difference-between-call-analytics-and-call-quality-dashboard.md)という 2 つの方法を利用できます。</span><span class="sxs-lookup"><span data-stu-id="559d4-231">Teams gives you two ways to monitor and troubleshoot call quality problems: [Call Analytics and Call Quality Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md).</span></span> <span data-ttu-id="559d4-232">通話分析は、各ユーザーの特定の通話および会議に関連するデバイス、ネットワーク、および接続性についての詳細情報を示します。</span><span class="sxs-lookup"><span data-stu-id="559d4-232">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user.</span></span> <span data-ttu-id="559d4-233">通話分析は特定の通話の品質にかかわる問題を管理者やヘルプデスク エージェントがトラブルシューティングする際の支援を目的として設計されていますが、通話品質ダッシュボードは管理者やネットワーク エンジニアがネットワークを最適化する際の支援を目的として設計されています。</span><span class="sxs-lookup"><span data-stu-id="559d4-233">Call Analytics is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, whereas the Call Quality Dashboard is designed to help admins and network engineers optimize a network.</span></span> <span data-ttu-id="559d4-234">通話品質ダッシュボードは、特定のユーザーに焦点を合わせるのではなく、Teams 組織全体についての集計情報に注目します。</span><span class="sxs-lookup"><span data-stu-id="559d4-234">Call Quality Dashboard shifts focus from specific users and instead looks at aggregate information for an entire Teams organization.</span></span> 

|<span data-ttu-id="559d4-235">確認事項</span><span class="sxs-lookup"><span data-stu-id="559d4-235">Ask yourself</span></span>|<span data-ttu-id="559d4-236">アクション</span><span class="sxs-lookup"><span data-stu-id="559d4-236">Action</span></span> |
|------------|-------|
| <span data-ttu-id="559d4-237">通話品質の問題についての監視およびトラブルシューティングを誰が担当するか?</span><span class="sxs-lookup"><span data-stu-id="559d4-237">Who will be responsible for monitoring and troubleshooting call quality issues?</span></span> | <span data-ttu-id="559d4-238">通話品質の問題をトラブルシューティングするために必要なアクセス許可レベルの詳細については、「[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-238">Read [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md) for information about permission levels required to troubleshoot call quality issues.</span></span>|
|||

### <a name="operate-your-meetings-service"></a><span data-ttu-id="559d4-239">ミーティング サービスの運用</span><span class="sxs-lookup"><span data-stu-id="559d4-239">Operate your meetings service</span></span>

<span data-ttu-id="559d4-240">Teams のサービスにかかわる全体的な正常性を把握して、サービスに影響を与えるあらゆるイベントについて組織内の他のユーザーに事前に警告できるようにすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="559d4-240">It’s important that you understand the overall health of the Teams service so that you can proactively alert others in your organization of any event that affects the service.</span></span> <span data-ttu-id="559d4-241">「[サービスを運用する](1-drive-value-operate-my-service.md)」の記事には、サービスの運用に関する詳細なガイダンスが記載されています。</span><span class="sxs-lookup"><span data-stu-id="559d4-241">The [Operate my service](1-drive-value-operate-my-service.md) articles provide in-depth guidance for service operations.</span></span>

|<span data-ttu-id="559d4-242">確認事項</span><span class="sxs-lookup"><span data-stu-id="559d4-242">Ask yourself</span></span>|<span data-ttu-id="559d4-243">アクション</span><span class="sxs-lookup"><span data-stu-id="559d4-243">Action</span></span> |
|------------|-------|
|<span data-ttu-id="559d4-244">ミーティング サービスの管理を組織内の誰が担当するか?</span><span class="sxs-lookup"><span data-stu-id="559d4-244">Who in my organization will be responsible for managing the meetings service?</span></span> | <span data-ttu-id="559d4-245">この担当者には、ミーティング サービスを管理するために必要な Teams の管理者アクセス許可があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-245">Make sure this person has the Teams admin permissions they need in order to manage your meetings service.</span></span> <span data-ttu-id="559d4-246">Teams 管理者の役割の詳細については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-246">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|||


## <a name="next-steps"></a><span data-ttu-id="559d4-247">次のステップ</span><span class="sxs-lookup"><span data-stu-id="559d4-247">Next steps</span></span>
- <span data-ttu-id="559d4-248">組織全体にミーティングと会議の[導入を推進する](adopt-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="559d4-248">[Drive adoption](adopt-microsoft-teams-landing-page.md) of meetings & conferencing throughout your organization.</span></span>
- [<span data-ttu-id="559d4-249">電話会議を追加する</span><span class="sxs-lookup"><span data-stu-id="559d4-249">Add audio conferencing</span></span>](deploy-audio-conferencing-teams-landing-page.md)
- [<span data-ttu-id="559d4-250">クラウド ボイスを展開する</span><span class="sxs-lookup"><span data-stu-id="559d4-250">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)
- <span data-ttu-id="559d4-251">お勧めのアプリ (Planner など) を Teams の初期ロールアウトに組み込む。</span><span class="sxs-lookup"><span data-stu-id="559d4-251">Include featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="559d4-252">Teams 導入の進行に応じて、その他の[アプリ、ボット、およびコネクタ](deploy-apps-microsoft-teams-landing-page.md)を追加してください。</span><span class="sxs-lookup"><span data-stu-id="559d4-252">Add other [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>
