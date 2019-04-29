---
title: ダイレクト ルーティングの監視とトラブルシューティング
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: この資料では、監視し、直接ルーティングの構成をトラブルシューティングする方法について説明します。
ms.openlocfilehash: e21d3e020f477fd1518017e0d6fc484e7ea10344
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402447"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>ダイレクト ルーティングの監視とトラブルシューティング

この資料では、監視し、直接ルーティングの構成をトラブルシューティングする方法について説明します。 

作成し、直接ルーティングを使用して呼び出しを受信する機能には、次のコンポーネントが含まれます。 

- セッション ボーダー コント ローラー (SBCs) 
- マイクロソフトのクラウドでの直接のルーティング コンポーネント 
- トランクの電気通信 

に関する問題のトラブルシューティングの問題がある場合は、SBC の製造元またはマイクロソフトのサポート ・ リクエストを開いてください。 

マイクロソフトは、トラブルシューティングと監視に関するその他のツールを提供することに取り組んでいます。 更新プログラムを定期的にドキュメントを確認してください。 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>メッセージのセッション開始プロトコル (SIP) オプションを使用してセッションの枠線のコント ローラーの可用性の監視

直接ルーティングでは、SBC の状態を監視するのにセッション ボーダー コント ローラーから送信された SIP のオプションを使用します。 SIP オプションの監視を有効にするのには、テナントの管理者から必要なアクションはありません。 ルーティングの決定が行われると、収集した情報を考慮にします。 

などの場合は、特定のユーザーの通話のルーティングに使用できるいくつかの SBCs、直接ルーティングと見なされるルーティングを決定するのには、各 SBC から受信した SIP オプション情報です。 

構成の例を次の図に示します。 

![SIP オプションの構成の例](media/sip-options-config-example.png)

番号 +1 425 への呼び出しを行うと、\<直接ルーティングでは、7 つの digits> は、ルートを評価します。 ルートにある 2 つの SBCs: sbc1.contoso.com と sbc2.contoso.com。 SBCs の両方では、工順の優先度が同じがあります。 ルーティング メカニズムが、SBC に送信される SIP オプションに基づいて、SBCs の稼働状態を評価する SBC をピッキングする前に最後の時間します。 

SBC は、SBC が一定の間隔のオプションを送信する送信呼び出しの時点での統計情報が表示されている場合は正常と見なされます。  

直接ルーティングは、SBC が呼び出しを行うと、5 分を追加する前にオプションを送信するときに、2 回の平均をとることによって一定の間隔を計算します。 

たとえば、次の点を想定しています。 

- SBC の構成オプションの 1 分ごとに送信します。 
- 午前 11時 00分、SBC と同じです。  
- SBC は、11.01 AM、11.02 AM というようにオプションを送信します。  
- 11.15 でユーザーが呼び出しを行うし、ルーティング メカニズムは、この SBC を選択します。 

次のロジックを適用: SBC は、さらに 5 分 = 7 分 (1 分間および 1 つ分 = 2 分) のオプションを送信するときに、平均の間隔が 2 倍です。 これは、SBC の一定の間隔の値です。
 
この例では、SBC では、11時 08分 AM と 11時 15分 AM (呼び出しが行われた時間) との間にあるオプションを送信する場合正常と見なされます。 それ以外の場合は、SBC をルートから降格されます。 

降格では、ある、SBC は試行されませんが、最初を意味します。 たとえば、sbc1.contoso.com と sbc2.contoso.com が同じ優先度であります。  

Sbc1.contoso.com は、前述のとおり、一定の間隔のオプションの SIP を送信しません、する場合は降格されます。 次に、sbc2.contoso.com は、呼び出しを試みます。 Sbc2.contoso.con は、呼び出しを配信できません、エラーが生成される前に (降格) sbc1.contoso.com としました。 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>ダッシュ ボードの品質の分析機能を呼び出すと SBC のログを監視します。 
 
場合によっては、最初のペアリング時に、特に可能性があります、SBCs または直接ルーティング サービスの構成の誤りに関連する問題。 

構成を監視するのには、次のツールを使用できます。  
 
- 通話品質ダッシュボード 
- SBC のログ 

直接ルーティング サービスには非常にわかりやすいエラー コードの分析機能を呼び出すか、SBC のログに報告します。 

コール品質のダッシュ ボードでは、通話の音質と信頼性に関する情報を提供します。 分析機能の呼び出しを使用して問題をトラブルシューティングする方法の詳細について[を有効にしてマイクロソフトのチームとビジネス オンラインの Skype の品質ダッシュ ボードの呼び出しを使用して](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)[不適切な呼び出し品質のトラブルシューティングを行うコール分析機能の使用](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)を参照してください。 

呼び出しの失敗が発生した場合は、分析機能の呼び出しは、トラブルシューティングするための標準の SIP コードを提供します。 

![呼び出しが失敗した SIP のサンプル コード](media/failed-response-code.png)

ただし、分析機能を呼び出すのに役立つだけ呼び出しが直接ルーティングの内部コンポーネントにアクセスし、失敗するとします。 SBC の組み合わせで問題または SIP」への招待」が (FQDN が正しく構成されていないトランクの名前など) が拒否された問題では、分析機能を呼び出すことができます。 この例では、SBC のログを参照してください。 直接ルーティングは、半角英数字に問題の詳細な説明を送信します。これらの問題は、SBC のログから読み取ることができます。 
