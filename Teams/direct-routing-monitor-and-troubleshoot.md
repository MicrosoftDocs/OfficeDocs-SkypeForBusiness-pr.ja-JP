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
- M365-voice
appliesto:
- Microsoft Teams
description: この記事では、ダイレクトルーティング構成の監視とトラブルシューティングを行う方法について説明します。
ms.openlocfilehash: b2afef2a8f02f6823be10d127c8efc7b4cd5d72d
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572170"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="1bbeb-103">ダイレクト ルーティングの監視とトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1bbeb-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="1bbeb-104">この記事では、ダイレクトルーティング構成の監視とトラブルシューティングを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="1bbeb-105">ダイレクトルーティングを使用して通話の発信と受信を行うには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="1bbeb-106">セッション境界コントローラー (SBCs)</span><span class="sxs-lookup"><span data-stu-id="1bbeb-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="1bbeb-107">Microsoft Cloud でのダイレクトルーティングコンポーネント</span><span class="sxs-lookup"><span data-stu-id="1bbeb-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="1bbeb-108">電気通信 trunks</span><span class="sxs-lookup"><span data-stu-id="1bbeb-108">Telecom trunks</span></span> 

<span data-ttu-id="1bbeb-109">問題のトラブルシューティングで問題が発生した場合は、SBC ベンダーまたは Microsoft とのサポートケースを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="1bbeb-110">Microsoft は、トラブルシューティングと監視のためのより多くのツールを提供するための作業を進めています。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="1bbeb-111">アップデートについてはドキュメントを定期的にチェックしてください。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="1bbeb-112">セッション開始プロトコル (SIP) オプションメッセージを使用してセッション境界コントローラーの可用性を監視する</span><span class="sxs-lookup"><span data-stu-id="1bbeb-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="1bbeb-113">ダイレクトルーティングでは、セッション境界コントローラーによって送信される SIP オプションを使用して、SBC ヘルスを監視します。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="1bbeb-114">SIP オプションの監視を有効にするには、テナント管理者からの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="1bbeb-115">収集された情報は、ルーティング決定が行われるときに考慮されます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="1bbeb-116">たとえば、特定のユーザーに対して、通話のルーティングに使用できる複数の SBCs がある場合、直接ルーティングでは、各 SBC から受信した SIP オプション情報がルーティングを決定します。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="1bbeb-117">次の図は、構成の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-117">The following diagram shows an example of the configuration:</span></span> 

![SIP オプション構成の例](media/sip-options-config-example.png)

<span data-ttu-id="1bbeb-119">ユーザーが数字 + 1 425 \<への任意の 7> 桁の通話を発信すると、ダイレクトルーティングによってルートが評価されます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="1bbeb-120">ルートには、sbc1.contoso.com と sbc2.contoso.com の2つの SBCs があります。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="1bbeb-121">SBCs は両方ともルートの優先度が同じです。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="1bbeb-122">SBC を選ぶ前に、SBC が SIP オプションを最後に送信した場合に基づく SBCs の正常性が評価されます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="1bbeb-123">通話を送信するときに、SBC がオプションを1分おきに送信することを示している場合は、SBC は良好であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="1bbeb-124">通話が行われると、次のロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="1bbeb-125">SBC は、11:00 AM でペアリングされました。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="1bbeb-126">SBC は、11:01 AM、11:02 AM などでオプションを送信します。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="1bbeb-127">11:15 では、ユーザーが通話を発信し、ルーティングメカニズムによってこの SBC が選択されます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="1bbeb-128">[直接ルーティング] は、通常の間隔オプションを3回行います (通常の間隔は1分です)。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="1bbeb-129">残り3分間にオプションが送信された場合は、SBC は正常であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="1bbeb-130">この例の SBC が、11:12 AM と 11:15 AM (通話が発信された時刻) の間に任意の期間にオプションを送信した場合は、正常であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="1bbeb-131">それ以外の場合は、SBC がルートから降格されます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="1bbeb-132">降格とは、SBC が最初に試されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="1bbeb-133">たとえば、sbc1.contoso.com と sbc2.contoso.com は同じ優先度で設定されています。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="1bbeb-134">前に説明したように、sbc1.contoso.com が SIP オプションを通常の間隔で送信しない場合は、降格されます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="1bbeb-135">次に、sbc2.contoso.com が通話を試みます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="1bbeb-136">Sbc2 で通話を発信できない場合、エラーが発生する前に、sbc1.contoso.com (降格) がもう一度試行されます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="1bbeb-137">1つ以上の SBCs の1つのルートが正常で等しいと見なされた場合は、SBCs 間の通話を分散するために、フィッシャーのシャッフルが適用されます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="1bbeb-138">通話品質分析ダッシュボードと SBC ログを監視する</span><span class="sxs-lookup"><span data-stu-id="1bbeb-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="1bbeb-139">場合によっては、最初のペアリングの際に、SBCs またはダイレクトルーティングサービスの構成の誤りに関連して問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="1bbeb-140">以下のツールを使用して、構成を監視できます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="1bbeb-141">通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="1bbeb-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="1bbeb-142">SBC ログ</span><span class="sxs-lookup"><span data-stu-id="1bbeb-142">SBC logs</span></span> 

<span data-ttu-id="1bbeb-143">ダイレクトルーティングサービスには、通話分析または SBC ログのどちらかに報告される非常にわかりやすいエラーコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="1bbeb-144">通話音質ダッシュボードには、通話品質と信頼性に関する情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="1bbeb-145">通話分析を使用して問題を解決する方法の詳細については、「 [Microsoft Teams および Skype For Business Online で通話品質ダッシュボードをオンにして使用](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)する」および「[通話分析を使用して低品質の通話品質をトラブルシューティングする」を](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="1bbeb-146">通話が失敗した場合、通話分析では、トラブルシューティングに役立つ標準的な SIP コードが提供されます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![通話の失敗に関する SIP コードの例](media/failed-response-code.png)

<span data-ttu-id="1bbeb-148">ただし、通話分析は、通話が直接ルーティングの内部コンポーネントに到達して失敗した場合にのみ役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="1bbeb-149">SBC ペアリング、または SIP "Invite" が拒否された問題がある場合 (たとえば、トランク FQDN の名前が正しく構成されていない場合)、通話分析はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-149">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="1bbeb-150">この場合は、SBC ログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="1bbeb-151">直接ルーティングでは、問題の詳細な説明が SBCs に送信されます。これらの問題は、SBC ログから読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="1bbeb-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
