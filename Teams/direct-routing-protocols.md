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
description: ダイレクトルーティングプロトコル
appliesto:
- Microsoft Teams
ms.openlocfilehash: a470c402ebfd4e70955f4e864d45dbaaca476dfd
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065627"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="50ae6-103">ダイレクトルーティング-定義と RFC 標準</span><span class="sxs-lookup"><span data-stu-id="50ae6-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="50ae6-104">この記事では、Microsoft Phone システムのダイレクトルーティングが RFC 標準プロトコルを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="50ae6-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="50ae6-105">この記事は、オンプレミスのセッション境界コントローラー (SBC) とセッション開始プロトコル (SIP) プロキシサービスとの間の接続の構成を担当する音声管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="50ae6-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="50ae6-106">顧客の SBC インターフェイスは、Microsoft Teams バックエンドの次のコンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="50ae6-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="50ae6-107">通知の**SIP プロキシ**。</span><span class="sxs-lookup"><span data-stu-id="50ae6-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="50ae6-108">これは、SBCs と Direct ルーティングの間の SIP (TLS) 接続を処理する、インターネット向けのダイレクトルーティングのコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="50ae6-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="50ae6-109">メディアの**メディアプロセッサ**。</span><span class="sxs-lookup"><span data-stu-id="50ae6-109">**The media processors** for media.</span></span> <span data-ttu-id="50ae6-110">これは、メディアトラフィックを処理するインターネット向けのダイレクトルーティングのコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="50ae6-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="50ae6-111">このコンポーネントは、SRTP と SRTP プロトコルを使います。</span><span class="sxs-lookup"><span data-stu-id="50ae6-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="50ae6-112">直接ルーティングの詳細については、「[電話システムのダイレクトルーティング](direct-routing-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50ae6-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="50ae6-113">SIP プロトコルの直接ルーティングの実装方法について詳しくは、「 [Direct routing-SIP protocol](direct-routing-protocols-sip.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="50ae6-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="50ae6-114">RFC 規格</span><span class="sxs-lookup"><span data-stu-id="50ae6-114">RFC standards</span></span>

