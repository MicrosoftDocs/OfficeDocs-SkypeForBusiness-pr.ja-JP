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
f1.keywords:
- NOCSH
description: ダイレクト ルーティング プロトコル
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888576"
---
# <a name="overview"></a><span data-ttu-id="d6cf8-103">概要</span><span class="sxs-lookup"><span data-stu-id="d6cf8-103">Overview</span></span>

<span data-ttu-id="d6cf8-104">この記事では [、RFC 5245](https://tools.ietf.org/html/rfc5245)で説明されているとおり、直接ルーティングで ICE Lite に対してセッション ボーダー コントローラー (SBC) が有効になっているメディア バイパスをサポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="d6cf8-105">この記事は、オンプレミスの SBC と SIP プロキシ サービス間の接続の構成を担当する音声管理者を対象にしています。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="d6cf8-106">この記事では、ICE Lite のシナリオの概要と相互運用性の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="d6cf8-107">この記事では、メッセージ形式と、信頼性の高い呼び出しとメディア フローを確保するために必要な状態マシンの遷移について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="d6cf8-108">用語</span><span class="sxs-lookup"><span data-stu-id="d6cf8-108">Terminology</span></span>

- <span data-ttu-id="d6cf8-109">First Hello – 呼び出し元と呼び出し先が話す最初の単語。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="d6cf8-110">ほとんどの場合、エンドポイントからの最初のパケットが確実に配信されるのを確実に確保するために、すべての努力が必要です。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="d6cf8-111">forking – 呼び出し先が複数のデバイスで使用できる場合は、呼び出し元からのオファーが複数の呼び出し先エンドポイントに配信される可能性があります (たとえば、Teams ユーザーが Windows の場合は Teams にサインインし、Android または iPhone の場合は Teams にサインインしている可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="d6cf8-112">Provisional Answer (183) - 通話設定を高速化するための呼び出し先エンドポイントは、メディア フローを確立するために必要な候補とキーを含む回答を送信します。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="d6cf8-113">これは、ユーザーが特定の呼び出し先インスタンスからの呼び出し (200OK) に応答する可能性を予測して行われます。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="d6cf8-114">forking を使用すると、呼び出し元は複数の仮回答を受け取る準備が整う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="d6cf8-115">Re-Invite – ICE 制御エンドポイントによって選択された最終的な候補を含むオファー。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="d6cf8-116">これには、複数のフォークを処理する競合状態を解決するための a=remote-candidate 属性があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="d6cf8-117">Teamsエンドポイント – サーバー (メディア プロセッサ、トランスポート リレー) またはクライアントTeamsできます。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="d6cf8-118">メッセージ形式</span><span class="sxs-lookup"><span data-stu-id="d6cf8-118">Message format</span></span>

<span data-ttu-id="d6cf8-119">このTeamsは、ICE-Lite 用の RFC 5245 に従います。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="d6cf8-120">つまり、すべての STUN メッセージが [RFC 5389 に準拠します](https://tools.ietf.org/html/rfc5389)。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="d6cf8-121">RFC 5389 で要求される SBC は、認識されない STUN 属性を無視し、既知の属性を持つメッセージを処理し続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="d6cf8-122">不正な形式のパケットが受信された場合、メディア セッションの確立に影響を与えることなくパケットを破棄する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="d6cf8-123">ICE Lite の要件</span><span class="sxs-lookup"><span data-stu-id="d6cf8-123">ICE Lite requirements</span></span>

<span data-ttu-id="d6cf8-124">このセクションでは、ICE Lite の要件について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="d6cf8-125">候補者の集まり</span><span class="sxs-lookup"><span data-stu-id="d6cf8-125">Candidate gathering</span></span>

<span data-ttu-id="d6cf8-126">SBC は、パブリックに到達可能な 1 つの候補のみを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="d6cf8-127">現時点では、IPV4 候補だけがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="d6cf8-128">接続チェック</span><span class="sxs-lookup"><span data-stu-id="d6cf8-128">Connectivity checks</span></span>

<span data-ttu-id="d6cf8-129">ICE Lite 実装は、受信した接続チェックに応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="d6cf8-130">ICE Lite エンドポイントは、接続チェック要求を送信できません。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="d6cf8-131">(接続チェックが違反で送信された場合、実装全体が応答し、予期しないピア派生候補が検出され、呼び出しエラーが発生する可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="d6cf8-132">ノミネート</span><span class="sxs-lookup"><span data-stu-id="d6cf8-132">Nominations</span></span>

<span data-ttu-id="d6cf8-133">ICE 完全実装エンドポイントは常に制御エンドポイントであり、メディア フローに使用する最終的な候補を選択するための "通常" のノミネートに従います。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="d6cf8-134">ICE Lite エンドポイントは、ノミネートを使用して、メディアおよび完全な通話確立に使用されるパスを終了できます。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="d6cf8-135">注: 183 の暫定回答を送信するピア エンドポイントで forking を実行する場合、SBC は複数のエンドポイントからのチェックに応答する準備が整っている必要があります。また、200OK より前に指名が発生した場合は、複数のエンドポイントからのノミネートも行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="d6cf8-136">ICE 状態マシンの最終パスとユーザー応答のタイミングの収束によっては、200OK の前または後にノミネートが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="d6cf8-137">SBC は両方のケースを処理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="d6cf8-138">Forking の収束</span><span class="sxs-lookup"><span data-stu-id="d6cf8-138">Converging for forking</span></span>

<span data-ttu-id="d6cf8-139">SBC からのオファーが複数の Teams エンドポイントにフォークした場合、Teams エンドポイントは暫定回答で応答し、接続チェックを開始できます。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="d6cf8-140">SBC は、接続チェックを受信し、複数のピア エンドポイントからの接続チェックに応答するために準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="d6cf8-141">たとえば、ユーザー Teamsデスクトップと携帯電話の両方にサインインできます。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="d6cf8-142">両方のデバイスに受信呼び出しが通知され、SBC との接続チェックが試行されます。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="d6cf8-143">最終的には、1 つのエンドポイントだけが呼び出しに応答します (200OK)。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="d6cf8-144">200OK を受信すると、SBC はメディア パケットを処理する適切なコンテキストを設定できます。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="d6cf8-145">シナリオ</span><span class="sxs-lookup"><span data-stu-id="d6cf8-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="d6cf8-146">SBC からの受信呼び出し</span><span class="sxs-lookup"><span data-stu-id="d6cf8-146">Inbound call from SBC</span></span>

<span data-ttu-id="d6cf8-147">このシナリオでは、SBC が処理する必要があるいくつかの可能なピア エンドポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="d6cf8-148">サーバー エンドポイントは通常、200OK で直接応答します。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="d6cf8-149">これらは、通常、ボイスメール、通話キュー、自動応答のシナリオに関係する完全な ICE エンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="d6cf8-150">クライアント エンドポイントは、異なる From/To タグ (183) に続いて、呼び出しに応答するエンドポイントから 200OK を使用して、複数の仮回答を送信できます。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="d6cf8-151">これらは、通常、エンド ユーザー クライアントを表す完全な ICE エンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="d6cf8-152">その他の SBC エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-152">Other SBC endpoints.</span></span> <span data-ttu-id="d6cf8-153">これらは、通常、クライアント エンドポイントと別の電話番号を同時に呼び出すシナリオに関与する ICE Lite エンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="d6cf8-154">SBC は、完全な ICE エンドポイントから受信した有効なすべての接続チェック要求に応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="d6cf8-155">RFC ごとに、完全な ICE エンドポイントが制御エンドポイントになります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="d6cf8-156">接続Teams (クライアント/サーバー) エンドポイントは、接続チェックを完了するために "通常" の要求を実行します。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="d6cf8-157">最後の 200Ok は、早期メディアを送信したエンドポイントから送信するか、別のエンドポイントから送信できます。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="d6cf8-158">200Ok を受信する場合、SBC はメディア フローに適切なコンテキストを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="d6cf8-159">初期メディア</span><span class="sxs-lookup"><span data-stu-id="d6cf8-159">Early media</span></span>

<span data-ttu-id="d6cf8-160">早期メディア フローがある場合、SBC はメディアのストリーミングを開始する最初のエンドポイントにラッチする必要があります。メディア フローは、候補者がノミネートされる前に開始できます。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="d6cf8-161">SBC は、IVR/ボイスメールシナリオを有効にするには、このフェーズ中に DTMF を送信するためのサポートを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="d6cf8-162">SBC は、ノミネートが完了していない場合にチェックを受け取った最も優先度の高いパスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="d6cf8-163">SBC への発信呼び出し</span><span class="sxs-lookup"><span data-stu-id="d6cf8-163">Outbound call to SBC</span></span>

<span data-ttu-id="d6cf8-164">このTeamsエンドポイントは、このシナリオの呼び出し元であり、制御エンドポイントになります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="d6cf8-165">暫定回答 (183) または最終的な回答 (200OK) のいずれかを受け取った場合、Teams エンドポイントは接続チェックを開始し、"標準" のノミネートに進み、接続チェックを完了します。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="d6cf8-166">注: SBC が暫定回答 (183) を送信する場合、SBC は接続チェック要求を受信し、200OK が SBC によって送信される前に、要求を完了する準備ができている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="d6cf8-167">200OK を受信する前にチェックやノミネートが完了した場合、200OK を受信した後、チェックやノミネートは再び実行されません。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="d6cf8-168">SBC は、ICE 候補、パスワード、および ufrag (ユーザー名フラグメント) を 183 から 200 の間で変更しすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="d6cf8-169">早期メディアをサポートするために、SBC は、Teams エンドポイントによってノミネートが完了する前でも、受信した接続チェックに基づいて最も高い優先順位で、ピア ICE 候補へのメディアのストリーミングを開始できます。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="d6cf8-170">SBC は、指名が完了するまで、Teamsに関するメディアを受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="d6cf8-171">候補がノミネートされた後、SBC は適切なコンテキストにリセットしてメディア パケットを送受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="d6cf8-172">SRTP のサポート要件</span><span class="sxs-lookup"><span data-stu-id="d6cf8-172">SRTP support requirements</span></span>

<span data-ttu-id="d6cf8-173">SBC は、次の形式でオファーと回答AES_CM_128_HMAC_SHA1_80 SRTP 暗号化暗号をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```console
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="d6cf8-174">SBC の SDP オファーの暗号属性の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="d6cf8-175">MKI パラメーターと Length パラメーターは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="d6cf8-176">詳細については [、RFC 4568、セクション 6.1 を参照してください](https://tools.ietf.org/html/rfc4568#section-6.1)。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="d6cf8-177">SDES サポート要件</span><span class="sxs-lookup"><span data-stu-id="d6cf8-177">SDES support requirements</span></span>

<span data-ttu-id="d6cf8-178">デバイスは、以下で説明する形式で SDES を提供できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="d6cf8-179">Microsoft Media Processors は常に SDES を好む。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="d6cf8-180">非メディア バイパスでは、クライアントが DTLS のみをサポートしている場合でも、メディア プロセッサは SDES に変換されます。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="d6cf8-181">メディア バイパスでは、クライアントが DTLS のみ (将来の Google Chrome 状態) の場合、ダイレクト ルーティングはパスに MP を挿入し、メディア バイパスから非メディア バイパスに通話を変換します。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="d6cf8-182">SBC とダイレクト ルーティングのメディア プロセッサ コンポーネントの間では、常に SDES が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="d6cf8-183">現時点では、DTLS のみをTeamsクライアントはありません。ただし、Google は、ある時点で SDES のサポートを停止すると発表しています。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="d6cf8-184">バイパス モードでの SBC からのオファーの形式</span><span class="sxs-lookup"><span data-stu-id="d6cf8-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="d6cf8-185">オファーには SDES が含まれている必要があります。また、次の形式で DTLS を省略可能に含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="d6cf8-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="d6cf8-186">SBC に対する SDES を含む回答の形式</span><span class="sxs-lookup"><span data-stu-id="d6cf8-186">Format for answer containing SDES to SBC</span></span>

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="d6cf8-187">Teams から SBC へのオファーの形式</span><span class="sxs-lookup"><span data-stu-id="d6cf8-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="d6cf8-188">SBC に対する SDES のみオファーの形式</span><span class="sxs-lookup"><span data-stu-id="d6cf8-188">Format for SDES only offer to SBC</span></span>

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

