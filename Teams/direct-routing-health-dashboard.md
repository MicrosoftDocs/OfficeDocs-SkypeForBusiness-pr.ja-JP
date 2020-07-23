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
description: 正常性ダッシュボードを使って、セッションの境界コントローラーとダイレクトルーティングの間の接続を監視する方法について説明します。
ms.openlocfilehash: a75510340815489921a5dd67a204b6914a9539d4
ms.sourcegitcommit: 863347fb6e5916d8d936adc4ddcebb2e32a91d1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "45229113"
---
# <a name="health-dashboard-for-direct-routing"></a><span data-ttu-id="f4f88-103">直接ルーティングの正常性ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="f4f88-103">Health Dashboard for Direct Routing</span></span>

<span data-ttu-id="f4f88-104">直接ルーティング用の正常性ダッシュボードでは、セッション境界コントローラー (SBC) とダイレクトルーティングインターフェイスの間の接続を監視できます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-104">Health Dashboard for Direct Routing lets you monitor the connection between your Session Border Controller (SBC) and the Direct Routing interface.</span></span>  <span data-ttu-id="f4f88-105">正常性ダッシュボードでは、SBC、テレフォニーサービス、および SBC とダイレクトルーティングインターフェイス間のネットワークパラメーターに関する情報を監視できます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-105">With Health Dashboard, you can monitor information about your SBC, the telephony service, and the network parameters between your SBC and the Direct Routing interface.</span></span> <span data-ttu-id="f4f88-106">この情報は、通話の中断の理由など、問題を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="f4f88-107">たとえば、sbc の証明書の有効期限が切れた場合、またはネットワークの問題が発生した場合、SBC は通話の送信を停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4f88-107">For example, the SBC might stop sending calls if a certificate on the SBC has expired or if there are network issues.</span></span> <span data-ttu-id="f4f88-108">正常性ダッシュボードへのアクセス権があるユーザーを確認するには、[管理者ロール](using-admin-roles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4f88-108">See the [admin roles](using-admin-roles.md) to learn who has access to the health dashboard.</span></span>

<span data-ttu-id="f4f88-109">正常性ダッシュボードは、次の2つのレベルの情報を監視します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-109">Health Dashboard monitors two levels of information:</span></span>

- <span data-ttu-id="f4f88-110">接続された SBCs の全体的な正常性</span><span class="sxs-lookup"><span data-stu-id="f4f88-110">Overall health of the connected SBCs</span></span>
- <span data-ttu-id="f4f88-111">接続された SBCs に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="f4f88-111">Detailed information about the connected SBCs</span></span>

<span data-ttu-id="f4f88-112">正常性ダッシュボードは、Microsoft Teams および Skype for Business 管理センターで表示できます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-112">You can view Health Dashboard in the Microsoft Teams and Skype for Business Admin Center.</span></span>

## <a name="overall-health"></a><span data-ttu-id="f4f88-113">全体的な正常性</span><span class="sxs-lookup"><span data-stu-id="f4f88-113">Overall health</span></span>

<span data-ttu-id="f4f88-114">正常性ダッシュボードは、接続されている SBCs の全体的な正常性に関する次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-114">Health Dashboard provides the following information related to overall health of the connected SBCs:</span></span>

 ![正常性ダッシュボードの統計情報を表示します](media/direct-routing-dashboard-stats1.png)

- <span data-ttu-id="f4f88-116">[ **Direct Routing summary** ]-システムに登録されている SBCs の合計数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-116">**Direct Routing summary** - Shows the total number of SBCs registered in the system.</span></span> <span data-ttu-id="f4f88-117">登録とは、テナント管理者が CsOnlinePSTNGateway コマンドを使用して SBC を追加したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-117">Registration means that the tenant administrator added an SBC by using the New-CsOnlinePSTNGateway command.</span></span> <span data-ttu-id="f4f88-118">SBC が PowerShell で追加されているが、接続していない場合、正常性ダッシュボードは問題のある状態であることを示します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-118">If the SBC was added in PowerShell, but never connected, the Health Dashboard shows it in an unhealthy status.</span></span>

