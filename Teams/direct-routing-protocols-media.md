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
# <a name="overview"></a>概要

この記事では [、RFC 5245](https://tools.ietf.org/html/rfc5245)で説明されているとおり、直接ルーティングで ICE Lite に対してセッション ボーダー コントローラー (SBC) が有効になっているメディア バイパスをサポートする方法について説明します。 この記事は、オンプレミスの SBC と SIP プロキシ サービス間の接続の構成を担当する音声管理者を対象にしています。

この記事では、ICE Lite のシナリオの概要と相互運用性の要件について説明します。 この記事では、メッセージ形式と、信頼性の高い呼び出しとメディア フローを確保するために必要な状態マシンの遷移について説明します。

## <a name="terminology"></a>用語

- First Hello – 呼び出し元と呼び出し先が話す最初の単語。 ほとんどの場合、エンドポイントからの最初のパケットが確実に配信されるのを確実に確保するために、すべての努力が必要です。

- forking – 呼び出し先が複数のデバイスで使用できる場合は、呼び出し元からのオファーが複数の呼び出し先エンドポイントに配信される可能性があります (たとえば、Teams ユーザーが Windows の場合は Teams にサインインし、Android または iPhone の場合は Teams にサインインしている可能性があります)。

- Provisional Answer (183) - 通話設定を高速化するための呼び出し先エンドポイントは、メディア フローを確立するために必要な候補とキーを含む回答を送信します。 これは、ユーザーが特定の呼び出し先インスタンスからの呼び出し (200OK) に応答する可能性を予測して行われます。 forking を使用すると、呼び出し元は複数の仮回答を受け取る準備が整う必要があります。

- Re-Invite – ICE 制御エンドポイントによって選択された最終的な候補を含むオファー。 これには、複数のフォークを処理する競合状態を解決するための a=remote-candidate 属性があります。

- Teamsエンドポイント – サーバー (メディア プロセッサ、トランスポート リレー) またはクライアントTeamsできます。

## <a name="message-format"></a>メッセージ形式

このTeamsは、ICE-Lite 用の RFC 5245 に従います。 つまり、すべての STUN メッセージが [RFC 5389 に準拠します](https://tools.ietf.org/html/rfc5389)。

RFC 5389 で要求される SBC は、認識されない STUN 属性を無視し、既知の属性を持つメッセージを処理し続ける必要があります。 

不正な形式のパケットが受信された場合、メディア セッションの確立に影響を与えることなくパケットを破棄する必要があります。

## <a name="ice-lite-requirements"></a>ICE Lite の要件

このセクションでは、ICE Lite の要件について簡単に説明します。

### <a name="candidate-gathering"></a>候補者の集まり

SBC は、パブリックに到達可能な 1 つの候補のみを提供する必要があります。 現時点では、IPV4 候補だけがサポートされています。


#### <a name="connectivity-checks"></a>接続チェック

ICE Lite 実装は、受信した接続チェックに応答する必要があります。 ICE Lite エンドポイントは、接続チェック要求を送信できません。 (接続チェックが違反で送信された場合、実装全体が応答し、予期しないピア派生候補が検出され、呼び出しエラーが発生する可能性があります)。

#### <a name="nominations"></a>ノミネート

ICE 完全実装エンドポイントは常に制御エンドポイントであり、メディア フローに使用する最終的な候補を選択するための "通常" のノミネートに従います。 ICE Lite エンドポイントは、ノミネートを使用して、メディアおよび完全な通話確立に使用されるパスを終了できます。

注: 183 の暫定回答を送信するピア エンドポイントで forking を実行する場合、SBC は複数のエンドポイントからのチェックに応答する準備が整っている必要があります。また、200OK より前に指名が発生した場合は、複数のエンドポイントからのノミネートも行う必要があります。 ICE 状態マシンの最終パスとユーザー応答のタイミングの収束によっては、200OK の前または後にノミネートが発生する可能性があります。 SBC は両方のケースを処理できる必要があります。

#### <a name="converging-for-forking"></a>Forking の収束

SBC からのオファーが複数の Teams エンドポイントにフォークした場合、Teams エンドポイントは暫定回答で応答し、接続チェックを開始できます。 SBC は、接続チェックを受信し、複数のピア エンドポイントからの接続チェックに応答するために準備する必要があります。 たとえば、ユーザー Teamsデスクトップと携帯電話の両方にサインインできます。 両方のデバイスに受信呼び出しが通知され、SBC との接続チェックが試行されます。

最終的には、1 つのエンドポイントだけが呼び出しに応答します (200OK)。 200OK を受信すると、SBC はメディア パケットを処理する適切なコンテキストを設定できます。

## <a name="scenarios"></a>シナリオ

###  <a name="inbound-call-from-sbc"></a>SBC からの受信呼び出し

このシナリオでは、SBC が処理する必要があるいくつかの可能なピア エンドポイントがあります。

- サーバー エンドポイントは通常、200OK で直接応答します。 これらは、通常、ボイスメール、通話キュー、自動応答のシナリオに関係する完全な ICE エンドポイントです。

- クライアント エンドポイントは、異なる From/To タグ (183) に続いて、呼び出しに応答するエンドポイントから 200OK を使用して、複数の仮回答を送信できます。 これらは、通常、エンド ユーザー クライアントを表す完全な ICE エンドポイントです。

- その他の SBC エンドポイント。 これらは、通常、クライアント エンドポイントと別の電話番号を同時に呼び出すシナリオに関与する ICE Lite エンドポイントです。

SBC は、完全な ICE エンドポイントから受信した有効なすべての接続チェック要求に応答する必要があります。 RFC ごとに、完全な ICE エンドポイントが制御エンドポイントになります。 接続Teams (クライアント/サーバー) エンドポイントは、接続チェックを完了するために "通常" の要求を実行します。 最後の 200Ok は、早期メディアを送信したエンドポイントから送信するか、別のエンドポイントから送信できます。 200Ok を受信する場合、SBC はメディア フローに適切なコンテキストを設定する必要があります。 

###  <a name="early-media"></a>初期メディア

早期メディア フローがある場合、SBC はメディアのストリーミングを開始する最初のエンドポイントにラッチする必要があります。メディア フローは、候補者がノミネートされる前に開始できます。 SBC は、IVR/ボイスメールシナリオを有効にするには、このフェーズ中に DTMF を送信するためのサポートを持っている必要があります。 SBC は、ノミネートが完了していない場合にチェックを受け取った最も優先度の高いパスを使用する必要があります。

### <a name="outbound-call-to-sbc"></a>SBC への発信呼び出し

このTeamsエンドポイントは、このシナリオの呼び出し元であり、制御エンドポイントになります。 暫定回答 (183) または最終的な回答 (200OK) のいずれかを受け取った場合、Teams エンドポイントは接続チェックを開始し、"標準" のノミネートに進み、接続チェックを完了します。

注: SBC が暫定回答 (183) を送信する場合、SBC は接続チェック要求を受信し、200OK が SBC によって送信される前に、要求を完了する準備ができている必要があります。 200OK を受信する前にチェックやノミネートが完了した場合、200OK を受信した後、チェックやノミネートは再び実行されません。 SBC は、ICE 候補、パスワード、および ufrag (ユーザー名フラグメント) を 183 から 200 の間で変更しすることはできません。

早期メディアをサポートするために、SBC は、Teams エンドポイントによってノミネートが完了する前でも、受信した接続チェックに基づいて最も高い優先順位で、ピア ICE 候補へのメディアのストリーミングを開始できます。 SBC は、指名が完了するまで、Teamsに関するメディアを受け入れる必要があります。 候補がノミネートされた後、SBC は適切なコンテキストにリセットしてメディア パケットを送受信する必要があります。

## <a name="srtp-support-requirements"></a>SRTP のサポート要件

SBC は、次の形式でオファーと回答AES_CM_128_HMAC_SHA1_80 SRTP 暗号化暗号をサポートする必要があります。

```console
"inline:" <key||salt> ["|" lifetime]
```

SBC の SDP オファーの暗号属性の例を次に示します。

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

MKI パラメーターと Length パラメーターは必要ありません。

詳細については [、RFC 4568、セクション 6.1 を参照してください](https://tools.ietf.org/html/rfc4568#section-6.1)。

## <a name="sdes-support-requirements"></a>SDES サポート要件

デバイスは、以下で説明する形式で SDES を提供できる必要があります。 Microsoft Media Processors は常に SDES を好む。

- 非メディア バイパスでは、クライアントが DTLS のみをサポートしている場合でも、メディア プロセッサは SDES に変換されます。

- メディア バイパスでは、クライアントが DTLS のみ (将来の Google Chrome 状態) の場合、ダイレクト ルーティングはパスに MP を挿入し、メディア バイパスから非メディア バイパスに通話を変換します。 SBC とダイレクト ルーティングのメディア プロセッサ コンポーネントの間では、常に SDES が使用されます。

現時点では、DTLS のみをTeamsクライアントはありません。ただし、Google は、ある時点で SDES のサポートを停止すると発表しています。

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>バイパス モードでの SBC からのオファーの形式 

オファーには SDES が含まれている必要があります。また、次の形式で DTLS を省略可能に含めることもできます。

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>SBC に対する SDES を含む回答の形式

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Teams から SBC へのオファーの形式 

### <a name="format-for-sdes-only-offer-to-sbc"></a>SBC に対する SDES のみオファーの形式

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

