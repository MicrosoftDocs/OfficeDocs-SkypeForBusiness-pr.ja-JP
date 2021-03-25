---
title: 直接ルーティングの正常性ダッシュボード
ms.reviewer: nmurav
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 正常性ダッシュボードを使用してセッション ボーダー コントローラーと直接ルーティング間の接続を監視する方法について説明します。
ms.openlocfilehash: cb5e802d904cd2eb364fd480ebcde385e64cf02b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122231"
---
# <a name="health-dashboard-for-direct-routing"></a><span data-ttu-id="836fc-103">直接ルーティングの正常性ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="836fc-103">Health Dashboard for Direct Routing</span></span>

<span data-ttu-id="836fc-104">直接ルーティングの正常性ダッシュボードでは、セッション ボーダー コントローラー (SBC) とダイレクト ルーティング インターフェイス間の接続を監視できます。</span><span class="sxs-lookup"><span data-stu-id="836fc-104">Health Dashboard for Direct Routing lets you monitor the connection between your Session Border Controller (SBC) and the Direct Routing interface.</span></span>  <span data-ttu-id="836fc-105">正常性ダッシュボードを使用すると、SBC、テレフォニー サービス、SBC とダイレクト ルーティング インターフェイス間のネットワーク パラメーターに関する情報を監視できます。</span><span class="sxs-lookup"><span data-stu-id="836fc-105">With Health Dashboard, you can monitor information about your SBC, the telephony service, and the network parameters between your SBC and the Direct Routing interface.</span></span> <span data-ttu-id="836fc-106">この情報は、通話をドロップした理由など、問題を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="836fc-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="836fc-107">たとえば、SBC の証明書の有効期限が切れている場合や、ネットワークに問題がある場合、SBC は通話の送信を停止する場合があります。</span><span class="sxs-lookup"><span data-stu-id="836fc-107">For example, the SBC might stop sending calls if a certificate on the SBC has expired or if there are network issues.</span></span> <span data-ttu-id="836fc-108">正常性ダッシュボード [にアクセスできる](using-admin-roles.md) ユーザーについては、管理者の役割を参照してください。</span><span class="sxs-lookup"><span data-stu-id="836fc-108">See the [admin roles](using-admin-roles.md) to learn who has access to the health dashboard.</span></span>

<span data-ttu-id="836fc-109">正常性ダッシュボードは、次の 2 つのレベルの情報を監視します。</span><span class="sxs-lookup"><span data-stu-id="836fc-109">Health Dashboard monitors two levels of information:</span></span>

- <span data-ttu-id="836fc-110">接続されている SPC の全体的な正常性</span><span class="sxs-lookup"><span data-stu-id="836fc-110">Overall health of the connected SBCs</span></span>
- <span data-ttu-id="836fc-111">接続されている SPC に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="836fc-111">Detailed information about the connected SBCs</span></span>

<span data-ttu-id="836fc-112">Microsoft Teams と Skype for Business 管理センターで正常性ダッシュボードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="836fc-112">You can view Health Dashboard in the Microsoft Teams and Skype for Business Admin Center.</span></span>

## <a name="overall-health"></a><span data-ttu-id="836fc-113">全体的な正常性</span><span class="sxs-lookup"><span data-stu-id="836fc-113">Overall health</span></span>

<span data-ttu-id="836fc-114">正常性ダッシュボードには、接続されている SPC の全体的な正常性に関する次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="836fc-114">Health Dashboard provides the following information related to overall health of the connected SBCs:</span></span>

 ![正常性ダッシュボードの統計情報を表示する](media/direct-routing-dashboard-stats1.png)

- <span data-ttu-id="836fc-116">**ダイレクト ルーティングの概要** - システムに登録されている SPC の総数を示します。</span><span class="sxs-lookup"><span data-stu-id="836fc-116">**Direct Routing summary** - Shows the total number of SBCs registered in the system.</span></span> <span data-ttu-id="836fc-117">登録とは、テナント管理者がドメイン コマンドを使用して SBC を追加New-CsOnlinePSTNGateway意味します。</span><span class="sxs-lookup"><span data-stu-id="836fc-117">Registration means that the tenant administrator added an SBC by using the New-CsOnlinePSTNGateway command.</span></span> <span data-ttu-id="836fc-118">SBC が PowerShell で追加されたが、接続されていない場合、正常性ダッシュボードには、それが不健康な状態で表示されます。</span><span class="sxs-lookup"><span data-stu-id="836fc-118">If the SBC was added in PowerShell, but never connected, the Health Dashboard shows it in an unhealthy status.</span></span>