- <span data-ttu-id="f4f88-119">**Sbc** -組み合わせた SBC の FQDN。</span><span class="sxs-lookup"><span data-stu-id="f4f88-119">**SBC** - The FQDN of the paired SBC.</span></span>

- <span data-ttu-id="f4f88-120">**ネットワークの有効性比 (** 技術者)-送信された通話の数と受信者に配信された通話の数を測定することで、ネットワークが通話を発信する能力を測定します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-120">**Network Effectiveness Ratio (NER)** - The NER measures the ability of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>  

   <span data-ttu-id="f4f88-121">この技術では、お客様の反対側の端末への通話発信が可能であることを測定します。その結果、通話拒否が発生します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-121">The NER measures the ability of networks to deliver calls to the far-end terminal--excluding user actions resulting in call rejections.</span></span>  <span data-ttu-id="f4f88-122">受信者が通話を拒否した場合、またはボイスメールに着信した場合、通話は正常に送信されます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-122">If the recipient rejected a call or sent the call to voicemail, the call is counted as a successful delivery.</span></span> <span data-ttu-id="f4f88-123">これは、応答メッセージ、ビジー信号、または応答のないリングはすべて成功したと見なされることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-123">This means that an answer message, a busy signal, or a ring with no answer are all considered successful calls.</span></span>
  
   <span data-ttu-id="f4f88-124">たとえば、直接ルーティングによって SBC への通話が送信されたとして、SBC が SIP コード "504 サーバーのタイムアウト-サーバーから別のサーバーにアクセスしようとしたときに、要求を処理しようとしましたが、プロンプト応答を受信しなかったとします。</span><span class="sxs-lookup"><span data-stu-id="f4f88-124">For example, assume Direct Routing sent a call to the SBC and the SBC returns SIP code “504 Server Time-out - The server attempted to access another server in attempting to process the request and did not receive a prompt response”.</span></span> <span data-ttu-id="f4f88-125">この応答は、SBC 側に問題があることを示します。これにより、この SBC の正常性ダッシュボードの原因が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="f4f88-125">This response indicates there is an issue on the SBC side, and this will decrease the NER on the Health Dashboard for this SBC.</span></span>
  
   <span data-ttu-id="f4f88-126">実行する操作は、影響を受ける電話の回数によって異なるため、正常性ダッシュボードは、パラメーターを計算するために分析された通話の数を示します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-126">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span> <span data-ttu-id="f4f88-127">通話の数が100よりも小さい場合は、その可能性は非常に低く、通常どおり発生します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-127">If the number of calls is less than 100, the NER might be quite low, but still be normal.</span></span>

   <span data-ttu-id="f4f88-128">この計算式は、次の数式で計算されます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-128">The formula used to calculate NER is:</span></span>

   <span data-ttu-id="f4f88-129">解説 = 100 x (回答された通話 + ユーザーの取り込み中 + Ring Answer + ターミナル拒否発作)/通話合計</span><span class="sxs-lookup"><span data-stu-id="f4f88-129">NER = 100 x (Answered calls + User Busy + Ring no Answer + Terminal Reject Seizures)/Total Calls</span></span>

- <span data-ttu-id="f4f88-130">**平均通話時間**-平均通話時間に関する情報は、通話の品質を監視するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-130">**Average call duration** - Information about average call duration can help you monitor the quality of calls.</span></span> <span data-ttu-id="f4f88-131">1:1 PSTN 通話の平均時間は、4 ~ 5 分です。</span><span class="sxs-lookup"><span data-stu-id="f4f88-131">The average duration of a 1:1 PSTN call is four to five minutes.</span></span>  <span data-ttu-id="f4f88-132">ただし、会社ごとに、この平均は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4f88-132">However, for each company, this average can differ.</span></span>  <span data-ttu-id="f4f88-133">Microsoft は、会社の平均通話時間のベースラインを確立することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f4f88-133">Microsoft recommends establishing a baseline for the average call duration for your company.</span></span> <span data-ttu-id="f4f88-134">このパラメーターがベースラインより大きくなっている場合は、ユーザーが通話品質または信頼性に問題があり、通常よりも早く切断されていることを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4f88-134">If this parameter goes significantly below the baseline, it might indicate that your users are having issues with call quality or reliability and are hanging up earlier than usual.</span></span> <span data-ttu-id="f4f88-135">わずかな平均通話時間 (たとえば15秒) が表示されると、サービスが確実に動作していないために、発信者が停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4f88-135">If you start seeing extremely low average call duration, for example 15 seconds, callers might be hanging up because your service is not performing reliably.</span></span>

   <span data-ttu-id="f4f88-136">実行する操作は、影響を受ける電話の回数によって異なるため、正常性ダッシュボードは、パラメーターを計算するために分析された通話の数を示します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-136">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span>

