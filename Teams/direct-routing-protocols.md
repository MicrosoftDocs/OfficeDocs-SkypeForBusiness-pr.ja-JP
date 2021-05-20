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
# <a name="direct-routing---definitions-and-rfc-standards"></a>直接ルーティング - 定義と RFC 標準

この資料では、システム ダイレクト ルーティングMicrosoft 電話 RFC 標準プロトコルを実装する方法について説明します。 この記事は、オンプレミスのセッション ボーダー コントローラー (SBC) とセッション開始プロトコル (SIP) プロキシ サービス間の接続を構成する責任者を対象としています。

顧客 SBC は、Microsoft Teams バックエンドで次のコンポーネントとインターフェイスします。 

- **シグ** ナリング用の SIP プロキシ。 これは、SBC とダイレクト ルーティング間の SIP (TLS) 接続を処理する、インターネットに接続するダイレクト ルーティングのコンポーネントです。

- **メディア用のメディア プロセッサ** 。 これは、メディア トラフィックを処理するダイレクト ルーティングのインターネットに接続するコンポーネントです。 このコンポーネントは、SRTP および SRTCP プロトコルを使用します。


ダイレクト ルーティングの詳細については、「[ダイレクト ルーティングの電話システム](direct-routing-landing-page.md)」を参照してください。

直接ルーティングが SIP プロトコルを実装する方法の詳細については、「 [ダイレクト ルーティング - SIP プロトコル](direct-routing-protocols-sip.md)」を参照してください。

## <a name="rfc-standards"></a>RFC 標準

直接ルーティングは RFC 標準に準拠しています。  ダイレクト ルーティングに接続された SBC は、次の RFC (またはその後継) にも準拠する必要があります。 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>非メディア バイパス モードをサポートするデバイスに適用される標準 

メディア バイパス モード以外のデバイスのみをサポートするデバイスには、次の標準が適用されます。

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): セッション開始プロトコル
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). 信頼されたネットワーク内のアサートされた ID のセッション開始プロトコルへのプライベート拡張 - P-Asserted ID ヘッダーの処理に関するセクション。 ダイレクト ルーティングは、プライバシー ID ヘッダーを含む P-Asserted ID を送信します。 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) 必要な履歴情報のセッション開始プロトコル (SIP) の拡張。 詳細については、「ルーティング SIP プロトコルの説明」も参照してください。
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) セッション開始プロトコルReferred-Byメカニズム
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) セッション開始プロトコル (SIP) の "置換" ヘッダー 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) セッション開始プロトコル (SIP) オファー/回答モデルの使用。
  「RFC からの逸脱」セクションを参照してください。
- [RFC 3711](https://tools.ietf.org/html/rfc3711) および [RFC 4771](https://tools.ietf.org/html/rfc4771). SRTP を使用して RTP トラフィックを保護します。 SBC は、SDES を使用してキーを確立できる必要があります。 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) RTP/RTCP 多重化のセッション記述プロトコル(SDP)の提供/回答の明確化

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>メディア バイパス モードをサポートするデバイスに適用される標準

非バイパス モードに適用可能な標準に加えて、メディア バイパス モードには次の標準が使用されます。

- [メディア バイパスの RFC 5245 インタラクティブ接続確立 (ICE)](https://tools.ietf.org/html/rfc5245)  SBC は、次の機能をサポートする必要があります。
  - ICE Lite - Teamsクライアントは完全なICEクライアントです
  - [ICE が再起動します](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)。 ICE の再起動のユースケースと例の詳細については、「ICE Restart: メディア バイパスをサポートしていないエンドポイントに転送されたメディア バイパス コール」を参照してください。   
- [RFC RFC 5589 セッション開始プロトコル (SIP) コール制御 – 転送](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 セッション開始プロトコル (SIP) の初期メディアと着信音生成](https://tools.ietf.org/html/rfc3960)のセクション 3.1、フォーク、および 3.2、着信音生成を参照してください。 
- [NAT (STUN) の RFC 5389 セッション トラバーサル ユーティリティ](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 NAT (TURN) のリレーを使用したトラバーサル: NAT (STUN) のセッション トラバーサル ユーティリティへのリレー拡張](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>E911プロバイダーへの位置情報の伝達をサポートするための規格

- [RFC 6442,セッション開始プロトコルのロケーション搬送](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>RFC からの逸脱

次の表は、マイクロソフトの SIP またはメディア スタックの実装が標準から逸脱している RFC のセクションを示しています。

| RFC とセクション | 説明 | 偏差 |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337、セクション 5.3 メディアの保留と再開](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC は、"a=非アクティブ"、"a=sendonly"、a=recvonly" を使用してコールを保留にすることを許可します。 |SIP プロキシーは「a=非アクティブ」のみをサポートしており、SBC が「a=sendonly」または「a=recvonly」を送信するかどうかは認識しません。
| [RFC 6337、 セクション 5.4 "C=0.0.0.0 の SDP 受信時の動作](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) では、エージェントが接続アドレス 0.0.0.0 の SDP を受信できる必要があります。 | SIP プロキシはこのオプションをサポートしていません。 |

## <a name="operational-modes"></a>運用モード

ダイレクト ルーティングには、次の 2 つの操作モードがあります。

- すべての RTP トラフィックがTeams クライアント、メディア プロセッサ、および SBC 間を流れる **メディア バイパスがない** 場合。  

- **メディア バイパス** で、すべての RTP メディアがTeams エンドポイントと SBC の間を流れる。 

SIP トラフィックは常に SIP プロキシを経由して流れる点に注意してください。 

## <a name="dtmf"></a>DTMF
インバンド DTMF はメディア スタックでサポートされていません。
