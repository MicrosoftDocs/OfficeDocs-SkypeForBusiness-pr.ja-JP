---
title: Microsoft Teams のクラウド ビデオ相互運用性の設定
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
description: この記事では、組織内のユーザーに対してクラウドビデオの相互運用機能を計画してセットアップする方法について説明します。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a94292719f8f93b818cbc52dd312859611940e3b
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516663"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="9c57b-103">Microsoft Teams のクラウド ビデオ相互運用性の設定</span><span class="sxs-lookup"><span data-stu-id="9c57b-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="9c57b-104">[クラウドビデオの相互運用パートナーを選択](cloud-video-interop.md)した後は、展開を計画し、プロビジョニングの詳細とパートナーのテナントキーを設定して、組織内のビデオ相互運用アプリへの同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c57b-104">After you have [chosen your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="9c57b-105">次の図は、プロセスの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="9c57b-105">The following diagram outlines the process.</span></span> 

![組織での CVI の展開](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="9c57b-107">計画</span><span class="sxs-lookup"><span data-stu-id="9c57b-107">Plan</span></span>

<span data-ttu-id="9c57b-108">組織で使用するパートナーまたはパートナーを特定する方法については、「 [Microsoft Teams のクラウドビデオ相互運用機能](cloud-video-interop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c57b-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="9c57b-109">ユーザーに基づく、同時、またはサイト全体の有効化を計画するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9c57b-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="9c57b-110">使用する展開モデル/ホストモデルを選ぶ</span><span class="sxs-lookup"><span data-stu-id="9c57b-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="9c57b-111">組織に最適なライセンスプランを選択します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="9c57b-112">Vm の容量を計画するには、ビデオインフラストラクチャをホストしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c57b-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="9c57b-113">構成</span><span class="sxs-lookup"><span data-stu-id="9c57b-113">Configure</span></span> 

<span data-ttu-id="9c57b-114">クラウドビデオ相互運用機能を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="9c57b-115">選択したパートナー/パートナーから構成情報を取得します (テナントキー、appIds...)。</span><span class="sxs-lookup"><span data-stu-id="9c57b-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="9c57b-116">組織では、1つ以上のビデオ相互運用パートナーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c57b-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="9c57b-117">ネットワークが正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="9c57b-118">境界ネットワークトラバーサルをサポートするために、標準ベースのビデオファイアウォールを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="9c57b-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-119">For example:</span></span> 
    - <span data-ttu-id="9c57b-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="9c57b-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="9c57b-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="9c57b-121">Polycom RPAD</span></span>

3. <span data-ttu-id="9c57b-122">統合された会議室を exchange と OTD で構成します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="9c57b-123">ほとんどの場合、追加の中継は環境で設定して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c57b-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="9c57b-124">規定</span><span class="sxs-lookup"><span data-stu-id="9c57b-124">Provision</span></span>
 
<span data-ttu-id="9c57b-125">テナントキーは、パートナーサービスへのダイヤルアウトになります。</span><span class="sxs-lookup"><span data-stu-id="9c57b-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="9c57b-126">次の例では、813878896@t.plcm.vc はテナントキーです。</span><span class="sxs-lookup"><span data-stu-id="9c57b-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![テナントキーの例](media/tenant-key-example.png) 

<span data-ttu-id="9c57b-128">テナントキーをプロビジョニングするには、次のコマンドレットを実行する必要があります。また、選択したユーザーまたは組織全体で、ビデオ相互運用機能による会議を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9c57b-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="9c57b-129">\*\* [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):\*\* Microsoft は、クラウドビデオ相互運用に使用するパートナーを指定することができる、サポートされている各パートナーの事前構築ポリシーを提供しています。</span><span class="sxs-lookup"><span data-stu-id="9c57b-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="9c57b-130">このコマンドレットでは、組織で使用できる事前構築済みのポリシーを識別できます。</span><span class="sxs-lookup"><span data-stu-id="9c57b-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="9c57b-131">このポリシーは、Grant-CsTeamsVideoInteropServicePolicy コマンドレットを利用する1人以上のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9c57b-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="9c57b-132">\*\* [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):\*\* Grant-CsTeamsVideoInteropServicePolicy コマンドレットを使用すると、組織で使用するために事前構築されたポリシーを割り当てることができます。または、特定のユーザーにポリシーを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="9c57b-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="9c57b-133">**[新規-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** 組織で使用する、サポートされている CVI パートナーに関する情報を指定するには、CsVideoInteropServiceProvider を使用します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="9c57b-134">\*\* [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):\*\* CsVideoInteropServiceProvider を使用して、組織が使用するサポートされている CVI パートナーに関する情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="9c57b-135">\*\* [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):\*\* 組織内で使用するように構成されているすべてのプロバイダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="9c57b-136">\*\* [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):\*\* 組織で使用されなくなったプロバイダーに関するすべてのプロバイダー情報を削除するには、CsVideoInteropServiceProvider を使用します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="9c57b-137">同意</span><span class="sxs-lookup"><span data-stu-id="9c57b-137">Consent</span></span>

<span data-ttu-id="9c57b-138">パートナーサービス経由で組織の会議に参加するには、ビデオ会議デバイス (VTCs) に対するアクセス許可の同意を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c57b-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="9c57b-139">この同意リンクは、パートナーによって提供されることもあります。</span><span class="sxs-lookup"><span data-stu-id="9c57b-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="9c57b-140">これらの手順を完了すると、上記の Grant コマンドレット、またはテナントが有効になっている場合、組織内のすべてのユーザーに対して個別に許可されているユーザーには、スケジュールされているすべてのチーム会議の VTC 座標が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9c57b-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="9c57b-141">任意の VTC は、これらの調整を通じてこれらの会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="9c57b-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="9c57b-142">名前</span><span class="sxs-lookup"><span data-stu-id="9c57b-142">Name</span></span>|<span data-ttu-id="9c57b-143">アプリケーションアクセス許可の短い説明</span><span class="sxs-lookup"><span data-stu-id="9c57b-143">Application Permission Short Description</span></span>| <span data-ttu-id="9c57b-144">説明</span><span class="sxs-lookup"><span data-stu-id="9c57b-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="9c57b-145">JoinGroupCall を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="9c57b-146">グループ通話と会議をアプリとして参加する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9c57b-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="9c57b-147">サインインしているユーザーがいなくても、アプリがグループ通話や組織内のスケジュールされた会議に参加することを許可します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="9c57b-148">アプリは、テナントの会議にディレクトリユーザーの権限と共に参加します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="9c57b-149">JoinGroupCallasGuest を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="9c57b-150">ゲストユーザーとしてグループ通話と会議に参加する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9c57b-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="9c57b-151">サインインしているユーザーがいなくても、アプリがグループ通話と組織内のスケジュールされた会議に匿名で参加することを許可します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="9c57b-152">アプリは、テナントの会議にゲストとして参加します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="9c57b-153">アクセスメディア。すべて</span><span class="sxs-lookup"><span data-stu-id="9c57b-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="9c57b-154">アプリとしての通話でのメディアストリームへのアクセス (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9c57b-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="9c57b-155">サインインしているユーザーがいなくても、アプリが通話中のメディアストリームに直接アクセスすることを許可します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="9c57b-156">OnlineMeetings</span><span class="sxs-lookup"><span data-stu-id="9c57b-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="9c57b-157">オンライン会議の詳細を読む (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9c57b-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="9c57b-158">サインインしているユーザーがいなくても、組織内のオンライン会議の詳細をアプリで読むことができます。</span><span class="sxs-lookup"><span data-stu-id="9c57b-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="9c57b-159">基点</span><span class="sxs-lookup"><span data-stu-id="9c57b-159">Schedule</span></span>

<span data-ttu-id="9c57b-160">次に、ビデオ相互運用機能の調整を使って Teams 会議をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="9c57b-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="9c57b-161">有効なユーザーは、次の方法で teams 会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="9c57b-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="9c57b-162">Outlook 用 Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="9c57b-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="9c57b-163">Teams クライアントのデスクトップとモバイル</span><span class="sxs-lookup"><span data-stu-id="9c57b-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="9c57b-164">Join</span><span class="sxs-lookup"><span data-stu-id="9c57b-164">Join</span></span>

<span data-ttu-id="9c57b-165">次のような方法で、チーム会議に VTC デバイスと参加することができます。</span><span class="sxs-lookup"><span data-stu-id="9c57b-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="9c57b-166">IVR (インタラクティブな音声応答)</span><span class="sxs-lookup"><span data-stu-id="9c57b-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="9c57b-167">Tenantkey @ domain を使って、パートナーの IVR にダイヤルインすることができます。</span><span class="sxs-lookup"><span data-stu-id="9c57b-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="9c57b-168">パートナー IVR に参加すると、VTC conferenceId を入力するように求められます。これにより、Teams の会議に接続されます。</span><span class="sxs-lookup"><span data-stu-id="9c57b-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="9c57b-169">ダイレクトダイヤル</span><span class="sxs-lookup"><span data-stu-id="9c57b-169">Direct dial</span></span>
    - <span data-ttu-id="9c57b-170">このダイレクトダイヤル機能を使用すると、パートナーの IVR と直接やり取りすることなく、チーム会議に直接ダイヤルできます。VTC ConferenceId @ domain</span><span class="sxs-lookup"><span data-stu-id="9c57b-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="9c57b-171">ワンタッチダイヤル</span><span class="sxs-lookup"><span data-stu-id="9c57b-171">One-touch dial</span></span>
    - <span data-ttu-id="9c57b-172">統合されたチームルームがある場合は、パートナーが提供するワンタッチダイヤル機能を使用できます (ダイヤル文字列を入力する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="9c57b-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="9c57b-173">最後に、音声、ビデオ、およびコンテンツ共有を使用して、会議の Teams ユーザーと協力します。</span><span class="sxs-lookup"><span data-stu-id="9c57b-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 