- <span data-ttu-id="f4f88-137">**Tls 接続状態**-Tls (トランスポート層セキュリティ) 接続は、直接ルーティングと SBC の間の TLS 接続の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-137">**TLS connectivity status** - TLS (Transport Layer Security) connectivity shows the status of the TLS connections between Direct Routing and the SBC.</span></span> <span data-ttu-id="f4f88-138">また、正常性ダッシュボードでは、証明書の有効期限が30日以内に期限切れになるように設定されている場合に警告が表示され、サービスが中断される前に証明書を更新できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f4f88-138">Health Dashboard also analyzes the certificate expiration date and warns if a certificate is set to expire within 30 days so that administrators can renew the certificate before service is disrupted.</span></span>

   <span data-ttu-id="f4f88-139">警告メッセージをクリックすると、右側のポップアップウィンドウに詳細な問題の説明が表示され、問題の修正方法についての推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-139">By clicking the Warning message, you can see a detailed issue description in a popup window on the right and recommendations for how to fix the issue.</span></span>

- <span data-ttu-id="f4f88-140">**SIP オプションのステータス**: 既定では、SBC はオプションメッセージを1分間隔で送信します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-140">**SIP options status** – By default, the SBC sends options messages every minute.</span></span> <span data-ttu-id="f4f88-141">この構成は、さまざまな SBC ベンダーによって異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4f88-141">This configuration can vary for different SBC vendors.</span></span> <span data-ttu-id="f4f88-142">SIP オプションが送信されない、または構成されていない場合は、ダイレクトルーティングの警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-142">Direct Routing warns if the SIP options are not sent or are not configured.</span></span> <span data-ttu-id="f4f88-143">SIP オプションの監視と、SBC を機能しないとマークされた場合の条件の詳細については、「[直接ルーティングを監視してトラブルシューティング](direct-routing-monitor-and-troubleshoot.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4f88-143">For more information about SIP options monitoring, and conditions when an SBC can be marked as not functional, see [Monitor and troubleshoot Direct Routing](direct-routing-monitor-and-troubleshoot.md).</span></span>

