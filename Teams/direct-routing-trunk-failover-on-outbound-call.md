---
title: 発信通話でのトランクのフェイルオーバー
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: このトピックでは、Teamsからセッション ボーダー コントローラー (SBC) への送信呼び出しでのトランク フェールオーバーを処理する方法について説明します。
ms.openlocfilehash: 83320e93df7cbf476d71b3b9165d50ca387292b9
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727866"
---
# <a name="trunk-failover-on-outbound-calls"></a>発信通話でのトランクのフェイルオーバー

このトピックでは、Teamsからセッション ボーダー コントローラー (SBC) への送信呼び出しでのトランク フェールオーバーを回避する方法について説明します。

## <a name="failover-on-network-errors"></a>ネットワーク エラーでのフェールオーバー

何らかの理由でトランクを接続できない場合、同じトランクへの接続は別の Microsoft Datacenter から試行されます。 たとえば、接続が拒否された場合、TLS タイムアウトが発生した場合、または他のネットワーク レベルの問題がある場合など、トランクは接続されていない可能性があります。
たとえば、管理者が既知の IP アドレスからのみ SBC へのアクセスを制限しているが、すべての Microsoft Direct Routing データセンターの IP アドレスを SBC のAccess Controlリスト (ACL) に配置することを忘れた場合、接続が失敗することがあります。 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>セッション ボーダー コントローラー (SBC) から受信した特定の SIP コードのフェールオーバー

ダイレクト ルーティングが送信招待に応答して 4xx または 6xx SIP エラー コードを受信した場合、呼び出しは既定で完了したものと見なされます。 発信とは、Teams クライアントから公衆交換電話網 (PSTN) への呼び出しを意味し、Teams クライアント -> ダイレクト ルーティング -> SBC -> テレフォニー ネットワークです。

SIP コードの一覧は、 [セッション開始プロトコル (SIP) RFC](https://tools.ietf.org/html/rfc3261) にあります。

SBC が受信招待に対して"408 要求タイムアウト: サーバーが適切な時間内に応答を生成できなかった場合 (たとえば、ユーザーの場所を時間内に特定できなかった場合) を使用して応答を返したとします。 クライアントは、後で変更せずに要求を繰り返すことができます。

この特定の SBC では、ネットワークの構成ミスやその他のエラーが原因で、呼び出し先への接続に問題がある可能性があります。 ただし、ルートには、呼び出し先に到達できる可能性がある SBC がもう 1 つあります。

次の図では、ユーザーが電話番号を呼び出すときに、この呼び出しを配信できる可能性のある 2 つの SBC がルート内に存在します。 最初は、SBC1.contoso.com が呼び出しに対して選択されますが、ネットワークの問題により、SBC1.contoso.com は PTSN ネットワークに到達できません。
既定では、この時点で呼び出しが完了します。 
 
![ネットワークの問題が原因で SBC が PSTN に到達できないことを示す図。](media/direct-routing-failover-response-codes1.png)

ただし、ルート内にもう 1 つの SBC があり、呼び出しを配信できる可能性があります。
パラメーター `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`を構成すると、2 番目の SBC が試行されます。次の図に SBC2.contoso.com。

![2 番目の SBC へのルーティングを示す図。](media/direct-routing-failover-response-codes2.png)

パラメーター -FailoverResponseCodes を設定し、コードを指定すると、ルーティングを微調整し、ネットワークやその他の問題が原因で SBC が呼び出しを行えない場合に発生する可能性のある問題を回避できます。

既定値: 408、503、504

