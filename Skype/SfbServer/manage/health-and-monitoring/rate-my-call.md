---
title: Skype for Business Server での通話の評価
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: '概要: Skype for Business Server の通話料金の評価機能について説明します。'
ms.openlocfilehash: e146bba647c9586d96682bf8056417630676726e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279859"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="4ce67-103">Skype for Business Server での通話の評価</span><span class="sxs-lookup"><span data-stu-id="4ce67-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="4ce67-104">**概要:** Skype for Business Server の通話料金の評価機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ce67-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="4ce67-105">Skype for Business 2015 および2016クライアントでは、自分の通話料金は、エンドユーザーからのフィードバックを得るための手段として提供されています。</span><span class="sxs-lookup"><span data-stu-id="4ce67-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="4ce67-106">通話の速度の評価ウィンドウには、音声通話とビデオ通話のための "スター" 評価システムと事前定義されたトークンが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4ce67-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="4ce67-107">さらに、管理者は、ユーザー設定フィールドを有効にしてフィードバックを提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="4ce67-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="4ce67-108">収集された比率現在、通話データは既存の監視レポートには含まれていませんが、別の監視レポートがあります。</span><span class="sxs-lookup"><span data-stu-id="4ce67-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="4ce67-109">Sql クエリを実行してアクセスできるデータは、SQL テーブルで収集されます。</span><span class="sxs-lookup"><span data-stu-id="4ce67-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="4ce67-110">通話の評価の前提条件</span><span class="sxs-lookup"><span data-stu-id="4ce67-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="4ce67-111">Skype for Business Server の展開のユーザーが通話機能にアクセスできるようにするには、次のコンポーネントのセットを展開して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ce67-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="4ce67-112">Skype for Business Server (バージョン9160以降) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ce67-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="4ce67-113">ユーザーが Skype for Business の最新バージョンをインストールして更新する必要があります。また、Skype for business の UI を使用するように依頼することもできます。</span><span class="sxs-lookup"><span data-stu-id="4ce67-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="4ce67-114">ユーザーは、Skype for Business Server のフロントエンドプールに所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ce67-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="4ce67-115">Skype for business server monitoring データベースを展開して、Skype for Business Server のプールに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ce67-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="4ce67-116">通話品質ダッシュボード (CQD) を展開することをお勧めします</span><span class="sxs-lookup"><span data-stu-id="4ce67-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="4ce67-117">通話の評価の構成</span><span class="sxs-lookup"><span data-stu-id="4ce67-117">Configure Rate my Call</span></span>

