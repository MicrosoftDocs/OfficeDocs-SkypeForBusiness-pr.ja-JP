---
title: Microsoft Teams のクラウド ビデオ相互運用機能の設定
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: この記事では、組織内のユーザーについてクラウド ビデオ相互運用を計画して設定する方法について説明します。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64d790e775ac0d76de48a71de8d165656f2e6927
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102603"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="b7c6b-103">Microsoft Teams のクラウド ビデオ相互運用機能の設定</span><span class="sxs-lookup"><span data-stu-id="b7c6b-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="b7c6b-104">[クラウド ビデオ相互運用パートナーを選択](cloud-video-interop.md)した後は、展開を計画し、プロビジョニングの詳細とパートナーのテナント キーを使用して設定を行い、組織のビデオ相互運用アプリに同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-104">After you have [chosen your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="b7c6b-105">この手順を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-105">The following diagram outlines the process.</span></span> 

![組織で CVI を展開する](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="b7c6b-107">計画</span><span class="sxs-lookup"><span data-stu-id="b7c6b-107">Plan</span></span>

<span data-ttu-id="b7c6b-108">組織で使用するパートナーを特定する方法については、「[Microsoft Teams のクラウド ビデオ相互運用](cloud-video-interop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="b7c6b-109">ユーザー ベース、同時、サイト全体での有効化を計画するには</span><span class="sxs-lookup"><span data-stu-id="b7c6b-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="b7c6b-110">使用する展開モデルやホスト モデルを選ぶ</span><span class="sxs-lookup"><span data-stu-id="b7c6b-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="b7c6b-111">組織に最適なライセンス プランを選択する</span><span class="sxs-lookup"><span data-stu-id="b7c6b-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="b7c6b-112">ビデオ インフラストラクチャをホストしている VM の容量を計画する</span><span class="sxs-lookup"><span data-stu-id="b7c6b-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="b7c6b-113">構成</span><span class="sxs-lookup"><span data-stu-id="b7c6b-113">Configure</span></span> 

<span data-ttu-id="b7c6b-114">クラウド ビデオ相互運用を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="b7c6b-115">選択したパートナーから構成情報 (テナント キー、アプリ ID など) を入手します。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="b7c6b-116">組織では、1 つまたは複数のビデオ相互運用パートナーを使用できます</span><span class="sxs-lookup"><span data-stu-id="b7c6b-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="b7c6b-117">ネットワークが正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="b7c6b-118">境界ネットワーク トラバーサルをサポートするために、標準ベースのビデオ ファイアウォールを構成します。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="b7c6b-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-119">For example:</span></span> 
    - <span data-ttu-id="b7c6b-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="b7c6b-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="b7c6b-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="b7c6b-121">Polycom RPAD</span></span>

3. <span data-ttu-id="b7c6b-122">統合された会議室を Exchange と OTD を使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="b7c6b-123">ほとんどの場合、追加の中継は、環境でセットアップして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="b7c6b-124">プロビジョニング</span><span class="sxs-lookup"><span data-stu-id="b7c6b-124">Provision</span></span>
 
<span data-ttu-id="b7c6b-125">テナント キーは、パートナー サービスへのダイヤル アウトになります。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="b7c6b-126">次の例では、813878896@t.plcm.vc がテナント キーです。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![テナント キーの例](media/tenant-key-example.png) 

<span data-ttu-id="b7c6b-128">テナント キーをプロビジョニングするには、次のコマンドレットを実行する必要があります。また、選択したユーザーまたは組織全体がビデオ相互運用座標を使用して会議を作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="b7c6b-129">**[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft では、サポート対象の各パートナーに対して、クラウド ビデオ相互運用性に使用するパートナーを指定できる事前構築ポリシーを提供しています。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-129">**[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="b7c6b-130">このコマンドレットは、組織内で使用できる事前構築ポリシーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="b7c6b-131">Grant-CsTeamsVideoInteropServicePolicy コマンドレットを使用して、このポリシーを 1 人または複数のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="b7c6b-132">**[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** Grant-CsTeamsVideoInteropServicePolicy コマンドレットを使用すると、組織で使用するために事前構築されたポリシーを割り当てたり、特定のユーザーにポリシーを割り当てたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-132">**[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="b7c6b-133">**[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** New-CsVideoInteropServiceProvider を使用して、組織が使用するサポート対象の CVI パートナーに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-133">**[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="b7c6b-134">**[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Set-CsVideoInteropServiceProvider を使用して、組織が使用するサポート対象の CVI パートナーに関する情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-134">**[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="b7c6b-135">**[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** 組織内で使用するために構成されているすべてのプロバイダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-135">**[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="b7c6b-136">**[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Remove-CsVideoInteropServiceProvider を使用して、組織で使用しなくなったプロバイダーに関するすべてのプロバイダー情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-136">**[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="b7c6b-137">同意</span><span class="sxs-lookup"><span data-stu-id="b7c6b-137">Consent</span></span>

<span data-ttu-id="b7c6b-138">パートナー サービスを介して組織の会議に参加するには、ビデオ会議デバイス (VTC) に対するアクセス許可の同意を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="b7c6b-139">また、この同意リンクはパートナーによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="b7c6b-140">これらの手順が完了すると、上記の Grant コマンドレットを使用して個別に有効にされたユーザー、またはテナントが有効な場合は組織内のすべてのユーザーが、スケジュールされているすべての Teams 会議において VTC 座標を持つようになります。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="b7c6b-141">すべての VTC は、これらの座標を使用してこれらの会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="b7c6b-142">名前</span><span class="sxs-lookup"><span data-stu-id="b7c6b-142">Name</span></span>|<span data-ttu-id="b7c6b-143">アプリケーションのアクセス許可の簡潔な説明</span><span class="sxs-lookup"><span data-stu-id="b7c6b-143">Application Permission Short Description</span></span>| <span data-ttu-id="b7c6b-144">説明</span><span class="sxs-lookup"><span data-stu-id="b7c6b-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="b7c6b-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="b7c6b-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="b7c6b-146">グループ通話と会議にアプリとして参加する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="b7c6b-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="b7c6b-147">アプリで、サインインしているユーザーがいなくても、組織のグループ通話やスケジュールされた会議に参加することができるようにします。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="b7c6b-148">このアプリでは、ディレクトリ ユーザーの特権を使用してテナントの会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="b7c6b-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="b7c6b-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="b7c6b-150">グループ通話と会議にゲスト ユーザーとして参加する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="b7c6b-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="b7c6b-151">アプリで、サインインしているユーザーがいなくても、組織のグループ通話とスケジュールされた会議に匿名で参加することができるようにします。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="b7c6b-152">このアプリは、テナントの会議にゲストとして参加します。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="b7c6b-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="b7c6b-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="b7c6b-154">通話内のメディア ストリームにアプリとしてアクセスする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="b7c6b-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="b7c6b-155">アプリで、サインインしているユーザーがいなくても、通話内のメディア ストリームに直接アクセスすることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="b7c6b-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="b7c6b-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="b7c6b-157">オンライン会議の詳細を読み取る (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="b7c6b-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="b7c6b-158">アプリで、サインインしているユーザーがいなくても、組織内のオンライン会議の詳細を読み取ることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="b7c6b-159">スケジュール</span><span class="sxs-lookup"><span data-stu-id="b7c6b-159">Schedule</span></span>

<span data-ttu-id="b7c6b-160">次に、ビデオ相互運用座標を使用して Teams 会議をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="b7c6b-161">有効なユーザーは、次のようにして Teams 会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="b7c6b-162">Outlook 用 Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="b7c6b-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="b7c6b-163">チーム クライアントのデスクトップとモバイル</span><span class="sxs-lookup"><span data-stu-id="b7c6b-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="b7c6b-164">参加</span><span class="sxs-lookup"><span data-stu-id="b7c6b-164">Join</span></span>

<span data-ttu-id="b7c6b-165">次の方法で、Teams 会議を VTC デバイスと結合できます。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="b7c6b-166">IVR (対話型音声応答)</span><span class="sxs-lookup"><span data-stu-id="b7c6b-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="b7c6b-167">tenantkey@domain を使用して、パートナーの IVR にダイヤルインできます。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="b7c6b-168">パートナー IVR に入ると、VTC conferenceId を入力するように求められます。これにより、Teams 会議に接続されます。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="b7c6b-169">直接ダイヤル</span><span class="sxs-lookup"><span data-stu-id="b7c6b-169">Direct dial</span></span>
    - <span data-ttu-id="b7c6b-170">TenantKey の全文字列を使用して、直接ダイヤル機能を使用すると、パートナーの IVR に対する操作なしに、Teams 会議に直接ダイヤルインできます。VTC ConferenceId@domain。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="b7c6b-171">ワンタッチ ダイヤル</span><span class="sxs-lookup"><span data-stu-id="b7c6b-171">One-touch dial</span></span>
    - <span data-ttu-id="b7c6b-172">Teams ミーティングが統合されている場合は、パートナーが提供するワンタッチ ダイヤル機能を使用できます (ダイヤルの文字列を入力する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="b7c6b-173">最後に、音声、ビデオ、コンテンツ共有を使用して、Teams ユーザーと打ち合わせを行います。</span><span class="sxs-lookup"><span data-stu-id="b7c6b-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span>