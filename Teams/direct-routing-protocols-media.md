---
title: 電話システムのダイレクト ルーティング
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
description: ダイレクトルーティングプロトコル
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08b022799b2c8bf80ee30cbb0a5ef3e74f0a29e1
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065667"
---
# <a name="overview"></a><span data-ttu-id="963a6-103">概要</span><span class="sxs-lookup"><span data-stu-id="963a6-103">Overview</span></span>

<span data-ttu-id="963a6-104">この記事では、 [RFC 5245](https://tools.ietf.org/html/rfc5245)で説明されているように、ダイレクトルーティングが氷用に有効になっているセッションボーダーコントローラー (SBC) でメディアバイパスをサポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="963a6-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="963a6-105">この記事は、オンプレミスの SBC と SIP プロキシサービス間の接続を構成する責任を負うボイス管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="963a6-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="963a6-106">この記事では、ICE Lite のシナリオと相互運用性の要件の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="963a6-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="963a6-107">この記事では、信頼性の高い通話とメディアフローを実現するために、メッセージ形式と必要なステートマシンの移行について説明します。</span><span class="sxs-lookup"><span data-stu-id="963a6-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="963a6-108">用語</span><span class="sxs-lookup"><span data-stu-id="963a6-108">Terminology</span></span>

- <span data-ttu-id="963a6-109">最初の Hello: 発信者と呼び出し先が最初に発声した単語。</span><span class="sxs-lookup"><span data-stu-id="963a6-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="963a6-110">エンドポイントからの最初のパケットがほとんどのユースケースで確実に配信されるように、すべての取り組みを行っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="963a6-111">フォーク–発信者からのオファーが複数のデバイスで使用できる場合 (たとえば、チームユーザーが Windows 用の Teams や Android または iPhone のチームにサインインしている場合など)、複数の呼び出し元のエンドポイントに配信されることがあります。</span><span class="sxs-lookup"><span data-stu-id="963a6-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="963a6-112">仮応答 (183) –通話を高速化するための呼び出し先エンドポイントメディアフローを確立するために必要な候補とキーを使って応答を送信します。</span><span class="sxs-lookup"><span data-stu-id="963a6-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="963a6-113">これは、ユーザーが特定の呼び出し元インスタンスから呼び出し (200OK) に応答する可能性があることを想定して行われます。</span><span class="sxs-lookup"><span data-stu-id="963a6-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="963a6-114">Fork では、呼び出し元が複数の仮応答を受け取る準備ができている必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="963a6-115">再招待-ICE を制御するエンドポイントによって最終的な候補が選択された申し出。</span><span class="sxs-lookup"><span data-stu-id="963a6-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="963a6-116">これには、a = リモート候補の属性があります。これにより、競合状態を解決して複数のフォークを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="963a6-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="963a6-117">Teams エンドポイント–これは、サーバー (メディアプロセッサ、トランスポートリレー)、または Teams クライアントのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="963a6-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="963a6-118">メッセージ形式</span><span class="sxs-lookup"><span data-stu-id="963a6-118">Message format</span></span>

<span data-ttu-id="963a6-119">Teams インフラストラクチャは、ICE-Lite の RFC 5245 に従います。</span><span class="sxs-lookup"><span data-stu-id="963a6-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="963a6-120">これは、すべての STUN メッセージが[RFC 5389](https://tools.ietf.org/html/rfc5389)に準拠していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="963a6-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="963a6-121">RFC 5389 が必要とする SBCs は、認識されないすべての STUN 属性を無視する必要があります。また、既知の属性を使ってメッセージを処理し続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="963a6-122">不正なパケットを受信した場合、メディアセッションの確立に影響を与えることなく、パケットを破棄する必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="963a6-123">ICE Lite の要件</span><span class="sxs-lookup"><span data-stu-id="963a6-123">ICE Lite requirements</span></span>

<span data-ttu-id="963a6-124">このセクションでは、ICE Lite の要件について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="963a6-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="963a6-125">候補の収集</span><span class="sxs-lookup"><span data-stu-id="963a6-125">Candidate gathering</span></span>

<span data-ttu-id="963a6-126">SBC は、公開可能な候補を1つだけ提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="963a6-127">現時点では、IPV4 の候補者のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="963a6-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="963a6-128">接続チェック</span><span class="sxs-lookup"><span data-stu-id="963a6-128">Connectivity checks</span></span>

<span data-ttu-id="963a6-129">ICE Lite の実装は、受け取った接続チェックに応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="963a6-130">ICE Lite エンドポイントは、接続チェック要求を送信しないでください。</span><span class="sxs-lookup"><span data-stu-id="963a6-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="963a6-131">(接続チェックが違反で送信された場合は、完全な実装が応答するため、予期しないピア派生候補が検出され、呼び出しの失敗が発生する可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="963a6-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="963a6-132">Nominations</span><span class="sxs-lookup"><span data-stu-id="963a6-132">Nominations</span></span>

<span data-ttu-id="963a6-133">ICE 完全実装のエンドポイントは、常に制御エンドポイントであり、メディアフローに使用する最終的な候補を選択するための "Regular" nominations に従います。</span><span class="sxs-lookup"><span data-stu-id="963a6-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="963a6-134">ICE Lite エンドポイントでは、nominations を使って、メディアと完全な通話の確立に使用されるパスを終了することができます。</span><span class="sxs-lookup"><span data-stu-id="963a6-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="963a6-135">注: ピアエンドポイントで183の仮応答を送信するようにフォークを行う場合、SBC は、複数のエンドポイントからのチェックに応答する準備ができていて、200 OK の前に nominations が発生した場合は、複数のエンドポイントから nominations する必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="963a6-136">ユーザーが応答する最終的なパスとタイミングでの ICE ステートマシンの収束に応じて、nominations は200OK の前または後に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="963a6-137">SBC は両方のケースを処理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="963a6-138">フォークのための収束</span><span class="sxs-lookup"><span data-stu-id="963a6-138">Converging for forking</span></span>

<span data-ttu-id="963a6-139">SBC のフォークから複数の Teams のエンドポイントに対して提供されている場合、チームのエンドポイントは、仮の応答に応答して接続チェックを開始することがあります。</span><span class="sxs-lookup"><span data-stu-id="963a6-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="963a6-140">SBC は、接続チェックを受け、複数のピアエンドポイントからの接続チェックに応答するために準備されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="963a6-141">たとえば、Teams ユーザーは、デスクトップと携帯電話の両方にサインインしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="963a6-142">両方のデバイスに着信通話の通知が送信され、SBC で接続チェックが試行されます。</span><span class="sxs-lookup"><span data-stu-id="963a6-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="963a6-143">最終的に、通話に応答するのはエンドポイントの1つだけです (200OK)。</span><span class="sxs-lookup"><span data-stu-id="963a6-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="963a6-144">200OK を受け取ると、SBC はメディアパケットを処理するための適切なコンテキストを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="963a6-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="963a6-145">シナリオ</span><span class="sxs-lookup"><span data-stu-id="963a6-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="963a6-146">SBC からの着信通話</span><span class="sxs-lookup"><span data-stu-id="963a6-146">Inbound call from SBC</span></span>

<span data-ttu-id="963a6-147">このシナリオでは、SBC が処理しなければならないピアエンドポイントがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="963a6-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="963a6-148">通常、サーバーのエンドポイントは、200OK で直接応答します。</span><span class="sxs-lookup"><span data-stu-id="963a6-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="963a6-149">通常、ボイスメール、通話キュー、自動応答のシナリオに関連する完全な ICE エンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="963a6-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="963a6-150">クライアントのエンドポイントでは、異なる "From/To タグ (183)" を使用して、通話に応答するエンドポイントからの 200 OK を使って、複数の仮応答を送信できます。</span><span class="sxs-lookup"><span data-stu-id="963a6-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="963a6-151">通常は、エンドユーザークライアントを示す完全な ICE エンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="963a6-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="963a6-152">その他の SBC エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="963a6-152">Other SBC endpoints.</span></span> <span data-ttu-id="963a6-153">これらは通常、クライアントエンドポイントと別の電話番号を同時に呼び出してしまうシナリオに関連する、ICE Lite エンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="963a6-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="963a6-154">SBC は、完全な氷エンドポイントから受け取った有効な接続確認要求すべてに応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="963a6-155">各 RFC では、完全な ICE エンドポイントがエンドポイントを制御します。</span><span class="sxs-lookup"><span data-stu-id="963a6-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="963a6-156">Teams (クライアント/サーバー) のエンドポイントは、接続チェックを完了するために "通常" の nominations を実行します。</span><span class="sxs-lookup"><span data-stu-id="963a6-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="963a6-157">最後の200Ok は、前のメディアを送信したエンドポイントか、別のエンドポイントからのどちらかになります。</span><span class="sxs-lookup"><span data-stu-id="963a6-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="963a6-158">200Ok の場合、SBC はメディアフローの適切なコンテキストを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="963a6-159">初期のメディア</span><span class="sxs-lookup"><span data-stu-id="963a6-159">Early media</span></span>

<span data-ttu-id="963a6-160">早いメディアフローが存在する場合、SBC は、ストリーミングメディアを開始する最初のエンドポイントにラッチする必要があります。メディアフローは、候補が指定される前に開始することができます。</span><span class="sxs-lookup"><span data-stu-id="963a6-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="963a6-161">このフェーズでは、IVR またはボイスメールシナリオを可能にするために DTMF の送信がサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="963a6-162">SBC では、nominations が完了していないかどうかを確認するために、最も優先度の高いパスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="963a6-163">SBC への発信通話</span><span class="sxs-lookup"><span data-stu-id="963a6-163">Outbound call to SBC</span></span>

<span data-ttu-id="963a6-164">Teams のエンドポイントはこのシナリオの呼び出し元であり、制御するエンドポイントになります。</span><span class="sxs-lookup"><span data-stu-id="963a6-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="963a6-165">仮応答 (183) または最終回答 (200OK) を受け取ると、Teams のエンドポイントで接続チェックが開始され、"通常" の nominations に進み、接続チェックが完了します。</span><span class="sxs-lookup"><span data-stu-id="963a6-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="963a6-166">注: SBC が暫定応答 (183) を送信する場合、SBC は、接続確認要求を受信する準備ができていて、nominations を完了する前に、SBC によって200OK が送信される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="963a6-167">200OK が受信される前にチェックまたは nominations が完了した場合、nominations は、200OK を受け取った後にもう一度実行されることはありません。</span><span class="sxs-lookup"><span data-stu-id="963a6-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="963a6-168">SBC は、183と200の間で ICE 候補、パスワード、および ufrag (ユーザー名フラグメント) を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="963a6-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="963a6-169">以前のメディアをサポートするために、SBC は、チームのエンドポイントによって nominations が完了する前であっても、受信した接続チェックに基づいて、最も優先度の高いメディアをピア氷候補にストリーミングすることができます。</span><span class="sxs-lookup"><span data-stu-id="963a6-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="963a6-170">SBC は、nominations が完了するまで、任意の候補者に対して Teams からメディアを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="963a6-171">候補が指定されると、SBC は、メディアパケットを送受信するために適切なコンテキストにリセットされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="963a6-172">SRTP のサポート要件</span><span class="sxs-lookup"><span data-stu-id="963a6-172">SRTP support requirements</span></span>

<span data-ttu-id="963a6-173">SBC は、次の形式の AES_CM_128_HMAC_SHA1_80 の特典と回答について、SRTP 暗号化暗号をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="963a6-174">SBC の SDP オファーの crypto 属性の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="963a6-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="963a6-175">MKI パラメーターと Length パラメーターは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="963a6-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="963a6-176">詳細については、「 [RFC 4568、セクション6.1」](https://tools.ietf.org/html/rfc4568#section-6.1)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="963a6-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="963a6-177">SDES のサポート要件</span><span class="sxs-lookup"><span data-stu-id="963a6-177">SDES support requirements</span></span>

<span data-ttu-id="963a6-178">デバイスは、以下で説明する形式で SDES を提供できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="963a6-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="963a6-179">Microsoft メディアプロセッサは、常に SDES を優先します。</span><span class="sxs-lookup"><span data-stu-id="963a6-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="963a6-180">メディア以外のバイパスの場合、クライアントが DTLS のみをサポートしている場合でも、メディアプロセッサは SDES に変換されます。</span><span class="sxs-lookup"><span data-stu-id="963a6-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="963a6-181">メディアバイパスの場合、クライアントが DTLS のみ (Google Chrome の今後の状態) である場合、ダイレクトルーティングはパスに MP を挿入します。これにより、メディアバイパスからメディア以外のバイパスへの呼び出しが変換されます。</span><span class="sxs-lookup"><span data-stu-id="963a6-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="963a6-182">直接ルーティングの SBC とメディアプロセッサコンポーネントの間では、常に SDES が使用されます。</span><span class="sxs-lookup"><span data-stu-id="963a6-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="963a6-183">現時点では、DTLS のみを提供している Teams クライアントはありません。ただし、一部の時点では、Google は SDES のサポートを停止することを発表しました。</span><span class="sxs-lookup"><span data-stu-id="963a6-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="963a6-184">使用している SBC のバイパスモードの書式</span><span class="sxs-lookup"><span data-stu-id="963a6-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="963a6-185">Offer は SDES を含んでいる必要があります。また、次の形式の DTLS オプションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="963a6-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="963a6-186">SDES と SBC を含む応答の書式を設定する</span><span class="sxs-lookup"><span data-stu-id="963a6-186">Format for answer containing SDES to SBC</span></span>

```
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="963a6-187">Teams から SBC へのオファーの書式設定</span><span class="sxs-lookup"><span data-stu-id="963a6-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="963a6-188">SDES でのみ使用できる形式</span><span class="sxs-lookup"><span data-stu-id="963a6-188">Format for SDES only offer to SBC</span></span>

```
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

