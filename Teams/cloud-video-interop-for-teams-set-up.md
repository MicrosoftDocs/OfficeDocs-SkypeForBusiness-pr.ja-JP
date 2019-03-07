---
title: クラウド ビデオ マイクロソフト チームの相互運用機能を設定します。
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: この資料では、計画し、組織でユーザーのクラウドのビデオの相互運用機能を設定する方法について説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b51bcd5cd5813c317c79a5f89656e11423d91412
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462541"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="dcdcc-103">クラウド ビデオ マイクロソフト チームの相互運用機能を設定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="dcdcc-104">[ビデオの相互運用機能をクラウド取引先を選択](cloud-video-interop.md)したら、導入、プロビジョニングの詳細とパートナーのテナントのキーと、組織内のビデオの相互運用アプリケーションに同意の取得の設定を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-104">After you have [chosen on your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="dcdcc-105">プロセスの概要を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-105">The following diagram outlines the process.</span></span> 

![CVI を組織で展開します。](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="dcdcc-107">計画</span><span class="sxs-lookup"><span data-stu-id="dcdcc-107">Plan</span></span>

<span data-ttu-id="dcdcc-108">組織で使用するには、パートナーやパートナーを識別する方法については、[マイクロソフト チームのクラウド ビデオの相互運用機能](cloud-video-interop.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="dcdcc-109">ユーザー ベース、同時実行とサイトのさまざまな支援を計画します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="dcdcc-110">使用する配置モデルとホストされているモデルを選択します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="dcdcc-111">組織に最適なライセンス プランを選択します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="dcdcc-112">Vm の容量の計画では、ビデオ ・ インフラストラクチャをホストしています。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="dcdcc-113">構成</span><span class="sxs-lookup"><span data-stu-id="dcdcc-113">Configure</span></span> 

<span data-ttu-id="dcdcc-114">クラウド ビデオの相互運用機能を構成するのには以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="dcdcc-115">(テナント キー、Appid...) を選択したがあるパートナーやパートナーから構成情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="dcdcc-116">組織の 1 つまたは複数のビデオ相互運用パートナーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="dcdcc-117">ネットワークが正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="dcdcc-118">境界ネットワークの走査をサポートするための標準に準拠したビデオ ファイアウォールを構成します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="dcdcc-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-119">For example:</span></span> 
    - <span data-ttu-id="dcdcc-120">Cisco の VCS-e</span><span class="sxs-lookup"><span data-stu-id="dcdcc-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="dcdcc-121">ポリコム RPAD</span><span class="sxs-lookup"><span data-stu-id="dcdcc-121">Polycom RPAD</span></span>

3. <span data-ttu-id="dcdcc-122">Exchange と OTD に統合された会議室を構成します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="dcdcc-123">ほとんどの場合、その他のリレーを設定する必要がありますで環境内で構成されています。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="dcdcc-124">準備</span><span class="sxs-lookup"><span data-stu-id="dcdcc-124">Provision</span></span>
 
<span data-ttu-id="dcdcc-125">テナントとなるパートナー サービスにダイヤルアウトします。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="dcdcc-126">次の例では、813878896@t.plcm.vc は、テナントのキーです。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![テナントの例](media/tenant-key-example.png) 

<span data-ttu-id="dcdcc-128">テナントのキー、およびビデオの相互運用機能の座標を使用して会議を作成するには、[ユーザーまたは組織全体にも有効にすることは、次のコマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="dcdcc-129">\*\* [Get CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):\*\* マイクロソフトでは、サポートされているパートナーのクラウドのビデオの相互運用機能を使用する取引先を指定するための事前に構築されたポリシーを提供します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="dcdcc-130">このコマンドレットを使用すると、組織内で使用できる事前に構築されたポリシーを識別できます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="dcdcc-131">1 つ以上の補助金 CsTeamsVideoInteropServicePolicy コマンドレットを活用すること、ユーザーにこのポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="dcdcc-132">**[与える CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** 許可 CsTeamsVideoInteropServicePolicy コマンドレットを使用すると、組織で使用するため事前に構築されたポリシーを割り当てたり、特定のユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="dcdcc-133">**[新しいの CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** 新規の CsVideoInteropServiceProvider を使用すると、組織が使用にはサポートされている CVI パートナーに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="dcdcc-134">**[セット CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** セット-CsVideoInteropServiceProvider を使用して、組織で使用して、サポートされている CVI パートナーに関する情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="dcdcc-135">\*\* [Get CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):\*\* 組織内で使用するには、すべての構成されているプロバイダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="dcdcc-136">**[削除 CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** 削除 CsVideoInteropServiceProvider を使用すると、組織が不要になった使用するプロバイダーのすべてのプロバイダー情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="dcdcc-137">同意するものと</span><span class="sxs-lookup"><span data-stu-id="dcdcc-137">Consent</span></span>

<span data-ttu-id="dcdcc-138">ビデオ会議デバイス パートナー サービスを経由して、組織の会議に参加するには、(VTCs) のアクセス許可の承認を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="dcdcc-139">この同意のリンクもパートナーによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="dcdcc-140">次の手順が完了すると、テナントが有効な場合に、Grant コマンドレット、または組織内のユーザーのすべてを使用して個別に有効にするユーザーはこれらのスケジュールを設定するすべてのチーム会議で VTC の座標があります。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="dcdcc-141">VTC は、その座標を使用してこれらの会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="dcdcc-142">名前</span><span class="sxs-lookup"><span data-stu-id="dcdcc-142">Name</span></span>|<span data-ttu-id="dcdcc-143">アプリケーションのアクセス許可の概要</span><span class="sxs-lookup"><span data-stu-id="dcdcc-143">Application Permission Short Description</span></span>| <span data-ttu-id="dcdcc-144">説明</span><span class="sxs-lookup"><span data-stu-id="dcdcc-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="dcdcc-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="dcdcc-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="dcdcc-146">アプリ (プレビュー) とグループ通話や会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="dcdcc-147">サインインしているユーザーに、組織のグループの呼び出しとスケジュールされたミーティングに参加するようにアプリケーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="dcdcc-148">アプリケーションは、テナント内の会議ディレクトリ ユーザーの特権を使用して結合されます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="dcdcc-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="dcdcc-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="dcdcc-150">(プレビュー) ゲスト ユーザーとグループの通話や会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="dcdcc-151">匿名でログインしているユーザーに、組織のグループ呼び出しおよび予約されたミーティングに参加するようにアプリケーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="dcdcc-152">アプリケーションは、テナント内の会議にゲストとして参加できます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="dcdcc-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="dcdcc-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="dcdcc-154">アプリ (プレビュー) としての呼び出しでアクセスのメディア ストリーム</span><span class="sxs-lookup"><span data-stu-id="dcdcc-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="dcdcc-155">呼び出し、サインインしているユーザーがいない状態でメディア ストリームへの直接アクセスを取得するアプリケーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="dcdcc-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="dcdcc-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="dcdcc-157">読み取りオンライン会議の詳細 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="dcdcc-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="dcdcc-158">サインイン中のユーザー、組織内のオンライン会議の詳細を参照するようにアプリケーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="dcdcc-159">スケジュール</span><span class="sxs-lookup"><span data-stu-id="dcdcc-159">Schedule</span></span>

<span data-ttu-id="dcdcc-160">次に、ビデオの相互運用機能の座標を使用してチームの会議のスケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="dcdcc-161">有効なユーザーを使用してチームのミーティングをスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="dcdcc-162">アドインを Outlook の会議のチーム</span><span class="sxs-lookup"><span data-stu-id="dcdcc-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="dcdcc-163">チームのクライアント デスクトップ コンピューターとモバイル</span><span class="sxs-lookup"><span data-stu-id="dcdcc-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="dcdcc-164">Join</span><span class="sxs-lookup"><span data-stu-id="dcdcc-164">Join</span></span>

<span data-ttu-id="dcdcc-165">VTC のデバイスでチームの会議を結合するには次のようにします。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="dcdcc-166">IVR (インタラクティブ音声応答)</span><span class="sxs-lookup"><span data-stu-id="dcdcc-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="dcdcc-167">Tenantkey@domain を使用してパートナーの IVR にダイヤルインすることができます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="dcdcc-168">IVR のパートナーが表示されたらは、VTC の conferenceId、チーム会議に接続し、先の入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="dcdcc-169">直通ダイヤル</span><span class="sxs-lookup"><span data-stu-id="dcdcc-169">Direct dial</span></span>
    - <span data-ttu-id="dcdcc-170">Tenantkey の完全な文字列を使用して直接ダイヤル機能を使用して、パートナーの IVR と対話するのには、チームの会議に直接ダイヤルできます。VTC ConferenceId@domain。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="dcdcc-171">ワンタッチ ダイヤル</span><span class="sxs-lookup"><span data-stu-id="dcdcc-171">One-touch dial</span></span>
    - <span data-ttu-id="dcdcc-172">統合のチームの部屋を使っている場合は、(せずにすべてのダイヤル文字列を入力する必要がある)、パートナーによって提供されているワンタッチ ダイヤル機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="dcdcc-173">最後に、オーディオ、ビデオ、およびコンテンツの共有を使用して、ミーティングでチームのユーザーと連携します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 