---
title: ダイレクト ルーティングの通話通知を管理する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: ダイレクト ルーティング呼び出し通知
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 4aa8e6a6f75141f7858e2342b65fb59d09326c33
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268432"
---
# <a name="manage-call-notifications"></a>着信通知の管理

この記事では、ダイレクト ルーティング ユーザーの通話通知を管理する方法について説明します。 Teams とサード パーティのプライベート ブランチ Exchange (PBX) またはセッション ボーダー コントローラー (SBC) の両方に対して通話エンドポイントを構成できます。 この設定は、たとえば、ユーザーの携帯電話とデスクフォンに同時に通話を送信する場合に便利です。   

次の図では、ユーザー Irena には 2 つのエンドポイントがあります。

- Teams エンドポイント
- サード パーティの SBC に接続されている SIP 電話

呼び出しが到着すると、SBC はダイレクト ルーティングとサード パーティ SBC の間の呼び出しをフォークします。


![フォークされた Teams エンドポイントを示す図。](media/direct-routing-call-notification-1.png)

通話がフォーク 2 で (サード パーティの SBC によって) 受け入れられた場合、Teams は "不在着信" 通知を生成します。  

次のように SBC を構成して Fork 1 で Cancel を送信するように構成することで、"不在着信" 通知を防止できます。

理由: SIP;cause=200;text"Call completed elsewhere" 

通話は、Teams Phone System の通話詳細レコードに正常に呼び出しとして登録されません。 この呼び出しは、Final SIP Code "487"、Final Microsoft サブコード "540200"、および Final SIP Code Phrase "Call completed elsewhere" で "試行" として登録されます。  (通話詳細レコードを表示するには、Teams 管理 センター ->**分析およびレポート** -> **使用状況レポート** に移動し、**PSTN 使用法** を選択します)。


次の図は、フォーク 1 の SIP ラダー、呼び出しフロー、およびキャンセル メッセージの想定される REASON を示しています。 

![図は、フォークされた Teams エンドポイントを示しています。](media/direct-routing-call-notification-2.png)
