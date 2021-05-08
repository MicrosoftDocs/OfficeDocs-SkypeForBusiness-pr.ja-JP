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
ms.openlocfilehash: 7462822626b698f95b80a716a55f94dfe92148ff
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835027"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>ダイレクト ルーティング - 定義と RFC 標準

この記事では、システム ダイレクト ルーティングMicrosoft 電話 RFC 標準プロトコルを実装する方法について説明します。 この記事は、オンプレミスのセッション ボーダー コントローラー (SBC) とセッション開始プロトコル (SIP) プロキシ サービス間の接続の構成を担当する音声管理者を対象にしています。

顧客の SBC は、バックエンド内の次のコンポーネントMicrosoft Teamsします。 

- **シグナリング用の SIP** プロキシ。 これは、SBC とダイレクト ルーティング間の SIP (TLS) 接続を処理するダイレクト ルーティングのインターネットに接続するコンポーネントです。

- **メディアのメディア** プロセッサ。 これは、メディア トラフィックを処理するダイレクト ルーティングのインターネットに接続するコンポーネントです。 このコンポーネントでは、SRTP プロトコルと SRTCP プロトコルを使用します。


ダイレクト ルーティングの詳細については、「ダイレクト ルーティング[」電話システム参照してください](direct-routing-landing-page.md)。

ダイレクト ルーティングによる SIP プロトコルの実装方法の詳細については、「ダイレクト ルーティング - SIP プロトコル」 [を参照してください](direct-routing-protocols-sip.md)。

## <a name="rfc-standards"></a>RFC 標準

ダイレクト ルーティングは RFC 標準に準拠しています。  ダイレクト ルーティングに接続されている SBC は、次の RFC (または後続の RFC) にも準拠する必要があります。 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>非メディア バイパス モードをサポートするデバイスに適用される標準 

次の標準は、非メディア バイパス モードのみをサポートするデバイスに適用されます。

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): セッション開始プロトコル
- [RFC 3325](https://www.ietf.org/rfc/rfc3325)。 信頼されたネットワーク内でアサートされた ID のセッション開始プロトコルへのプライベート拡張機能-- P-Asserted-Identity ヘッダーの処理に関するセクション。 ダイレクト ルーティングは、プライバシー ID ヘッダーを使用して P-Asserted-Identity を送信します。 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) 必要な履歴情報のセッション開始プロトコル (SIP) の拡張機能。 詳細については、SIP プロトコルのルーティングに関する説明も参照してください。
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) セッション開始プロトコルのReferred-Byメカニズム
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) セッション開始プロトコル (SIP) "Replaces" ヘッダー 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) オファー/回答モデルのセッション開始プロトコル (SIP) の使用。
  「RFC からの逸脱」セクションを参照してください。
- [RFC 3711 および](https://tools.ietf.org/html/rfc3711) [RFC 4771。](https://tools.ietf.org/html/rfc4771) SRTP を使用して RTP トラフィックを保護します。 SBC は、SDES を使用してキーを確立できる必要があります。 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) RTP/RTCP 多重化のためのセッション記述プロトコル (SDP) オファー/回答の明確化

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>メディア バイパス モードをサポートするデバイスに適用される標準

非バイパス モードに適用できる標準に加えて、メディア バイパス モードには次の標準が使用されます。

- [RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).  SBC は次をサポートする必要があります。
  - ICE Lite - TEAMSクライアントは完全な ICE クライアントです
  - [ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). ICE 再起動の使用例と例については、「ICE Restart: Media bypass call transferred to an endpoints to support media bypass (ICE Restart: メディア バイパスをサポートしていないエンドポイントに転送されるメディア バイパス呼び出し)」の詳細を参照してください。   
- [RFC RFC 5589 セッション開始プロトコル (SIP) 呼び出し制御 – 転送](https://tools.ietf.org/html/rfc5589)。 
- [セッション開始プロトコル (SIP) の RFC 3960](https://tools.ietf.org/html/rfc3960)早期メディアおよび呼び出し音の生成については、「3.1、Forking、3.2, Ringing Tone Generation (呼び出し音の生成)」セクションを参照してください。 
- [RFC 5389 Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal Using Relays around NAT (TURN): NAT (STUN) のセッション トラバーサル ユーティリティへのリレー拡張機能](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>E911 プロバイダーへの位置情報の伝達をサポートするために適用される標準

- [RFC 6442、セッション開始プロトコルの場所伝達](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>RFC からの逸脱

次の表は、MICROSOFT の SIP またはメディア スタックの実装が標準から異なる RFC のセクションを示しています。

| RFC とセクション | 説明 | 偏差 |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337、セクション 5.3 メディアの保留と再開](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC では、"a=inactive"、"a=sendonly"、a=recvonly" を使用して通話を保留にできます。 |SIP プロキシは "a=inactive" のみをサポートし、SBC が "a=sendonly" または "a=recvonly" を送信する場合は理解しません。
| [RFC 6337、セクション 5.4 "C=0.0.0.0 を使用した SDP の受信に関する動作](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) では、エージェントが接続アドレス 0.0.0.0 の SDP を受信できる必要があります。その場合、RTP も RTCP もピアに送信する必要がなされません。 | SIP プロキシでは、このオプションはサポートされていません。 |

## <a name="operational-modes"></a>操作モード

ダイレクト ルーティングには、次の 2 つの操作モードがあります。

- **クライアント、メディア** プロセッサ、SBC の間ですべての RTP トラフィックTeamsが流れるメディア バイパスがない。  

- **すべての** RTP メディアが、エンドポイントと SBC の間でTeamsメディア バイパスを使用します。 

SIP トラフィックは常に SIP プロキシ経由で流れます。   
