---
title: ダイレクト ルーティングの監視とトラブルシューティング
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: セッション ボーダー コントローラー、ダイレクト ルーティング コンポーネント、Telecom トランクなど、ダイレクト ルーティング構成を監視およびトラブルシューティングする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74a67493fa2f9647e6cd0364bb4c9d6a3c05e48a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121405"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>ダイレクト ルーティングの監視とトラブルシューティング

この記事では、ダイレクト ルーティング構成を監視およびトラブルシューティングする方法について説明します。 

直接ルーティングを使用して通話を送受信する機能には、次のコンポーネントが含まれます。 

- セッション ボーダー コントローラー (SPC) 
- Microsoft Cloud のダイレクト ルーティング コンポーネント 
- Telecom trunks 

問題のトラブルシューティングで問題が発生した場合は、SBC ベンダーまたは Microsoft にサポート ケースを開きます。 

Microsoft では、トラブルシューティングと監視のためのその他のツールの提供に取り組み中です。 ドキュメントの更新プログラムを定期的に確認してください。 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>セッション開始プロトコル (SIP) オプション メッセージを使用したセッション ボーダー コントローラーの可用性の監視

ダイレクト ルーティングでは、セッション ボーダー コントローラーから送信された SIP オプションを使用して、SBC の正常性を監視します。 SIP オプションの監視を有効にするには、テナント管理者から必要なアクションはありません。 収集された情報は、ルーティングの決定が行われたときに考慮されます。 

たとえば、特定のユーザーに対して、通話をルーティングするために使用できる複数の SBC がある場合、ダイレクト ルーティングは、各 SBC から受信した SIP オプション情報を考慮してルーティングを決定します。 

次の図は、構成の例を示しています。 

![SIP オプションの構成例](media/sip-options-config-example.png)

ユーザーが番号 +1 425 を呼び出す場合、ダイレクト ルーティングは \<any seven digits> ルートを評価します。 ルートには、2 つの SPC があります。sbc1.contoso.com と sbc2.contoso.com。 両方の SPC は、ルートで同じ優先度を持っています。 SBC を選択する前に、ルーティング メカニズムは、SBC が前回 SIP オプションを送信した時刻に基づいて、SBC の正常性を評価します。 

SBC は、通話の送信時点での統計情報が SBC が 1 分ごとにオプションを送信すると、正常と見なされます。  

呼び出しが行われた場合、次のロジックが適用されます。

- SBC は 11:00 AM にペアリングされました。  
- SBC は、午前 11:01、午前 11:02 など、オプションを送信します。  
- 11:15 にユーザーが通話を行い、ルーティング メカニズムによってこの SBC が選択されます。 

ダイレクト ルーティングは、一定の間隔オプションを 3 回受け取ります (一定の間隔は 1 分です)。 オプションが最後の 3 分間に送信された場合、SBC は正常と見なされます。

例の SBC が 11:12 AM から 11:15 AM (通話が行われた時刻) の任意の期間にオプションを送信した場合、正常と見なされます。 そうしない場合、SBC はルートから降格されます。 

降格とは、SBC が最初に試されないという意味です。 たとえば、優先度が等しい sbc1.contoso.com と sbc2.contoso.com を設定します。  

前述 sbc1.contoso.com 一定の間隔で SIP オプションを送信しない場合、SIP オプションは降格されます。 次に、sbc2.contoso.com を試します。 sbc2.contoso.con が呼び出しを配信できない場合、エラー sbc1.contoso.com 発生する前に、sbc1.contoso.com (降格) がもう一度試されます。 

1 つのルートで 2 つ (以上) の SPC が正常で等しいと見なされた場合、Fisher-Yatesシャッフルが適用され、SPC 間で呼び出しが分散されます。

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>通話品質分析ダッシュボードと SBC ログを監視する 
 
場合によっては、特に初期ペアリング時に、SPC またはダイレクト ルーティング サービスの構成ミスに関連する問題が発生する可能性があります。 

次のツールを使用して構成を監視できます。  
 
- 通話品質ダッシュボード 
- SBC ログ 

ダイレクト ルーティング サービスには、通話分析または SBC ログに報告される非常にわかりやすいエラー コードがあります。 

通話品質ダッシュボードには、通話の品質と信頼性に関する情報が表示されます。 通話分析を使用して問題のトラブルシューティングを行う方法の詳細については[、「Microsoft Teams](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)および Skype for Business Online の[](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)通話品質ダッシュボードをオンにして使用する」および「通話分析を使用して低品質の通話品質をトラブルシューティングする」を参照してください。 

通話エラーが発生した場合、通話分析はトラブルシューティングに役立つ標準的な SIP コードを提供します。 

![通話エラーのサンプル SIP コード](media/failed-response-code.png)

ただし、通話分析は、通話がダイレクト ルーティングの内部コンポーネントに到達して失敗した場合にのみ役立ちます。 SBC のペアリングに関する問題や、SIP "招待" が拒否された問題 (たとえば、トランク FQDN の名前が正しく構成されていない) の場合、通話分析は役立たされません。 この場合は、SBC ログを参照してください。 直接ルーティングは、問題の詳細な説明を SPC に送信します。これらの問題は SBC ログから読み取り可能です。