---
title: Skype for Business Server での通話の評価
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: '概要: Skype for Business Server の通話の評価機能について学習します。'
ms.openlocfilehash: 597a8213576e7aa2316ace68ed91288475df2a0d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814337"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="b586d-103">Skype for Business Server での通話の評価</span><span class="sxs-lookup"><span data-stu-id="b586d-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="b586d-104">**概要:** Skype for Business Server の通話の評価機能について学習します。</span><span class="sxs-lookup"><span data-stu-id="b586d-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="b586d-105">通話の評価は、エンタープライズがエンド ユーザーからフィードバックを得る方法を提供する、Windows 上の Skype for Business 2015 および 2016 クライアントの新機能でした。</span><span class="sxs-lookup"><span data-stu-id="b586d-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="b586d-106">[通話の評価] ウィンドウには、"スター" 評価システムと、音声通話とビデオ通話用の定義済みトークンが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b586d-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="b586d-107">また、管理者はユーザー設定フィールドを有効にしてフィードバックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="b586d-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="b586d-108">収集された通話の評価データは、現在、既存の監視レポートには含まれていませんが、個別の監視レポートがあります。</span><span class="sxs-lookup"><span data-stu-id="b586d-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="b586d-109">データは、クエリSQL実行してアクセスできるテーブルにSQLされます。</span><span class="sxs-lookup"><span data-stu-id="b586d-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="b586d-110">通話の評価の前提条件</span><span class="sxs-lookup"><span data-stu-id="b586d-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="b586d-111">Skype for Business Server 展開のユーザーが通話の評価機能にアクセスするには、次のコンポーネントセットを展開して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b586d-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="b586d-112">Skype for Business Server (バージョン 9160 以上) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b586d-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="b586d-113">ユーザーに Skype for Business の最新バージョンをインストールして更新し、Skype for Business UI の使用を求める。</span><span class="sxs-lookup"><span data-stu-id="b586d-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="b586d-114">ユーザーは、Skype for Business Server フロントエンド プールにホームとして設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b586d-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="b586d-115">Skype for Business Server 監視データベースが展開され、Skype for Business Server プールに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b586d-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="b586d-116">通話品質ダッシュボード (CQD) を展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b586d-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="b586d-117">通話の評価を構成する</span><span class="sxs-lookup"><span data-stu-id="b586d-117">Configure Rate my Call</span></span>

