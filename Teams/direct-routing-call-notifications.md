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

この記事では、ダイレクト ルーティング ユーザーの通話通知を管理する方法について説明します。 通話エンドポイントは、サード パーティのプライベート ブランチ Teams (PBX) またはセッション ボーダー コントローラー (SBC) Exchangeに対して構成できます。 このセットアップは、たとえば、ユーザーの携帯電話とデスクフォンに同時に通話を送信する場合に便利です。   

次の図では、ユーザー Irena には 2 つのエンドポイントがあります。

- エンドポイントTeamsエンドポイント
- サード パーティの SBC に接続されている SIP 電話

呼び出しが到着すると、SBC はダイレクト ルーティングとサード パーティの SBC の間の呼び出しをフォークします。


![フォークされたエンドポイントをTeams図。](media/direct-routing-call-notification-1.png)

(サード パーティの SBC によって) Fork 2 で呼び出しが受け入れられる場合、Teams"Missed Call" 通知が生成されます。  

次のように、フォーク 1 でキャンセルを送信する SBC を構成することで、"通話不足" 通知を防ぐことが可能です。

理由: SIP;cause=200;text"call completed elsewhere" 

呼び出しは、成功した呼び出しとして、Teams 電話システムレコードに登録されていません。 呼び出しは、Final SIP Code "487"、Final Microsoft サブコード "540200"、最後の SIP コード フレーズ "他の場所で完了しました" を含む "試行" として登録されます。  (通話の詳細レコードを表示するには、Teams 管理センター -> **Analytics and** **ReportsUsage** ->  Reports] に移動し、[PSTN の使用状況] **を選択** します)。


次の図は、Fork 1 の SIP ラダーを示しています。通話フローと、キャンセル メッセージの予想される理由について説明します。 

![図は、フォークされたエンドポイントTeams示しています。](media/direct-routing-call-notification-2.png)
