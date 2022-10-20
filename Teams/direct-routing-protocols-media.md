---
title: 電話システムダイレクト ルーティングの概要
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: hHw ダイレクト ルーティングでは、ICE Lite に対してセッション ボーダー コントローラーが有効になっているメディア バイパスがサポートされます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e6f9715ee410116a66c572522a910cd16ef27154
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614420"
---
# <a name="overview"></a>概要

この記事では、 [RFC 5245](https://tools.ietf.org/html/rfc5245) で説明されているように、ICE Lite に対してセッション ボーダー コントローラー (SBC) が有効になっているメディア バイパスをダイレクト ルーティングでサポートする方法について説明します。 この記事は、オンプレミスの SBC と SIP プロキシ サービスの間の接続の構成を担当する音声管理者を対象としています。

この記事では、ICE Lite のシナリオと相互運用性に関する要件の概要について説明します。 この記事では、信頼性の高い呼び出しとメディア フローを確保するためのメッセージ形式と必要なステート マシンの切り替えについて説明します。

## <a name="terminology"></a>用語

- First Hello – 呼び出し元と呼び出し先が話す最初の単語。 ほとんどのユース ケースでエンドポイントからの最初のパケットが確実に配信されるように、すべての取り組みが行われるようにすることが重要です。

- フォーク – 呼び出し先が複数のデバイスで使用できる場合は、呼び出し元からのオファーが複数の呼び出し先エンドポイントに配信される可能性があります (たとえば、Teams ユーザーが Teams for Windows と Teams for Android または iPhone にサインインしている可能性があります)。

- 仮回答 (183) – 通話のセットアップを高速化するための呼び出し先エンドポイントは、メディア フローを確立するために必要な候補とキーを含む回答を送信します。 これは、その特定の呼び出し先インスタンスからの呼び出し (200OK) に応答する可能性があるユーザーを想定して行われます。 フォークを使用すると、呼び出し元は複数の暫定的な回答を受け取る準備が整う必要があります。

- Re-Invite – ICE 制御エンドポイントによって選択された最終的な候補を含むオファー。 これには、複数のフォークを処理する競合状態を解決するための a=remote-candidate 属性があります。

- Teams エンドポイント – これは、サーバー (メディア プロセッサ、トランスポート リレー) または Teams クライアントのいずれかです。

## <a name="message-format"></a>メッセージ形式

Teams インフラストラクチャは、ICE-Lite の RFC 5245 に従います。 これは、すべての STUN メッセージが [RFC 5389](https://tools.ietf.org/html/rfc5389) に準拠することを意味します。

RFC 5389 で必要とされる SBC は、認識しない STUN 属性を無視し、既知の属性を使用してメッセージを処理し続ける必要があります。 

不正な形式のパケットを受信した場合は、メディア セッションの確立に影響を与えずにパケットを破棄する必要があります。

## <a name="ice-lite-requirements"></a>ICE Lite の要件

このセクションでは、ICE Lite の要件を簡単に取り上げます。

### <a name="candidate-gathering"></a>候補の収集

SBC は、1 つの候補のみを提供する必要があります。 現在、IPV4 候補のみがサポートされています。


#### <a name="connectivity-checks"></a>接続チェック

ICE Lite 実装は、受信した接続チェックに応答する必要があります。 ICE Lite エンドポイントは、接続チェック要求を送信しないでください。 (接続チェックが違反で送信された場合、完全な実装が応答し、予期しないピア派生候補が検出され、呼び出しエラーが発生する可能性があります)。

#### <a name="nominations"></a>ノミネート

ICE 完全実装エンドポイントは常に制御エンドポイントであり、メディア フローに使用する最終的な候補を選択するための "Regular" ノミネーションに従います。 ICE Lite エンドポイントは、ノミネーションを使用して、メディアに使用されるパスを終了し、通話の確立を完了できます。

注: 183 個の暫定的な回答を送信するピア エンドポイントを使用してフォークする場合、SBC は複数のエンドポイントからのチェックに応答する準備が整っている必要があります。また、200OK より前に指名が行われる場合は、複数のエンドポイントからの指名にも対応できる必要があります。 最終的なパス上の ICE ステート マシンの収束と、ユーザーが回答するタイミングに応じて、200OK の前または後にノミネーションが発生する可能性があります。 SBC は両方のケースを処理できる必要があります。

#### <a name="converging-for-forking"></a>フォークの収束

SBC フォークから複数の Teams エンドポイントへのオファーの場合、Teams エンドポイントは暫定的な回答で応答し、接続チェックを開始できます。 SBC は、接続チェックを受け取り、複数のピア エンドポイントからの接続チェックに応答するように準備する必要があります。 たとえば、Teams ユーザーはデスクトップと携帯電話の両方にサインオンできます。 どちらのデバイスも受信呼び出しの通知を受け取り、SBC との接続チェックを試行します。

最終的には、1 つのエンドポイントのみが呼び出しに応答します (200OK)。 200OK を受信すると、SBC はメディア パケットを処理するための適切なコンテキストを設定できます。

## <a name="scenarios"></a>シナリオ

###  <a name="inbound-call-from-sbc"></a>SBC からの受信呼び出し

このシナリオでは、SBC で処理する必要があるピア エンドポイントがいくつかあります。

- 通常、サーバー エンドポイントは 200OK で直接応答します。 これらは、ボイスメール、通話キュー、自動応答のシナリオに通常関係する完全な ICE エンドポイントです。

- クライアント エンドポイントは、異なる差出人タグ (183) を持つ複数の仮回答を送信し、その後に呼び出しに応答するエンドポイントから 200OK を送信できます。 これらは通常、エンド ユーザー クライアントを表す完全な ICE エンドポイントです。

- その他の SBC エンドポイント。 これらは、通常、クライアント エンドポイントと別の電話番号を同時に呼び出すシナリオに関係する ICE Lite エンドポイントです。

SBC は、完全な ICE エンドポイントから受信したすべての有効な接続チェック要求に応答する必要があります。 RFC ごとに、完全な ICE エンドポイントが制御エンドポイントになります。 Teams (クライアント/サーバー) エンドポイントは、接続チェックを完了するために "通常" の指名を実行します。 最後の 200Ok は、初期メディアを送信したエンドポイントから、または別のエンドポイントから行うことができます。 200Ok を受信すると、SBC はメディア フローに適したコンテキストを設定する必要があります。 

###  <a name="early-media"></a>初期メディア

初期メディア フローがある場合、SBC は、メディアのストリーミングを開始する最初のエンドポイントにラッチする必要があります。メディア フローは、候補が指名される前に開始できます。 SBC では、IVR/ボイスメールシナリオを有効にするために、このフェーズ中に DTMF を送信するサポートが必要です。 SBC は、ノミネーションが完了していない場合にチェックを受けた優先度の高いパスを使用する必要があります。

### <a name="outbound-call-to-sbc"></a>SBC への送信呼び出し

Teams エンドポイントは、このシナリオの呼び出し元であり、制御エンドポイントになります。 仮回答 (183) または最終回答 (200OK) を受け取ると、Teams エンドポイントは接続チェックを開始し、"標準" の指名に進んで接続チェックを完了します。

注: SBC から暫定的な回答 (183) が送信された場合、SBC は接続チェック要求を受け取り、200OK が SBC によって送信される前に指名を完了する準備が整っている必要があります。 200OK を受け取る前にチェックやノミネーションが完了した場合、200OK を受信した後は、チェックやノミネーションは再度実行されません。 SBC では、ICE 候補、パスワード、および ufrag (ユーザー名フラグメント) を 183 から 200 の間で変更しないでください。

初期メディアをサポートするために、SBC は、Teams エンドポイントによってノミネーションが完了する前であっても、受信した接続チェックに基づいて優先度が最も高いピア ICE 候補へのメディアのストリーミングを開始できます。 SBC は、指名が完了するまで、任意の候補者の Teams からのメディアを期待する必要があります。 候補が指定されたら、SBC はメディア パケットを送受信するために適切なコンテキストにリセットする必要があります。

## <a name="srtp-support-requirements"></a>SRTP サポート要件

SBC では、オファーと回答の SRTP 暗号化暗号AES_CM_128_HMAC_SHA1_80を次の形式でサポートする必要があります。

```console
"inline:" <key||salt> ["|" lifetime]
```

SBC からの SDP オファーの暗号化属性の例を次に示します。

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

MKI パラメーターと Length パラメーターは必要ありません。

詳細については、 [RFC 4568 のセクション 6.1 を](https://tools.ietf.org/html/rfc4568#section-6.1)参照してください。

## <a name="sdes-support-requirements"></a>SDES サポート要件

デバイスは、次に示す形式で SDES を提供できる必要があります。 Microsoft Media Processors は常に SDES を優先します。

- メディア以外のバイパスでは、クライアントが DTLS のみをサポートしている場合でも、メディア プロセッサは SDES に変換されます。

- メディア バイパスでは、クライアントが DTLS のみ (将来の Google Chrome 状態) の場合、ダイレクト ルーティングによってパスに MP が挿入され、メディア バイパスからの呼び出しがメディア バイパスからメディア以外のバイパスに変換されます。 ダイレクト ルーティングの SBC とメディア プロセッサ コンポーネントの間では、SDES が常に使用されます。

現時点では、DTLS のみを提供する Teams クライアントはありません。ただし、Google は、ある時点で SDES のサポートを停止すると発表しました。

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>バイパス モードでの SBC からのオファーの形式 

オファーには SDES が含まれている必要があり、次の形式で DTLS を省略可能に含めることができます。

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>SBC への SDES を含む回答の形式

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Teams から SBC へのオファーの形式 

### <a name="format-for-sdes-only-offer-to-sbc"></a>SBC に対する SDES のみのオファーの形式

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

