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
description: Teams からセッション ボーダー コントローラー (SBC) への送信呼び出しでトランク フェールオーバーを処理する方法については、このトピックを参照してください。
ms.openlocfilehash: 0fa0d452a2611874be570f4e80a746bb07da0163
ms.sourcegitcommit: d7a86b3a72005764c18acb60eedf5163523ffae3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2022
ms.locfileid: "67457137"
---
# <a name="trunk-failover-on-outbound-calls"></a>発信通話でのトランクのフェイルオーバー

このトピックでは、発信通話 (Teams からセッション ボーダー コントローラー (SBC) へのトランク フェールオーバーを回避する方法について説明します。

## <a name="failover-on-network-errors"></a>ネットワーク エラーでのフェールオーバー

何らかの理由でトランクを接続できない場合は、同じトランクへの接続が別の Microsoft Datacenter から試行されます。 データセンターは、現在のリージョンの外部にある別の地理的リージョンに配置されている可能性があります。 接続が拒否された場合、TLS タイムアウトが発生した場合、または他のネットワーク レベルの問題がある場合、トランクは接続されない可能性があります。

たとえば、管理者が既知の IP アドレスからのみ SBC へのアクセスを制限しているが、すべての Microsoft Direct Routing データセンターの IP アドレスを SBC のAccess Controlリスト (ACL) に配置することを忘れた場合、接続が失敗することがあります。 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>セッション ボーダー コントローラー (SBC) から受信した特定の SIP コードのフェールオーバー

ダイレクト ルーティングが送信招待に応答して 4xx または 6xx SIP エラー コードを受信した場合、呼び出しは既定で完了したものと見なされます。 発信とは、Teams クライアントから公衆交換電話網 (PSTN) への呼び出しを意味します。Teams クライアント -> ダイレクト ルーティング -> SBC -> テレフォニー ネットワーク。

SIP コードの一覧は、 [セッション開始プロトコル (SIP) RFC](https://tools.ietf.org/html/rfc3261) にあります。

SBC が受信招待に対して "408 要求タイムアウト: サーバーが適切な時間内に応答を生成できませんでした 。たとえば、ユーザーの場所を時間内に特定できなかった場合など)。 クライアントは、後で変更せずに要求を繰り返すことができます。

この特定の SBC では、ネットワークの構成ミスやその他のエラーが原因で、呼び出し先への接続に問題がある可能性があります。 ただし、ルートには、呼び出し先に到達できる可能性のある SBC がもう 1 つあります。

次の図では、ユーザーが電話番号を呼び出すときに、この呼び出しを配信できる可能性のある 2 つの SBC がルート内に存在します。 最初は、SBC1.contoso.com が呼び出しに対して選択されますが、ネットワークの問題により、SBC1.contoso.com は PTSN ネットワークに到達できません。
既定では、この時点で呼び出しが完了します。 
 
![ネットワークの問題が原因で SBC が PSTN に到達できないことを示す図。](media/direct-routing-failover-response-codes1.png)

ルートには、通話を配信する可能性のある SBC がもう 1 つあります。
パラメーター `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`を構成すると、2 番目の SBC が試行されます (次の図の SBC2.contoso.com)。

![2 番目の SBC へのルーティングを示す図。](media/direct-routing-failover-response-codes2.png)

パラメーター -FailoverResponseCodes を設定し、コードを指定すると、ルーティングを微調整し、ネットワークやその他の問題が原因で SBC が呼び出しを行えない場合の潜在的な問題を回避するのに役立ちます。

既定値: 408、503、504

