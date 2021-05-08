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
f1.keywords:
- NOCSH
description: セッション ボーダー コントローラー、ダイレクト ルーティング コンポーネント、通信トランクなど、ダイレクト ルーティング構成を監視およびトラブルシューティングする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74a67493fa2f9647e6cd0364bb4c9d6a3c05e48a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121405"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="9b14d-103">ダイレクト ルーティングの監視とトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9b14d-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="9b14d-104">この記事では、ダイレクト ルーティング構成を監視およびトラブルシューティングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b14d-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="9b14d-105">ダイレクト ルーティングを使用して通話を送受信する機能には、次のコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="9b14d-106">セッション ボーダー コントローラー (SBC)</span><span class="sxs-lookup"><span data-stu-id="9b14d-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="9b14d-107">Microsoft Cloud のダイレクト ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9b14d-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="9b14d-108">通信トランク</span><span class="sxs-lookup"><span data-stu-id="9b14d-108">Telecom trunks</span></span> 

<span data-ttu-id="9b14d-109">問題のトラブルシューティングに問題がある場合は、SBC ベンダーまたは Microsoft にサポート ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="9b14d-110">Microsoft では、トラブルシューティングと監視のためのその他のツールの提供に取り組み中です。</span><span class="sxs-lookup"><span data-stu-id="9b14d-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="9b14d-111">更新プログラムについては、ドキュメントを定期的に確認してください。</span><span class="sxs-lookup"><span data-stu-id="9b14d-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="9b14d-112">セッション開始プロトコル (SIP) オプション メッセージを使用したセッション ボーダー コントローラーの可用性の監視</span><span class="sxs-lookup"><span data-stu-id="9b14d-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="9b14d-113">直接ルーティングでは、セッション ボーダー コントローラーから送信された SIP オプションを使用して、SBC の正常性を監視します。</span><span class="sxs-lookup"><span data-stu-id="9b14d-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="9b14d-114">SIP オプションの監視を有効にするには、テナント管理者から必要なアクションはありません。</span><span class="sxs-lookup"><span data-stu-id="9b14d-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="9b14d-115">収集された情報は、ルーティングの決定が行われたときに考慮されます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="9b14d-116">たとえば、特定のユーザーに対して、通話のルーティングに使用できる SBC が複数ある場合、ダイレクト ルーティングは、各 SBC から受信した SIP オプション情報を考慮してルーティングを決定します。</span><span class="sxs-lookup"><span data-stu-id="9b14d-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="9b14d-117">次の図は、構成の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="9b14d-117">The following diagram shows an example of the configuration:</span></span> 

![SIP オプションの構成例](media/sip-options-config-example.png)

<span data-ttu-id="9b14d-119">ユーザーが番号 +1 425 の呼び出しを行った \<any seven digits> 場合、ダイレクト ルーティングによってルートが評価されます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="9b14d-120">ルートには 2 つの SBC があります。ルートには、sbc1.contoso.com と sbc2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="9b14d-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="9b14d-121">両方の SPC は、ルートの優先順位が等しくなります。</span><span class="sxs-lookup"><span data-stu-id="9b14d-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="9b14d-122">SBC を選択する前に、ルーティング メカニズムは、SBC が前回 SIP オプションを送信した時刻に基づいて、SBC の正常性を評価します。</span><span class="sxs-lookup"><span data-stu-id="9b14d-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="9b14d-123">SBC は、呼び出しを送信した時点の統計情報で、SBC が 1 分ごとにオプションを送信する場合に正常と見なされます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="9b14d-124">呼び出しが行われた場合、次のロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="9b14d-125">SBC は午前 11 時 00 分にペアリングされました。</span><span class="sxs-lookup"><span data-stu-id="9b14d-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="9b14d-126">SBC は、午前 11 時 11 分、午前 11 時 02 分など、オプションを送信します。</span><span class="sxs-lookup"><span data-stu-id="9b14d-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="9b14d-127">11 時 15 分にユーザーが呼び出しを行い、ルーティング メカニズムによってこの SBC が選択されます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="9b14d-128">ダイレクト ルーティングは、一定の間隔オプションを 3 回受け取ります (一定の間隔は 1 分です)。</span><span class="sxs-lookup"><span data-stu-id="9b14d-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="9b14d-129">オプションが最後の 3 分間に送信された場合、SBC は正常と見なされます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="9b14d-130">この例の SBC が午前 11 時 12 分から午前 11 時 15 分 (呼び出しが行われた時刻) の間にオプションを送信した場合、正常と見なされます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="9b14d-131">存在しない場合、SBC はルートから降格されます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="9b14d-132">降格とは、SBC が最初に試みようとしないという意味です。</span><span class="sxs-lookup"><span data-stu-id="9b14d-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="9b14d-133">たとえば、優先順位が等しい sbc1.contoso.com、sbc2.contoso.com を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b14d-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="9b14d-134">前述 sbc1.contoso.com 一定の間隔で SIP オプションを送信しない場合は、降格されます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="9b14d-135">次に、sbc2.contoso.com を試します。</span><span class="sxs-lookup"><span data-stu-id="9b14d-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="9b14d-136">sbc2.contoso.con が呼び出しを配信できない場合、エラーが生成される前に、sbc1.contoso.com (降格) が再度試みされます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="9b14d-137">1 つのルート内の 2 つ (以上) の SBC が正常で等しいと見なされた場合は、Fisher-Yates シャッフルが適用され、SPC 間で呼び出しが分散されます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="9b14d-138">通話品質分析ダッシュボードと SBC ログの監視</span><span class="sxs-lookup"><span data-stu-id="9b14d-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="9b14d-139">場合によっては、特に初期ペアリング中に、SBC またはダイレクト ルーティング サービスの構成ミスに関連する問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9b14d-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="9b14d-140">次のツールを使用して、構成を監視できます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="9b14d-141">通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="9b14d-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="9b14d-142">SBC ログ</span><span class="sxs-lookup"><span data-stu-id="9b14d-142">SBC logs</span></span> 

<span data-ttu-id="9b14d-143">ダイレクト ルーティング サービスには、Call Analytics または SBC ログに報告される非常にわかりやすいエラー コードがあります。</span><span class="sxs-lookup"><span data-stu-id="9b14d-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="9b14d-144">通話品質ダッシュボードには、通話の品質と信頼性に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="9b14d-145">通話分析を使用して問題をトラブルシューティングする方法の詳細については[、「Microsoft Teams](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)および Skype for Business Online の通話品質ダッシュボードを有効にして使用する」および「通話分析を使用して低品質の通話品質をトラブルシューティングする」を参照[してください。](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)</span><span class="sxs-lookup"><span data-stu-id="9b14d-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="9b14d-146">通話エラーが発生した場合、Call Analytics にはトラブルシューティングに役立つ標準的な SIP コードが提供されています。</span><span class="sxs-lookup"><span data-stu-id="9b14d-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![呼び出しエラーのサンプル SIP コード](media/failed-response-code.png)

<span data-ttu-id="9b14d-148">ただし、通話分析は、呼び出しがダイレクト ルーティングの内部コンポーネントに到達して失敗した場合にのみ役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="9b14d-149">SBC のペアリングに関する問題や、SIP の "招待" が拒否された問題 (たとえば、トランク FQDN の名前が正しく構成されていない) の場合、通話分析は役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9b14d-149">In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="9b14d-150">この場合は、SBC ログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b14d-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="9b14d-151">直接ルーティングは、問題の詳細な説明を SBC に送信します。これらの問題は、SBC ログから読み取り可能です。</span><span class="sxs-lookup"><span data-stu-id="9b14d-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span>