<span data-ttu-id="b586d-118">[通話の評価] 機能は、クライアント ポリシーで既定で次の設定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="b586d-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="b586d-119">通話の表示率 - 10%</span><span class="sxs-lookup"><span data-stu-id="b586d-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="b586d-120">通話の評価カスタム ユーザー フィードバックを許可 - 無効</span><span class="sxs-lookup"><span data-stu-id="b586d-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="b586d-121">基本機能を有効にする操作は必要ありませんが、カスタム フィードバックが必要な場合は、個別に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b586d-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="b586d-122">次のWindows PowerShellは、エンド ユーザーのカスタム フィードバックを有効にし、間隔を 10% から 80% に変更する例です。</span><span class="sxs-lookup"><span data-stu-id="b586d-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="b586d-123">通話データの評価へのアクセス</span><span class="sxs-lookup"><span data-stu-id="b586d-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="b586d-124">ユーザーからのデータは、監視データベースの 2 つのテーブルに収集されます。</span><span class="sxs-lookup"><span data-stu-id="b586d-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="b586d-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - この表には、エンド ユーザーによるトークン ポーリングの結果が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b586d-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="b586d-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - このテーブルにはトークン定義が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b586d-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="b586d-127">トークン定義は次のようにコード化されています。</span><span class="sxs-lookup"><span data-stu-id="b586d-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b586d-128">1 </span><span class="sxs-lookup"><span data-stu-id="b586d-128">1</span></span>  <br/> |<span data-ttu-id="b586d-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="b586d-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="b586d-130">2 </span><span class="sxs-lookup"><span data-stu-id="b586d-130">2</span></span>  <br/> | <span data-ttu-id="b586d-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="b586d-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="b586d-132">3 </span><span class="sxs-lookup"><span data-stu-id="b586d-132">3</span></span>  <br/> | <span data-ttu-id="b586d-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="b586d-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="b586d-134">4 </span><span class="sxs-lookup"><span data-stu-id="b586d-134">4</span></span>  <br/> |<span data-ttu-id="b586d-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="b586d-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="b586d-136">5 </span><span class="sxs-lookup"><span data-stu-id="b586d-136">5</span></span>  <br/> |<span data-ttu-id="b586d-137">Echo</span><span class="sxs-lookup"><span data-stu-id="b586d-137">Echo</span></span>  <br/> |
|<span data-ttu-id="b586d-138"> 21</span><span class="sxs-lookup"><span data-stu-id="b586d-138">21</span></span>  <br/> | <span data-ttu-id="b586d-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="b586d-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="b586d-140">22</span><span class="sxs-lookup"><span data-stu-id="b586d-140">22</span></span>  <br/> | <span data-ttu-id="b586d-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="b586d-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="b586d-142">23</span><span class="sxs-lookup"><span data-stu-id="b586d-142">23</span></span>  <br/> | <span data-ttu-id="b586d-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="b586d-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="b586d-144">24</span><span class="sxs-lookup"><span data-stu-id="b586d-144">24</span></span>  <br/> | <span data-ttu-id="b586d-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="b586d-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="b586d-146">25</span><span class="sxs-lookup"><span data-stu-id="b586d-146">25</span></span>  <br/> | <span data-ttu-id="b586d-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="b586d-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="b586d-148">101</span><span class="sxs-lookup"><span data-stu-id="b586d-148">101</span></span>  <br/> |<span data-ttu-id="b586d-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="b586d-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="b586d-150">102</span><span class="sxs-lookup"><span data-stu-id="b586d-150">102</span></span>  <br/> |<span data-ttu-id="b586d-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="b586d-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="b586d-152">103</span><span class="sxs-lookup"><span data-stu-id="b586d-152">103</span></span>  <br/> |<span data-ttu-id="b586d-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="b586d-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="b586d-154">104</span><span class="sxs-lookup"><span data-stu-id="b586d-154">104</span></span>  <br/> |<span data-ttu-id="b586d-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="b586d-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="b586d-156">105</span><span class="sxs-lookup"><span data-stu-id="b586d-156">105</span></span>  <br/> |<span data-ttu-id="b586d-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="b586d-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="b586d-158">106</span><span class="sxs-lookup"><span data-stu-id="b586d-158">106</span></span>  <br/> |<span data-ttu-id="b586d-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="b586d-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="b586d-160">107</span><span class="sxs-lookup"><span data-stu-id="b586d-160">107</span></span>  <br/> |<span data-ttu-id="b586d-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="b586d-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="b586d-162">108</span><span class="sxs-lookup"><span data-stu-id="b586d-162">108</span></span>  <br/> |<span data-ttu-id="b586d-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="b586d-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="b586d-164">109</span><span class="sxs-lookup"><span data-stu-id="b586d-164">109</span></span>  <br/> |<span data-ttu-id="b586d-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="b586d-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="b586d-166">201</span><span class="sxs-lookup"><span data-stu-id="b586d-166">201</span></span>  <br/> |<span data-ttu-id="b586d-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="b586d-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="b586d-168">202</span><span class="sxs-lookup"><span data-stu-id="b586d-168">202</span></span>  <br/> |<span data-ttu-id="b586d-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="b586d-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="b586d-170">203</span><span class="sxs-lookup"><span data-stu-id="b586d-170">203</span></span>  <br/> |<span data-ttu-id="b586d-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="b586d-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="b586d-172">204</span><span class="sxs-lookup"><span data-stu-id="b586d-172">204</span></span>  <br/> |<span data-ttu-id="b586d-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="b586d-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="b586d-174">205</span><span class="sxs-lookup"><span data-stu-id="b586d-174">205</span></span>  <br/> |<span data-ttu-id="b586d-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="b586d-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="b586d-176">206</span><span class="sxs-lookup"><span data-stu-id="b586d-176">206</span></span>  <br/> |<span data-ttu-id="b586d-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="b586d-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="b586d-178">207</span><span class="sxs-lookup"><span data-stu-id="b586d-178">207</span></span>  <br/> |<span data-ttu-id="b586d-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="b586d-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="b586d-180">208</span><span class="sxs-lookup"><span data-stu-id="b586d-180">208</span></span>  <br/> |<span data-ttu-id="b586d-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="b586d-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="b586d-182">301</span><span class="sxs-lookup"><span data-stu-id="b586d-182">301</span></span>  <br/> |<span data-ttu-id="b586d-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="b586d-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="b586d-184">401</span><span class="sxs-lookup"><span data-stu-id="b586d-184">401</span></span>  <br/> |<span data-ttu-id="b586d-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="b586d-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="b586d-186">402</span><span class="sxs-lookup"><span data-stu-id="b586d-186">402</span></span>  <br/> |<span data-ttu-id="b586d-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="b586d-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="b586d-188">403</span><span class="sxs-lookup"><span data-stu-id="b586d-188">403</span></span>  <br/> |<span data-ttu-id="b586d-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="b586d-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="b586d-190">404</span><span class="sxs-lookup"><span data-stu-id="b586d-190">404</span></span>  <br/> |<span data-ttu-id="b586d-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="b586d-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="b586d-192">405</span><span class="sxs-lookup"><span data-stu-id="b586d-192">405</span></span>  <br/> |<span data-ttu-id="b586d-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="b586d-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="b586d-194">406</span><span class="sxs-lookup"><span data-stu-id="b586d-194">406</span></span>  <br/> |<span data-ttu-id="b586d-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="b586d-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="b586d-196">407</span><span class="sxs-lookup"><span data-stu-id="b586d-196">407</span></span>  <br/> |<span data-ttu-id="b586d-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="b586d-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="b586d-198">408</span><span class="sxs-lookup"><span data-stu-id="b586d-198">408</span></span>  <br/> |<span data-ttu-id="b586d-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="b586d-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="b586d-200">501</span><span class="sxs-lookup"><span data-stu-id="b586d-200">501</span></span>  <br/> |<span data-ttu-id="b586d-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="b586d-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="b586d-202">502</span><span class="sxs-lookup"><span data-stu-id="b586d-202">502</span></span>  <br/> |<span data-ttu-id="b586d-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="b586d-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="b586d-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** この表には、"Star" 投票からのポーリング結果と、有効な場合の顧客フィードバックが含されます。</span><span class="sxs-lookup"><span data-stu-id="b586d-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="b586d-205">テーブルからのデータは **\* 、[Table.Name]** クエリから選択するか、または Microsoft SQL Server Management Studio を使用して呼び出Microsoft SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="b586d-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="b586d-206">次のSQLクエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b586d-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="b586d-207">**Audio**</span><span class="sxs-lookup"><span data-stu-id="b586d-207">**Audio**</span></span>

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

 <span data-ttu-id="b586d-208">**Video**</span><span class="sxs-lookup"><span data-stu-id="b586d-208">**Video**</span></span>

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

## <a name="updating-token-definitions"></a><span data-ttu-id="b586d-209">トークン定義の更新</span><span class="sxs-lookup"><span data-stu-id="b586d-209">Updating Token Definitions</span></span>

<span data-ttu-id="b586d-210">最新の Skype for Business クライアントは、[QoeMetrics] に存在しない可能性がある新しい問題トークン ID ( \> 100) を報告します。dbo].[CallQualityFeedbackTokenDef] テーブル。</span><span class="sxs-lookup"><span data-stu-id="b586d-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="b586d-211">データベース テーブルを最新のトークン定義で更新するには、次の SQL コマンドを使用して監視データベースで実行Microsoft SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="b586d-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="b586d-212">このコマンドは、[QoeMetrics] 内のすべてのエントリを置き換えるコマンドです。[dbo].[CallQualityFeedbackTokenDef] テーブル。</span><span class="sxs-lookup"><span data-stu-id="b586d-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

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