<span data-ttu-id="50ae6-115">直接ルーティングは、RFC 標準に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="50ae6-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="50ae6-116">直接ルーティングに接続されている SBC は、次の Rfc (またはその後継) にも準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="50ae6-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="50ae6-117">メディア以外のバイパスモードをサポートするデバイスに適用可能な標準</span><span class="sxs-lookup"><span data-stu-id="50ae6-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="50ae6-118">次の規格は、メディア以外のバイパスモードのみをサポートするデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="50ae6-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="50ae6-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): セッション開始プロトコル</span><span class="sxs-lookup"><span data-stu-id="50ae6-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="50ae6-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325)。</span><span class="sxs-lookup"><span data-stu-id="50ae6-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="50ae6-121">信頼されたネットワーク内のアサートされた id のセッションの開始プロトコルのプライベート拡張--P--Identity ヘッダーの処理に関するセクション。</span><span class="sxs-lookup"><span data-stu-id="50ae6-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="50ae6-122">直接ルーティングでは、プライバシー ID ヘッダーを使用して、P がアサートされた Id が送信されます。</span><span class="sxs-lookup"><span data-stu-id="50ae6-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="50ae6-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt)必要な履歴情報についてのセッション開始プロトコル (SIP) の拡張。</span><span class="sxs-lookup"><span data-stu-id="50ae6-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="50ae6-124">詳細については、「SIP プロトコルの説明をルーティングする」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="50ae6-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="50ae6-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt)セッション開始プロトコルによって参照されるメカニズム</span><span class="sxs-lookup"><span data-stu-id="50ae6-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="50ae6-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt)セッション開始プロトコル (SIP) は、ヘッダーを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="50ae6-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="50ae6-127">[RFC 6337](https://tools.ietf.org/html/rfc6337)Offer/Answer Model のセッション開始プロトコル (SIP) の使用状況。</span><span class="sxs-lookup"><span data-stu-id="50ae6-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="50ae6-128">「RFC の偏差」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="50ae6-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="50ae6-129">[Rfc 3711](https://tools.ietf.org/html/rfc3711)および[rfc 4771](https://tools.ietf.org/html/rfc4771)。</span><span class="sxs-lookup"><span data-stu-id="50ae6-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="50ae6-130">SRTP を使って RTP トラフィックを保護します。</span><span class="sxs-lookup"><span data-stu-id="50ae6-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="50ae6-131">SBC は、SDES を使ってキーを確立できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="50ae6-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="50ae6-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt)セッション記述プロトコル (SDP) RTP/RTCP 多重化についての説明</span><span class="sxs-lookup"><span data-stu-id="50ae6-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="50ae6-133">メディアバイパスモードをサポートするデバイスに適用される標準</span><span class="sxs-lookup"><span data-stu-id="50ae6-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="50ae6-134">非バイパスモードに該当する場合は、次の規格がメディアバイパスモードで使用されます。</span><span class="sxs-lookup"><span data-stu-id="50ae6-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="50ae6-135">[メディアバイパスの RFC 5245 対話型接続確立 (ICE)](https://tools.ietf.org/html/rfc5245)。</span><span class="sxs-lookup"><span data-stu-id="50ae6-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="50ae6-136">SBC は、次の機能をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="50ae6-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="50ae6-137">ICE Lite-Teams クライアントはフル ICE クライアントである</span><span class="sxs-lookup"><span data-stu-id="50ae6-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="50ae6-138">[ICE を再起動](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)します。</span><span class="sxs-lookup"><span data-stu-id="50ae6-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="50ae6-139">詳細については、「アイスクリームの再起動」の使用例と例を参照してください。メディアのバイパスをサポートしていないエンドポイントに転送されたメディアバイパス通話</span><span class="sxs-lookup"><span data-stu-id="50ae6-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="50ae6-140">[RFC rfc 5589 セッション開始プロトコル (SIP) 通話制御–転送](https://tools.ietf.org/html/rfc5589)。</span><span class="sxs-lookup"><span data-stu-id="50ae6-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="50ae6-141">[RFC 3960 初期メディアと着信音の生成セッション開始プロトコル (SIP) に](https://tools.ietf.org/html/rfc3960)ついては、「3.1、フォーク、3.2、着信音の生成」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="50ae6-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="50ae6-142">NAT 用の RFC 5389 セッショントラバーサルユーティリティ (STUN)</span><span class="sxs-lookup"><span data-stu-id="50ae6-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="50ae6-143">NAT (TURN) でのリレーを使った RFC 5766 トラバーサル: NAT 用のセッショントラバーサルユーティリティの中継拡張機能 (STUN)</span><span class="sxs-lookup"><span data-stu-id="50ae6-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="50ae6-144">E911 プロバイダーへの位置情報の伝達のサポートに適用される標準</span><span class="sxs-lookup"><span data-stu-id="50ae6-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="50ae6-145">RFC 6442、セッション開始プロトコルの場所 Conveyance</span><span class="sxs-lookup"><span data-stu-id="50ae6-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="50ae6-146">RFC の</span><span class="sxs-lookup"><span data-stu-id="50ae6-146">Deviations from the RFC's</span></span>

<span data-ttu-id="50ae6-147">次の表は、Microsoft による SIP またはメディアスタックの実装が標準から逸脱している RFC のセクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="50ae6-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="50ae6-148">RFC とセクション</span><span class="sxs-lookup"><span data-stu-id="50ae6-148">RFC and sections</span></span> | <span data-ttu-id="50ae6-149">説明</span><span class="sxs-lookup"><span data-stu-id="50ae6-149">Description</span></span> | <span data-ttu-id="50ae6-150">逸脱</span><span class="sxs-lookup"><span data-stu-id="50ae6-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="50ae6-151">RFC 6337、5.3 でのメディアの保留と再開</span><span class="sxs-lookup"><span data-stu-id="50ae6-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="50ae6-152">RFC では、"a = inactive"、"a = sendonly"、a = recvonly "を使用して、通話を保留にすることができます。</span><span class="sxs-lookup"><span data-stu-id="50ae6-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="50ae6-153">SIP プロキシは "a = 無効" のみをサポートしており、SBC が "a = sendonly" または "a = recvonly" を送信しているかどうかを認識できません。</span><span class="sxs-lookup"><span data-stu-id="50ae6-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="50ae6-154">RFC 6337、セクション5.4 「c = 0.0.0.0 での SDP 受信の動作」</span><span class="sxs-lookup"><span data-stu-id="50ae6-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="50ae6-155">[RFC3264](https://tools.ietf.org/html/rfc3264)を使用するには、エージェントが接続アドレス0.0.0.0 の SDP を受け取ることができます。この場合は、RTP と RTCP のどちらもピアに送信されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="50ae6-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="50ae6-156">SIP プロキシはこのオプションをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="50ae6-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="50ae6-157">操作モード</span><span class="sxs-lookup"><span data-stu-id="50ae6-157">Operational modes</span></span>

<span data-ttu-id="50ae6-158">直接ルーティングには、次の2つの操作モードがあります。</span><span class="sxs-lookup"><span data-stu-id="50ae6-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="50ae6-159">**メディアバイパスなし**。すべての RTP トラフィックが Teams クライアント、メディアプロセッサ、SBC の間で流れるようにします。</span><span class="sxs-lookup"><span data-stu-id="50ae6-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="50ae6-160">**メディアのバイパス**で、すべての RTP メディアが Teams のエンドポイントと SBC の間で流れるようにします。</span><span class="sxs-lookup"><span data-stu-id="50ae6-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="50ae6-161">SIP トラフィックは常に SIP プロキシ経由で流れることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="50ae6-161">Note that SIP traffic always flows via the SIP proxy.</span></span>   
