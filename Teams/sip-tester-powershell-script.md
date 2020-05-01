---
title: ダイレクトルーティングセッションの境界コントローラー接続をテストする PowerShell スクリプト
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Microsoft Teams でダイレクトルーティングセッションの境界コントローラー接続をテストするには、この PowerShell スクリプトサンプルを使用します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43d1514eff811461ac8b6ad73f7c2a215205f4e3
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951262"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>ダイレクトルーティングセッションの境界コントローラー接続をテストする PowerShell スクリプト

SIP Tester クライアントは、Microsoft Teams でダイレクトルーティングセッションの境界コントローラー (SBC) 接続をテストするために使用できるサンプル PowerShell スクリプトです。 このスクリプトは、ダイレクトルーティングを使用して、ユーザーペアのセッション開始プロトコル (SIP) トランクの基本的な機能をテストします。

このスクリプトは、SIP テストをテストランナーに送信し、結果を待ち、人間が読める形式で提示します。 このスクリプトを使用して、次のシナリオをテストすることができます。

- 発信通話と着信通話
- 同時呼び出し
- メディアのエスカレーション
- 提案転送

## <a name="download-the-script-and-documentation"></a>スクリプトとドキュメントをダウンロードする

[SIP テスターのクライアントスクリプトとドキュメント](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)をダウンロードします。

  > [!NOTE]
  > SIP Tester クライアントスクリプトは adal.ps バージョン3.19.8.1 のみをサポートしています。 Adal.ps の新しいバージョンが使用されると、エラーが返されます。
  
  
