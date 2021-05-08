---
title: Microsoft Teams でライブ イベント設定を構成する
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
description: 組織内に保持されている Teams のライブ イベントの設定を管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9749484344d969671e8a0195de3386a57388d275
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637879"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="39cd4-103">Microsoft Teams でライブ イベント設定を構成する</span><span class="sxs-lookup"><span data-stu-id="39cd4-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="39cd4-104">Teams のライブ イベント設定を使用して、組織で保持されているライブ イベントの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="39cd4-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="39cd4-105">サポート URL を設定して、サード パーティ製のビデオ配信プロバイダーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="39cd4-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="39cd4-106">この設定は、組織で作成したすべてのライブ イベントに適用します。</span><span class="sxs-lookup"><span data-stu-id="39cd4-106">These settings apply to all live events that are created in your organization.</span></span>

<span data-ttu-id="39cd4-107">Microsoft Teams 管理センターでこの設定を簡単にできます。</span><span class="sxs-lookup"><span data-stu-id="39cd4-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="39cd4-108">左側のナビゲーションで、[**会議**]  >  [**ライブ イベント設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="39cd4-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span>

<span data-ttu-id="39cd4-109">![ライブ イベント設定Teamsスクリーン ショット](../media/teams-live-events-settings.png "管理センター Teamsで構成できるライブ イベント設定のスクリーン Microsoft Teamsショット")</span><span class="sxs-lookup"><span data-stu-id="39cd4-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span>

## <a name="set-up-event-support-url"></a><span data-ttu-id="39cd4-110">イベントのサポート URL を設定する</span><span class="sxs-lookup"><span data-stu-id="39cd4-110">Set up event support URL</span></span>

