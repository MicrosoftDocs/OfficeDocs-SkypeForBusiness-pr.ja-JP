---
title: 電話システムのダイレクト ルーティング
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
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
ms.openlocfilehash: 88fb4459192ad9ff5af8702878d1cbf6a59d8e9d
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569205"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="dc1c0-103">ダイレクト ルーティング - 定義と RFC 標準</span><span class="sxs-lookup"><span data-stu-id="dc1c0-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="dc1c0-104">この記事では、システム ダイレクト ルーティングMicrosoft 電話 RFC 標準プロトコルを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="dc1c0-105">この記事は、オンプレミスのセッション ボーダー コントローラー (SBC) とセッション開始プロトコル (SIP) プロキシ サービス間の接続の構成を担当する音声管理者を対象にしています。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="dc1c0-106">顧客の SBC は、バックエンド内の次のコンポーネントMicrosoft Teamsします。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="dc1c0-107">**シグナリング用の SIP** プロキシ。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="dc1c0-108">これは、SBC とダイレクト ルーティング間の SIP (TLS) 接続を処理するダイレクト ルーティングのインターネットに接続するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="dc1c0-109">**メディアのメディア** プロセッサ。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-109">**The media processors** for media.</span></span> <span data-ttu-id="dc1c0-110">これは、メディア トラフィックを処理するダイレクト ルーティングのインターネットに接続するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="dc1c0-111">このコンポーネントでは、SRTP プロトコルと SRTCP プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="dc1c0-112">ダイレクト ルーティングの詳細については、「ダイレクト ルーティング[」電話システム参照してください](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="dc1c0-113">ダイレクト ルーティングによる SIP プロトコルの実装方法の詳細については、「ダイレクト ルーティング - SIP プロトコル」 [を参照してください](direct-routing-protocols-sip.md)。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="dc1c0-114">RFC 標準</span><span class="sxs-lookup"><span data-stu-id="dc1c0-114">RFC standards</span></span>