- <span data-ttu-id="f4f88-144">**Sip オプションの詳細状態**-sip オプションのフローに問題があることを示すだけでなく、正常性ダッシュボードでもエラーの詳細な説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-144">**Detailed SIP options status** - In addition to showing that there is an issue with SIP options flow, the Health Dashboard also provides detailed descriptions of the errors.</span></span> <span data-ttu-id="f4f88-145">「警告」メッセージをクリックして、説明にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-145">You can access the description by clicking the “Warning” message.</span></span> <span data-ttu-id="f4f88-146">右側のポップアップウィンドウには、詳細なエラーの説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-146">A pop-up window on the right will show the detailed error description.</span></span>

   <span data-ttu-id="f4f88-147">SIP オプションのステータスメッセージの可能な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f4f88-147">Possible values for SIP options status messages are as follows:</span></span>

    - <span data-ttu-id="f4f88-148">アクティブ– SBC は active--Microsoft ダイレクトルーティングサービスは、定期的に表示されるオプションを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-148">Active – The SBC is active--Microsoft Direct Routing service sees the options flowing on a regular interval.</span></span>

    - <span data-ttu-id="f4f88-149">警告、SIP オプションはありません。セッションボーダーコントローラーはデータベース内に存在します (管理者が、command New-CsOnlinePSTNGateway を使用して作成した)。</span><span class="sxs-lookup"><span data-stu-id="f4f88-149">Warning, no SIP options - The Session Border Controller exists in the database (your administrator created it using the command New-CsOnlinePSTNGateway).</span></span> <span data-ttu-id="f4f88-150">SIP オプションを送信するように構成されていますが、この SBC から返される SIP オプションは、直接ルーティングサービスには表示されません。</span><span class="sxs-lookup"><span data-stu-id="f4f88-150">It is configured to send SIP options, but the Direct Routing service never saw the SIP options coming back from this SBC.</span></span>

    - <span data-ttu-id="f4f88-151">警告、SIP メッセージが構成されていません-SIP オプションを使用したトランク監視は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="f4f88-151">Warning, SIP Messages aren't configured - Trunk monitoring using SIP options isn’t turned on.</span></span> <span data-ttu-id="f4f88-152">Microsoft 通話システムでは、SIP オプションとトランスポート層セキュリティ (TLS) ハンドシェイク監視を使用して、接続されているセッション境界コントローラー (SBCs) の正常性をアプリケーションレベルで検出します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-152">Microsoft Calling System uses SIP options and Transport Layer Security (TLS) handshake monitoring to detect the health of the connected Session Border Controllers (SBCs) at the application level.</span></span> <span data-ttu-id="f4f88-153">このトランクがネットワークレベル (ping) で到達しても、証明書の有効期限が切れた、または SIP スタックが機能しない場合、問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-153">You’ll have problems if this trunk can be reached at the network level (by ping), but the certificate has expired or the SIP stack doesn’t work.</span></span> <span data-ttu-id="f4f88-154">早期にこのような問題を特定するために、SIP オプションの送信を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f4f88-154">To help identify such problems early, Microsoft recommends enabling sending SIP options.</span></span> <span data-ttu-id="f4f88-155">お客様の SBC メーカーのマニュアルを確認して、SIP の送信オプションを設定してください。</span><span class="sxs-lookup"><span data-stu-id="f4f88-155">Check your SBC manufacturer documentation to configure sending SIP options.</span></span>

- <span data-ttu-id="f4f88-156">**同時通話容量**-MaxConcurrentSessions パラメーターを指定して、新しい-CsOnlinePSTNGateway コマンドを使用して、SBC が処理できる同時呼び出しの制限を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-156">**Concurrent calls capacity** - You can specify the limit of concurrent calls that an SBC can handle by using the New- or Set-CsOnlinePSTNGateway command with the -MaxConcurrentSessions parameter.</span></span> <span data-ttu-id="f4f88-157">このパラメーターは、特定の SBC を使って直接ルーティングによって送受信された通話の数を計算し、それを制限セットと比較します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-157">This parameter calculates how many calls were sent or received by Direct Routing using a specific SBC and compares it with the limit set.</span></span> <span data-ttu-id="f4f88-158">注: SBC では、異なる Pbx への通話も処理しますが、この番号には、実際の同時呼び出しは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f4f88-158">Note:  If the SBC also handles calls to different PBXs, this number will not show the actual concurrent calls.</span></span>

## <a name="detailed-information-for-each-sbc"></a><span data-ttu-id="f4f88-159">各 SBC の詳細情報</span><span class="sxs-lookup"><span data-stu-id="f4f88-159">Detailed information for each SBC</span></span>

<span data-ttu-id="f4f88-160">次のスクリーンショットに示すように、特定の SBC の詳細情報を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-160">You can also view the detailed information for a specific SBC as shown in the following screenshot:</span></span>

![正常性ダッシュボードの SBC の詳細](media/direct-routing-dashboard-SBC-detail1.png)

<span data-ttu-id="f4f88-162">詳細ビューには、次の追加パラメーターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-162">The detailed view shows the following additional parameters:</span></span>

