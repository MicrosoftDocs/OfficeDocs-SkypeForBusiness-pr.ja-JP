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
ms.openlocfilehash: 04e9507595ef721ced5d47eb58646559601c5cab
ms.sourcegitcommit: 8750f98d59e74e3835d762d510fb0e038c8f17eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899128"
---
# <a name="direct-routing---sip-protocol"></a>ダイレクト ルーティング - SIP プロトコル

この記事では、ダイレクト ルーティングでセッション開始プロトコル (SIP) を実装する方法について説明します。 セッション ボーダー コントローラー (SBC) と SIP プロキシの間でトラフィックを適切にルーティングするには、一部の SIP パラメーターに特定の値が必要です。 この記事は、オンプレミスの SBC と SIP プロキシ サービス間の接続の構成を担当する音声管理者を対象にしています。

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>受信要求の処理: テナントとユーザーの検索

着信または送信呼び出しを処理する前に、SIP プロキシと SBC の間で OPTIONS メッセージが交換されます。 これらの OPTIONS メッセージにより、SIP プロキシは SBC に許可される機能を提供できます。 OPTIONS ネゴシエーションが成功し (200OK 応答)、SBC と SIP プロキシ間の通信を可能にし、呼び出しを確立することが重要です。 SIP プロキシへの OPTIONS メッセージの SIP ヘッダーを次の例に示します。

| パラメーター名 | 値の例 | 
| :---------------------  |:---------------------- |
| Request-URI | OPTIONS sip:sip.pstnhub.microsoft.com:5061 SIP /2.0 |
| ヘッダー経由 | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards ヘッダー | Max-Forwards:68 |
| ヘッダーから | From Header From: <sip:sbc1.adatum.biz:5058> |
| To Header | 宛先： <sip:sip.pstnhub.microsoft.com:5061> |
| CSeq ヘッダー | CSeq: 1 INVITE | 
| 連絡先ヘッダー | 連絡先: <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> SIP ヘッダーには、使用されている SIP URI に userinfo が含まれています。 RFC [3261、セクション 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1)のように、URI の userinfo 部分は省略可能であり、宛先ホストにユーザーの考え方が存在しない場合や、hosst 自体が識別されるリソースである場合は存在しない場合があります。 @ 記号が SIP URI に存在する場合、ユーザー フィールドは空にすることはできません (MUST NOT)。

着信呼び出しでは、SIP プロキシは、呼び出しの宛先であるテナントを検索し、このテナント内の特定のユーザーを見つける必要があります。 テナント管理者は、複数のテナントで非 DID 番号 (+1001 など) を構成できます。 そのため、複数の組織または組織で DID 以外の番号が同じになる可能性があるため、番号検索を実行する特定のテナントを見Microsoft 365重要Office 365。  

このセクションでは、SIP プロキシがテナントとユーザーを検索し、受信接続で SBC の認証を実行する方法について説明します。

着信通話での SIP 招待メッセージの例を次に示します。

| パラメーター名 | 値の例 | 
| :---------------------  |:---------------------- |
| Request-URI | SIP sip:+18338006777@sip.pstnhub.microsoft.com /2.0 を招待する |
| ヘッダー経由 | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards ヘッダー | Max-Forwards:68 |
| ヘッダーから | From Header From: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| To Header | To: sip:+183338006777@sbc1.adatum.biz | 
| CSeq ヘッダー | CSeq: 1 INVITE | 
| 連絡先ヘッダー | 連絡先: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls> | 

招待を受信すると、SIP プロキシは次の手順を実行します。

1. 証明書を確認します。 最初の接続では、ダイレクト ルーティング サービスは、Contact ヘッダーに表示される FQDN 名を受け取り、提示された証明書の共通名またはサブジェクトの代替名と一致します。 SBC 名は、次のいずれかのオプションと一致する必要があります。

   - オプション 1。 Contact ヘッダーに表示される完全な FQDN 名は、提示された証明書の共通名/サブジェクトの代替名と一致する必要があります。  

   - オプション 2. 連絡先ヘッダーに表示される FQDN 名のドメイン部分 (FQDN 名 sbc1.adatum.biz の adatum.biz など) は、共通名/サブジェクトの代替名 (*.adatum.biz など) のワイルドカード値と一致する必要があります。

