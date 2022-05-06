---
title: 'Teams電話システムダイレクト ルーティング: 定義と RFC 標準'
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
description: システム ダイレクト ルーティングMicrosoft 電話 RFC 標準プロトコルを実装する方法。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26178fa52105f43ce9f7f18c0058a2ead3ef1c02
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235342"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>ダイレクト ルーティング - 定義と RFC 標準

この記事では、システム ダイレクト ルーティングMicrosoft 電話 RFC 標準プロトコルを実装する方法について説明します。 この記事は、オンプレミス のセッション ボーダー コントローラー (SBC) とセッション開始プロトコル (SIP) プロキシ サービスの間の接続を構成する役割を担う音声管理者を対象としています。

お客様の SBC は、Microsoft Teams バックエンドで次のコンポーネントとインターフェイスします。 

- シグナリング用の **SIP プロキシ**。 これは、SBC とダイレクト ルーティング間の SIP (TLS) 接続を処理するダイレクト ルーティングのインターネットに接続するコンポーネントです。

- **メディアのメディア プロセッサ** 。 これは、メディア トラフィックを処理するダイレクト ルーティングのインターネットに接続するコンポーネントです。 このコンポーネントでは、SRTP プロトコルと SRTCP プロトコルを使用します。


ダイレクト ルーティングの詳細については、「ダイレクト ルーティング[の電話システム」を](direct-routing-landing-page.md)参照してください。

ダイレクト ルーティングで SIP プロトコルを実装する方法の詳細については、「 [ダイレクト ルーティング - SIP プロトコル」を](direct-routing-protocols-sip.md)参照してください。

## <a name="rfc-standards"></a>RFC 標準

ダイレクト ルーティングは RFC 標準に準拠しています。  ダイレクト ルーティングに接続されている SBC は、次の RFC (またはその後続の RFC) にも準拠している必要があります。 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>メディア以外のバイパス モードをサポートするデバイスに適用される標準 

次の標準は、メディア以外のバイパス モードのみをサポートするデバイスに適用されます。

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): セッション開始プロトコル
- [RFC 3325](https://www.ietf.org/rfc/rfc3325)。 信頼されたネットワーク内のアサートされた ID のセッション開始プロトコルへのプライベート拡張機能--P-Asserted-Identity ヘッダーの処理に関するセクション。 ダイレクト ルーティングは、プライバシー ID ヘッダーを使用して P-Asserted-Identity を送信します。 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) 必要な履歴情報のセッション開始プロトコル (SIP) の拡張機能。 詳細については、「SIP プロトコルのルーティングに関する説明」も参照してください。
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) セッション開始プロトコル Referred-By メカニズム
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) セッション開始プロトコル (SIP) "Replaces" ヘッダー 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) オファー/応答モデルのセッション開始プロトコル (SIP) の使用。
  「RFC からの逸脱」セクションを参照してください。
- [RFC 3711](https://tools.ietf.org/html/rfc3711) と [RFC 4771](https://tools.ietf.org/html/rfc4771)。 SRTP を使用して RTP トラフィックを保護します。 SBC は、SDES を使用してキーを確立できる必要があります。 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) RTP/RTCP 多重化のセッション記述プロトコル (SDP) オファー/応答の明確化

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>メディア バイパス モードをサポートするデバイスに適用される標準

非バイパス モードに適用できる標準に加えて、メディア バイパス モードには次の標準が使用されます。

- [メディア バイパス用の RFC 5245 対話型接続確立 (ICE)。](https://tools.ietf.org/html/rfc5245)  SBC では、次のものがサポートされている必要があります。
  - ICE Lite - Teams クライアントは完全な ICE クライアントです
  - [ICE が再起動します](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)。 ICE 再起動のユース ケースと例については、「ICE Restart: メディア バイパスをサポートしていないエンドポイントに転送されたメディア バイパス呼び出し」を参照してください。   
- [RFC RFC 5589 セッション開始プロトコル (SIP) 呼び出し制御 – 転送](https://tools.ietf.org/html/rfc5589)。 
- [セッション開始プロトコル (SIP) の RFC 3960 Early Media and Ringing Tone Generation(セッション開始プロトコル (SIP))](https://tools.ietf.org/html/rfc3960)、セクション 3.1、フォーク、および 3.2 の「呼び出し音の生成」を参照してください。 
- [NAT (STUN) 用の RFC 5389 セッション トラバーサル ユーティリティ](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal using Relays around NAT (TURN): NAT (STUN) 用セッション トラバーサル ユーティリティへのリレー拡張機能](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>E911 プロバイダーへの位置情報の伝達をサポートするために適用される標準

- [RFC 6442、セッション開始プロトコルの場所の伝達](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>RFC からの逸脱

次の表に、MICROSOFT による SIP またはメディア スタックの実装が標準から逸脱している RFC のセクションを示します。

| RFC とセクション | 説明 | 偏差 |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337、セクション 5.3 メディアの保持と再開](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC では、"a=非アクティブ"、"a=sendonly"、a=recvonly" を使用して通話を保留にできます。 |SIP プロキシは"a=非アクティブ" のみをサポートし、SBC が "a=sendonly" または "a=recvonly" を送信するかどうかを認識しません。
| [RFC 6337、セクション 5.4 「C=0.0.0.0 を使用した SDP の受信に関する動作](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) では、エージェントが接続アドレス 0.0.0.0 の SDP を受信できることが必要です。この場合、RTP も RTCP もピアに送信する必要がありません。 | SIP プロキシでは、このオプションはサポートされていません。 |

## <a name="operational-modes"></a>操作モード

ダイレクト ルーティングには、次の 2 つの操作モードがあります。

- すべての RTP トラフィックが、Teams クライアント、メディア プロセッサ、および SBC の間をフローするメディア **バイパスなし**。  

- すべての RTP メディアがTeams エンドポイントと SBC の間を流れる **メディア バイパス**。 

SIP トラフィックは常に SIP プロキシ経由でフローされることに注意してください。 

## <a name="dtmf"></a>DTMF
インバンド DTMF は、メディア スタックではサポートされていません。
