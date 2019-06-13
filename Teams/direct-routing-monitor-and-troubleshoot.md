---
title: ダイレクト ルーティングの監視とトラブルシューティング
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: この記事では、ダイレクトルーティング構成の監視とトラブルシューティングを行う方法について説明します。
ms.openlocfilehash: eeae12aafba87d9af210138f546ed82b12acbbd7
ms.sourcegitcommit: 1a768e470a9509139eeb24034def12630acb7914
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2019
ms.locfileid: "34915157"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="8b0f6-103">ダイレクト ルーティングの監視とトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8b0f6-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="8b0f6-104">この記事では、ダイレクトルーティング構成の監視とトラブルシューティングを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="8b0f6-105">ダイレクトルーティングを使用して通話の発信と受信を行うには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="8b0f6-106">セッション境界コントローラー (SBCs)</span><span class="sxs-lookup"><span data-stu-id="8b0f6-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="8b0f6-107">Microsoft Cloud でのダイレクトルーティングコンポーネント</span><span class="sxs-lookup"><span data-stu-id="8b0f6-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="8b0f6-108">電気通信 trunks</span><span class="sxs-lookup"><span data-stu-id="8b0f6-108">Telecom trunks</span></span> 

<span data-ttu-id="8b0f6-109">問題のトラブルシューティングに問題がある場合は、SBC ベンダーまたは Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-109">If you have difficulties troubleshooting issues, please open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="8b0f6-110">Microsoft は、トラブルシューティングと監視のためのより多くのツールを提供するための作業を進めています。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="8b0f6-111">アップデートについてはドキュメントを定期的にチェックしてください。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="8b0f6-112">セッション開始プロトコル (SIP) オプションメッセージを使用してセッション境界コントローラーの可用性を監視する</span><span class="sxs-lookup"><span data-stu-id="8b0f6-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="8b0f6-113">ダイレクトルーティングでは、セッション境界コントローラーによって送信される SIP オプションを使用して、SBC ヘルスを監視します。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="8b0f6-114">SIP オプションの監視を有効にするには、テナント管理者からの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="8b0f6-115">収集された情報は、ルーティング決定が行われるときに考慮されます。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="8b0f6-116">たとえば、特定のユーザーに対して、通話のルーティングに使用できる複数の SBCs がある場合、直接ルーティングでは、各 SBC から受信した SIP オプション情報がルーティングを決定します。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="8b0f6-117">次の図は、構成の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-117">The following diagram shows an example of the configuration:</span></span> 

![SIP オプション構成の例](media/sip-options-config-example.png)

<span data-ttu-id="8b0f6-119">ユーザーが数字 + 1 425 \<への任意の 7> 桁の通話を発信すると、ダイレクトルーティングによってルートが評価されます。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="8b0f6-120">ルートには、sbc1.contoso.com と sbc2.contoso.com の2つの SBCs があります。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="8b0f6-121">SBCs は両方ともルートの優先度が同じです。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="8b0f6-122">SBC を選ぶ前に、SBC が SIP オプションを最後に送信した場合に基づく SBCs の正常性が評価されます。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="8b0f6-123">通話を送信するときに、SBC が通常の間隔でオプションを送信することを示している場合は、SBC は良好であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends Options on a regular interval.</span></span>  

<span data-ttu-id="8b0f6-124">直接ルーティングでは、SBC が通話を発信して5分追加する前に、SBC がオプションを送信するときに2倍の平均値を計算します。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-124">Direct Routing calculates regular intervals by taking two times the average when the SBC sends options before making the call and adding five minutes.</span></span> 

<span data-ttu-id="8b0f6-125">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-125">For example, assume the following:</span></span> 

