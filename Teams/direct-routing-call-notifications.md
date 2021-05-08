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
description: ダイレクト ルーティング呼び出し通知
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

この記事では、ユーザーの通話通知を管理する方法について説明します。 サード パーティのプライベート ブランチ Teams (PBX) またはセッション ボーダー コントローラー (SBC) の両方Exchangeエンドポイントを構成できます。  これは、たとえば、ユーザーの携帯電話とデスクフォンに同時に通話を送信する場合に便利です。   

次の図では、ユーザー Irena には 2 つのエンドポイントがあります。

- エンドポイントTeamsエンドポイント
- サード パーティの SBC に接続されている SIP 電話

呼び出しが到着すると、SBC は、ダイレクト ルーティングとサード パーティの SBC 電話システム間の呼び出しをフォークします。


![フォークされたエンドポイントをTeams図](media/direct-routing-call-notification-1.png)

(サード パーティの SBC によって) Fork 2 で呼び出しが受け入れられる場合、Teams"Missed Call" 通知が生成されます。  

次のように、フォーク 1 でキャンセルを送信する SBC を構成することで、"通話不足" 通知を防ぐことが可能です。

理由: SIP;cause=200;text"call completed elsewhere" 

この呼び出しは、正常な呼び出しとして Microsoft 電話詳細レコードに登録されない点に注意してください。 呼び出しは、Final SIP Code "487"、Final Microsoft サブコード "540200"、最後の SIP コード フレーズ "他の場所で完了しました" を含む "試行" として登録されます。  (通話の詳細レコードを表示するには、[管理Teams分析とレポート、利用状況レポート] に移動し、[PSTN の使用状況] を選択します)。


次の図は、Fork 1 の SIP ラダーを示しています。通話フローと、キャンセル メッセージの予想される理由について説明します。 

![フォークされたエンドポイントをTeams図](media/direct-routing-call-notification-2.png)
