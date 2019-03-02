---
title: 監視し、直接ルーティングのトラブルシューティングを行う
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto: Microsoft Teams
description: この資料では、監視し、直接ルーティングの構成をトラブルシューティングする方法について説明します。
ms.openlocfilehash: 75f116004c0385aa7d13b0173380221304590814
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "30350987"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="fcb76-103">監視し、直接ルーティングのトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="fcb76-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="fcb76-104">この資料では、監視し、直接ルーティングの構成をトラブルシューティングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fcb76-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="fcb76-105">作成し、直接ルーティングを使用して呼び出しを受信する機能には、次のコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fcb76-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="fcb76-106">セッション ボーダー コント ローラー (SBCs)</span><span class="sxs-lookup"><span data-stu-id="fcb76-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="fcb76-107">マイクロソフトのクラウドでの直接のルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fcb76-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="fcb76-108">トランクの電気通信</span><span class="sxs-lookup"><span data-stu-id="fcb76-108">Telecom trunks</span></span> 

<span data-ttu-id="fcb76-109">に関する問題のトラブルシューティングの問題がある場合は、SBC の製造元またはマイクロソフトのサポート ・ リクエストを開いてください。</span><span class="sxs-lookup"><span data-stu-id="fcb76-109">If you have difficulties troubleshooting issues, please open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="fcb76-110">マイクロソフトは、トラブルシューティングと監視に関するその他のツールを提供することに取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="fcb76-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="fcb76-111">更新プログラムを定期的にドキュメントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fcb76-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="fcb76-112">メッセージのセッション開始プロトコル (SIP) オプションを使用してセッションの枠線のコント ローラーの可用性の監視</span><span class="sxs-lookup"><span data-stu-id="fcb76-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) Options messages</span></span>

<span data-ttu-id="fcb76-113">直接ルーティングでは、SBC の状態を監視するのにセッション ボーダー コント ローラーから送信された SIP のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="fcb76-113">Direct Routing uses SIP Options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="fcb76-114">SIP オプションの監視を有効にするのには、テナントの管理者から必要なアクションはありません。</span><span class="sxs-lookup"><span data-stu-id="fcb76-114">There are no actions required from the tenant administrator to enable the SIP Options monitoring.</span></span> <span data-ttu-id="fcb76-115">ルーティングの決定が行われると、収集した情報を考慮にします。</span><span class="sxs-lookup"><span data-stu-id="fcb76-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="fcb76-116">などの場合は、特定のユーザーの通話のルーティングに使用できるいくつかの SBCs、直接ルーティングと見なされるルーティングを決定するのには、各 SBC から受信した SIP オプション情報です。</span><span class="sxs-lookup"><span data-stu-id="fcb76-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP Options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="fcb76-117">構成の例を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="fcb76-117">The following diagram shows an example of the configuration:</span></span> 

![SIP オプションの構成の例](media/sip-options-config-example.png)

<span data-ttu-id="fcb76-119">番号 +1 425 への呼び出しを行うと、\<直接ルーティングでは、7 つの digits> は、ルートを評価します。</span><span class="sxs-lookup"><span data-stu-id="fcb76-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="fcb76-120">ルートにある 2 つの SBCs: sbc1.contoso.com と sbc2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="fcb76-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="fcb76-121">SBCs の両方では、工順の優先度が同じがあります。</span><span class="sxs-lookup"><span data-stu-id="fcb76-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="fcb76-122">ルーティング メカニズムが、SBC に送信される SIP オプションに基づいて、SBCs の稼働状態を評価する SBC をピッキングする前に最後の時間します。</span><span class="sxs-lookup"><span data-stu-id="fcb76-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP Options last time.</span></span> 

<span data-ttu-id="fcb76-123">SBC は、SBC が一定の間隔のオプションを送信する送信呼び出しの時点での統計情報が表示されている場合は正常と見なされます。</span><span class="sxs-lookup"><span data-stu-id="fcb76-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends Options on a regular interval.</span></span>  

<span data-ttu-id="fcb76-124">直接ルーティングは、SBC が呼び出しを行うと、5 分を追加する前にオプションを送信するときに、2 回の平均をとることによって一定の間隔を計算します。</span><span class="sxs-lookup"><span data-stu-id="fcb76-124">Direct Routing calculates regular intervals by taking two times the average when the SBC sends Options before making the call and adding five minutes.</span></span> 

<span data-ttu-id="fcb76-125">たとえば、次の点を想定しています。</span><span class="sxs-lookup"><span data-stu-id="fcb76-125">For example, assume the following:</span></span> 