- <span data-ttu-id="836fc-119">**SBC** - ペアリングされた SBC の FQDN。</span><span class="sxs-lookup"><span data-stu-id="836fc-119">**SBC** - The FQDN of the paired SBC.</span></span>

- <span data-ttu-id="836fc-120">**Network Effectiveness Ratio (NER)** - NER は、ネットワークが通話を配信する機能を測定します。この測定は、送信された通話数と受信者に配信された通話の数を測定します。</span><span class="sxs-lookup"><span data-stu-id="836fc-120">**Network Effectiveness Ratio (NER)** - The NER measures the ability of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>  

   <span data-ttu-id="836fc-121">NER は、呼び出しが拒否される、遠端のターミナルを除くユーザーアクションに通話を配信するネットワークの機能を測定します。</span><span class="sxs-lookup"><span data-stu-id="836fc-121">The NER measures the ability of networks to deliver calls to the far-end terminal--excluding user actions resulting in call rejections.</span></span>  <span data-ttu-id="836fc-122">受信者が通話を拒否した場合、または通話をボイスメールに送信した場合、通話は正常に配信されたとカウントされます。</span><span class="sxs-lookup"><span data-stu-id="836fc-122">If the recipient rejected a call or sent the call to voicemail, the call is counted as a successful delivery.</span></span> <span data-ttu-id="836fc-123">つまり、応答メッセージ、取り込み中の信号、または応答がないリングはすべて正常な呼び出しと見なされます。</span><span class="sxs-lookup"><span data-stu-id="836fc-123">This means that an answer message, a busy signal, or a ring with no answer are all considered successful calls.</span></span>
  
   <span data-ttu-id="836fc-124">たとえば、ダイレクト ルーティングが SBC に通話を送信し、SBC が SIP コード "504 Server Time-out - サーバーが要求を処理しようとして別のサーバーにアクセスしようとし、プロンプト応答を受信しなかった" とします。</span><span class="sxs-lookup"><span data-stu-id="836fc-124">For example, assume Direct Routing sent a call to the SBC and the SBC returns SIP code “504 Server Time-out - The server attempted to access another server in attempting to process the request and did not receive a prompt response”.</span></span> <span data-ttu-id="836fc-125">この回答は、SBC 側に問題が発生し、これによりこの SBC の正常性ダッシュボードの NER が減ります。</span><span class="sxs-lookup"><span data-stu-id="836fc-125">This response indicates there is an issue on the SBC side, and this will decrease the NER on the Health Dashboard for this SBC.</span></span>
  
   <span data-ttu-id="836fc-126">実行するアクションは、影響を受ける呼び出しの数によって異なる場合があります。正常性ダッシュボードには、パラメーターを計算するために分析された呼び出しの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="836fc-126">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span> <span data-ttu-id="836fc-127">呼び出し数が 100 未満の場合、NER は非常に低い可能性がありますが、それでも正常です。</span><span class="sxs-lookup"><span data-stu-id="836fc-127">If the number of calls is less than 100, the NER might be quite low, but still be normal.</span></span>

   <span data-ttu-id="836fc-128">NER の計算に使用される数式は次の数式で表されます。</span><span class="sxs-lookup"><span data-stu-id="836fc-128">The formula used to calculate NER is:</span></span>

   <span data-ttu-id="836fc-129">NER = 100 x (応答された通話 + ユーザー取り込み + 呼び出しなし + ターミナル拒否の発作)/合計通話</span><span class="sxs-lookup"><span data-stu-id="836fc-129">NER = 100 x (Answered calls + User Busy + Ring no Answer + Terminal Reject Seizures)/Total Calls</span></span>

