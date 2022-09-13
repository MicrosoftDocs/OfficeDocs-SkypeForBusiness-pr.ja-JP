---
title: ダイレクト ルーティングを監視する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: セッション ボーダー コントローラー、ダイレクト ルーティング コンポーネント、通信トランクなど、ダイレクト ルーティング構成を監視およびトラブルシューティングする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47a86e8dd98cdb86cd698b187b21453daa003b07
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657247"
---
# <a name="monitor-direct-routing"></a>ダイレクト ルーティングを監視する

この記事では、ダイレクト ルーティング構成を監視およびトラブルシューティングする方法について説明します。 

ダイレクト ルーティングを使用して呼び出しを行い、受信する機能には、次のコンポーネントが含まれます。 

- セッション ボーダー コントローラー (SBC) 
- Microsoft Cloud のダイレクト ルーティング コンポーネント 
- 通信トランク 

問題のトラブルシューティングに問題がある場合は、SBC ベンダーまたは Microsoft でサポート ケースを開くことができます。 

Microsoft は、トラブルシューティングと監視のためのより多くのツールの提供に取り組んでいます。 更新プログラムについては、ドキュメントを定期的に確認してください。 

## <a name="troubleshoot-direct-routing"></a>ダイレクト ルーティングのトラブルシューティング

ダイレクト ルーティングのトラブルシューティングについては、「 [ダイレクト ルーティングに関する問題の診断」を](/MicrosoftTeams/troubleshoot/phone-system/direct-routing/diagnose-direct-routing-issues)参照してください。

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>セッション開始プロトコル (SIP) オプション メッセージを使用したセッション ボーダー コントローラーの可用性の監視

ダイレクト ルーティングでは、セッション ボーダー コントローラーから送信された SIP オプションを使用して、SBC の正常性を監視します。 テナント管理者が SIP オプションの監視を有効にするために必要なアクションはありません。 収集された情報は、ルーティングの決定が行われるときに考慮されます。 

たとえば、特定のユーザーに対して、呼び出しのルーティングに使用できる SBC が複数ある場合、ダイレクト ルーティングでは、各 SBC から受信した SIP オプション情報を考慮してルーティングを決定します。 

次の図は、構成の例を示しています。 

![SIP オプションの構成例。](media/sip-options-config-example.png)

ユーザーが番号 +1 425 \<any seven digits>を呼び出すと、ダイレクト ルーティングによってルートが評価されます。 ルートには、sbc1.contoso.com と sbc2.contoso.com の 2 つの SBC があります。 両方の SBC は、ルート内で同じ優先度を持ちます。 SBC を選択する前に、ルーティング メカニズムは、SBC が前回 SIP オプションを送信した日時に基づいて、SBC の正常性を評価します。 

SBC は、呼び出しを送信した時点の統計情報が、SBC が 1 分ごとにオプションを送信することを示している場合、正常と見なされます。  

呼び出しが行われると、次のロジックが適用されます。

- SBC は午前 11 時にペアリングされました。  
- SBC は、午前 11:01、午前 11:02 などのオプションを送信します。  
- 11:15 に、ユーザーが呼び出しを行い、ルーティング メカニズムによってこの SBC が選択されます。 

ダイレクト ルーティングは、一定間隔オプションを 3 回受け取ります (一定間隔は 1 分です)。 過去 3 分間にオプションが送信された場合、SBC は正常と見なされます。

この例の SBC が午前 11 時 12 分から午前 11 時 15 分 (呼び出しが行われた時刻) の間の任意の期間にオプションを送信した場合、正常と見なされます。 そうでない場合、SBC はルートから降格されます。 

降格とは、SBC が最初に試行されないことを意味します。 たとえば、優先順位が等しい sbc1.contoso.com と sbc2.contoso.com があるとします。  

前述のように、sbc1.contoso.com が一定の間隔で SIP オプションを送信しない場合は、降格されます。 次に、sbc2.contoso.com 呼び出しを試行します。 sbc2.contoso.con が呼び出しを配信できない場合は、エラーが生成される前に sbc1.contoso.com (降格) が再試行されます。 

1 つのルート内の 2 つ以上の SBC が正常で等しいと見なされる場合は、Fisher-Yatesシャッフルが適用されて、SBC 間で呼び出しが分散されます。

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>通話品質分析ダッシュボードと SBC ログを監視する 
 
場合によっては、特に初期ペアリング中に、SBC またはダイレクト ルーティング サービスの構成ミスに関連する問題が発生する可能性があります。 

次のツールを使用して、構成を監視できます。  
 
- 通話品質ダッシュボード 
- SBC ログ 

ダイレクト ルーティング サービスには、Call Analytics または SBC ログに説明的なエラー コードが報告されています。

通話品質ダッシュボードには、通話の品質と信頼性に関する情報が表示されます。 Call Analytics を使用して問題のトラブルシューティングを行う方法の詳細については、「[Microsoft Teams の通話品質ダッシュボードを有効にして使用する」を参照し、オンラインSkype for Business](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)し[、通話品質の低下のトラブルシューティングに Call Analytics を使用する方法に関するページを](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)参照してください。 

通話エラーが発生した場合、Call Analytics には、トラブルシューティングに役立つ標準 SIP コードが用意されています。 

![呼び出しエラーのサンプル SIP コード。](media/failed-response-code.png)

ただし、Call Analytics は、通話がダイレクト ルーティングの内部コンポーネントに到達して失敗した場合にのみ役立ちます。 SBC ペアリングに関する問題、または SIP "Invite" が拒否された問題 (トランク FQDN の名前が正しく構成されていないなど) の場合、Call Analytics は役に立ちません。 この場合は、SBC ログを参照してください。 ダイレクト ルーティングは、問題の詳細な説明を SBC に送信します。これらの問題は、SBC ログから読み取ることができます。
