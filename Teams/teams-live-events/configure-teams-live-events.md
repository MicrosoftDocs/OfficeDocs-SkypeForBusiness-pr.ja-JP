---
title: Microsoft Teams でライブ イベント設定を構成する
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 組織内に保持されているチームのライブ イベントの設定を管理する方法について説明します。
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3c1a3c4883705f5e9e5ded88cce94fc37da650b
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30664893"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="cd1c9-103">Microsoft Teams でライブ イベント設定を構成する</span><span class="sxs-lookup"><span data-stu-id="cd1c9-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="cd1c9-104">チームのライブ イベントの設定を使用すると、組織内で保持されているライブのイベントの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="cd1c9-105">サポート URL を設定し、サード ・ パーティ製ビデオ配信プロバイダーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="cd1c9-106">これらの設定は、組織内に作成されるすべてのライブ イベントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="cd1c9-107">マイクロソフトのチームの管理センターでこれらの設定を簡単に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="cd1c9-108">左側のナビゲーションで**の会議**に移動する > **のライブ イベントを設定**します。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="cd1c9-109">![ライブ イベント settings.png](../media/teams-live-events-settings.png "チームのスクリーン ショットは、マイクロソフトのチームの管理センターで構成可能なイベントの設定をライブ")</span><span class="sxs-lookup"><span data-stu-id="cd1c9-109">![live-event-settings.png](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="cd1c9-110">イベント サポートの URL を設定します</span><span class="sxs-lookup"><span data-stu-id="cd1c9-110">Set up event support URL</span></span>

<span data-ttu-id="cd1c9-111">ライブ イベントの参加者には、この URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="cd1c9-112">ライブ イベント中に、サポートに連絡する方法を参加者に提供する組織のサポート URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![チーム ・ ロゴ ・ 30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="cd1c9-114">マイクロソフトのチーム管理センターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="cd1c9-115">左側のナビゲーションでは、**会議**に移動 > **ライブ イベントを設定**します。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="cd1c9-116">[**サポート URL**] には、組織のサポートの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="cd1c9-117">![ライブ マイクロソフト チームの管理センターでのイベントのサポート URL の設定](../media/teams-live-events-settings-supporturl.png "スクリーン ショットは、チームのライブ イベントを設定する URL をサポート")</span><span class="sxs-lookup"><span data-stu-id="cd1c9-117">![Support URL setting for live events in the Microsoft Teams admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="cd1c9-118">The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.</span><span class="sxs-lookup"><span data-stu-id="cd1c9-118">Using Windows PowerShell</span></span>
<span data-ttu-id="cd1c9-119">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-119">Run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="cd1c9-120">詳細については、[一連の CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="cd1c9-121">サード ・ パーティ製ビデオ配信プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="cd1c9-122">購入し、定義されているソフトウェアのネットワーク (SDN) ソリューションや Microsoft ビデオ配信パートナーを通じて、エンタープライズ コンテンツ配信ネットワーク (eCDN) ソリューションを設定すると場合、は、チームでのライブ イベントのプロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![チーム ・ ロゴ ・ 30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="cd1c9-124">マイクロソフトのチーム管理センターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="cd1c9-125">左側のナビゲーションでは、**会議**に移動 > **ライブ イベントを設定**します。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="cd1c9-126">[**サード パーティのビデオ配信プロバイダー**では、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="cd1c9-127">![マイクロソフトのチームの管理センターでのサード ・ パーティ製ビデオ配信プロバイダーの設定](../media/teams-live-events-settings-distribution-provider.png "サード ・ パーティ製ビデオ配信プロバイダーの設定のスクリーン ショットのライブ イベント")</span><span class="sxs-lookup"><span data-stu-id="cd1c9-127">![Third-party video distribution provider settings in the Microsoft Teams admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="cd1c9-128">**配布のサード ・ パーティ製プロバイダーを使用**サード ・ パーティ製ビデオ配信プロバイダーを有効にするには、これを有効にします。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="cd1c9-129">**SDN プロバイダー名**使用しているプロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="cd1c9-130">**プロバイダー ライセンス ・ キー**相手のプロバイダーから入手したライセンス ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="cd1c9-131">**SDN API テンプレートの URL**相手のプロバイダーから入手した API のテンプレートの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="cd1c9-132">The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.</span><span class="sxs-lookup"><span data-stu-id="cd1c9-132">Using Windows PowerShell</span></span>
<span data-ttu-id="cd1c9-133">プロバイダーの連絡先からライセンス ID または API トークンおよび API のテンプレートを取得し、お使いのプロバイダーに応じて、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="cd1c9-134">**ハイブ**</span><span class="sxs-lookup"><span data-stu-id="cd1c9-134">**Hive**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="cd1c9-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="cd1c9-135">**Kollective**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="cd1c9-136">詳細については、[一連の CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="cd1c9-137">外部エンコーダーを使用して、ライブのイベントを作成する場合は、[マイクロソフトのストリームで、eCDN のプロバイダーを設定](https://docs.microsoft.com/stream/network-caching)する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="cd1c9-137">If you plan to create live events that use external encoders, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="cd1c9-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd1c9-138">Related topics</span></span>
- [<span data-ttu-id="cd1c9-139">Teams のライブ イベントについて</span><span class="sxs-lookup"><span data-stu-id="cd1c9-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="cd1c9-140">Teams のライブ イベントの計画</span><span class="sxs-lookup"><span data-stu-id="cd1c9-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="cd1c9-141">Teams のライブ イベントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="cd1c9-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)