- <span data-ttu-id="836fc-130">**平均通話時間** - 平均通話時間に関する情報は、通話の品質を監視するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="836fc-130">**Average call duration** - Information about average call duration can help you monitor the quality of calls.</span></span> <span data-ttu-id="836fc-131">1 対 1 の PSTN 通話の平均デュレーションは 4 ~ 5 分です。</span><span class="sxs-lookup"><span data-stu-id="836fc-131">The average duration of a 1:1 PSTN call is four to five minutes.</span></span>  <span data-ttu-id="836fc-132">ただし、企業ごとに、この平均は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="836fc-132">However, for each company, this average can differ.</span></span>  <span data-ttu-id="836fc-133">Microsoft では、会社の平均通話時間の基準計画を確立する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="836fc-133">Microsoft recommends establishing a baseline for the average call duration for your company.</span></span> <span data-ttu-id="836fc-134">このパラメーターが基準値を大幅に下回る場合は、ユーザーが通話の品質や信頼性に問題を起こして、通常より早くハングアップしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="836fc-134">If this parameter goes significantly below the baseline, it might indicate that your users are having issues with call quality or reliability and are hanging up earlier than usual.</span></span> <span data-ttu-id="836fc-135">平均通話時間が非常に低い (15 秒など) と表示される場合、サービスが確実に実行されていないため、発信者が電話を切っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="836fc-135">If you start seeing extremely low average call duration, for example 15 seconds, callers might be hanging up because your service is not performing reliably.</span></span>

   <span data-ttu-id="836fc-136">実行するアクションは、影響を受ける呼び出しの数によって異なる場合があります。正常性ダッシュボードには、パラメーターを計算するために分析された呼び出しの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="836fc-136">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span>

- <span data-ttu-id="836fc-137">**TLS 接続状態** - TLS (トランスポート層セキュリティ) 接続は、ダイレクト ルーティングと SBC の間の TLS 接続の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="836fc-137">**TLS connectivity status** - TLS (Transport Layer Security) connectivity shows the status of the TLS connections between Direct Routing and the SBC.</span></span> <span data-ttu-id="836fc-138">正常性ダッシュボードでは、証明書の有効期限も分析され、証明書が 30 日以内に期限切れに設定されている場合に警告が表示され、サービスが中断される前に管理者が証明書を更新できます。</span><span class="sxs-lookup"><span data-stu-id="836fc-138">Health Dashboard also analyzes the certificate expiration date and warns if a certificate is set to expire within 30 days so that administrators can renew the certificate before service is disrupted.</span></span>

   <span data-ttu-id="836fc-139">警告メッセージをクリックすると、右側のポップアップ ウィンドウに問題の詳細な説明と、問題の修正方法に関する推奨事項を確認できます。</span><span class="sxs-lookup"><span data-stu-id="836fc-139">By clicking the Warning message, you can see a detailed issue description in a popup window on the right and recommendations for how to fix the issue.</span></span>