2. Contact ヘッダーに表示される完全な FQDN 名を使用してテナントを検索してみてください。  

   連絡先ヘッダー (sbc1.adatum.biz) の FQDN 名が、任意の組織または組織の DNS Microsoft 365登録Office 365します。 見つかった場合、ユーザーの参照は、SBC FQDN がドメイン名として登録されているテナントで実行されます。 見つからない場合は、手順 3 が適用されます。   

3. 手順 3 は、手順 2 が失敗した場合にのみ適用されます。 

   [連絡先] ヘッダー (FQDN: sbc12.adatum.biz、ホスト部分を削除した後に adatum.biz) に表示されている FQDN からホスト部分を削除し、この名前が Microsoft 365 または Office 365 組織の DNS 名として登録されていないか確認します。 見つかった場合、ユーザー参照は、このテナントで実行されます。 見つからない場合、呼び出しは失敗します。

4. 要求 URI に示されている電話番号を使用して、手順 2 または 3 で見つかったテナント内で逆引き番号参照を実行します。 表示された電話番号を、前の手順で見つかったテナント内のユーザー SIP URI と一致します。

5. トランク設定を適用します。 この SBC のテナント管理者によって設定されたパラメーターを見つける。

   Microsoft は、Microsoft SIP プロキシとペアの SBC の間にサードパーティの SIP プロキシまたはユーザー エージェント サーバーを持つことをサポートしません。これは、ペアの SBC によって作成された要求 URI を変更する可能性があります。

   1 つの SBC が多数のテナント (運送業者のシナリオ) に相互接続されているシナリオに必要な 2 つの参照 (手順 2 と 3) の要件については、この記事の後半で説明します。

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>連絡先ヘッダーと要求 URI の詳細な要件

#### <a name="contact-header"></a>連絡先ヘッダー

Microsoft SIP プロキシへのすべての着信 SIP メッセージ (オプション、招待) について、Contact ヘッダーには、URI ホスト名にペアの SBC FQDN が必要です。

構文: 連絡先: <sip:phone または sip address@FQDN SBC;transport=tls> 