<span data-ttu-id="4ce67-118">電話料金の評価機能は、クライアントポリシーでは既定で有効になっていますが、次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="4ce67-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="4ce67-119">通話表示率を評価する-10%</span><span class="sxs-lookup"><span data-stu-id="4ce67-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="4ce67-120">通話料金カスタムユーザーフィードバックを許可する-無効</span><span class="sxs-lookup"><span data-stu-id="4ce67-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="4ce67-121">基本機能を有効にするために必要な操作はありませんが、カスタムのフィードバックが必要な場合は、個別に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ce67-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="4ce67-122">次の Windows PowerShell コマンドレットは、カスタムエンドユーザーフィードバックを有効にし、間隔を 10% から 80% に変更する例です。</span><span class="sxs-lookup"><span data-stu-id="4ce67-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="4ce67-123">通話の評価データへのアクセス</span><span class="sxs-lookup"><span data-stu-id="4ce67-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="4ce67-124">ユーザーからのデータは、監視データベースの2つのテーブルで収集されます。</span><span class="sxs-lookup"><span data-stu-id="4ce67-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="4ce67-125">**[QoeMetrics] を選びます。[dbo][CallQualityFeedbackToken]**-このテーブルには、エンドユーザによるトークンのポーリングの結果が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ce67-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="4ce67-126">**[QoeMetrics] を選びます。[dbo][CallQualityFeedbackTokenDef]**-このテーブルにはトークンの定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ce67-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="4ce67-127">トークンの定義は、次のように記述します。</span><span class="sxs-lookup"><span data-stu-id="4ce67-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4ce67-128">1</span><span class="sxs-lookup"><span data-stu-id="4ce67-128">1</span></span>  <br/> |<span data-ttu-id="4ce67-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="4ce67-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="4ce67-130">2</span><span class="sxs-lookup"><span data-stu-id="4ce67-130">2</span></span>  <br/> | <span data-ttu-id="4ce67-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="4ce67-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="4ce67-132">3</span><span class="sxs-lookup"><span data-stu-id="4ce67-132">3</span></span>  <br/> | <span data-ttu-id="4ce67-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="4ce67-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="4ce67-134">4</span><span class="sxs-lookup"><span data-stu-id="4ce67-134">4</span></span>  <br/> |<span data-ttu-id="4ce67-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="4ce67-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="4ce67-136">5</span><span class="sxs-lookup"><span data-stu-id="4ce67-136">5</span></span>  <br/> |<span data-ttu-id="4ce67-137">Echo</span><span class="sxs-lookup"><span data-stu-id="4ce67-137">Echo</span></span>  <br/> |
|<span data-ttu-id="4ce67-138">2004</span><span class="sxs-lookup"><span data-stu-id="4ce67-138">21</span></span>  <br/> | <span data-ttu-id="4ce67-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="4ce67-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="4ce67-140">22</span><span class="sxs-lookup"><span data-stu-id="4ce67-140">22</span></span>  <br/> | <span data-ttu-id="4ce67-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="4ce67-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="4ce67-142">最高</span><span class="sxs-lookup"><span data-stu-id="4ce67-142">23</span></span>  <br/> | <span data-ttu-id="4ce67-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="4ce67-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="4ce67-144">24</span><span class="sxs-lookup"><span data-stu-id="4ce67-144">24</span></span>  <br/> | <span data-ttu-id="4ce67-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="4ce67-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="4ce67-146">50</span><span class="sxs-lookup"><span data-stu-id="4ce67-146">25</span></span>  <br/> | <span data-ttu-id="4ce67-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="4ce67-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="4ce67-148">101</span><span class="sxs-lookup"><span data-stu-id="4ce67-148">101</span></span>  <br/> |<span data-ttu-id="4ce67-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="4ce67-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="4ce67-150">102</span><span class="sxs-lookup"><span data-stu-id="4ce67-150">102</span></span>  <br/> |<span data-ttu-id="4ce67-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="4ce67-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="4ce67-152">103</span><span class="sxs-lookup"><span data-stu-id="4ce67-152">103</span></span>  <br/> |<span data-ttu-id="4ce67-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="4ce67-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="4ce67-154">104</span><span class="sxs-lookup"><span data-stu-id="4ce67-154">104</span></span>  <br/> |<span data-ttu-id="4ce67-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="4ce67-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="4ce67-156">105</span><span class="sxs-lookup"><span data-stu-id="4ce67-156">105</span></span>  <br/> |<span data-ttu-id="4ce67-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="4ce67-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="4ce67-158">106</span><span class="sxs-lookup"><span data-stu-id="4ce67-158">106</span></span>  <br/> |<span data-ttu-id="4ce67-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="4ce67-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="4ce67-160">107</span><span class="sxs-lookup"><span data-stu-id="4ce67-160">107</span></span>  <br/> |<span data-ttu-id="4ce67-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="4ce67-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="4ce67-162">108</span><span class="sxs-lookup"><span data-stu-id="4ce67-162">108</span></span>  <br/> |<span data-ttu-id="4ce67-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="4ce67-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="4ce67-164">109</span><span class="sxs-lookup"><span data-stu-id="4ce67-164">109</span></span>  <br/> |<span data-ttu-id="4ce67-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="4ce67-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="4ce67-166">201</span><span class="sxs-lookup"><span data-stu-id="4ce67-166">201</span></span>  <br/> |<span data-ttu-id="4ce67-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="4ce67-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="4ce67-168">202</span><span class="sxs-lookup"><span data-stu-id="4ce67-168">202</span></span>  <br/> |<span data-ttu-id="4ce67-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="4ce67-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="4ce67-170">203</span><span class="sxs-lookup"><span data-stu-id="4ce67-170">203</span></span>  <br/> |<span data-ttu-id="4ce67-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="4ce67-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="4ce67-172">204</span><span class="sxs-lookup"><span data-stu-id="4ce67-172">204</span></span>  <br/> |<span data-ttu-id="4ce67-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="4ce67-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="4ce67-174">205</span><span class="sxs-lookup"><span data-stu-id="4ce67-174">205</span></span>  <br/> |<span data-ttu-id="4ce67-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="4ce67-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="4ce67-176">206</span><span class="sxs-lookup"><span data-stu-id="4ce67-176">206</span></span>  <br/> |<span data-ttu-id="4ce67-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="4ce67-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="4ce67-178">207</span><span class="sxs-lookup"><span data-stu-id="4ce67-178">207</span></span>  <br/> |<span data-ttu-id="4ce67-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="4ce67-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="4ce67-180">208</span><span class="sxs-lookup"><span data-stu-id="4ce67-180">208</span></span>  <br/> |<span data-ttu-id="4ce67-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="4ce67-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="4ce67-182">301</span><span class="sxs-lookup"><span data-stu-id="4ce67-182">301</span></span>  <br/> |<span data-ttu-id="4ce67-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="4ce67-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="4ce67-184">401</span><span class="sxs-lookup"><span data-stu-id="4ce67-184">401</span></span>  <br/> |<span data-ttu-id="4ce67-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="4ce67-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="4ce67-186">402</span><span class="sxs-lookup"><span data-stu-id="4ce67-186">402</span></span>  <br/> |<span data-ttu-id="4ce67-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="4ce67-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="4ce67-188">403</span><span class="sxs-lookup"><span data-stu-id="4ce67-188">403</span></span>  <br/> |<span data-ttu-id="4ce67-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="4ce67-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="4ce67-190">404</span><span class="sxs-lookup"><span data-stu-id="4ce67-190">404</span></span>  <br/> |<span data-ttu-id="4ce67-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="4ce67-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="4ce67-192">405</span><span class="sxs-lookup"><span data-stu-id="4ce67-192">405</span></span>  <br/> |<span data-ttu-id="4ce67-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="4ce67-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="4ce67-194">406</span><span class="sxs-lookup"><span data-stu-id="4ce67-194">406</span></span>  <br/> |<span data-ttu-id="4ce67-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="4ce67-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="4ce67-196">407</span><span class="sxs-lookup"><span data-stu-id="4ce67-196">407</span></span>  <br/> |<span data-ttu-id="4ce67-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="4ce67-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="4ce67-198">408</span><span class="sxs-lookup"><span data-stu-id="4ce67-198">408</span></span>  <br/> |<span data-ttu-id="4ce67-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="4ce67-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="4ce67-200">501</span><span class="sxs-lookup"><span data-stu-id="4ce67-200">501</span></span>  <br/> |<span data-ttu-id="4ce67-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="4ce67-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="4ce67-202">502</span><span class="sxs-lookup"><span data-stu-id="4ce67-202">502</span></span>  <br/> |<span data-ttu-id="4ce67-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="4ce67-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="4ce67-204">**[QoeMetrics] を選びます。[dbo][CallQualityFeedback]** この表には、有効になっている場合に "Star" の投票と顧客のフィードバックからのポーリング結果が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ce67-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="4ce67-205">テーブルのデータは、 **select \* from [Table.Name]** クエリまたは Microsoft SQL Server Management Studio を使って呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4ce67-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="4ce67-206">次の SQL クエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4ce67-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="4ce67-207">**音声**</span><span class="sxs-lookup"><span data-stu-id="4ce67-207">**Audio**</span></span>

```
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

 <span data-ttu-id="4ce67-208">**ビデオ**</span><span class="sxs-lookup"><span data-stu-id="4ce67-208">**Video**</span></span>

```
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

## <a name="updating-token-definitions"></a><span data-ttu-id="4ce67-209">トークン定義の更新</span><span class="sxs-lookup"><span data-stu-id="4ce67-209">Updating Token Definitions</span></span>

<span data-ttu-id="4ce67-210">最新の Skype for Business クライアントでは、[QoeMetrics]\>に表示されない可能性がある新しい問題のトークン id (100) が報告されています。[dbo][CallQualityFeedbackTokenDef] テーブル。</span><span class="sxs-lookup"><span data-stu-id="4ce67-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="4ce67-211">最新のトークン定義を使ってデータベーステーブルを更新するには、次の SQL コマンドを監視データベースで Microsoft SQL Server Management Studio を使用して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="4ce67-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="4ce67-212">このコマンドを実行すると、[QoeMetrics] のすべてのエントリが置き換えられます。[dbo][CallQualityFeedbackTokenDef] テーブル。</span><span class="sxs-lookup"><span data-stu-id="4ce67-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

```
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