<span data-ttu-id="39cd4-111">この URL は、ライブ イベントの参加者に表示されます。</span><span class="sxs-lookup"><span data-stu-id="39cd4-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="39cd4-112">ライブ イベント中にサポートへの連絡方法を参加者に提供する組織のサポートの URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="39cd4-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams のロゴが表示されたアイコン](../media/teams-logo-30x30.png) <span data-ttu-id="39cd4-114&quot;>Microsoft Teams 管理センターの使用</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;39cd4-114&quot;>Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id=&quot;39cd4-115&quot;>左側のナビゲーションで、[**会議**]  >  [**ライブ イベント設定**] に移動します。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;39cd4-115&quot;>In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id=&quot;39cd4-116&quot;>[**サポート URL**] で組織のサポート URL を入力します。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;39cd4-116&quot;>Under **Support URL**, enter your organization's support URL.</span></span>

    <span data-ttu-id=&quot;39cd4-117&quot;>![管理センターでのライブ イベントのサポート URL 設定](../media/teams-live-events-settings-supporturl.png &quot;ライブ イベントのサポート URL 設定Teamsスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="39cd4-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="39cd4-118">Windows PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="39cd4-118">Using Windows PowerShell</span></span>

<span data-ttu-id="39cd4-119">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="39cd4-119">Run the following:</span></span>

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
<span data-ttu-id="39cd4-120">詳細については、[CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39cd4-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="39cd4-121">サード パーティ製のビデオ配信プロバイダーを設定する</span><span class="sxs-lookup"><span data-stu-id="39cd4-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="39cd4-122">Microsoft ビデオ配信パートナーを通じてソフトウェア定義ネットワーク (SDN) ソリューションまたはエンタープライズ コンテンツ配信ネットワーク (eCDN) ソリューションを購入してセット アップした場合は、Teams でライブ イベント プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="39cd4-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams のロゴが表示されたアイコン](../media/teams-logo-30x30.png) <span data-ttu-id="39cd4-124&quot;>Microsoft Teams 管理センターの使用</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;39cd4-124&quot;>Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id=&quot;39cd4-125&quot;>左側のナビゲーションで、[**会議**]  >  [**ライブ イベント設定**] に移動します。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;39cd4-125&quot;>In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id=&quot;39cd4-126&quot;>[**サード パーティ製ビデオ配信プロバイダー**] で次を実行します。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;39cd4-126&quot;>Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id=&quot;39cd4-127&quot;>![管理センターのサード パーティのビデオ配信プロバイダーの設定](../media/teams-live-events-settings-distribution-provider.png &quot;ライブ イベントのサード パーティのビデオ配信プロバイダー設定のスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="39cd4-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="39cd4-128">**サード パーティ製配信プロバイダーを使用する** これを選択してサード パーティ製ビデオ配信プロバイダーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="39cd4-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="39cd4-129">**SDN プロバイダー名** お使いのプロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="39cd4-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="39cd4-130">**プロバイダー ライセンス キー** プロバイダーの連絡先から取得したライセンス ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="39cd4-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="39cd4-131">**SDN API テンプレート URL** プロバイダーの連絡先から取得した API のテンプレート URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="39cd4-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="39cd4-132">Windows PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="39cd4-132">Using Windows PowerShell</span></span>
<span data-ttu-id="39cd4-133">プロバイダーの連絡先からのライセンス ID または API トークンと API テンプレートを取得し、お使いのプロバイダーに合わせて次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="39cd4-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="39cd4-134">**Hive**</span><span class="sxs-lookup"><span data-stu-id="39cd4-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="39cd4-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="39cd4-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="39cd4-136">**Riverbed**</span><span class="sxs-lookup"><span data-stu-id="39cd4-136">**Riverbed**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```
<span data-ttu-id="39cd4-137">**Ramp**</span><span class="sxs-lookup"><span data-stu-id="39cd4-137">**Ramp**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```

<span data-ttu-id="39cd4-138">詳細については、[CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39cd4-138">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="39cd4-139">外部アプリまたはデバイスを使用してライブ イベントを作成する場合は、Microsoft Stream を使用して [eCDN](/stream/network-caching)プロバイダーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39cd4-139">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](/stream/network-caching).</span></span> 

>[!Note]
> <span data-ttu-id="39cd4-p104">Microsoft Stream の使用から[会議の記録用の OneDrive for Business および SharePoint ](../tmr-meeting-recording-change.md)への変更は段階的なアプローチになります。リリース時には、この機能にオプトインできるようになります。Stream を使い続けるには、11 月にオプトアウトする必要があります。また、2021 年初頭には、すべてのお客様に、新しい会議の記録に OneDrive と SharePoint を使用するように要請する予定です。</span><span class="sxs-lookup"><span data-stu-id="39cd4-p104">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

>[!Note]
> <span data-ttu-id="39cd4-142">選択した eCDN ソリューションには、選択したサードパーティ プロバイダーのサービス利用規約とプライバシー ポリシーが適用されます。このポリシーによって、eCDN プロバイダーのソリューションの使用が管理されます。</span><span class="sxs-lookup"><span data-stu-id="39cd4-142">Your chosen eCDN solution is subject to the selected 3rd party provider’s terms of service and privacy policy, which will govern your use of the eCDN provider’s solution.</span></span> <span data-ttu-id="39cd4-143">eCDN プロバイダーのソリューションの使用には、Microsoft ボリューム ライセンス条項またはオンライン サービス条件の適用対象となんら適用されないものとします。</span><span class="sxs-lookup"><span data-stu-id="39cd4-143">Your use of the eCDN provider’s solution will not be subject to the Microsoft volume licensing terms or Online Services Terms.</span></span> <span data-ttu-id="39cd4-144">サードパーティ プロバイダーの条項に同意しない場合は、Microsoft Teams で eCDN ソリューションを有効にMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="39cd4-144">If you don't agree to the 3rd party provider’s terms, then don't enable the eCDN solution in Microsoft Teams.</span></span>

### <a name="related-topics"></a><span data-ttu-id="39cd4-145">関連トピック</span><span class="sxs-lookup"><span data-stu-id="39cd4-145">Related topics</span></span>
- [<span data-ttu-id="39cd4-146">Teams のライブ イベントについて</span><span class="sxs-lookup"><span data-stu-id="39cd4-146">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="39cd4-147">Teams のライブ イベントの計画</span><span class="sxs-lookup"><span data-stu-id="39cd4-147">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="39cd4-148">Teams のライブ イベントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="39cd4-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