- <span data-ttu-id="8b0f6-126">SBC は、毎分オプションを送信するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-126">An SBC is configured to send options every minute.</span></span> 
- <span data-ttu-id="8b0f6-127">SBC は、11.00 AM でペアリングされました。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-127">The SBC was paired at 11.00 AM.</span></span>  
- <span data-ttu-id="8b0f6-128">SBC は、11.01 AM、11.02 AM などでオプションを送信します。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-128">The SBC sends options at 11.01 AM, 11.02 AM, and so on.</span></span>  
- <span data-ttu-id="8b0f6-129">11.15 では、ユーザーが通話を発信し、ルーティングメカニズムによってこの SBC が選択されます。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-129">At 11.15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="8b0f6-130">次のロジックが適用されます。 SBC がオプションを送信するときの平均間隔 (1 分 + 1 分 = 2 分) + 5 分 = 7 分。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-130">The following logic is applied: Two times the average interval when the SBC sends options (one minute plus one minute = two minutes) plus five minutes = seven minutes.</span></span> <span data-ttu-id="8b0f6-131">これは、SBC の定期的な間隔の値です。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-131">This is the value of the regular interval for the SBC.</span></span>
 
<span data-ttu-id="8b0f6-132">この例の SBC が、11.08 AM と 11.15 AM (通話が発信された時刻) の間に任意の期間でオプションを送信した場合は、正常であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-132">If the SBC in our example sent options at any period between 11.08 AM and 11.15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="8b0f6-133">それ以外の場合は、SBC がルートから降格されます。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-133">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="8b0f6-134">降格とは、SBC が最初に試されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-134">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="8b0f6-135">たとえば、sbc1.contoso.com と sbc2.contoso.com は同じ優先度で設定されています。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-135">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="8b0f6-136">上で説明したように、sbc1.contoso.com が SIP オプションを通常の間隔で送信しない場合は、降格されます。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-136">If sbc1.contoso.com does not send SIP options on a regular interval as described above, it is demoted.</span></span> <span data-ttu-id="8b0f6-137">次に、sbc2.contoso.com が通話を試みます。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-137">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="8b0f6-138">Sbc2 で通話を発信できない場合、エラーが発生する前に、sbc1.contoso.com (降格) がもう一度試行されます。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-138">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="8b0f6-139">通話品質分析ダッシュボードと SBC ログを監視する</span><span class="sxs-lookup"><span data-stu-id="8b0f6-139">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="8b0f6-140">場合によっては、最初のペアリングの際に、SBCs またはダイレクトルーティングサービスの構成の誤りに関連して問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-140">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs and/or the Direct Routing service.</span></span> 

<span data-ttu-id="8b0f6-141">以下のツールを使用して、構成を監視できます。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-141">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="8b0f6-142">通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="8b0f6-142">Call Quality Dashboard</span></span> 
- <span data-ttu-id="8b0f6-143">SBC ログ</span><span class="sxs-lookup"><span data-stu-id="8b0f6-143">SBC logs</span></span> 

<span data-ttu-id="8b0f6-144">ダイレクトルーティングサービスには、通話分析または SBC ログのどちらかに報告される非常にわかりやすいエラーコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-144">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="8b0f6-145">通話音質ダッシュボードには、通話品質と信頼性に関する情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-145">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="8b0f6-146">通話分析を使用して問題を解決する方法の詳細については、「 [Microsoft Teams および Skype For Business Online で通話品質ダッシュボードをオンにして使用](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)する」および「[通話分析を使用して低品質の通話品質をトラブルシューティングする」を](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-146">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="8b0f6-147">通話が失敗した場合、通話分析では、トラブルシューティングに役立つ標準的な SIP コードが提供されます。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-147">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![通話の失敗に関する SIP コードの例](media/failed-response-code.png)

<span data-ttu-id="8b0f6-149">ただし、通話分析は、通話が直接ルーティングの内部コンポーネントに到達して失敗した場合にのみ役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-149">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="8b0f6-150">SBC ペアリング、または SIP "Invite" が拒否された問題がある場合 (たとえば、トランク FQDN の名前が正しく構成されていない場合)、通話分析はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-150">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="8b0f6-151">この場合は、SBC ログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-151">In this case, please refer to the SBC logs.</span></span> <span data-ttu-id="8b0f6-152">直接ルーティングでは、問題の詳細な説明が SBCs に送信されます。これらの問題は、SBC ログから読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="8b0f6-152">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
