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
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: ダイレクト ルーティング呼び出し通知
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 4af5d65a3d92fbe104b7c998cd8045b6fb52c653
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457187"
---
# <a name="manage-call-notifications"></a>着信通知の管理

この記事では、ダイレクト ルーティング ユーザーの通話通知を管理する方法について説明します。 通話エンドポイントは、Teamsとサードパーティのプライベート ブランチ Exchange (PBX) またはセッション ボーダー コントローラー (SBC) の両方に構成できます。 この設定は、たとえば、ユーザーの携帯電話とデスクフォンに同時に通話を送信する場合に便利です。   

次の図では、ユーザー Irena には 2 つのエンドポイントがあります。

- Teams エンドポイント
- サード パーティの SBC に接続されている SIP 電話

呼び出しが到着すると、SBC はダイレクト ルーティングとサード パーティ SBC の間の呼び出しをフォークします。


![フォークされたTeamsエンドポイントを示す図。](media/direct-routing-call-notification-1.png)

フォーク 2 で (サード パーティの SBC によって) 呼び出しが受け入れられた場合、Teamsは "不在着信" 通知を生成します。  

次のように SBC を構成して Fork 1 で Cancel を送信するように構成することで、"不在着信" 通知を防止できます。

理由: SIP;cause=200;text"Call completed elsewhere" 

呼び出しは、正常な呼び出しとしてTeams 電話システムの呼び出し詳細レコードに登録されません。 この呼び出しは、Final SIP Code "487"、Final Microsoft サブコード "540200"、および Final SIP Code Phrase "Call completed elsewhere" で "試行" として登録されます。  (通話詳細レコードを表示するには、Teams管理センター -> **Analytics と ReportsUsage** ->  **レポート** に移動し、**PSTN 使用法** を選択します。


次の図は、フォーク 1 の SIP ラダー、呼び出しフロー、およびキャンセル メッセージの想定される REASON を示しています。 

![図は、フォークされたTeamsエンドポイントを示しています。](media/direct-routing-call-notification-2.png)