- <span data-ttu-id="f4f88-163">**TLS 接続状態**–これは、"全体的な正常性" ページと同じメトリックです。</span><span class="sxs-lookup"><span data-stu-id="f4f88-163">**TLS Connectivity status** – this is the same metric as on the “Overall Health” page;</span></span>

- <span data-ttu-id="f4f88-164">**TLS 接続の前回の状態**– SBC がダイレクトルーティングサービスに TLS 接続した時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-164">**TLS Connectivity last status** – shows time when the SBC made a TLS connection to the Direct Routing service;</span></span>

- <span data-ttu-id="f4f88-165">**SIP オプションのステータス**: 「全体的な正常性」ページと同じメトリック。</span><span class="sxs-lookup"><span data-stu-id="f4f88-165">**SIP options status** – the same metric as on the “Overall Health” page.</span></span>

- <span data-ttu-id="f4f88-166">**Sip オプションは最後にチェック**されました。 sip オプションを前回受信した時刻。</span><span class="sxs-lookup"><span data-stu-id="f4f88-166">**SIP options last checked** – time when the SIP options were received last time.</span></span>

- <span data-ttu-id="f4f88-167">**Sbc 状態**–すべての監視対象パラメーターに基づいて、sbc の全体的な状態です。</span><span class="sxs-lookup"><span data-stu-id="f4f88-167">**SBC status** – overall status of the SBC, based on all monitored parameters.</span></span>

- <span data-ttu-id="f4f88-168">**同時通話**-SBC が処理した同時呼び出しの数を示します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-168">**Concurrent call**- shows  how many concurrent calls the SBC handled.</span></span> <span data-ttu-id="f4f88-169">この情報は、必要な同時チャネルの数を予測し、トレンドを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-169">This information is useful to predict the number of concurrent channels you need and see the trend.</span></span> <span data-ttu-id="f4f88-170">データは、日数と通話方向 (受信/送信/すべてのストリーム) でスライドできます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-170">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

- <span data-ttu-id="f4f88-171">**ネットワークパラメーター** -すべてのネットワークパラメーターは、ダイレクトルーティングインターフェイスからセッション境界コントローラーに測定されます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-171">**Network parameters** - All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="f4f88-172">推奨値の詳細については、「 [Microsoft Teams 用に組織のネットワークを準備](https://docs.microsoft.com/microsoftteams/prepare-network)する」を参照してください。顧客の Edge を microsoft Edge で推奨される値について確認します。</span><span class="sxs-lookup"><span data-stu-id="f4f88-172">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

   - <span data-ttu-id="f4f88-173">ジッター– RTCP (RTP 制御プロトコル) を使って2つのエンドポイントの間で計算されたネットワーク伝達遅延時間の単位 (ミリ秒) です。</span><span class="sxs-lookup"><span data-stu-id="f4f88-173">Jitter – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

   - <span data-ttu-id="f4f88-174">パケット損失–到着に失敗したパケットの測定。これは、2つのエンドポイントの間で計算されます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-174">Packet Loss – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

   - <span data-ttu-id="f4f88-175">待ち時間-(ラウンドトリップ時間とも呼ばれます) は、シグナルが送信されるまでにかかる時間と、そのシグナルの受信確認にかかる時間の長さです。</span><span class="sxs-lookup"><span data-stu-id="f4f88-175">Latency - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="f4f88-176">この時間遅延は、シグナルの2つのポイント間の伝播時間で構成されます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-176">This time delay consists of the propagation times between the two points of a signal.</span></span>

   <span data-ttu-id="f4f88-177">データは、日数と通話方向 (受信/送信/すべてのストリーム) でスライドできます。</span><span class="sxs-lookup"><span data-stu-id="f4f88-177">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

<span data-ttu-id="f4f88-178">[**ネットワークの有効性率**]-これは、全体的な正常性ダッシュボードに表示されるのと同じパラメーターであり、時系列または通話の方向でデータをスライスするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="f4f88-178">**Network Effectiveness ratio** - This is the same parameter that appears on the Overall Health dashboard, but with the option to slice the data by time series or call direction.</span></span>