- <span data-ttu-id="836fc-140">**SIP オプションの状態** – 既定では、SBC はオプション メッセージを 1 分ごとに送信します。</span><span class="sxs-lookup"><span data-stu-id="836fc-140">**SIP options status** – By default, the SBC sends options messages every minute.</span></span> <span data-ttu-id="836fc-141">この構成は、SBC ベンダーによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="836fc-141">This configuration can vary for different SBC vendors.</span></span> <span data-ttu-id="836fc-142">直接ルーティングは、SIP オプションが送信されていないか、構成されていない場合に警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="836fc-142">Direct Routing warns if the SIP options are not sent or are not configured.</span></span> <span data-ttu-id="836fc-143">SIP オプションの監視と、SBC を機能していないとマークできる状態の詳細については、「ダイレクト ルーティングの監視とトラブルシューティング」を [参照してください](direct-routing-monitor-and-troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="836fc-143">For more information about SIP options monitoring, and conditions when an SBC can be marked as not functional, see [Monitor and troubleshoot Direct Routing](direct-routing-monitor-and-troubleshoot.md).</span></span>

- <span data-ttu-id="836fc-144">**詳細な SIP オプション** の状態 - SIP オプション フローに問題がある場合に加えて、正常性ダッシュボードには、エラーの詳細な説明も表示されます。</span><span class="sxs-lookup"><span data-stu-id="836fc-144">**Detailed SIP options status** - In addition to showing that there is an issue with SIP options flow, the Health Dashboard also provides detailed descriptions of the errors.</span></span> <span data-ttu-id="836fc-145">説明にアクセスするには、"警告" メッセージをクリックします。</span><span class="sxs-lookup"><span data-stu-id="836fc-145">You can access the description by clicking the “Warning” message.</span></span> <span data-ttu-id="836fc-146">右側にポップアップ ウィンドウが表示され、詳細なエラーの説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="836fc-146">A pop-up window on the right will show the detailed error description.</span></span>

   <span data-ttu-id="836fc-147">SIP オプションのステータス メッセージに使用できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="836fc-147">Possible values for SIP options status messages are as follows:</span></span>

    - <span data-ttu-id="836fc-148">アクティブ – SBC はアクティブです。Microsoft ダイレクト ルーティング サービスは、一定の間隔でオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="836fc-148">Active – The SBC is active--Microsoft Direct Routing service sees the options flowing on a regular interval.</span></span>

    - <span data-ttu-id="836fc-149">警告。SIP オプションはありません - セッション ボーダー コントローラーはデータベースに存在します (管理者が New-CsOnlinePSTNGateway コマンドを使用して作成しました)。</span><span class="sxs-lookup"><span data-stu-id="836fc-149">Warning, no SIP options - The Session Border Controller exists in the database (your administrator created it using the command New-CsOnlinePSTNGateway).</span></span> <span data-ttu-id="836fc-150">SIP オプションを送信するように構成されているが、ダイレクト ルーティング サービスでは、この SBC から戻ってくる SIP オプションを見たことがない。</span><span class="sxs-lookup"><span data-stu-id="836fc-150">It is configured to send SIP options, but the Direct Routing service never saw the SIP options coming back from this SBC.</span></span>

    - <span data-ttu-id="836fc-151">警告:SIP メッセージが構成されていない - SIP オプションを使用したトランク監視が有効ではない。</span><span class="sxs-lookup"><span data-stu-id="836fc-151">Warning, SIP Messages aren't configured - Trunk monitoring using SIP options isn’t turned on.</span></span> <span data-ttu-id="836fc-152">Microsoft 通話システムでは、SIP オプションとトランスポート層セキュリティ (TLS) ハンドシェイク監視を使用して、アプリケーション レベルで接続されているセッション ボーダー コントローラー (SPC) の正常性を検出します。</span><span class="sxs-lookup"><span data-stu-id="836fc-152">Microsoft Calling System uses SIP options and Transport Layer Security (TLS) handshake monitoring to detect the health of the connected Session Border Controllers (SBCs) at the application level.</span></span> <span data-ttu-id="836fc-153">このトランクがネットワーク レベル (ping) でアクセスできるが、証明書の有効期限が切れているか、SIP スタックが機能しない場合は、問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="836fc-153">You’ll have problems if this trunk can be reached at the network level (by ping), but the certificate has expired or the SIP stack doesn’t work.</span></span> <span data-ttu-id="836fc-154">このような問題を早期に特定するために、Microsoft は SIP オプションの送信を有効に設定します。</span><span class="sxs-lookup"><span data-stu-id="836fc-154">To help identify such problems early, Microsoft recommends enabling sending SIP options.</span></span> <span data-ttu-id="836fc-155">SBC 製造元のドキュメントを確認して、SIP の送信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="836fc-155">Check your SBC manufacturer documentation to configure sending SIP options.</span></span>

- <span data-ttu-id="836fc-156">**同時呼び** 出しの容量 - -MaxConcurrentSessions パラメーターで New または Set-CsOnlinePSTNGateway コマンドを使用して、SBC が処理できる同時呼び出しの制限を指定できます。</span><span class="sxs-lookup"><span data-stu-id="836fc-156">**Concurrent calls capacity** - You can specify the limit of concurrent calls that an SBC can handle by using the New- or Set-CsOnlinePSTNGateway command with the -MaxConcurrentSessions parameter.</span></span> <span data-ttu-id="836fc-157">このパラメーターは、特定の SBC を使用して直接ルーティングによって送信または受信された通話の数を計算し、制限セットと比較します。</span><span class="sxs-lookup"><span data-stu-id="836fc-157">This parameter calculates how many calls were sent or received by Direct Routing using a specific SBC and compares it with the limit set.</span></span> <span data-ttu-id="836fc-158">注: SBC が異なる PBX の呼び出しも処理する場合、この番号は実際の同時呼び出しを表示しません。</span><span class="sxs-lookup"><span data-stu-id="836fc-158">Note:  If the SBC also handles calls to different PBXs, this number will not show the actual concurrent calls.</span></span>

## <a name="detailed-information-for-each-sbc"></a><span data-ttu-id="836fc-159">各 SBC の詳細情報</span><span class="sxs-lookup"><span data-stu-id="836fc-159">Detailed information for each SBC</span></span>

<span data-ttu-id="836fc-160">次のスクリーンショットに示すように、特定の SBC の詳細情報を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="836fc-160">You can also view the detailed information for a specific SBC as shown in the following screenshot:</span></span>

![正常性ダッシュボード SBC の詳細](media/direct-routing-dashboard-SBC-detail1.png)

<span data-ttu-id="836fc-162">詳細なビューには、次の追加パラメーターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="836fc-162">The detailed view shows the following additional parameters:</span></span>

- <span data-ttu-id="836fc-163">**TLS 接続の状態** – これは[全体の正常性] ページと同じメトリックです。</span><span class="sxs-lookup"><span data-stu-id="836fc-163">**TLS Connectivity status** – this is the same metric as on the “Overall Health” page;</span></span>

- <span data-ttu-id="836fc-164">**TLS 接続の最後の状態** – SBC がダイレクト ルーティング サービスに TLS 接続を行った時刻を示します。</span><span class="sxs-lookup"><span data-stu-id="836fc-164">**TLS Connectivity last status** – shows time when the SBC made a TLS connection to the Direct Routing service;</span></span>

- <span data-ttu-id="836fc-165">**SIP オプションの状態** – [全体の正常性] ページと同じメトリック。</span><span class="sxs-lookup"><span data-stu-id="836fc-165">**SIP options status** – the same metric as on the “Overall Health” page.</span></span>

- <span data-ttu-id="836fc-166">**最後にチェックされた SIP オプション** – 前回 SIP オプションを受信した時刻。</span><span class="sxs-lookup"><span data-stu-id="836fc-166">**SIP options last checked** – time when the SIP options were received last time.</span></span>

- <span data-ttu-id="836fc-167">**SBC ステータス** – 監視対象のすべてのパラメーターに基づく、SBC の全体的な状態。</span><span class="sxs-lookup"><span data-stu-id="836fc-167">**SBC status** – overall status of the SBC, based on all monitored parameters.</span></span>

- <span data-ttu-id="836fc-168">**同時呼び出** し - SBC が処理した同時呼び出しの数を示します。</span><span class="sxs-lookup"><span data-stu-id="836fc-168">**Concurrent call**- shows  how many concurrent calls the SBC handled.</span></span> <span data-ttu-id="836fc-169">この情報は、必要な同時チャネルの数を予測し、傾向を確認する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="836fc-169">This information is useful to predict the number of concurrent channels you need and see the trend.</span></span> <span data-ttu-id="836fc-170">日数と通話の方向 (受信/送信/すべてのストリーム) でデータをスライドできます。</span><span class="sxs-lookup"><span data-stu-id="836fc-170">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

- <span data-ttu-id="836fc-171">**ネットワーク パラメーター** - すべてのネットワーク パラメーターは、直接ルーティング インターフェイスからセッション ボーダー コントローラーに測定されます。</span><span class="sxs-lookup"><span data-stu-id="836fc-171">**Network parameters** - All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="836fc-172">推奨される値の詳細については、「組織のネットワークを [Microsoft Teams](./prepare-network.md)用に準備する」を参照し、カスタマー エッジから Microsoft Edge への推奨値を参照してください。</span><span class="sxs-lookup"><span data-stu-id="836fc-172">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](./prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

   - <span data-ttu-id="836fc-173">Jitter – RTCP (RTP コントロール プロトコル) を使用して 2 つのエンドポイント間で計算されるネットワーク伝達遅延時間の変化のミリ秒単位の測定です。</span><span class="sxs-lookup"><span data-stu-id="836fc-173">Jitter – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

   - <span data-ttu-id="836fc-174">[パケット損失] - パケットの受信に失敗したメジャーです。2 つのエンドポイント間で計算されます。</span><span class="sxs-lookup"><span data-stu-id="836fc-174">Packet Loss – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

   - <span data-ttu-id="836fc-175">遅延 - (ラウンドトリップ時間とも呼ばれる) は、信号が送信される時間の長さと、その信号の確認応答が受信されるのにかかる時間の長さです。</span><span class="sxs-lookup"><span data-stu-id="836fc-175">Latency - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="836fc-176">この時間遅延は、信号の 2 点間の伝達時間で構成されます。</span><span class="sxs-lookup"><span data-stu-id="836fc-176">This time delay consists of the propagation times between the two points of a signal.</span></span>

   <span data-ttu-id="836fc-177">日数と通話の方向 (受信/送信/すべてのストリーム) でデータをスライドできます。</span><span class="sxs-lookup"><span data-stu-id="836fc-177">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

<span data-ttu-id="836fc-178">**ネットワークの有効性** の比率 - これは、全体的な正常性ダッシュボードに表示されるパラメーターと同じですが、時系列または通話方向でデータをスライスするオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="836fc-178">**Network Effectiveness ratio** - This is the same parameter that appears on the Overall Health dashboard, but with the option to slice the data by time series or call direction.</span></span>