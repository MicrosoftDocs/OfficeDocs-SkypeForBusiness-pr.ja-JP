---
title: Skype for Business Server での通話の評価
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: '概要: Skype for Business Server の通話の評価機能について説明します。'
ms.openlocfilehash: 15f2bcbcf75690baaa350541f5f1da134fb32025
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902221"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="f3cf1-103">Skype for Business Server での通話の評価</span><span class="sxs-lookup"><span data-stu-id="f3cf1-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="f3cf1-104">**概要:** Skype for Business Server の通話の評価機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="f3cf1-105">[通話の評価] Windows 上の Skype for Business 2015 および2016クライアントでは、エンドユーザーからフィードバックを取得する方法を提供する新機能でした。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="f3cf1-106">[通話の評価] ウィンドウには、音声およびビデオ通話用の "星" レベルの評価システムと定義済みのトークンが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="f3cf1-107">さらに、管理者はユーザー設定フィールドにフィードバックを提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="f3cf1-108">収集されたレート現在の通話データは既存の監視レポートには含まれていませんが、別の監視レポートがあります。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="f3cf1-109">Sql クエリを実行することによってアクセスできる、SQL テーブル内のデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="f3cf1-110">通話の前提条件の評価</span><span class="sxs-lookup"><span data-stu-id="f3cf1-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="f3cf1-111">Skype for Business Server の展開のユーザーが通話速度にアクセスできるようにするには、次のコンポーネントのセットを展開して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="f3cf1-112">Skype for Business Server がインストールされている必要があります (バージョン9160以降)。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="f3cf1-113">ユーザーが Skype for business の最新バージョンをインストールして更新するようにして、Skype for Business UI を使用するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="f3cf1-114">ユーザーは、Skype for Business Server のフロントエンドプールに所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="f3cf1-115">Skype for business Server の監視データベースを展開して、Skype for Business Server プールに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="f3cf1-116">通話品質ダッシュボード (CQD) を展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="f3cf1-117">通話のレートを構成する</span><span class="sxs-lookup"><span data-stu-id="f3cf1-117">Configure Rate my Call</span></span>

