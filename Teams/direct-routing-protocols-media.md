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
description: ダイレクトルーティングプロトコル
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888576"
---
# <a name="overview"></a>概要

この記事では、 [RFC 5245](https://tools.ietf.org/html/rfc5245)で説明されているように、ダイレクトルーティングが氷用に有効になっているセッションボーダーコントローラー (SBC) でメディアバイパスをサポートする方法について説明します。 この記事は、オンプレミスの SBC と SIP プロキシサービス間の接続を構成する責任を負うボイス管理者を対象としています。

この記事では、ICE Lite のシナリオと相互運用性の要件の概要について説明します。 この記事では、信頼性の高い通話とメディアフローを実現するために、メッセージ形式と必要なステートマシンの移行について説明します。

## <a name="terminology"></a>用語

- 最初の Hello: 発信者と呼び出し先が最初に発声した単語。 エンドポイントからの最初のパケットがほとんどのユースケースで確実に配信されるように、すべての取り組みを行っておく必要があります。

- フォーク–発信者からのオファーが複数のデバイスで使用できる場合 (たとえば、チームユーザーが Windows 用の Teams や Android または iPhone のチームにサインインしている場合など)、複数の呼び出し元のエンドポイントに配信されることがあります。

- 仮応答 (183) –通話を高速化するための呼び出し先エンドポイントメディアフローを確立するために必要な候補とキーを使って応答を送信します。 これは、ユーザーが特定の呼び出し元インスタンスから呼び出し (200OK) に応答する可能性があることを想定して行われます。 Fork では、呼び出し元が複数の仮応答を受け取る準備ができている必要があります。

- 再招待-ICE を制御するエンドポイントによって最終的な候補が選択された申し出。 これには、a = リモート候補の属性があります。これにより、競合状態を解決して複数のフォークを処理することができます。

- Teams エンドポイント–これは、サーバー (メディアプロセッサ、トランスポートリレー)、または Teams クライアントのいずれかになります。

## <a name="message-format"></a>メッセージ形式

Teams インフラストラクチャは、ICE-Lite の RFC 5245 に従います。 これは、すべての STUN メッセージが[RFC 5389](https://tools.ietf.org/html/rfc5389)に準拠していることを意味します。

RFC 5389 が必要とする SBCs は、認識されないすべての STUN 属性を無視する必要があります。また、既知の属性を使ってメッセージを処理し続ける必要があります。 

不正なパケットを受信した場合、メディアセッションの確立に影響を与えることなく、パケットを破棄する必要があります。

## <a name="ice-lite-requirements"></a>ICE Lite の要件

このセクションでは、ICE Lite の要件について簡単に説明します。

### <a name="candidate-gathering"></a>候補の収集

SBC は、公開可能な候補を1つだけ提供する必要があります。 現時点では、IPV4 の候補者のみがサポートされています。


#### <a name="connectivity-checks"></a>接続チェック

ICE Lite の実装は、受け取った接続チェックに応答する必要があります。 ICE Lite エンドポイントは、接続チェック要求を送信しないでください。 (接続チェックが違反で送信された場合は、完全な実装が応答するため、予期しないピア派生候補が検出され、呼び出しの失敗が発生する可能性があります)。

#### <a name="nominations"></a>Nominations

ICE 完全実装のエンドポイントは、常に制御エンドポイントであり、メディアフローに使用する最終的な候補を選択するための "Regular" nominations に従います。 ICE Lite エンドポイントでは、nominations を使って、メディアと完全な通話の確立に使用されるパスを終了することができます。

注: ピアエンドポイントで183の仮応答を送信するようにフォークを行う場合、SBC は、複数のエンドポイントからのチェックに応答する準備ができていて、200 OK の前に nominations が発生した場合は、複数のエンドポイントから nominations する必要があります。 ユーザーが応答する最終的なパスとタイミングでの ICE ステートマシンの収束に応じて、nominations は200OK の前または後に発生する可能性があります。 SBC は両方のケースを処理できる必要があります。

#### <a name="converging-for-forking"></a>フォークのための収束

SBC のフォークから複数の Teams のエンドポイントに対して提供されている場合、チームのエンドポイントは、仮の応答に応答して接続チェックを開始することがあります。 SBC は、接続チェックを受け、複数のピアエンドポイントからの接続チェックに応答するために準備されている必要があります。 たとえば、Teams ユーザーは、デスクトップと携帯電話の両方にサインインしている可能性があります。 両方のデバイスに着信通話の通知が送信され、SBC で接続チェックが試行されます。

最終的に、通話に応答するのはエンドポイントの1つだけです (200OK)。 200OK を受け取ると、SBC はメディアパケットを処理するための適切なコンテキストを設定することができます。

## <a name="scenarios"></a>シナリオ

###  <a name="inbound-call-from-sbc"></a>SBC からの着信通話

このシナリオでは、SBC が処理しなければならないピアエンドポイントがいくつかあります。

- 通常、サーバーのエンドポイントは、200OK で直接応答します。 通常、ボイスメール、通話キュー、自動応答のシナリオに関連する完全な ICE エンドポイントです。

- クライアントのエンドポイントでは、異なる "From/To タグ (183)" を使用して、通話に応答するエンドポイントからの 200 OK を使って、複数の仮応答を送信できます。 通常は、エンドユーザークライアントを示す完全な ICE エンドポイントです。

- その他の SBC エンドポイント。 これらは通常、クライアントエンドポイントと別の電話番号を同時に呼び出してしまうシナリオに関連する、ICE Lite エンドポイントです。

SBC は、完全な氷エンドポイントから受け取った有効な接続確認要求すべてに応答する必要があります。 各 RFC では、完全な ICE エンドポイントがエンドポイントを制御します。 Teams (クライアント/サーバー) のエンドポイントは、接続チェックを完了するために "通常" の nominations を実行します。 最後の200Ok は、前のメディアを送信したエンドポイントか、別のエンドポイントからのどちらかになります。 200Ok の場合、SBC はメディアフローの適切なコンテキストを設定する必要があります。 

###  <a name="early-media"></a>初期のメディア

早いメディアフローが存在する場合、SBC は、ストリーミングメディアを開始する最初のエンドポイントにラッチする必要があります。メディアフローは、候補が指定される前に開始することができます。 このフェーズでは、IVR またはボイスメールシナリオを可能にするために DTMF の送信がサポートされている必要があります。 SBC では、nominations が完了していないかどうかを確認するために、最も優先度の高いパスを使用する必要があります。

### <a name="outbound-call-to-sbc"></a>SBC への発信通話

Teams のエンドポイントはこのシナリオの呼び出し元であり、制御するエンドポイントになります。 仮応答 (183) または最終回答 (200OK) を受け取ると、Teams のエンドポイントで接続チェックが開始され、"通常" の nominations に進み、接続チェックが完了します。

注: SBC が暫定応答 (183) を送信する場合、SBC は、接続確認要求を受信する準備ができていて、nominations を完了する前に、SBC によって200OK が送信される可能性があります。 200OK が受信される前にチェックまたは nominations が完了した場合、nominations は、200OK を受け取った後にもう一度実行されることはありません。 SBC は、183と200の間で ICE 候補、パスワード、および ufrag (ユーザー名フラグメント) を変更することはできません。

以前のメディアをサポートするために、SBC は、チームのエンドポイントによって nominations が完了する前であっても、受信した接続チェックに基づいて、最も優先度の高いメディアをピア氷候補にストリーミングすることができます。 SBC は、nominations が完了するまで、任意の候補者に対して Teams からメディアを受け取る必要があります。 候補が指定されると、SBC は、メディアパケットを送受信するために適切なコンテキストにリセットされる必要があります。

## <a name="srtp-support-requirements"></a>SRTP のサポート要件

SBC は、次の形式の AES_CM_128_HMAC_SHA1_80 の特典と回答について、SRTP 暗号化暗号をサポートしている必要があります。

```console
"inline:" <key||salt> ["|" lifetime]
```

SBC の SDP オファーの crypto 属性の例を次に示します。

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

MKI パラメーターと Length パラメーターは必要ありません。

詳細については、「 [RFC 4568、セクション6.1」](https://tools.ietf.org/html/rfc4568#section-6.1)を参照してください。

## <a name="sdes-support-requirements"></a>SDES のサポート要件

デバイスは、以下で説明する形式で SDES を提供できる必要があります。 Microsoft メディアプロセッサは、常に SDES を優先します。

- メディア以外のバイパスの場合、クライアントが DTLS のみをサポートしている場合でも、メディアプロセッサは SDES に変換されます。

- メディアバイパスの場合、クライアントが DTLS のみ (Google Chrome の今後の状態) である場合、ダイレクトルーティングはパスに MP を挿入します。これにより、メディアバイパスからメディア以外のバイパスへの呼び出しが変換されます。 直接ルーティングの SBC とメディアプロセッサコンポーネントの間では、常に SDES が使用されます。

現時点では、DTLS のみを提供している Teams クライアントはありません。ただし、一部の時点では、Google は SDES のサポートを停止することを発表しました。

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>使用している SBC のバイパスモードの書式 

Offer は SDES を含んでいる必要があります。また、次の形式の DTLS オプションを含めることができます。

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>SDES と SBC を含む応答の書式を設定する

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Teams から SBC へのオファーの書式設定 

### <a name="format-for-sdes-only-offer-to-sbc"></a>SDES でのみ使用できる形式

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