- <span data-ttu-id="fcb76-126">SBC の構成オプションの 1 分ごとに送信します。</span><span class="sxs-lookup"><span data-stu-id="fcb76-126">An SBC is configured to send Options every minute.</span></span> 
- <span data-ttu-id="fcb76-127">午前 11時 00分、SBC と同じです。</span><span class="sxs-lookup"><span data-stu-id="fcb76-127">The SBC was paired at 11.00 AM.</span></span>  
- <span data-ttu-id="fcb76-128">SBC は、11.01 AM、11.02 AM というようにオプションを送信します。</span><span class="sxs-lookup"><span data-stu-id="fcb76-128">The SBC sends options at 11.01 AM, 11.02 AM, and so on.</span></span>  
- <span data-ttu-id="fcb76-129">11.15 でユーザーが呼び出しを行うし、ルーティング メカニズムは、この SBC を選択します。</span><span class="sxs-lookup"><span data-stu-id="fcb76-129">At 11.15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="fcb76-130">次のロジックを適用: SBC は、さらに 5 分 = 7 分 (1 分間および 1 つ分 = 2 分) のオプションを送信するときに、平均の間隔が 2 倍です。</span><span class="sxs-lookup"><span data-stu-id="fcb76-130">The following logic is applied: Two times the average interval when the SBC sends Options (one minute plus one minute = two minutes) plus five minutes = seven minutes.</span></span> <span data-ttu-id="fcb76-131">これは、SBC の一定の間隔の値です。</span><span class="sxs-lookup"><span data-stu-id="fcb76-131">This is the value of the regular interval for the SBC.</span></span>
 
<span data-ttu-id="fcb76-132">この例では、SBC では、11時 08分 AM と 11時 15分 AM (呼び出しが行われた時間) との間にあるオプションを送信する場合正常と見なされます。</span><span class="sxs-lookup"><span data-stu-id="fcb76-132">If the SBC in our example sent options at any period between 11.08 AM and 11.15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="fcb76-133">それ以外の場合は、SBC をルートから降格されます。</span><span class="sxs-lookup"><span data-stu-id="fcb76-133">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="fcb76-134">降格では、ある、SBC は試行されませんが、最初を意味します。</span><span class="sxs-lookup"><span data-stu-id="fcb76-134">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="fcb76-135">たとえば、sbc1.contoso.com と sbc2.contoso.com が同じ優先度であります。</span><span class="sxs-lookup"><span data-stu-id="fcb76-135">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="fcb76-136">Sbc1.contoso.com は、前述のとおり、一定の間隔のオプションの SIP を送信しません、する場合は降格されます。</span><span class="sxs-lookup"><span data-stu-id="fcb76-136">If sbc1.contoso.com does not send SIP Options on a regular interval as described above, it is demoted.</span></span> <span data-ttu-id="fcb76-137">次に、sbc2.contoso.com は、呼び出しを試みます。</span><span class="sxs-lookup"><span data-stu-id="fcb76-137">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="fcb76-138">Sbc2.contoso.con は、呼び出しを配信できません、エラーが生成される前に (降格) sbc1.contoso.com としました。</span><span class="sxs-lookup"><span data-stu-id="fcb76-138">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="fcb76-139">ダッシュ ボードの品質の分析機能を呼び出すと SBC のログを監視します。</span><span class="sxs-lookup"><span data-stu-id="fcb76-139">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="fcb76-140">場合によっては、最初のペアリング時に、特に可能性があります、SBCs または直接ルーティング サービスの構成の誤りに関連する問題。</span><span class="sxs-lookup"><span data-stu-id="fcb76-140">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs and/or the Direct Routing service.</span></span> 

<span data-ttu-id="fcb76-141">構成を監視するのには、次のツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fcb76-141">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="fcb76-142">通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="fcb76-142">Call Quality Dashboard</span></span> 
- <span data-ttu-id="fcb76-143">SBC のログ</span><span class="sxs-lookup"><span data-stu-id="fcb76-143">SBC logs</span></span> 

<span data-ttu-id="fcb76-144">直接ルーティング サービスには非常にわかりやすいエラー コードの分析機能を呼び出すか、SBC のログに報告します。</span><span class="sxs-lookup"><span data-stu-id="fcb76-144">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="fcb76-145">コール品質のダッシュ ボードでは、通話の音質と信頼性に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="fcb76-145">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="fcb76-146">分析機能の呼び出しを使用して問題をトラブルシューティングする方法の詳細について[を有効にしてマイクロソフトのチームとビジネス オンラインの Skype の品質ダッシュ ボードの呼び出しを使用して](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)[不適切な呼び出し品質のトラブルシューティングを行うコール分析機能の使用](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcb76-146">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="fcb76-147">呼び出しの失敗が発生した場合は、分析機能の呼び出しは、トラブルシューティングするための標準の SIP コードを提供します。</span><span class="sxs-lookup"><span data-stu-id="fcb76-147">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![呼び出しが失敗した SIP のサンプル コード](media/failed-response-code.png)

<span data-ttu-id="fcb76-149">ただし、分析機能を呼び出すのに役立つだけ呼び出しが直接ルーティングの内部コンポーネントにアクセスし、失敗するとします。</span><span class="sxs-lookup"><span data-stu-id="fcb76-149">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="fcb76-150">SBC の組み合わせで問題または SIP」への招待」が (FQDN が正しく構成されていないトランクの名前など) が拒否された問題では、分析機能を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fcb76-150">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="fcb76-151">この例では、SBC のログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcb76-151">In this case, please refer to the SBC logs.</span></span> <span data-ttu-id="fcb76-152">直接ルーティングは、半角英数字に問題の詳細な説明を送信します。これらの問題は、SBC のログから読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="fcb76-152">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
