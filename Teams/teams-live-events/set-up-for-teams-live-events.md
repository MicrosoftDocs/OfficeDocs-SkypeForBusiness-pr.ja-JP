---
title: マイクロソフトのチームでのライブ イベントを設定します。
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: マイクロソフトのチーム、ネットワークの準備を含むライブ イベントをユーザーのスケジュールを設定し、eCDN プロバイダーの設定を有効にすると、ライセンスを割り当てることでイベントをライブを設定する手順について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6fa8e2bc277bbece7dcbd94fca397e219cdf278
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296381"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a><span data-ttu-id="d11e9-103">マイクロソフトのチームでのライブ イベントを設定します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-103">Set up for live events in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="d11e9-104">ライブ イベントを設定するときにいくつかの手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d11e9-104">When you are setting up for live events, there are several steps that you must take:</span></span>

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a><span data-ttu-id="d11e9-105">手順 1: マイクロソフトのチームでのライブ イベントのネットワークのセットアップします。</span><span class="sxs-lookup"><span data-stu-id="d11e9-105">Step 1: Set up your network for live events in Microsoft Teams</span></span>
<span data-ttu-id="d11e9-106">クイック スタートのライブ イベントでは、[マイクロソフトのチームの組織のネットワークを準備](https://docs.microsoft.com/microsoftteams/prepare-network)するのには必要です。</span><span class="sxs-lookup"><span data-stu-id="d11e9-106">The quick start live events require you to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).</span></span>  

## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="d11e9-107">手順 2: ライセンスを取得して割り当てる</span><span class="sxs-lookup"><span data-stu-id="d11e9-107">Step 2: Get and assign licenses</span></span>
<span data-ttu-id="d11e9-108">正しいライセンスの割り当てがあることを確認して[を作成し、ライブ イベントのスケジュールを設定することができますでしょうか。](#who-can-create-and-schedule-live-events)と[のライブ イベントを監視するですか?](#who-can-watch-live-events)。</span><span class="sxs-lookup"><span data-stu-id="d11e9-108">Ensure you have correct license assignments for [Who can create and schedule live events?](#who-can-create-and-schedule-live-events) and [Who can watch live events?](#who-can-watch-live-events).</span></span>

## <a name="step-3-enable-live-event-scheduling-for-users"></a><span data-ttu-id="d11e9-109">手順 3: ユーザーのライブ イベントのスケジュール設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d11e9-109">Step 3: Enable live event scheduling for users</span></span>
<span data-ttu-id="d11e9-110">チームのユーザーが行う必要があります追加の手順がある外部のエンコーダーのイベントをスケジュールするのにはユーザーのお問い合わせは、かどうかの既定では、ライブ イベントのスケジュールを有効になっています。</span><span class="sxs-lookup"><span data-stu-id="d11e9-110">Live event scheduling is enabled by default for Teams users but if you are wanting users to schedule external encoder events there are additional steps that you must do.</span></span>

### <a name="for-quick-start-events"></a><span data-ttu-id="d11e9-111">クイック スタートのイベント</span><span class="sxs-lookup"><span data-stu-id="d11e9-111">For quick start events</span></span>
<span data-ttu-id="d11e9-112">チーム PowerShell では、 **TeamsMeetingBroadcastPolicy**の*AllowBroadcastScheduling*コントロールの設定を使用して、ユーザーは、かに、チームでのライブ イベントを作成できるかどうか。</span><span class="sxs-lookup"><span data-stu-id="d11e9-112">Use the setting *AllowBroadcastScheduling* in **TeamsMeetingBroadcastPolicy** in Teams PowerShell to control whether the user can create live events in Teams or not.</span></span> <span data-ttu-id="d11e9-113">TeamsMeetingBroadcastPolicy の管理に関する詳細については、[ここで](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d11e9-113">You can learn more about managing TeamsMeetingBroadcastPolicy [here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

 <span data-ttu-id="d11e9-114">ユーザーに割り当てられているカスタム ポリシーが割り当てられていない場合、*グローバル*ポリシーは、既定で有効になっている記録を持っているが、ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d11e9-114">If you haven't assigned a custom policy assigned to the users, the users will get the *Global* policy, which has recording enabled by default.</span></span>

<span data-ttu-id="d11e9-115">*AllowBroadcastScheduling*パラメーターが*True*に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-115">Verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="d11e9-116">*グローバル*ポリシーの実行にユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d11e9-116">Then assign the user to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="user-scenarios"></a><span data-ttu-id="d11e9-117">ユーザー シナリオ</span><span class="sxs-lookup"><span data-stu-id="d11e9-117">User scenarios</span></span>
<span data-ttu-id="d11e9-118">**ライブ イベントを作成できるよう、社内のすべてのユーザーをします。**</span><span class="sxs-lookup"><span data-stu-id="d11e9-118">**You want all users in your company to be able to create live events.**</span></span>

<span data-ttu-id="d11e9-119">実行し、確認の場合はユーザーには、 *「ローカル*ポリシーが割り当てられているが、その*AllowBroadcastScheduling* \* *True*に設定します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-119">If users are assigned the *Glocal* policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="d11e9-120">ユーザーには、*グローバル*ポリシー以外のポリシーが割り当てられている場合、次を実行し、 *-AllowBroadcastScheduling*が*True*に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-120">If the users are assigned a policy other than the *Global* policy, run the following and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

<span data-ttu-id="d11e9-121">**ライブ イベントを組織全体で 100% 無効にするスケジュールを設定します。**</span><span class="sxs-lookup"><span data-stu-id="d11e9-121">**You want live event scheduling to be 100% disabled across your organization.**</span></span>

<span data-ttu-id="d11e9-122">ブロードキャストのスケジュールを無効にするには、実行します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-122">Disable broadcast scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="d11e9-123">*グローバル*ポリシーは、実行するには、組織内のすべてのユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d11e9-123">Assign all users in your organization to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="d11e9-124">**ライブ イベントを作成できるユーザーの数が多いが、一連のユーザーがそれらを作成することを防止します。**</span><span class="sxs-lookup"><span data-stu-id="d11e9-124">**You want a large number of users to be able to create live events, but want to prevent a set of users from creating them.**</span></span>

<span data-ttu-id="d11e9-125">一部のユーザーを有効にする) の**補助金 CsTeamsMeetingBroadcastPolicy**を使用して、*グローバル*ポリシーを割り当てるが最初次を実行して、 *AllowBroadcastScheduling*が*True*に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-125">Assign the *Global* policy using the **Grant-CsTeamsMeetingBroadcastPolicy** for some of the users (that you want enabled) but first run the following and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="d11e9-126">*グローバル*ポリシーの実行にユーザーまたはユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d11e9-126">Then assign a user or users to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="d11e9-127">作成し、(無効にする)、他のユーザーに**与える CsTeamsMeetingBroadcastPolicy**コマンドレットを使用してスケジュール設定を無効にするポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-127">Create and assign a policy for disabling scheduling using the  **Grant-CsTeamsMeetingBroadcastPolicy** cmdlet to the other users (you want disabled).</span></span> 

<span data-ttu-id="d11e9-128">新しいポリシーを作成すると無効になっていることを実行します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-128">Create the new policy with it disabled, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
<span data-ttu-id="d11e9-129">スケジュールを無効にするを実行します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-129">Disable scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="d11e9-130">このポリシーの実行にユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d11e9-130">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
<span data-ttu-id="d11e9-131">**ライブのイベントを無効にするか、ユーザーの数が多いですが、それを作成するユーザーのセットを許可します。**</span><span class="sxs-lookup"><span data-stu-id="d11e9-131">**You want live events to be disabled for a large number of the users, but want to allow a set of users to create them.**</span></span>

<span data-ttu-id="d11e9-132">ブロードキャストのスケジュールを無効にするには、実行します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-132">Disable broadcast scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="d11e9-133">*グローバル*ポリシーの実行にこれらのユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d11e9-133">Then assign those users to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="d11e9-134">作成、スケジュール設定を有効にするポリシーを割り当てると、実行します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-134">Create and assign a policy for enabling scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="d11e9-135">スケジューリングを有効にするを実行します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-135">Enable scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="d11e9-136">このポリシーの実行にユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d11e9-136">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

### <a name="for-external-encoder-events"></a><span data-ttu-id="d11e9-137">外部エンコーダーのイベント</span><span class="sxs-lookup"><span data-stu-id="d11e9-137">For external encoder events</span></span>
<span data-ttu-id="d11e9-138">ライブ イベントをそれらのユーザーのスケジュール設定を有効にするのには、次を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d11e9-138">You must do the following to enable live event scheduling for those users.</span></span>

#### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a><span data-ttu-id="d11e9-139">手順 1: のユーザー、組織 \* \* マイクロソフトのストリームを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d11e9-139">Step 1: Enable Microsoft Stream for users in your organization\*\*</span></span>
<span data-ttu-id="d11e9-140">Microsoft ストリームは、対象の Office 365 サブスクリプションの一部として、またはスタンドアロン サービスとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="d11e9-140">Microsoft Stream is available as part of eligible Office 365 subscriptions or as a standalone service.</span></span> <span data-ttu-id="d11e9-141">詳細については、[ストリームのライセンスの概要](https://docs.microsoft.com/stream/license-overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11e9-141">See [Stream licensing overview](https://docs.microsoft.com/stream/license-overview) for more details.</span></span>

> <span data-ttu-id="d11e9-142">![メモ]ビジネスに関する重要事項またはビジネス プレミアム プランでは、マイクロソフトのストリームが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d11e9-142">![NOTE] Microsoft Stream is not included in Business Essentials or Business Premium plans.</span></span>  

<span data-ttu-id="d11e9-143">方法[Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)ユーザーが Microsoft のストリームにアクセスできるようにする方法の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-143">Learn more about how you can [assign licenses to users in Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) so that users can access Microsoft Stream.</span></span> <span data-ttu-id="d11e9-144">[この資料](https://docs.microsoft.com/stream/disable-user-organization)で定義されているユーザーの Microsoft のストリームがブロックされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-144">Ensure Microsoft Stream is not blocked for the users as defined in [this article](https://docs.microsoft.com/stream/disable-user-organization).</span></span>

#### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a><span data-ttu-id="d11e9-145">手順 2: は、ユーザーは、ライブ イベントの作成のアクセス許可を持つで Microsoft \* ストリーム \* ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-145">Step 2: Ensure users have live event creation permission in Microsoft Stream\*\*</span></span>
<span data-ttu-id="d11e9-146">既定では、管理者がエンコーダーを作成する外部のライブ イベントです。</span><span class="sxs-lookup"><span data-stu-id="d11e9-146">By default, administrators can create external encoder live events.</span></span> <span data-ttu-id="d11e9-147">Microsoft ストリームの管理者は、ストリームでの[ライブ イベントを作成するための他のユーザーを有効にする](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating)ことができます。</span><span class="sxs-lookup"><span data-stu-id="d11e9-147">Microsoft Stream administrator can [enable additional users for live event creation](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) in Stream.</span></span>  

#### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a><span data-ttu-id="d11e9-148">手順 3: がライブ イベントを開催者が会社のポリシーでストリームの管理 \* \* に設定するに同意したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-148">Step 3: Ensure live event organizers have consented to the company policy set by Stream admin\*\*</span></span>
<span data-ttu-id="d11e9-149">Microsoft ストリームには、管理者[、会社のガイドラインのポリシーを設定する](https://docs.microsoft.com/stream/company-policy-and-consent)には、従業員がコンテンツを保存する前にこのポリシーをそのまま使用する必要がありますし、ユーザーする必要がありますようにチームで (外部のエンコーダーの生産) でのライブ イベントを作成する前にします。</span><span class="sxs-lookup"><span data-stu-id="d11e9-149">If a Microsoft Stream administrator has [set up a company guidelines policy](https://docs.microsoft.com/stream/company-policy-and-consent) and requires employees to accept this policy before saving content, then users must do so before creating a live event (with External Encoder production) in Teams.</span></span> <span data-ttu-id="d11e9-150">組織でのライブ イベントの機能をロールアウトする前にこれらのライブ イベントを作成するユーザーは、ポリシーに同意したがいることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-150">Before you rollout the live events feature in the organization, make sure users who will be creating these live events have consented to the policy.</span></span> 

## <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a><span data-ttu-id="d11e9-151">手順 4: マイクロソフトのチームでのライブ イベントの eCDN のプロバイダーのセットアップします。</span><span class="sxs-lookup"><span data-stu-id="d11e9-151">Step 4: Set up eCDN provider for live events in Microsoft Teams</span></span> 
<span data-ttu-id="d11e9-152">適応のビットレート (ABR) のストリーミングを使用して、ライブ イベントのビデオの再生は、ユニキャスト ストリーム、つまり、万人がインターネットから自分のビデオ ストリームを取得します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-152">Playback of live event videos uses adaptive bitrate streaming (ABR) but it is a unicast stream, meaning every viewer is getting their own video stream from the internet.</span></span> <span data-ttu-id="d11e9-153">ライブ イベントや、組織の大部分に送信されるビデオは、膨大なインターネットの帯域幅のあるユーザーによって消費されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d11e9-153">For live events or videos sent out to large portions of your organization, there could be a significant amount of internet bandwidth consumed by viewers.</span></span> <span data-ttu-id="d11e9-154">ライブ イベントの場合は、このインターネット トラフィックを削減する組織では、マイクロソフトのソリューションは、統合のライブ イベントでは、ソフトウェアを提供するビデオの配信パートナーには、ネットワーク (SDNs) またはエンタープライズ ・ コンテンツ配信ネットワーク (eCDNs) が定義されている信頼されています。</span><span class="sxs-lookup"><span data-stu-id="d11e9-154">For organizations that want to reduce this internet traffic for live events, live events solutions are integrated with Microsoft's trusted video delivery partners offering software defined networks (SDNs) or enterprise content delivery networks (eCDNs).</span></span> <span data-ttu-id="d11e9-155">これらの SDN/eCDN ・ プラットフォームを犠牲にエンド ユーザー エクスペリエンスを表示することがなくネットワークの帯域幅を最適化するために組織を有効化します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-155">These SDN / eCDN platforms enable organizations to optimize network bandwidth without sacrificing end user viewing experiences.</span></span> <span data-ttu-id="d11e9-156">パートナーは、エンタープライズ ネットワーク上よりスケーラブルで効率的なビデオ配信を有効にするに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d11e9-156">Our partners can help enable a more scalable and efficient video distribution across your enterprise network.</span></span>

<span data-ttu-id="d11e9-157">**購入とセットアップのソリューションをマイクロソフトのチーム以外で**マイクロソフトのビデオ配信を信頼できるパートナーを活用することでビデオの配信を拡大・縮小で専門的なヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-157">**Purchase & setup your solution outside of Microsoft Teams** Get expert help with scaling video delivery by leveraging Microsoft’s trusted video delivery partners.</span></span> <span data-ttu-id="d11e9-158">チームで使用するビデオ配信プロバイダーを有効にすることができます前に購入して外部とのチームとは別に SDN と eCDN ソリューションをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="d11e9-158">Before you can enable a video delivery provider to be used with Teams you must purchase and setup the SDN/eCDN solution outside and separate from Teams.</span></span>

<span data-ttu-id="d11e9-159">次の SDN と eCDN ソリューションは、事前統合されてし、Microsoft のストリームで使用する設定をすることができます。</span><span class="sxs-lookup"><span data-stu-id="d11e9-159">The following SDN/eCDN solutions are pre-integrated and can be setup to be used with Microsoft Stream.</span></span>

- <span data-ttu-id="d11e9-160">**ハイブのストリーミング**ビデオ配信のライブとオンデマンドのエンタープライズのシンプルかつ強力なソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-160">**Hive Streaming** provides a simple and powerful solution for live and on-demand enterprise video distribution.</span></span> <span data-ttu-id="d11e9-161">ハイブは、追加のハードウェアや帯域幅は必要ありませんし、何千ものネットワークに影響を与えず、同時のビデオ ビューアーを有効にするセキュリティで保護された方法を提供するソフトウェア ・ ベースのソリューションです。</span><span class="sxs-lookup"><span data-stu-id="d11e9-161">Hive is a software-based solution that requires no additional hardware or bandwidth and provides a secure way to enable thousands of simultaneous video viewers without impact to your network.</span></span> <span data-ttu-id="d11e9-162">お客様への影響のビデオが、SDN と eCDN ソリューションを購入する前に、ネットワーク上にあるを理解して、ハイブのストリーミングが用意されていますブラウザ ・ ベースの分析ソリューション マイクロソフト ユーザーの場合。</span><span class="sxs-lookup"><span data-stu-id="d11e9-162">For customers looking to understand the impact video is having on their network prior to purchasing an SDN/eCDN solution, Hive Streaming also provides a browser-based analytics solution for Microsoft customers.</span></span> <span data-ttu-id="d11e9-163">[の詳細を表示](https://www.hivestreaming.com/partners/integration-partners/microsoft/)します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-163">[Learn more](https://www.hivestreaming.com/partners/integration-partners/microsoft/).</span></span>
 
- <span data-ttu-id="d11e9-164">**Kollective**クラウド ・ ベースのスマート ピアリング配布プラットフォーム (ライブのストリーミング ・ ビデオ、オンデマンド ビデオ、ソフトウェアの更新プログラム、セキュリティ修正プログラムなど) には、さまざまな形式でコンテンツを配信する既存のネットワーク インフラストラクチャを活用するがより迅速に、確実にしより少ない帯域幅にします。</span><span class="sxs-lookup"><span data-stu-id="d11e9-164">**Kollective** is a cloud-based, smart peering distribution platform that leverages your existing network infrastructure to deliver content, in many forms, (live streaming video, on-demand video, software updates, security patches, etc.) faster, more reliably and with less bandwidth.</span></span> <span data-ttu-id="d11e9-165">ハードウェアの追加と、世界最大の金融機関によって信頼されている、セキュリティで保護されたプラットフォームでは、セットアップと保守が容易です。</span><span class="sxs-lookup"><span data-stu-id="d11e9-165">Our secure platform is trusted by the world’s largest financial institutions and with no additional hardware, setup and maintenance are easy.</span></span> <span data-ttu-id="d11e9-166">[の詳細を表示](http://www.kollective.com)します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-166">[Learn more](http://www.kollective.com).</span></span>
 
- <span data-ttu-id="d11e9-167">イベントの製作者を支援するネットワーク帯域幅を最適化し、成功したライブ イベントのブロードキャストとオン ・ デマンドをサポートして、**ランプの OmniCache**は、次世代ネットワークの配分を提供し、グローバル Wan 経由でビデオ コンテンツのシームレスな配信を保証ストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="d11e9-167">**Ramp OmniCache** provides next-generation network distribution and ensures seamless delivery of video content across global WANs, helping event producers optimize network bandwidth and support successful live event broadcasts and on-demand streaming.</span></span> <span data-ttu-id="d11e9-168">ランプの OmniCache のライブ イベントのクイック スタートのサポートを準備中です。</span><span class="sxs-lookup"><span data-stu-id="d11e9-168">The support for Ramp OmniCache for quick start live events is coming soon.</span></span>  <span data-ttu-id="d11e9-169">[の詳細を表示](http://www.ramp.com)します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-169">[Learn more](http://www.ramp.com).</span></span> 
 
> [!NOTE] 
> <span data-ttu-id="d11e9-170">選択した eCDN ソリューションでは、選択した**サード パーティ プロバイダーのサービスとプライバシーのポリシー条件**、eCDN プロバイダーのソリューションの使用を制御するは。</span><span class="sxs-lookup"><span data-stu-id="d11e9-170">Your chosen eCDN solution is subject to the selected **3rd party provider’s terms of service and privacy policy**, which will governs your use of the eCDN provider’s solution.</span></span> <span data-ttu-id="d11e9-171">マイクロソフト ボリューム ライセンス契約の条項またはオンライン サービスの条件は、eCDN プロバイダーのソリューションを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d11e9-171">Your use of the eCDN provider’s solution will not be subject to the Microsoft volume licensing terms or Online Services Terms.</span></span> <span data-ttu-id="d11e9-172">**サード パーティ プロバイダーの条件**に同意しない場合はチームの eCDN ソリューション有効にしないし。</span><span class="sxs-lookup"><span data-stu-id="d11e9-172">If you do not agree to the **3rd party provider’s terms**, then don't enable the eCDN solution in Teams.</span></span> 

<span data-ttu-id="d11e9-173">**設定可能な「クイック スタート」eCDN のライブ イベント**PowerShell を使用するチームでは、ライブ イベントの eCDN のプロバイダーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d11e9-173">**Set up an eCDN for "Quick start" live events** You can configure eCDN provider for live events in Teams using PowerShell.</span></span> 

> [!NOTE] 
> <span data-ttu-id="d11e9-174">組織の 1 つの eCDN プロバイダーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d11e9-174">A single eCDN provider can be configured for your organization.</span></span> 

<span data-ttu-id="d11e9-175">***ハイブ***[セット CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell コマンドレットを使用するには eCDN のプロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-175">***Hive*** You can use [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet to configure eCDN provider.</span></span> <span data-ttu-id="d11e9-176">まず以下を実行して、ハイブのメンバーからライセンス ID と API のテンプレートの URL を入手します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-176">First obtain the license ID and API template URL from your Hive contact then run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="d11e9-177">***Kollective***[セット CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell コマンドレットを使用するには eCDN のプロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-177">***Kollective*** You can use [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet to configure eCDN provider.</span></span> <span data-ttu-id="d11e9-178">最初から Kollective 相手では、API トークンおよび API のテンプレートの URL を取得し、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-178">First obtain the API token and the API template URL from your Kollective contact, then run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="d11e9-179">**「外部エンコーダー」のライブ イベントを、eCDN を設定します**</span><span class="sxs-lookup"><span data-stu-id="d11e9-179">**Set up an eCDN for "External encoder" live events**</span></span> 

<span data-ttu-id="d11e9-180">外部エンコーダーを使用して、ライブのイベントを作成する場合は、[マイクロソフトのストリームで、eCDN のプロバイダーを構成する](https://docs.microsoft.com/stream/network-caching)にもする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d11e9-180">If you plan to create live events that use external encoders, you will need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching) as well.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="d11e9-181">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d11e9-181">Next steps</span></span>
<span data-ttu-id="d11e9-182">[Confgure チーム ライブ イベント](configure-teams-live-events.md)に移動します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-182">Go to [Confgure Teams live events](configure-teams-live-events.md).</span></span>
