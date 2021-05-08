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
description: セッション ボーダー コントローラー、ダイレクト ルーティング コンポーネント、通信トランクなど、ダイレクト ルーティング構成を監視およびトラブルシューティングする方法について説明します。
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

ダイレクト ルーティングを使用して通話を送受信する機能には、次のコンポーネントが含まれます。 

- セッション ボーダー コントローラー (SBC) 
- Microsoft Cloud のダイレクト ルーティング コンポーネント 
- 通信トランク 

問題のトラブルシューティングに問題がある場合は、SBC ベンダーまたは Microsoft にサポート ケースを開きます。 

Microsoft では、トラブルシューティングと監視のためのその他のツールの提供に取り組み中です。 更新プログラムについては、ドキュメントを定期的に確認してください。 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>セッション開始プロトコル (SIP) オプション メッセージを使用したセッション ボーダー コントローラーの可用性の監視

直接ルーティングでは、セッション ボーダー コントローラーから送信された SIP オプションを使用して、SBC の正常性を監視します。 SIP オプションの監視を有効にするには、テナント管理者から必要なアクションはありません。 収集された情報は、ルーティングの決定が行われたときに考慮されます。 

たとえば、特定のユーザーに対して、通話のルーティングに使用できる SBC が複数ある場合、ダイレクト ルーティングは、各 SBC から受信した SIP オプション情報を考慮してルーティングを決定します。 

次の図は、構成の例を示しています。 

![SIP オプションの構成例](media/sip-options-config-example.png)

ユーザーが番号 +1 425 の呼び出しを行った \<any seven digits> 場合、ダイレクト ルーティングによってルートが評価されます。 ルートには 2 つの SBC があります。ルートには、sbc1.contoso.com と sbc2.contoso.com。 両方の SPC は、ルートの優先順位が等しくなります。 SBC を選択する前に、ルーティング メカニズムは、SBC が前回 SIP オプションを送信した時刻に基づいて、SBC の正常性を評価します。 

SBC は、呼び出しを送信した時点の統計情報で、SBC が 1 分ごとにオプションを送信する場合に正常と見なされます。  

呼び出しが行われた場合、次のロジックが適用されます。

- SBC は午前 11 時 00 分にペアリングされました。  
- SBC は、午前 11 時 11 分、午前 11 時 02 分など、オプションを送信します。  
- 11 時 15 分にユーザーが呼び出しを行い、ルーティング メカニズムによってこの SBC が選択されます。 

ダイレクト ルーティングは、一定の間隔オプションを 3 回受け取ります (一定の間隔は 1 分です)。 オプションが最後の 3 分間に送信された場合、SBC は正常と見なされます。

この例の SBC が午前 11 時 12 分から午前 11 時 15 分 (呼び出しが行われた時刻) の間にオプションを送信した場合、正常と見なされます。 存在しない場合、SBC はルートから降格されます。 

降格とは、SBC が最初に試みようとしないという意味です。 たとえば、優先順位が等しい sbc1.contoso.com、sbc2.contoso.com を指定します。  

前述 sbc1.contoso.com 一定の間隔で SIP オプションを送信しない場合は、降格されます。 次に、sbc2.contoso.com を試します。 sbc2.contoso.con が呼び出しを配信できない場合、エラーが生成される前に、sbc1.contoso.com (降格) が再度試みされます。 

1 つのルート内の 2 つ (以上) の SBC が正常で等しいと見なされた場合は、Fisher-Yates シャッフルが適用され、SPC 間で呼び出しが分散されます。

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>通話品質分析ダッシュボードと SBC ログの監視 
 
場合によっては、特に初期ペアリング中に、SBC またはダイレクト ルーティング サービスの構成ミスに関連する問題が発生する可能性があります。 

次のツールを使用して、構成を監視できます。  
 
- 通話品質ダッシュボード 
- SBC ログ 

ダイレクト ルーティング サービスには、Call Analytics または SBC ログに報告される非常にわかりやすいエラー コードがあります。 

通話品質ダッシュボードには、通話の品質と信頼性に関する情報が表示されます。 通話分析を使用して問題をトラブルシューティングする方法の詳細については[、「Microsoft Teams](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)および Skype for Business Online の通話品質ダッシュボードを有効にして使用する」および「通話分析を使用して低品質の通話品質をトラブルシューティングする」を参照[してください。](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 

通話エラーが発生した場合、Call Analytics にはトラブルシューティングに役立つ標準的な SIP コードが提供されています。 

![呼び出しエラーのサンプル SIP コード](media/failed-response-code.png)

ただし、通話分析は、呼び出しがダイレクト ルーティングの内部コンポーネントに到達して失敗した場合にのみ役立ちます。 SBC のペアリングに関する問題や、SIP の "招待" が拒否された問題 (たとえば、トランク FQDN の名前が正しく構成されていない) の場合、通話分析は役立ちます。 この場合は、SBC ログを参照してください。 直接ルーティングは、問題の詳細な説明を SBC に送信します。これらの問題は、SBC ログから読み取り可能です。