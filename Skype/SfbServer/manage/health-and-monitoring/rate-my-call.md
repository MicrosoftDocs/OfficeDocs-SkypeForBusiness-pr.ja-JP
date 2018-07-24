---
title: Business Server に Skype で電話を評価する.
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: '概要: は、ビジネス サーバー用のレート自分を呼び出す機能は、Skype について説明します。'
ms.openlocfilehash: 737d6a71f6880139d558d601a14d8f76c61d80f2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20989064"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="29be0-103">Business Server に Skype で電話を評価する.</span><span class="sxs-lookup"><span data-stu-id="29be0-103">Rate my Call in Skype for Business Server</span></span>
 
<span data-ttu-id="29be0-104">**の概要:** ビジネス サーバーのマイ レートを呼び出す機能は、Skype を紹介します。</span><span class="sxs-lookup"><span data-stu-id="29be0-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="29be0-105">レート [呼び出すビジネス 2015年 2016 上およびクライアント企業のエンド ・ ユーザーからのフィードバックを取得する方法を提供する Windows 用 Skype の新機能をしました。</span><span class="sxs-lookup"><span data-stu-id="29be0-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>
  
<span data-ttu-id="29be0-106">レート [呼び出し] ウィンドウでは、「星」の評価システムと音声通話とビデオ通話用の定義済みのトークンを提供します。</span><span class="sxs-lookup"><span data-stu-id="29be0-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="29be0-107">さらに、管理者には、フィードバックを提供するユーザー設定フィールドが有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="29be0-107">In addition, administrators can enable a custom field to provide feedback.</span></span>
  
