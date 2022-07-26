---
title: Teams のブラウザー ログとトレース
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.date: 06/21/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Microsoft Teams によって生成されたブラウザーログと WebRTC ログについて説明します。ここで確認できます。このログは、Microsoft サポートを使用してログを収集する方法と、監視とトラブルシューティングに役立つ方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9592091d97ad4fb34f02e906888757f0c7ab14ec
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005469"
---
# <a name="browser-logs-and-tracing-for-teams"></a>Teams のブラウザー ログとトレース

一部のカテゴリのエラーでは、Microsoft サポートブラウザー トレースの収集が必要になる場合があります。 この情報は、エラーが発生した場合の Teams クライアントの状態に関する重要な詳細を提供できます。 この記事では、Teams のブラウザーと WebRTC ログを収集する方法について説明します。

## <a name="browser-logs"></a>ブラウザー ログ

ブラウザー トレースを開始する前に、Teams にサインインしていることを確認します。 トレースを開始する前に、トレースに機密サインイン情報が含まれないようにすることが重要です。

サインインしたら、ブラウザーに応じて次のいずれかのリンクを選択し、指定された手順に従います。 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Edge](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [サファリ](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> 手順では、Azure portalへの参照をすべて Teams クライアントに置き換えます。
  
## <a name="webrtc-logs-in-browsers"></a>ブラウザーの WebRTC ログ

WebRTC ログは、音声通話とビデオ通話の接続の詳細を提供することで、Microsoft サポートを支援できます。 Edge (Chromium) または Chrome で WebRTC ログにアクセスするには、次の手順に従います。
  
1. 新しいタブを開き、次のいずれかの URL に移動します。
    - エッジ (Chromium):`edge://webrtc-internals/`
    - クロム： `chrome://webrtc-internals/`
  
2. Teams Web アプリケーションを開き、問題を再現します。
  
3. 手順 1 でアクセスしたタブに戻るすると、少なくとも 2 つのタブが表示されます。
    - GetUserMedia 要求
    - `https://teams.microsoft.com/url`

4. Teams アプリケーションの名前を含むタブを選択し、ページコンテンツを保存します。

## <a name="related-topics"></a>関連項目

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)

[Teams で監視とトラブルシューティングを行うためのログ ファイルの構成](/MicrosoftTeams/log-files)