<span data-ttu-id="f3cf1-118">通話の評価機能は、次の設定でクライアントポリシーで既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="f3cf1-119">通話表示の評価率-10%</span><span class="sxs-lookup"><span data-stu-id="f3cf1-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="f3cf1-120">通話の評価 [カスタムユーザーフィードバックを許可する]-無効</span><span class="sxs-lookup"><span data-stu-id="f3cf1-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="f3cf1-121">基本機能を有効にするために必要な操作はありませんが、カスタムフィードバックを有効にする必要がある場合は、それを個別に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="f3cf1-122">次の Windows PowerShell コマンドレットは、カスタムエンドユーザーフィードバックを有効にし、10% から80% に間隔を変更する例です。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="f3cf1-123">通話の通話データへのアクセス</span><span class="sxs-lookup"><span data-stu-id="f3cf1-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="f3cf1-124">ユーザーからのデータは、監視データベースの2つのテーブルで収集されます。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="f3cf1-125">**[QoeMetrics]。[dbo]。[CallQualityFeedbackToken]**-この表には、エンドユーザーによるトークンポーリングの結果が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="f3cf1-126">**[QoeMetrics]。[dbo]。[CallQualityFeedbackTokenDef]**-この表にはトークンの定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="f3cf1-127">トークンの定義は次のようにコード化されます。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f3cf1-128">1 </span><span class="sxs-lookup"><span data-stu-id="f3cf1-128">1</span></span>  <br/> |<span data-ttu-id="f3cf1-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="f3cf1-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="f3cf1-130">2 </span><span class="sxs-lookup"><span data-stu-id="f3cf1-130">2</span></span>  <br/> | <span data-ttu-id="f3cf1-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="f3cf1-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="f3cf1-132">3 </span><span class="sxs-lookup"><span data-stu-id="f3cf1-132">3</span></span>  <br/> | <span data-ttu-id="f3cf1-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="f3cf1-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="f3cf1-134">4 </span><span class="sxs-lookup"><span data-stu-id="f3cf1-134">4</span></span>  <br/> |<span data-ttu-id="f3cf1-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="f3cf1-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="f3cf1-136">5 </span><span class="sxs-lookup"><span data-stu-id="f3cf1-136">5</span></span>  <br/> |<span data-ttu-id="f3cf1-137">Echo</span><span class="sxs-lookup"><span data-stu-id="f3cf1-137">Echo</span></span>  <br/> |
|<span data-ttu-id="f3cf1-138"> 21</span><span class="sxs-lookup"><span data-stu-id="f3cf1-138">21</span></span>  <br/> | <span data-ttu-id="f3cf1-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="f3cf1-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="f3cf1-140">×</span><span class="sxs-lookup"><span data-stu-id="f3cf1-140">22</span></span>  <br/> | <span data-ttu-id="f3cf1-141">ピクセルの画像</span><span class="sxs-lookup"><span data-stu-id="f3cf1-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="f3cf1-142">最高</span><span class="sxs-lookup"><span data-stu-id="f3cf1-142">23</span></span>  <br/> | <span data-ttu-id="f3cf1-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="f3cf1-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="f3cf1-144">ソケット</span><span class="sxs-lookup"><span data-stu-id="f3cf1-144">24</span></span>  <br/> | <span data-ttu-id="f3cf1-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="f3cf1-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="f3cf1-146">まで</span><span class="sxs-lookup"><span data-stu-id="f3cf1-146">25</span></span>  <br/> | <span data-ttu-id="f3cf1-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="f3cf1-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="f3cf1-148">101</span><span class="sxs-lookup"><span data-stu-id="f3cf1-148">101</span></span>  <br/> |<span data-ttu-id="f3cf1-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="f3cf1-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="f3cf1-150">102</span><span class="sxs-lookup"><span data-stu-id="f3cf1-150">102</span></span>  <br/> |<span data-ttu-id="f3cf1-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="f3cf1-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="f3cf1-152">103</span><span class="sxs-lookup"><span data-stu-id="f3cf1-152">103</span></span>  <br/> |<span data-ttu-id="f3cf1-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="f3cf1-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="f3cf1-154">104</span><span class="sxs-lookup"><span data-stu-id="f3cf1-154">104</span></span>  <br/> |<span data-ttu-id="f3cf1-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="f3cf1-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="f3cf1-156">105</span><span class="sxs-lookup"><span data-stu-id="f3cf1-156">105</span></span>  <br/> |<span data-ttu-id="f3cf1-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="f3cf1-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="f3cf1-158">106</span><span class="sxs-lookup"><span data-stu-id="f3cf1-158">106</span></span>  <br/> |<span data-ttu-id="f3cf1-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="f3cf1-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="f3cf1-160">107</span><span class="sxs-lookup"><span data-stu-id="f3cf1-160">107</span></span>  <br/> |<span data-ttu-id="f3cf1-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="f3cf1-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="f3cf1-162">108</span><span class="sxs-lookup"><span data-stu-id="f3cf1-162">108</span></span>  <br/> |<span data-ttu-id="f3cf1-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="f3cf1-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="f3cf1-164">109</span><span class="sxs-lookup"><span data-stu-id="f3cf1-164">109</span></span>  <br/> |<span data-ttu-id="f3cf1-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="f3cf1-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="f3cf1-166">201</span><span class="sxs-lookup"><span data-stu-id="f3cf1-166">201</span></span>  <br/> |<span data-ttu-id="f3cf1-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="f3cf1-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="f3cf1-168">202</span><span class="sxs-lookup"><span data-stu-id="f3cf1-168">202</span></span>  <br/> |<span data-ttu-id="f3cf1-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="f3cf1-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="f3cf1-170">203</span><span class="sxs-lookup"><span data-stu-id="f3cf1-170">203</span></span>  <br/> |<span data-ttu-id="f3cf1-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="f3cf1-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="f3cf1-172">204</span><span class="sxs-lookup"><span data-stu-id="f3cf1-172">204</span></span>  <br/> |<span data-ttu-id="f3cf1-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="f3cf1-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="f3cf1-174">205</span><span class="sxs-lookup"><span data-stu-id="f3cf1-174">205</span></span>  <br/> |<span data-ttu-id="f3cf1-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="f3cf1-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="f3cf1-176">206</span><span class="sxs-lookup"><span data-stu-id="f3cf1-176">206</span></span>  <br/> |<span data-ttu-id="f3cf1-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="f3cf1-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="f3cf1-178">207</span><span class="sxs-lookup"><span data-stu-id="f3cf1-178">207</span></span>  <br/> |<span data-ttu-id="f3cf1-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="f3cf1-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="f3cf1-180">208</span><span class="sxs-lookup"><span data-stu-id="f3cf1-180">208</span></span>  <br/> |<span data-ttu-id="f3cf1-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="f3cf1-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="f3cf1-182">301</span><span class="sxs-lookup"><span data-stu-id="f3cf1-182">301</span></span>  <br/> |<span data-ttu-id="f3cf1-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="f3cf1-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="f3cf1-184">401</span><span class="sxs-lookup"><span data-stu-id="f3cf1-184">401</span></span>  <br/> |<span data-ttu-id="f3cf1-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="f3cf1-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="f3cf1-186">402</span><span class="sxs-lookup"><span data-stu-id="f3cf1-186">402</span></span>  <br/> |<span data-ttu-id="f3cf1-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="f3cf1-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="f3cf1-188">403</span><span class="sxs-lookup"><span data-stu-id="f3cf1-188">403</span></span>  <br/> |<span data-ttu-id="f3cf1-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="f3cf1-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="f3cf1-190">404</span><span class="sxs-lookup"><span data-stu-id="f3cf1-190">404</span></span>  <br/> |<span data-ttu-id="f3cf1-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="f3cf1-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="f3cf1-192">405</span><span class="sxs-lookup"><span data-stu-id="f3cf1-192">405</span></span>  <br/> |<span data-ttu-id="f3cf1-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="f3cf1-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="f3cf1-194">406</span><span class="sxs-lookup"><span data-stu-id="f3cf1-194">406</span></span>  <br/> |<span data-ttu-id="f3cf1-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="f3cf1-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="f3cf1-196">407</span><span class="sxs-lookup"><span data-stu-id="f3cf1-196">407</span></span>  <br/> |<span data-ttu-id="f3cf1-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="f3cf1-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="f3cf1-198">408</span><span class="sxs-lookup"><span data-stu-id="f3cf1-198">408</span></span>  <br/> |<span data-ttu-id="f3cf1-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="f3cf1-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="f3cf1-200">501</span><span class="sxs-lookup"><span data-stu-id="f3cf1-200">501</span></span>  <br/> |<span data-ttu-id="f3cf1-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="f3cf1-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="f3cf1-202">502</span><span class="sxs-lookup"><span data-stu-id="f3cf1-202">502</span></span>  <br/> |<span data-ttu-id="f3cf1-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="f3cf1-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="f3cf1-204">**[QoeMetrics]。[dbo]。[CallQualityFeedback]** この表には、有効になっている場合の "Star" 投票およびお客様からのフィードバックのポーリング結果が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="f3cf1-205">テーブルからのデータは、 **select \* from [Table.Name]** クエリまたは Microsoft SQL Server Management Studio を使用して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="f3cf1-206">次の SQL クエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="f3cf1-207">**Audio**</span><span class="sxs-lookup"><span data-stu-id="f3cf1-207">**Audio**</span></span>

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

 <span data-ttu-id="f3cf1-208">**Video**</span><span class="sxs-lookup"><span data-stu-id="f3cf1-208">**Video**</span></span>

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a><span data-ttu-id="f3cf1-209">トークン定義の更新</span><span class="sxs-lookup"><span data-stu-id="f3cf1-209">Updating Token Definitions</span></span>

<span data-ttu-id="f3cf1-210">最新の Skype for Business クライアントは、 \> [QoeMetrics] に存在しない可能性がある新しい問題のトークン id (100) を報告します。 [dbo]。[CallQualityFeedbackTokenDef] テーブル。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="f3cf1-211">最新のトークン定義を使用してデータベーステーブルを更新するには、Microsoft SQL Server Management Studio を使用して、以下の SQL コマンドを監視データベースで実行できます。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="f3cf1-212">このコマンドを実行すると、[QoeMetrics] のすべてのエントリが置き換えられます。[dbo]。[CallQualityFeedbackTokenDef] テーブル。</span><span class="sxs-lookup"><span data-stu-id="f3cf1-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

```SQL
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');
```


