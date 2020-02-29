---
title: 電話システムのダイレクト ルーティング
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
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
description: 直接ルーティング通話の通知
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341801"
---
# <a name="manage-call-notifications"></a>着信通知の管理

この記事では、ユーザーの通話通知を管理する方法について説明します。 通話エンドポイントは、Teams とサードパーティの構内交換 (PBX) またはセッションボーダーコントローラー (SBC) の両方に対して構成できます。  これは、たとえば、ユーザーのモバイルおよび卓上電話に同時に通話を送信する場合に便利です。   

次の図では、ユーザー Irena に2つのエンドポイントがあります。

- Teams のエンドポイント
- サードパーティの SBC に接続された SIP 電話

通話が着信すると、SBC は、電話システムのダイレクトルーティングとサードパーティの SBC の間の通話をフォークします。


![フォークされた Teams エンドポイントを示す図](media/direct-routing-call-notification-1.png)

通話が Fork 2 (サードパーティの SBC) で受け入れられた場合、Teams は「不在着信」の通知を生成します。  

次のようにして、Fork 1 でキャンセルを送信するように SBC を設定すると、"不在着信" の通知を防ぐことができます。

理由: SIP;原因 = 200; テキスト "通話がどこかで完了しました" 

通話は、Microsoft 電話システムの通話の詳細レコードに正常に通話として登録されないことに注意してください。 通話は "試行" として登録されます。これには、最終 SIP コード "487"、最終的な Microsoft コードの "540200"、最終 SIP コードフレーズ "通話はどこかで完了しました" となります。  (通話の詳細レコードを表示するには、Teams 管理ポータル、分析とレポート、利用状況レポート、[PSTN の利用状況] を選択します)。


次の図は、Fork 1 での SIP のはしごを示しています。通話フローと、キャンセルメッセージで想定される理由について説明しています。 

![フォークされた Teams エンドポイントを示す図](media/direct-routing-call-notification-2.png)
