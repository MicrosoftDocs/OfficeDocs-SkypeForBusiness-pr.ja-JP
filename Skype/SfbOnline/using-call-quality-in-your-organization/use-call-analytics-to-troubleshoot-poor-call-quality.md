---
title: "不適切な Skype for Business のトラブルシューティングに使用する通話分析通話品質"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: "Skype for Business 通話と会議のユーザーの問題のトラブルシューティングを行うには、デバイス、ネットワーク、および接続について詳しくは通話の分析を使用します。"
ms.openlocfilehash: 4f43c517beba318889e12fca8b09a488f6da5916
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a><span data-ttu-id="71904-103">不適切な Skype for Business のトラブルシューティングに使用する通話分析通話品質</span><span class="sxs-lookup"><span data-stu-id="71904-103">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>

<span data-ttu-id="71904-p101">通話の分析を使用すると、Skype for Business で通話] または [接続の問題のトラブルシューティングを行うことができます。通話の分析は、Skype for Business アカウントにデバイス、ネットワーク、および通話と会議の各ユーザーの接続に関する詳細情報を示しています。サイト、およびテナントの構築する場合は、情報が追加されている分析の通話を着信およびセッションごとにも表示されます。情報の分析を通話に使用できますが低下通話を持っていた理由を把握する、または会議のエクスペリエンスします。</span><span class="sxs-lookup"><span data-stu-id="71904-p101">Call Analytics helps you to troubleshoot call or connection problems with Skype for Business. Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Skype for Business account. If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session. Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
    > [!NOTE]
    > Call Analytics is currently in preview. Text and images described here may not match your experience. 
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="71904-108">通話の分析を使用して通話品質の問題のトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="71904-108">Troubleshoot call quality problems using Call Analytics</span></span>

<span data-ttu-id="71904-109">情報の種類はどのようなアクセス権のある分析の電話で自分に割り当てられているアクセス許可レベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="71904-109">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="71904-110">**Skype for Business 管理者**: 分析を呼び出すと Skype for Business 管理センターですべての情報にアクセス権があります。</span><span class="sxs-lookup"><span data-stu-id="71904-110">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="71904-p102">**第 1 層のアクセス許可を持つヘルプデスク エージェント**: 通話分析でデータのセットを参照してください。呼び出しのトラブルシューティングを行うことができますが、第 2 の担当者に会議の問題が渡すされます。Business 管理センターの残りの Skype へのアクセスを必要はありません。</span><span class="sxs-lookup"><span data-stu-id="71904-p102">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics. You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent. You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="71904-p103">**第 2 のアクセス許可を持つヘルプデスク エージェント**: を呼び出す分析のすべての利用可能なデータを表示し、通話と会議の両方の問題のトラブルシューティングを行うことができます。Business 管理センターの残りの Skype へのアクセスを必要はありません。</span><span class="sxs-lookup"><span data-stu-id="71904-p103">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings. You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
<span data-ttu-id="71904-116">アクセス許可を持つヘルプが必要な場合は、Skype for Business の管理者を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71904-116">See your Skype for Business admin if you need help with permissions.</span></span>
  
 <span data-ttu-id="71904-117">**階層 1 または 2 層ヘルプデスク エージェントとして通話の分析を開く**</span><span class="sxs-lookup"><span data-stu-id="71904-117">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span></span>
  
1. <span data-ttu-id="71904-p104">Office 365 管理センターに移動し、職場または学校のアカウントを使用してサインインします。[Web ブラウザーで*https://adminportal.services.skypeforbusiness.com*に移動します。</span><span class="sxs-lookup"><span data-stu-id="71904-p104">Go to the Office 365 admin center and sign in using your work or school account. Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>
    
2. <span data-ttu-id="71904-120">**ユーザーの検索**] でのトラブルシューティングを行うし、リストからユーザーを選択する呼び出しをユーザーの名前または sip アドレスを入力を開始します。</span><span class="sxs-lookup"><span data-stu-id="71904-120">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span></span>
    
    ![Skype for Business 管理センターでの分析の通話の [ユーザーの検索] ボックスのスクリーン ショット。](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. <span data-ttu-id="71904-122">**通話履歴**には、[トラブルシューティングを行う通話または会議を選択します。</span><span class="sxs-lookup"><span data-stu-id="71904-122">In **Call history**, select the call or meeting that you want to troubleshoot.</span></span>
    
    ![スクリーン ショットは、7 日間の品質との会議と電話、アクティビティの概要と、日付と時刻、受信者、および音声の品質の概要については、ユーザーの連絡先の詳細についてなどの情報を持つユーザーの通話履歴] ページを示しています。](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. <span data-ttu-id="71904-124">[**詳細設定**] タブを選択し、低下通話の品質や接続の問題を示す黄色、赤のアイテムを調べます。</span><span class="sxs-lookup"><span data-stu-id="71904-124">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="71904-p105">各通話または会議のセッションの詳細] では、黄色の小さな問題が表示されます。(たとえば、次のスクリーン ショットでは、値は、黄色の平均ジッター、Max ジッター、平均パケット損失の割合で。)黄色がある場合は、通常の範囲外と、問題が発生する原因なっている可能性がありますがない問題の主な原因をする可能性があります。赤いがある場合は、重要な問題があるし、このセッションの低下通話品質の主な原因である可能性がします。</span><span class="sxs-lookup"><span data-stu-id="71904-p105">In the session details for each call or meeting, minor issues appear in yellow. (For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem. If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![スクリーン ショットは、つまりマイナーと受信ネットワーク] セクションを展開して、黄色の色] で、平均ジッター、最大ジッター、および平均パケット損失率のデータが表示されているユーザーの通話履歴の詳細設定] タブを示します。](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
<span data-ttu-id="71904-p106">不具合エクスペリエンスのデータの品質いない音声セッションで受信します。多くの場合これが原因通話ドロップして接続を終了してクライアントを使ってです。この場合、セッションの評価は""します。</span><span class="sxs-lookup"><span data-stu-id="71904-p106">In rare cases, quality of experience data isn't received for audio sessions. Often this is caused by the call dropping and connection with the client terminating. When this occurs, the session rating is "unavailable".</span></span>
  
<span data-ttu-id="71904-132">Experience (QoE) データの品質が音声セッションでは、次の表は「低下。」としてセッションの対象の点を示します。</span><span class="sxs-lookup"><span data-stu-id="71904-132">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span></span>
  
|<span data-ttu-id="71904-133">**問題**</span><span class="sxs-lookup"><span data-stu-id="71904-133">**Issue**</span></span>|<span data-ttu-id="71904-134">**領域**</span><span class="sxs-lookup"><span data-stu-id="71904-134">**Area**</span></span>|<span data-ttu-id="71904-135">**{Description}**</span><span class="sxs-lookup"><span data-stu-id="71904-135">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="71904-136">通話のセットアップ</span><span class="sxs-lookup"><span data-stu-id="71904-136">Call setup</span></span>  <br/> |<span data-ttu-id="71904-137">セッション</span><span class="sxs-lookup"><span data-stu-id="71904-137">Session</span></span>  <br/> |<span data-ttu-id="71904-p107">エラー コード Ms 20 ~ 29 を診断では、通話のセットアップに失敗しました。 が表示されます。ユーザーは、通話または会議に参加できませんでした。</span><span class="sxs-lookup"><span data-stu-id="71904-p107">The error code Ms-diag 20-29 indicates the call setup failed. The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="71904-140">オーディオ ネットワークが低下通話を分類します。</span><span class="sxs-lookup"><span data-stu-id="71904-140">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="71904-141">セッション</span><span class="sxs-lookup"><span data-stu-id="71904-141">Session</span></span>  <br/> |<span data-ttu-id="71904-p108">ネットワークの品質に問題は、パケット損失、ジッター NMOS 低下、RTT などの領域にあったまたは比率を非表示します。不適切な呼び出しを分類するための条件の詳細については、この[Microsoft ブログの投稿](https://go.microsoft.com/fwlink/p/?linkid=852133)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71904-p108">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio. For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).  </span></span><br/> |
|<span data-ttu-id="71904-144">デバイスが機能しません。</span><span class="sxs-lookup"><span data-stu-id="71904-144">Device not functioning</span></span>  <br/> |<span data-ttu-id="71904-145">デバイス</span><span class="sxs-lookup"><span data-stu-id="71904-145">Device</span></span>  <br/> | <span data-ttu-id="71904-p109">デバイスが正しく機能していません。比率が機能していないデバイスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="71904-p109">A device isn't functioning correctly. Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="71904-148">DeviceRenderNotFunctioningEventRatio > = 0.005</span><span class="sxs-lookup"><span data-stu-id="71904-148">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="71904-149">DeviceCaptureNotFunctioningEventRatio > = 0.005</span><span class="sxs-lookup"><span data-stu-id="71904-149">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="71904-150">関連トピック</span><span class="sxs-lookup"><span data-stu-id="71904-150">Related topics</span></span>
[<span data-ttu-id="71904-151">Skype for Business 通話分析を設定します。</span><span class="sxs-lookup"><span data-stu-id="71904-151">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="71904-152">通話の分析手法と通話品質のダッシュ ボードの違いは何ですか。</span><span class="sxs-lookup"><span data-stu-id="71904-152">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