<span data-ttu-id="29be0-108">レート [呼び出しの収集したデータが既存の監視のレポートに現在含まれていないが、監視、別のレポートがあります。</span><span class="sxs-lookup"><span data-stu-id="29be0-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="29be0-109">SQL クエリを実行することによってアクセスできる SQL テーブル内のデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="29be0-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>
  
## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="29be0-110">通話の評価の前提条件</span><span class="sxs-lookup"><span data-stu-id="29be0-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="29be0-111">ビジネス サーバーの展開について、Skype のユーザーは、レートの [呼び出しの機能にアクセスできる、前に次のコンポーネントのセットを展開し、構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29be0-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>
  
-  <span data-ttu-id="29be0-112">ビジネスのサーバーにインストールされている (9160 またはそれ以降のバージョン) には、Skype が必要です。</span><span class="sxs-lookup"><span data-stu-id="29be0-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>
    
- <span data-ttu-id="29be0-113">もらって、Skype を使用して、ビジネスの ui をインストールし、ビジネスの Skype の最新バージョンへの更新は、ユーザーがいます。</span><span class="sxs-lookup"><span data-stu-id="29be0-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>
    
- <span data-ttu-id="29be0-114">ビジネス サーバーのフロント エンド プールの Skype では、ユーザーが所属する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29be0-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>
    
- <span data-ttu-id="29be0-115">ビジネス サーバー監視のデータベースを展開し、Skype をビジネス サーバー プールに関連付けられているため、Skype が必要です。</span><span class="sxs-lookup"><span data-stu-id="29be0-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>
    
- <span data-ttu-id="29be0-116">通話品質ダッシュボード (CQD) を展開することをお勧めします</span><span class="sxs-lookup"><span data-stu-id="29be0-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>
    
## <a name="configure-rate-my-call"></a><span data-ttu-id="29be0-117">通話の評価の構成</span><span class="sxs-lookup"><span data-stu-id="29be0-117">Configure Rate my Call</span></span>

<span data-ttu-id="29be0-118">レート自分を呼び出す機能は既定では、次の設定でクライアントのポリシーを有効になっています。</span><span class="sxs-lookup"><span data-stu-id="29be0-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>
  
- <span data-ttu-id="29be0-119">[呼び出し表示の割合の 10% を評価します。</span><span class="sxs-lookup"><span data-stu-id="29be0-119">Rate My Call Display Percentage - 10%</span></span>
    
- <span data-ttu-id="29be0-120">呼び出しできるようにするカスタム ユーザー フィードバック - 無効になっている評価します。</span><span class="sxs-lookup"><span data-stu-id="29be0-120">Rate My Call Allow Custom User Feedback - disabled</span></span>
    
<span data-ttu-id="29be0-121">ただし、基本機能を有効にする必要がありませんが、カスタムのフィードバックをする場合は個別に有効にする必要があります。。</span><span class="sxs-lookup"><span data-stu-id="29be0-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="29be0-122">次の Windows PowerShell コマンドレットでは、カスタムのエンド ・ ユーザーからのフィードバックを有効にし、10% から 80% に変更する例を示します。</span><span class="sxs-lookup"><span data-stu-id="29be0-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>
  
```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="29be0-123">通話の評価データへのアクセス</span><span class="sxs-lookup"><span data-stu-id="29be0-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="29be0-124">監視データベース内の 2 つのテーブルでは、ユーザーからのデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="29be0-124">Data from users is collected in two tables in the monitoring database.</span></span>
  
 <span data-ttu-id="29be0-125">**[QoeMetrics] です。[dbo].[CallQualityFeedbackToken]**-次の表には、エンド ・ ユーザーによるトークンのポーリングの結果が含まれています。</span><span class="sxs-lookup"><span data-stu-id="29be0-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>
  
 <span data-ttu-id="29be0-126">**[QoeMetrics] です。[dbo].[CallQualityFeedbackTokenDef]**-次の表には、トークンの定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="29be0-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>
  
<span data-ttu-id="29be0-127">トークンの定義は、次のように記述します。</span><span class="sxs-lookup"><span data-stu-id="29be0-127">Token definitions are coded as follows:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="29be0-128">1</span><span class="sxs-lookup"><span data-stu-id="29be0-128">1</span></span>  <br/> |<span data-ttu-id="29be0-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="29be0-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="29be0-130">2</span><span class="sxs-lookup"><span data-stu-id="29be0-130">2</span></span>  <br/> | <span data-ttu-id="29be0-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="29be0-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="29be0-132">3</span><span class="sxs-lookup"><span data-stu-id="29be0-132">3</span></span>  <br/> | <span data-ttu-id="29be0-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="29be0-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="29be0-134">4</span><span class="sxs-lookup"><span data-stu-id="29be0-134">4</span></span>  <br/> |<span data-ttu-id="29be0-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="29be0-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="29be0-136">5</span><span class="sxs-lookup"><span data-stu-id="29be0-136">5</span></span>  <br/> |<span data-ttu-id="29be0-137">エコー</span><span class="sxs-lookup"><span data-stu-id="29be0-137">Echo</span></span>  <br/> |
|<span data-ttu-id="29be0-138">21</span><span class="sxs-lookup"><span data-stu-id="29be0-138">21</span></span>  <br/> | <span data-ttu-id="29be0-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="29be0-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="29be0-140">22</span><span class="sxs-lookup"><span data-stu-id="29be0-140">22</span></span>  <br/> | <span data-ttu-id="29be0-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="29be0-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="29be0-142">23</span><span class="sxs-lookup"><span data-stu-id="29be0-142">23</span></span>  <br/> | <span data-ttu-id="29be0-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="29be0-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="29be0-144">24</span><span class="sxs-lookup"><span data-stu-id="29be0-144">24</span></span>  <br/> | <span data-ttu-id="29be0-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="29be0-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="29be0-146">25</span><span class="sxs-lookup"><span data-stu-id="29be0-146">25</span></span>  <br/> | <span data-ttu-id="29be0-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="29be0-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="29be0-148">101</span><span class="sxs-lookup"><span data-stu-id="29be0-148">101</span></span>  <br/> |<span data-ttu-id="29be0-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="29be0-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="29be0-150">102</span><span class="sxs-lookup"><span data-stu-id="29be0-150">102</span></span>  <br/> |<span data-ttu-id="29be0-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="29be0-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="29be0-152">103</span><span class="sxs-lookup"><span data-stu-id="29be0-152">103</span></span>  <br/> |<span data-ttu-id="29be0-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="29be0-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="29be0-154">104</span><span class="sxs-lookup"><span data-stu-id="29be0-154">104</span></span>  <br/> |<span data-ttu-id="29be0-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="29be0-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="29be0-156">105</span><span class="sxs-lookup"><span data-stu-id="29be0-156">105</span></span>  <br/> |<span data-ttu-id="29be0-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="29be0-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="29be0-158">106</span><span class="sxs-lookup"><span data-stu-id="29be0-158">106</span></span>  <br/> |<span data-ttu-id="29be0-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="29be0-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="29be0-160">107</span><span class="sxs-lookup"><span data-stu-id="29be0-160">107</span></span>  <br/> |<span data-ttu-id="29be0-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="29be0-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="29be0-162">108</span><span class="sxs-lookup"><span data-stu-id="29be0-162">108</span></span>  <br/> |<span data-ttu-id="29be0-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="29be0-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="29be0-164">109</span><span class="sxs-lookup"><span data-stu-id="29be0-164">109</span></span>  <br/> |<span data-ttu-id="29be0-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="29be0-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="29be0-166">201</span><span class="sxs-lookup"><span data-stu-id="29be0-166">201</span></span>  <br/> |<span data-ttu-id="29be0-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="29be0-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="29be0-168">202</span><span class="sxs-lookup"><span data-stu-id="29be0-168">202</span></span>  <br/> |<span data-ttu-id="29be0-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="29be0-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="29be0-170">203</span><span class="sxs-lookup"><span data-stu-id="29be0-170">203</span></span>  <br/> |<span data-ttu-id="29be0-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="29be0-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="29be0-172">204</span><span class="sxs-lookup"><span data-stu-id="29be0-172">204</span></span>  <br/> |<span data-ttu-id="29be0-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="29be0-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="29be0-174">205</span><span class="sxs-lookup"><span data-stu-id="29be0-174">205</span></span>  <br/> |<span data-ttu-id="29be0-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="29be0-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="29be0-176">206</span><span class="sxs-lookup"><span data-stu-id="29be0-176">206</span></span>  <br/> |<span data-ttu-id="29be0-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="29be0-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="29be0-178">207</span><span class="sxs-lookup"><span data-stu-id="29be0-178">207</span></span>  <br/> |<span data-ttu-id="29be0-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="29be0-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="29be0-180">208</span><span class="sxs-lookup"><span data-stu-id="29be0-180">208</span></span>  <br/> |<span data-ttu-id="29be0-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="29be0-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="29be0-182">301</span><span class="sxs-lookup"><span data-stu-id="29be0-182">301</span></span>  <br/> |<span data-ttu-id="29be0-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="29be0-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="29be0-184">401</span><span class="sxs-lookup"><span data-stu-id="29be0-184">401</span></span>  <br/> |<span data-ttu-id="29be0-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="29be0-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="29be0-186">402</span><span class="sxs-lookup"><span data-stu-id="29be0-186">402</span></span>  <br/> |<span data-ttu-id="29be0-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="29be0-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="29be0-188">403</span><span class="sxs-lookup"><span data-stu-id="29be0-188">403</span></span>  <br/> |<span data-ttu-id="29be0-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="29be0-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="29be0-190">404</span><span class="sxs-lookup"><span data-stu-id="29be0-190">404</span></span>  <br/> |<span data-ttu-id="29be0-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="29be0-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="29be0-192">405</span><span class="sxs-lookup"><span data-stu-id="29be0-192">405</span></span>  <br/> |<span data-ttu-id="29be0-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="29be0-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="29be0-194">406</span><span class="sxs-lookup"><span data-stu-id="29be0-194">406</span></span>  <br/> |<span data-ttu-id="29be0-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="29be0-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="29be0-196">407</span><span class="sxs-lookup"><span data-stu-id="29be0-196">407</span></span>  <br/> |<span data-ttu-id="29be0-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="29be0-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="29be0-198">408</span><span class="sxs-lookup"><span data-stu-id="29be0-198">408</span></span>  <br/> |<span data-ttu-id="29be0-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="29be0-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="29be0-200">501</span><span class="sxs-lookup"><span data-stu-id="29be0-200">501</span></span>  <br/> |<span data-ttu-id="29be0-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="29be0-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="29be0-202">502</span><span class="sxs-lookup"><span data-stu-id="29be0-202">502</span></span>  <br/> |<span data-ttu-id="29be0-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="29be0-203">Reliabilty_Invite</span></span>  <br/> |
   
 <span data-ttu-id="29be0-204">**[QoeMetrics] です。[dbo].[CallQualityFeedback]** このテーブルには、有効になっている場合の「星」の投票および顧客のフィードバックからのポーリングの結果が含まれています。</span><span class="sxs-lookup"><span data-stu-id="29be0-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>
  
<span data-ttu-id="29be0-205">テーブルからデータを使用して呼び出すことができます、**を選択\*[Table.Name] から**クエリまたは Microsoft SQL Server Management Studio のを使用しています。</span><span class="sxs-lookup"><span data-stu-id="29be0-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>
  
<span data-ttu-id="29be0-206">次の SQL クエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="29be0-206">The following SQL queries can be used:</span></span>
  
 <span data-ttu-id="29be0-207">**音声**</span><span class="sxs-lookup"><span data-stu-id="29be0-207">**Audio**</span></span>
  
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

 <span data-ttu-id="29be0-208">**ビデオ**</span><span class="sxs-lookup"><span data-stu-id="29be0-208">**Video**</span></span>
  
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

## <a name="updating-token-definitions"></a><span data-ttu-id="29be0-209">トークンの定義を更新します。</span><span class="sxs-lookup"><span data-stu-id="29be0-209">Updating Token Definitions</span></span>

<span data-ttu-id="29be0-210">ビジネス クライアント用の最新の Skype は、新しい問題トークン Id を報告 (\> 100)、[QoeMetrics] 内に存在できません。[dbo].[CallQualityFeedbackTokenDef] テーブルです。</span><span class="sxs-lookup"><span data-stu-id="29be0-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="29be0-211">最新のトークン定義とデータベース テーブルを更新するのには、Microsoft SQL Server Management Studio のを使用して監視データベースに SQL の下コマンドを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="29be0-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="29be0-212">このコマンドは、[QoeMetrics] 内のすべてのエントリに置き換えられます。[dbo].[CallQualityFeedbackTokenDef] テーブルです。</span><span class="sxs-lookup"><span data-stu-id="29be0-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>
  
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


