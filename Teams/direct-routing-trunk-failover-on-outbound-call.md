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
description: このトピックでは、Teams からセッションボーダーコントローラー (SBC) への発信通話に対するトランクのフェイルオーバーを処理する方法について説明します。
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836179"
---
# <a name="trunk-failover-on-outbound-calls"></a>発信通話でのトランクのフェイルオーバー

このトピックでは、チームからセッションボーダーコントローラー (SBC) への、トランクのフェイルオーバーを回避する方法について説明します。

## <a name="failover-on-network-errors"></a>ネットワークエラーへのフェールオーバー

何らかの理由でトランクが接続できない場合、同じトランクへの接続は、別の Microsoft データセンターから試みられます。 接続が拒否された場合や、TLS タイムアウトがある場合、または他のネットワークレベルの問題が発生した場合など、トランクが接続されていない可能性があります。
たとえば、管理者が、既知の IP アドレスからの SBC のみへのアクセスを制限したが、SBC のアクセス制御リスト (ACL) にすべての Microsoft ダイレクトルーティングデータセンターの IP アドレスを指定していない場合、接続が失敗する可能性があります。 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>セッションボーダーコントローラー (SBC) から受信した特定の SIP コードのフェイルオーバー

直接ルーティングが、発信した招待に応答して4xx または 6xx SIP のエラーコードを受信した場合、通話は既定で完了したと見なされます。 [発信] は、チームクライアントから公衆交換電話網 (PSTN) への通話であり、次のトラフィックフローが含まれます。 Teams クライアント-> ダイレクトルーティング-> SBC-> テレフォニーネットワーク。

SIP コードの一覧は、[セッション開始プロトコル (SIP) RFC](https://tools.ietf.org/html/rfc3261)に記載されています。

"408 要求がタイムアウトしました。" というコードの着信招待に対して SBC が返信した場合、サーバーはユーザーの場所を特定できなかったなど、適切な時間内に応答を作成できませんでした。 クライアントは、後で変更せずに要求を繰り返すことがあります。 "

この特定の SBC は、呼び出し元への接続で問題が発生している可能性があります。これは、ネットワークの構成の誤りやエラーなどが原因です。 ただし、ルートにはもう1つの SBC があります。これは、呼び出し元に連絡できる可能性があります。

次の図では、ユーザーが電話番号に通話を発信すると、そのルートに2つの SBCs が含まれていて、この通話が行われる可能性があります。 最初に、通話に SBC1.contoso.com が選択されていますが、ネットワークの問題のため、SBC1.contoso.com は PTSN ネットワークに接続できません。
既定では、通話は現在完了しています。 
 
![ネットワークの問題のため、SBC に接続できないことを示す図](media/direct-routing-failover-response-codes1.png)

ただし、ルートにはさらに、通話を発信できる SBC が1つ追加されています。
パラメーター `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`を構成する場合、2つ目の SBC は次の図の SBC2.contoso.com で試行されます。

![第2の SBC へのルーティングを示す図](media/direct-routing-failover-response-codes2.png)

FailoverResponseCodes を設定してコードを指定すると、ネットワークやその他の問題が原因で、SBC が通話を発信できない場合に、ルーティングを微調整し、潜在的な問題を回避することができます。

既定値: 408、503、504