RFC [3261、セクション 11.1](https://tools.ietf.org/html/rfc3261#section-11.1)のように、連絡先ヘッダー フィールドが OPTIONS メッセージに表示される場合があります。 [ダイレクト ルーティング] では、連絡先ヘッダーが必要です。 上記の形式の INVITE メッセージの場合、OPTIONS メッセージの場合、userinfo を SIP URI から削除し、次のように形式で送信された FQDN のみを削除できます。

構文: Contact: <SBC;transport=tls の sip:FQDN>

この名前 (FQDN) は、提示された証明書の [共通名] フィールドまたは [サブジェクトの代替名] フィールドにも含まれる必要があります。 Microsoft では、証明書の [共通名] フィールドまたは [サブジェクトの代替名] フィールドで、名前のワイルドカード値の使用をサポートしています。   

ワイルドカードのサポートについては [、RFC 2818、セクション 3.1 で説明されています](https://tools.ietf.org/html/rfc2818#section-3.1)。 具体的には：

*"名前には、単一のドメイン名コンポーネントまたはコンポーネント フラグメントと一致すると見なされるワイルドカード \* 文字が含まれている可能性があります。例: .a.com は foo.a.com と一致 bar.foo.a.com。f .com は foo.com 一致しますが \* \* 、bar.com。*

SIP メッセージに表示される Contact ヘッダーの複数の値が SBC によって送信される場合、Contact ヘッダーの最初の値の FQDN 部分だけが使用されます。

直接ルーティングの経験則として、FQDN を使用して IP ではなく SIP URI を設定することが重要です。 ホスト名は FQDN ではなく IP で表され、接続は 403 Forbidden で拒否されます。

#### <a name="request-uri"></a>Request-URI 

すべての着信呼び出しで、要求 URI を使用して、電話番号をユーザーに一致します。   

現在、次の例に示すように、電話番号にはプラス記号 (+) が含まれている必要があります。 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a>連絡先とRecord-Routeに関する考慮事項

SIP プロキシは、新しいダイアログ内クライアント トランザクション (Bye や Re-Invite など) と SIP オプションに応答するときに、次ホップ FQDN を計算する必要があります。 [連絡先] または [Record-Routeが使用されます。 

RFC [3261、セクション 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)に従って、新しいダイアログが発生する可能性があるすべての要求に Contact ヘッダーが必要です。 このRecord-Routeは、プロキシがダイアログ内の将来の要求のパスにとどまる必要がある場合にのみ必要です。 プロキシ SBC が直接ルーティング用[](./direct-routing-media-optimization.md)のローカル メディア最適化で使用されている場合、プロキシ SBC がルート内に残る必要がある場合、レコード ルートを構成する必要があります。 

プロキシ SBC が使用されていない場合は、Contact ヘッダーのみを使用してください。

- [RFC 3261、セクション 20.30、Record-Route](https://tools.ietf.org/html/rfc3261#section-20.30)では、プロキシがダイアログ内の将来の要求のパスにとどまる場合に使用されます。これは、すべてのトラフィックが Microsoft SIP プロキシとペアの SBC の間を行く際にプロキシ SBC が構成されていない場合は必須ではありません。 

- Microsoft SIP プロキシは、送信 ping オプションを送信するときに、(レコード ルートではなく) 連絡先ヘッダーのみを使用して次ホップを決定します。 2 つのパラメーター (Contact と Record-Route) の代わりに 1 つのパラメーター (Contact) のみを構成すると、プロキシ SBC が使用されていない場合の管理が簡略化されます。 

次ホップを計算するために、SIP プロキシは次を使用します。

- 優先順位 1。 トップ レベルのレコード ルート。 トップ レベルのドメインRecord-Route FQDN 名が含まれている場合は、FQDN 名を使用して、ダイアログ内の送信接続が確立されます。

- 優先度 2. 連絡先ヘッダー。 存在Record-Route場合、SIP プロキシは Contact ヘッダーの値を参照して送信接続を確立します。 (推奨される構成です)。

連絡先と連絡先の両方Record-Route使用する場合、SBC 管理者は値を同じにする必要があります。この場合、管理オーバーヘッドが発生します。 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>連絡先または連絡先で FQDN 名を使用Record-Route

IP アドレスの使用は、連絡先または連絡先Record-Routeサポートされていません。 サポートされているオプションは FQDN のみです。これは、SBC 証明書の共通名またはサブジェクトの代替名と一致する必要があります (証明書のワイルドカード値がサポートされています)。

- IP アドレスが [レコード ルート] または [連絡先] に表示されている場合、証明書のチェックは失敗し、呼び出しは失敗します。

- FQDN が提示された証明書の共通またはサブジェクトの代替名の値と一致しない場合、呼び出しは失敗します。 

## <a name="inbound-call-sip-dialog-description"></a>着信呼び出し: SIP ダイアログの説明

次の表は、呼び出しフローの違いと、バイパスモード以外とバイパス モードの類似点をまとめたものです。

| パラメーター名 | バイパスモード以外 | バイパス モード
| :---------------------  |:---------------------- |:----------------|
| 183 および 200 件のメッセージからのメディア候補 | メディア プロセッサ | クライアント | 
| SBC が受信できる 183 メッセージの数 | セッションごとに 1 つ | 複数 | 
| 呼び出しは、暫定応答を使用して行えます (183) | はい | はい |
| 呼び出しは、仮回答なしで行えます (183) | はい | はい |

###  <a name="non-media-bypass-flow"></a>メディア以外のバイパス フロー

1 Teamsユーザーが同時に複数のエンドポイントを持つ場合があります。 たとえば、Teams クライアントWindows、Teams クライアントiPhone Teams 電話 (Android Teams) を使用します。 各エンドポイントは、次のように HTTP の残りを示す場合があります。

-   通話の進行状況 – SIP プロキシによって SIP メッセージ 180 に変換されます。 メッセージ 180 を受信する場合、SBC はローカル呼び出し音を生成する必要があります。

-   メディア応答 – SIP プロキシによって、セッション記述プロトコル (SDP) のメディア候補を含むメッセージ 183 に変換されます。 メッセージ 183 を受信すると、SBC は SDP メッセージで受信したメディア候補に接続する必要があります。 

    > [!NOTE]
    > 場合によっては、メディアの回答が生成されない可能性があります。また、エンド ポイントが "受け入れ呼び出し" メッセージで応答する場合があります。

-   呼び出しは受け入れ可能です。SDP を使用して SIP プロキシによって SIP メッセージ 200 に変換されます。 メッセージ 200 を受信すると、SBC は、提供された SDP 候補とメディアを送受信する必要があります。

    > [!NOTE]
    > ダイレクト ルーティングでは、遅延オファー招待 (SDP を使用しない招待) はサポートされていません。

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>複数のエンドポイントが仮回答で呼び出される

1.  SBC から最初の招待を受信すると、SIP プロキシは "SIP SIP/2.0 100 Trying" というメッセージを送信し、すべてのエンド ユーザー エンドポイントに着信通話について通知します。 

2.  通知すると、各エンドポイントが呼び出し音を鳴らして、SIP プロキシに "通話の進行状況" メッセージを送信します。 1 人のTeams複数のエンドポイントを持つ可能性がある場合、SIP プロキシは複数の通話進行状況メッセージを受信する可能性があります。

3.  クライアントから受信した通話の進行状況メッセージごとに、SIP プロキシは通話の進行状況メッセージを SIP メッセージ "SIP SIP/2.0 180 Trying" に変換します。 このようなメッセージを送信する間隔は、呼び出しコントローラーからのメッセージを受信する間隔によって定義されます。 次の図では、SIP プロキシによって 2 つの 180 メッセージが生成されています。 これらのメッセージは、ユーザーの 2 Teamsエンドポイントから送信されます。 クライアントは、それぞれ一意のタグ ID を持っています。  別のエンドポイントから送信されるメッセージは、個別のセッションになります ("To" フィールドのパラメーター "tag" は異なります)。 ただし、次の図に示すように、エンドポイントによってメッセージ 180 が生成され、メッセージ 183 が送信されない場合があります。

4.  エンドポイントがエンドポイントのメディア候補の IP アドレスを含む Media Answer メッセージを生成すると、SIP プロキシは、受信したメッセージを"SIP 183 Session Progress" メッセージに変換し、クライアントから SDP をメディア プロセッサから SDP に置き換えます。 次の図では、Fork 2 のエンドポイントが呼び出しに応答しました。 トランクがバイパスされていない場合、183 SIP メッセージは 1 回だけ生成されます (リング ボットまたはクライアント エンドポイント)。 183 は、既存のフォークに接続されている場合や、新しいフォークを開始する場合があります。

5.  通話受け入れメッセージが、呼び出しを受け入れるエンドポイントの最終的な候補と一緒に送信されます。 通話受け入れメッセージは SIP メッセージ 200 に変換されます。 

> [!div class="mx-imgBorder"]
> ![複数のエンドポイントが仮回答で呼び出されている図](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>複数のエンドポイントが、暫定応答なしで呼び出し音を鳴らしている

1.  SBC から最初の招待を受信すると、SIP プロキシは "SIP SIP/2.0 100 Trying" というメッセージを送信し、すべてのエンド ユーザー エンドポイントに着信通話について通知します。 

2.  通知すると、各エンドポイントが呼び出しを開始し、"通話の進行状況" というメッセージを SIP プロキシに送信します。 1 人のTeams複数のエンドポイントを持つ可能性がある場合、SIP プロキシは複数の通話進行状況メッセージを受信する可能性があります。

3.  クライアントから受信した通話の進行状況メッセージごとに、SIP プロキシは通話の進行状況メッセージを SIP メッセージ "SIP SIP/2.0 180 Trying" に変換します。  メッセージを送信する間隔は、通話コントローラーからメッセージを受信する間隔によって定義されます。 次の図では、SIP プロキシによって生成された 2 つの 180 メッセージがあります。つまり、ユーザーは 3 つの Teams クライアントにログインし、各クライアントは通話の進行状況を送信します。 すべてのメッセージは個別のセッションになります ("To" フィールドのパラメーター "tag" は異なります)。

4.  通話受け入れメッセージが、呼び出しを受け入れるエンドポイントの最終的な候補と一緒に送信されます。 通話受け入れメッセージは SIP メッセージ 200 に変換されます。 

> [!div class="mx-imgBorder"]
> ![暫定応答なしで呼び出される複数のエンドポイントを示す図](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>メディア バイパス フロー

メディア バイパス シナリオでは、同じメッセージ (100 Trying、180、183) が使用されます。 

次のスキーマは、バイパス呼び出しフローの例を示しています。 

> [!NOTE]
> メディア候補は、さまざまなエンドポイントから取得できます。 

> [!div class="mx-imgBorder"]
> ![複数のエンドポイントが仮回答で呼び出されている図](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>置換オプション

SBC では、Invite with Replaces をサポートする必要があります。

## <a name="size-of-sdp-considerations"></a>SDP の考慮事項のサイズ

ダイレクト ルーティング インターフェイスは、1,500 バイトを超える SIP メッセージを送信する場合があります。  SDP のサイズは主にこれが原因です。 ただし、SBC の背後に UDP トランクがある場合は、メッセージが Microsoft SIP プロキシから変更されていないトランクに転送される場合、メッセージを拒否する可能性があります。 メッセージを UDP トランクに送信するときに、SBC の SDP で一部の値を除去する方法をお勧めします。 たとえば、ICE 候補や未使用のコーデックは削除できます。

## <a name="call-transfer"></a>通話転送

ダイレクト ルーティングでは、呼び出し転送の 2 つの方法がサポートされています。

- オプション 1。 SIP プロキシ プロセス クライアントからローカルに参照し、RFC 3892 のセクション 7.1 で説明されているレフリーとして機能します。

  このオプションを使用すると、SIP プロキシは転送を終了し、新しい招待を追加します。 


- オプション 2. SIP プロキシは、「SBC を参照する」を送信し、RFC 5589 のセクション 6 で説明する Transferor として機能します。

  このオプションを使用すると、SIP プロキシは SBC の参照を送信し、SBC が転送を完全に処理する必要があります。

SIP プロキシは、SBC によって報告される機能に基づいてメソッドを選択します。 SBC がメソッド "Refer" をサポートしている場合、SIP プロキシはオプション 2 を呼び出し転送に使用します。

Refer メソッドがサポートされているメッセージを送信する SBC の例を次に示します。

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

SBC がサポートされている方法として参照する方法を示さなかった場合、ダイレクト ルーティングではオプション 1 が使用されます (SIP プロキシはレフリーとして機能します)。 SBC は、Notify メソッドをサポートしているという通知も必要です。

Refer メソッドがサポートされていないことを示す SBC の例:

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>SIP プロキシ プロセス クライアントからローカルに参照し、レフリーとして機能する

SBC が Refer メソッドがサポートされていないと示した場合、SIP プロキシはレフリーとして機能します。 

クライアントから送信される Refer 要求は、SIP プロキシで終了します。 (次の図では、クライアントからの Refer 要求が "Dave への転送を呼び出す" と表示されます。  詳細については [、RFC 3892](https://www.ietf.org/rfc/rfc3892.txt)のセクション 7.1 を参照してください。 

> [!div class="mx-imgBorder"]
> ![複数のエンドポイントが仮回答で呼び出されている図](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>SIP プロキシは、SBC を参照し、Transferor として機能します。

これは呼び出し転送に推奨される方法であり、メディア バイパス認定を求めているデバイスには必須です。 SBC が Refer を処理できない場合の呼び出し転送は、メディア バイパス モードではサポートされていません。 

標準については、RFC 5589 のセクション 6 で説明されています。 関連する RFC は次のとおりです。

- [セッション開始プロトコル (SIP) 呼び出し制御 - 転送](https://tools.ietf.org/html/rfc5589)

- [セッション開始プロトコル (SIP) "Replaces" ヘッダー](https://tools.ietf.org/html/rfc3891)

- [セッション開始プロトコル (SIP) "参照者" メカニズム](https://tools.ietf.org/html/rfc3892)

このオプションは、SIP プロキシが Transferor として機能し、参照メッセージを SBC に送信すると想定しています。 SBC は Transferee として機能し、転送の新しいオファーを生成する参照を処理します。 次の 2 つのケースが考えられる。

- 通話は外部 PSTN 参加者に転送されます。 
- この呼び出しは、SBC Teams同じテナント内Teams別のユーザーに転送されます。 

SBC を介して呼び出しが Teams ユーザー間で転送された場合、SBC は、参照メッセージで受信した情報を使用して転送ターゲット (Teams ユーザー) に対して新しい招待 (新しいダイアログを開始) を発行する予定です。 

要求のトランザクションの To/Transferor フィールドを内部的に設定するには、SIP プロキシが REFER-TO/REFERRED-BY ヘッダー内でこの情報を伝達する必要があります。 

SIP プロキシは、ホスト名内の SIP プロキシ FQDN と次のいずれかで構成される SIP URI として REFER-TO を形成します。

- 転送先が電話番号である場合、URI のユーザー名部分の E.164 電話番号。

- x-m パラメーターと x-t パラメーターで、それぞれ完全転送ターゲットのターゲットのサイズとテナント ID をエンコードします。 

REFERRED-BY ヘッダーは、次の表に示すように、転送者のテナント ID と他の転送コンテキスト パラメーターに加え、転送子の URI がエンコードされた SIP URI です。

| パラメーター | 値 | 説明 |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | [PDF] | CC によって設定された転送子/転送ターゲットの完全な PDF |
| x-t | テナント ID | x-t Tenant ID Optional Tenant ID as populated by CC |
| x-ti | Transferor の関連付け ID | 転送者への呼び出しの関連付け ID |
| x-tt | 転送先の呼び出し URI | エンコードされた呼び出し置換 URI |

この場合、Refer Header のサイズは最大 400 シンボルです。 SBC は、最大 400 シンボルのサイズの Refer メッセージの処理をサポートする必要があります。

> [!div class="mx-imgBorder"]
> ![複数のエンドポイントが仮回答で呼び出されている図](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>セッション タイマー

SIP プロキシは、バイパス以外の呼び出しでセッション タイマーをサポート (常に提供) しますが、バイパス呼び出しでは提供しません。 SBC によるセッション タイマーの使用は必須ではありません。

##  <a name="use-of-request-uri-parameter-userphone"></a>Request-URI パラメーター user=phone の使用

SIP プロキシは要求 URI を分析し、user=phone パラメーターが存在する場合、サービスは要求 URI を電話番号として処理し、その番号をユーザーに照合します。 パラメーターが存在しない場合、SIP プロキシはヒューリスティックを適用して、要求 URI ユーザーの種類 (電話番号または SIP アドレス) を決定します。

通話設定プロセスを簡略化するために、常に user=phone パラメーターを適用してください。

## <a name="history-info-header"></a>History-Info ヘッダー

History-Info ヘッダーは、SIP 要求のターゲットを変更するために使用され、"ネットワークとエンド ユーザー向けのさまざまなサービスを有効にするための要求履歴情報をキャプチャするための標準的なメカニズムを提供します"。 詳細については [、RFC 4244 – セクション 1.1 を参照してください](http://www.ietf.org/rfc/rfc4244.txt)。 システムMicrosoft 電話、このヘッダーは、Simulring および Call Forwarding のシナリオで使用されます。  

送信する場合、History-Info有効になります。

- SIP プロキシは、PSTN コントローラーに送信される History-Info ヘッダーを構成する個々の History-Info エントリに、関連付けられている電話番号を含むパラメーターを挿入します。  電話番号パラメーターを持つエントリのみを使用して、PSTN コントローラーは新しい History-Info ヘッダーを再構築し、SIP プロキシ経由で SIP トランク プロバイダーに渡します。

- History-Info呼び出し転送の場合、同時呼び出しヘッダーが追加されます。

- History-Info転送の場合、ヘッダーは追加されません。

- 再構築された History-Info ヘッダーの個々の履歴エントリには、URI のホスト部分として設定された直接ルーティング FQDN (sip.pstnhub.microsoft.com) と組み合わせて指定された電話番号パラメーターがあります。'user=phone' のパラメーターは、SIP URI の一部として追加されます。  元の History-Info ヘッダーに関連付けられているその他のパラメーター (電話コンテキスト パラメーターを除く) は、構築しHistory-Infoされます。  

  > [!NOTE]
  > プライベート (RFC 4244 のセクション 3.3 で定義されているメカニズムによって決定される) エントリは、SIP トランク プロバイダーが信頼されたピアなので、この方法で転送されます。

- 受信History-Infoは無視されます。

SIP プロキシによって送信される History-info ヘッダーの形式を次に示します。

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

呼び出しが何度かリダイレクトされた場合、すべてのリダイレクトに関する情報が、適切な理由に時系列で含まれます。


ヘッダーの例:

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

このHistory-Infoは、必須の TLS メカニズムによって保護されます。 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>ダイレクト ルーティングとフェールオーバー メカニズムへの SBC 接続

「ダイレクト ルーティングの計画」の「SIP シグナリングの [フェールオーバー メカニズム」セクションを参照してください](direct-routing-plan.md#failover-mechanism-for-sip-signaling)。

## <a name="retry-after"></a>Retry-After

ダイレクト ルーティング データセンターがビジー状態の場合、サービスは 1 秒の間隔Retry-Afterメッセージを SBC に送信できます。 SBC が INVITE に応答して Retry-After ヘッダーを含む 503 メッセージを受信した場合、SBC は接続を終了し、次に使用可能な Microsoft データセンターを試す必要があります。

## <a name="handling-retries-603-response"></a>再試行の処理 (603 応答)
エンド ユーザーが着信呼び出しを拒否した後に 1 回の呼び出しに対して複数の着信ミスを観察した場合、SBC または PSTN トランク プロバイダーの再試行メカニズムが正しく構成されていないという意味です。 603 応答での再試行を停止するには、SBC を再構成する必要があります。

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>ICE Restart: メディア バイパスをサポートしていないエンドポイントに転送されたメディア バイパス呼び出し

SBC は [、RFC 5245 セクション 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)で説明されている ICE 再起動をサポートする必要があります。

ダイレクト ルーティングでの再起動は、RFC の次の段落に従って実装されます。

*ICE を再起動するには、エージェントはオファー内のメディア ストリームの ice-pwd と ice-ufrag の両方を変更する必要があります。 1 つのオファーでセッション レベル属性を使用できますが、後続のオファーではメディア レベル属性と同じ ice-pwd または ice-ufrag を提供できます。 これはパスワードの変更ではなく、単なる表現の変更であり、ICE 再起動の原因となるのではありません。*

*エージェントは、このメディア ストリームの最初のオファーと同様に、このメディア ストリームの SDP の残りのフィールドを設定します (セクション 4.3 を参照)。 そのため、一連の候補には、そのストリームの以前の候補の一部、なし、またはすべての候補が含まれる場合があります。また、セクション 4.1.1 で説明したように、収集された全く新しい候補セットが含まれる場合があります(MAY)。*

最初にメディア バイパスを使用して通話が確立され、その呼び出しが Skype for Business クライアントに転送された場合、ダイレクト ルーティングはメディア プロセッサを挿入する必要があります。これは、メディア バイパスを使用して Skype for Business クライアントと直接ルーティングを使用できないためです。 直接ルーティングでは、ice-pwd と ice-ufrag を変更し、新しいメディア候補を再び提供することで、ICE 再起動プロセスを開始します。
