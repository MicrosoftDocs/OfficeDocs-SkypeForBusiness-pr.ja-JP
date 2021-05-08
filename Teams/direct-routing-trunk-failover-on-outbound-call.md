---
title: 発信通話でのトランクのフェイルオーバー
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: このトピックでは、セッション ボーダー コントローラー (SBC) への Teamsのトランク フェールオーバーを処理する方法について説明します。
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836179"
---
# <a name="trunk-failover-on-outbound-calls"></a>発信通話でのトランクのフェイルオーバー

このトピックでは、発信呼び出し (セッション ボーダー コントローラー (SBC) Teamsのトランク フェールオーバーを回避する方法について説明します。

## <a name="failover-on-network-errors"></a>ネットワーク エラーでのフェールオーバー

何らかの理由でトランクを接続できない場合、同じトランクへの接続は別の Microsoft データセンターから試されます。 たとえば、接続が拒否された場合、TLS タイムアウトがある場合、その他のネットワーク レベルの問題がある場合など、トランクが接続されていない可能性があります。
たとえば、管理者が既知の IP アドレスからのみ SBC へのアクセスを制限し、すべての Microsoft ダイレクト ルーティング データセンターの IP アドレスを SBC のアクセス制御リスト (ACL) に配置することを忘れた場合、接続が失敗することがあります。 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>セッション ボーダー コントローラー (SBC) から受信した特定の SIP コードのフェールオーバー

ダイレクト ルーティングが送信招待に応答して 4xx または 6xx の SIP エラー コードを受信した場合、呼び出しは既定で完了したと見なされます。 送信とは、Teams クライアントから公衆交換電話網 (PSTN) への通話を意味し、トラフィック フローは Teams Client -> Direct Routing -> SBC -> Telephoney ネットワークです。

SIP コードの一覧は、セッション開始プロトコル [(SIP) RFC に記載されています](https://tools.ietf.org/html/rfc3261)。

SBC が"408 Request Timeout: The server could not produce a response within a suitable of time, if it not determine the location of the user in time. (408 要求タイムアウト: サーバーが適切な時間内に応答を生成できない場合など)、受信した招待に対して SBC が応答した場合を想定します。 クライアントは、後で変更なしで要求を繰り返す場合があります。"

この特定の SBC では、ネットワークの構成ミスや他のエラーが原因で、呼び出し先への接続に問題がある可能性があります。 ただし、呼び出し先に到達できる可能性がある SBC がルートに 1 つ追加されます。

次の図では、ユーザーが電話番号に通話を行った場合、この通話を配信できる可能性のある 2 つの SBC がルートに含まれます。 最初に SBC1.contoso.com が選択されますが、SBC1.contoso.com の問題により、PTSN ネットワークに到達できない場合があります。
既定では、この時点で呼び出しが完了します。 
 
![ネットワークの問題が原因で SBC が PSTN に到達できない状態を示す図](media/direct-routing-failover-response-codes1.png)

ただし、ルートには、呼び出しを配信できる SBC がもう 1 つある可能性があります。
パラメーター を構成すると、2 つ目の SBC が試み `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` SBC2.contoso.com 図のようになります。

![第 2 の SBC へのルーティングを示す図](media/direct-routing-failover-response-codes2.png)

-FailoverResponseCodes パラメーターを設定し、コードを指定すると、ルーティングを微調整し、SBC がネットワークなどの問題のために呼び出しを行えなくなる場合の潜在的な問題を回避するのに役立ちます。

既定値: 408、503、504

