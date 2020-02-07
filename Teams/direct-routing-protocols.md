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
description: ダイレクトルーティングプロトコル
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7462822626b698f95b80a716a55f94dfe92148ff
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835027"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>ダイレクトルーティング-定義と RFC 標準

この記事では、Microsoft Phone システムのダイレクトルーティングが RFC 標準プロトコルを実装する方法について説明します。 この記事は、オンプレミスのセッション境界コントローラー (SBC) とセッション開始プロトコル (SIP) プロキシサービスとの間の接続の構成を担当する音声管理者を対象としています。

顧客の SBC インターフェイスは、Microsoft Teams バックエンドの次のコンポーネントで構成されています。 

- 通知の**SIP プロキシ**。 これは、SBCs と Direct ルーティングの間の SIP (TLS) 接続を処理する、インターネット向けのダイレクトルーティングのコンポーネントです。

- メディアの**メディアプロセッサ**。 これは、メディアトラフィックを処理するインターネット向けのダイレクトルーティングのコンポーネントです。 このコンポーネントは、SRTP と SRTP プロトコルを使います。


直接ルーティングの詳細については、「[電話システムのダイレクトルーティング](direct-routing-landing-page.md)」を参照してください。

SIP プロトコルの直接ルーティングの実装方法について詳しくは、「 [Direct routing-SIP protocol](direct-routing-protocols-sip.md)」をご覧ください。

## <a name="rfc-standards"></a>RFC 規格

直接ルーティングは、RFC 標準に準拠しています。  直接ルーティングに接続されている SBC は、次の Rfc (またはその後継) にも準拠している必要があります。 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>メディア以外のバイパスモードをサポートするデバイスに適用可能な標準 

次の規格は、メディア以外のバイパスモードのみをサポートするデバイスに適用されます。

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): セッション開始プロトコル
- [RFC 3325](https://www.ietf.org/rfc/rfc3325)。 信頼されたネットワーク内のアサートされた id のセッションの開始プロトコルのプライベート拡張--P--Identity ヘッダーの処理に関するセクション。 直接ルーティングでは、プライバシー ID ヘッダーを使用して、P がアサートされた Id が送信されます。 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt)必要な履歴情報についてのセッション開始プロトコル (SIP) の拡張。 詳細については、「SIP プロトコルの説明をルーティングする」もご覧ください。
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt)セッション開始プロトコルによって参照されるメカニズム
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt)セッション開始プロトコル (SIP) は、ヘッダーを置き換えます。 
- [RFC 6337](https://tools.ietf.org/html/rfc6337)Offer/Answer Model のセッション開始プロトコル (SIP) の使用状況。
  「RFC の偏差」セクションを参照してください。
- [Rfc 3711](https://tools.ietf.org/html/rfc3711)および[rfc 4771](https://tools.ietf.org/html/rfc4771)。 SRTP を使って RTP トラフィックを保護します。 SBC は、SDES を使ってキーを確立できる必要があります。 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt)セッション記述プロトコル (SDP) RTP/RTCP 多重化についての説明

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>メディアバイパスモードをサポートするデバイスに適用される標準

非バイパスモードに該当する場合は、次の規格がメディアバイパスモードで使用されます。

- [メディアバイパスの RFC 5245 対話型接続確立 (ICE)](https://tools.ietf.org/html/rfc5245)。  SBC は、次の機能をサポートしている必要があります。
  - ICE Lite-Teams クライアントはフル ICE クライアントである
  - [ICE を再起動](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)します。 詳細については、「アイスクリームの再起動」の使用例と例を参照してください。メディアのバイパスをサポートしていないエンドポイントに転送されたメディアバイパス通話   
- [RFC rfc 5589 セッション開始プロトコル (SIP) 通話制御–転送](https://tools.ietf.org/html/rfc5589)。 
- [RFC 3960 初期メディアと着信音の生成セッション開始プロトコル (SIP) に](https://tools.ietf.org/html/rfc3960)ついては、「3.1、フォーク、3.2、着信音の生成」をご覧ください。 
- [NAT 用の RFC 5389 セッショントラバーサルユーティリティ (STUN)](https://tools.ietf.org/html/rfc5389)
- [NAT (TURN) でのリレーを使った RFC 5766 トラバーサル: NAT 用のセッショントラバーサルユーティリティの中継拡張機能 (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>E911 プロバイダーへの位置情報の伝達のサポートに適用される標準

- [RFC 6442、セッション開始プロトコルの場所 Conveyance](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>RFC の

次の表は、Microsoft による SIP またはメディアスタックの実装が標準から逸脱している RFC のセクションを示しています。

| RFC とセクション | 説明 | 逸脱 |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337、5.3 でのメディアの保留と再開](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC では、"a = inactive"、"a = sendonly"、a = recvonly "を使用して、通話を保留にすることができます。 |SIP プロキシは "a = 無効" のみをサポートしており、SBC が "a = sendonly" または "a = recvonly" を送信しているかどうかを認識できません。
| [RFC 6337、セクション5.4 「c = 0.0.0.0 での SDP 受信の動作」](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264)を使用するには、エージェントが接続アドレス0.0.0.0 の SDP を受け取ることができます。この場合は、RTP と RTCP のどちらもピアに送信されないことを意味します。 | SIP プロキシはこのオプションをサポートしていません。 |

## <a name="operational-modes"></a>操作モード

直接ルーティングには、次の2つの操作モードがあります。

- **メディアバイパスなし**。すべての RTP トラフィックが Teams クライアント、メディアプロセッサ、SBC の間で流れるようにします。  

- **メディアのバイパス**で、すべての RTP メディアが Teams のエンドポイントと SBC の間で流れるようにします。 

SIP トラフィックは常に SIP プロキシ経由で流れることに注意してください。   