<span data-ttu-id="dc1c0-115">ダイレクト ルーティングは RFC 標準に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="dc1c0-116">ダイレクト ルーティングに接続されている SBC は、次の RFC (または後続の RFC) にも準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="dc1c0-117">非メディア バイパス モードをサポートするデバイスに適用される標準</span><span class="sxs-lookup"><span data-stu-id="dc1c0-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="dc1c0-118">次の標準は、非メディア バイパス モードのみをサポートするデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="dc1c0-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): セッション開始プロトコル</span><span class="sxs-lookup"><span data-stu-id="dc1c0-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="dc1c0-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325)。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="dc1c0-121">信頼されたネットワーク内でアサートされた ID のセッション開始プロトコルへのプライベート拡張機能-- P-Asserted-Identity ヘッダーの処理に関するセクション。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="dc1c0-122">ダイレクト ルーティングは、プライバシー ID ヘッダーを使用して P-Asserted-Identity を送信します。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="dc1c0-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) 必要な履歴情報のセッション開始プロトコル (SIP) の拡張機能。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="dc1c0-124">詳細については、SIP プロトコルのルーティングに関する説明も参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="dc1c0-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) セッション開始プロトコルのReferred-Byメカニズム</span><span class="sxs-lookup"><span data-stu-id="dc1c0-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="dc1c0-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) セッション開始プロトコル (SIP) "Replaces" ヘッダー</span><span class="sxs-lookup"><span data-stu-id="dc1c0-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="dc1c0-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) オファー/回答モデルのセッション開始プロトコル (SIP) の使用。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="dc1c0-128">「RFC からの逸脱」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="dc1c0-129">[RFC 3711 および](https://tools.ietf.org/html/rfc3711) [RFC 4771。](https://tools.ietf.org/html/rfc4771)</span><span class="sxs-lookup"><span data-stu-id="dc1c0-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="dc1c0-130">SRTP を使用して RTP トラフィックを保護します。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="dc1c0-131">SBC は、SDES を使用してキーを確立できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="dc1c0-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) RTP/RTCP 多重化のためのセッション記述プロトコル (SDP) オファー/回答の明確化</span><span class="sxs-lookup"><span data-stu-id="dc1c0-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="dc1c0-133">メディア バイパス モードをサポートするデバイスに適用される標準</span><span class="sxs-lookup"><span data-stu-id="dc1c0-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="dc1c0-134">非バイパス モードに適用できる標準に加えて、メディア バイパス モードには次の標準が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="dc1c0-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="dc1c0-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="dc1c0-136">SBC は次をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="dc1c0-137">ICE Lite - TEAMSクライアントは完全な ICE クライアントです</span><span class="sxs-lookup"><span data-stu-id="dc1c0-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="dc1c0-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="dc1c0-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="dc1c0-139">ICE 再起動の使用例と例については、「ICE Restart: Media bypass call transferred to an endpoints to support media bypass (ICE Restart: メディア バイパスをサポートしていないエンドポイントに転送されるメディア バイパス呼び出し)」の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="dc1c0-140">[RFC RFC 5589 セッション開始プロトコル (SIP) 呼び出し制御 – 転送](https://tools.ietf.org/html/rfc5589)。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="dc1c0-141">[セッション開始プロトコル (SIP) の RFC 3960](https://tools.ietf.org/html/rfc3960)早期メディアおよび呼び出し音の生成については、「3.1、Forking、3.2, Ringing Tone Generation (呼び出し音の生成)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="dc1c0-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="dc1c0-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="dc1c0-143">RFC 5766 Traversal Using Relays around NAT (TURN): NAT (STUN) のセッション トラバーサル ユーティリティへのリレー拡張機能</span><span class="sxs-lookup"><span data-stu-id="dc1c0-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="dc1c0-144">E911 プロバイダーへの位置情報の伝達をサポートするために適用される標準</span><span class="sxs-lookup"><span data-stu-id="dc1c0-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="dc1c0-145">RFC 6442、セッション開始プロトコルの場所伝達</span><span class="sxs-lookup"><span data-stu-id="dc1c0-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="dc1c0-146">RFC からの逸脱</span><span class="sxs-lookup"><span data-stu-id="dc1c0-146">Deviations from the RFC's</span></span>

<span data-ttu-id="dc1c0-147">次の表は、MICROSOFT の SIP またはメディア スタックの実装が標準から異なる RFC のセクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="dc1c0-148">RFC とセクション</span><span class="sxs-lookup"><span data-stu-id="dc1c0-148">RFC and sections</span></span> | <span data-ttu-id="dc1c0-149">説明</span><span class="sxs-lookup"><span data-stu-id="dc1c0-149">Description</span></span> | <span data-ttu-id="dc1c0-150">偏差</span><span class="sxs-lookup"><span data-stu-id="dc1c0-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="dc1c0-151">RFC 6337、セクション 5.3 メディアの保留と再開</span><span class="sxs-lookup"><span data-stu-id="dc1c0-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="dc1c0-152">RFC では、"a=inactive"、"a=sendonly"、a=recvonly" を使用して通話を保留にできます。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="dc1c0-153">SIP プロキシは "a=inactive" のみをサポートし、SBC が "a=sendonly" または "a=recvonly" を送信する場合は理解しません。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="dc1c0-154">RFC 6337、セクション 5.4 "C=0.0.0.0 を使用した SDP の受信に関する動作</span><span class="sxs-lookup"><span data-stu-id="dc1c0-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="dc1c0-155">[RFC3264](https://tools.ietf.org/html/rfc3264) では、エージェントが接続アドレス 0.0.0.0 の SDP を受信できる必要があります。その場合、RTP も RTCP もピアに送信する必要がなされません。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="dc1c0-156">SIP プロキシでは、このオプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="dc1c0-157">操作モード</span><span class="sxs-lookup"><span data-stu-id="dc1c0-157">Operational modes</span></span>

<span data-ttu-id="dc1c0-158">ダイレクト ルーティングには、次の 2 つの操作モードがあります。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="dc1c0-159">**クライアント、メディア** プロセッサ、SBC の間ですべての RTP トラフィックTeamsが流れるメディア バイパスがない。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="dc1c0-160">**すべての** RTP メディアが、エンドポイントと SBC の間でTeamsメディア バイパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="dc1c0-161">SIP トラフィックは常に SIP プロキシ経由で流れます。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-161">Note that SIP traffic always flows via the SIP proxy.</span></span> 

## <a name="dtmf"></a><span data-ttu-id="dc1c0-162">DTMF</span><span class="sxs-lookup"><span data-stu-id="dc1c0-162">DTMF</span></span>
<span data-ttu-id="dc1c0-163">インバンド DTMF はメディア スタックではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dc1c0-163">In-band DTMF is not supported by media stack.</span></span>
