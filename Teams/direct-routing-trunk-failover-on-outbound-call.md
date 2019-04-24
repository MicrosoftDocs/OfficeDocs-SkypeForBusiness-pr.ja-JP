---
title: 発信通話でのトランクのフェイルオーバー
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto: Microsoft Teams
description: セッション ボーダー コント ローラー (SBC) にチームから発信呼び出しのトランクのフェイル オーバーを処理する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 1a40cc3fa94bfba3c637769774f5f5b829d29ed4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232648"
---
# <a name="trunk-failover-on-outbound-calls"></a>発信通話でのトランクのフェイルオーバー

-セッション ボーダー コント ローラー (SBC) へのチームからの発信コールのトランクのフェイル オーバーを回避する方法について説明します。

## <a name="failover-on-network-errors"></a>ネットワーク エラーでフェイル オーバー

トランクは、何らかの理由で接続することはできません、別の Microsoft データ センターから同じトランクへの接続が試行されます。 トランクが接続されていないなどの場合は、TLS のタイムアウトがある場合、接続が拒否、またはその他のネットワーク レベルの問題がある場合。
などの接続は失敗する場合、管理者のアクセスを制限、SBC を既知の IP アドレスからのみですが、SBC のアクセス制御リスト (ACL) に直接ルーティングの Microsoft データ センターのすべての IP アドレスを配置するを忘れた場合します。 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>セッション ボーダー コント ローラー (SBC) からの受信 SIP コードの特定のフェイル オーバー

送信招待への応答での 4 xx または 6 xx SIP のエラー コードを受け取ると直接ルーティングでは、呼び出し既定で完了したと見なされます。 チーム クライアントからの呼び出しに、パブリック交換電話網 (PSTN) 次のトラフィック フローには、出力方向の: チームのクライアントの直接ルーティング _gt-_gt SBC-_gt テレフォニー ネットワーク。

SIP のコードの一覧については、[セッション開始プロトコル (SIP) の RFC](https://tools.ietf.org/html/rfc3261)を参照しています。

SBC がコードを使用して受信した招待に返信した場合を想定しています"408 要求のタイムアウト: サーバーを作成できませんでした、応答、適切な時間内などの場合は時間内のユーザーの場所を特定できませんでした。 クライアントは、可能性があります繰り返し変更することがなく要求後にいつでもします。

この特定の SBC には、ネットワーク設定ミスやその他のエラーが発生したため、呼び出し先 - への接続に関する問題が発生可能性があります。 しかし、1 つ以上の SBC では、ルート、呼び出し先に到達できる場合があります。

次の図では、ユーザーが電話番号への呼び出しと 2 つの半角にはこの呼び出しを提供できる可能性のあるルート。 最初に、呼び出しの SBC1.contoso.com が選択されているが、SBC1.contoso.com はネットワークの問題のための PTSN ネットワークに到達することはありません。
既定では、この時点で呼び出しが完了します。 
 
![PSTN ネットワーク上の問題のために到達できない SBC を示しています。](media/direct-routing-failover-response-codes1.png)

ですが、1 つ以上の SBC で可能性のある呼び出しを提供するルート。
パラメーターを構成する場合`Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`、2 つ目の SBC が行われます--次の図に SBC2.contoso.com。

![2 つ目の SBC へのルーティングを示しています](media/direct-routing-failover-response-codes2.png)

-FailoverResponseCodes コードでは、問題を指定する、ルーティングのチューニングし、を避けるために、パラメーターを設定することが潜在的な場合、SBC は、ネットワークまたはその他の問題のための呼び出しをすることはできません。

既定値: 408, 503, 504

