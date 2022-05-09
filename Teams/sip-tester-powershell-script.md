---
title: ダイレクト ルーティング セッション ボーダー コントローラー接続をテストする PowerShell スクリプト
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: この PowerShell スクリプト サンプルを使用して、Microsoft Teamsでダイレクト ルーティング セッション ボーダー コントローラー接続をテストします。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: e7158240ef6ab707dfeb4dafd6037295ae1069bf
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62405979"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>ダイレクト ルーティング セッション ボーダー コントローラー接続をテストする PowerShell スクリプト

SIP Tester クライアントは、Microsoft Teamsでダイレクト ルーティング セッション ボーダー コントローラー (SBC) 接続をテストするために使用できるサンプル PowerShell スクリプトです。 このスクリプトは、ダイレクト ルーティングを使用して、顧客とペアになっているセッション開始プロトコル (SIP) トランクの基本的な機能をテストします。

スクリプトは、テスト ランナーに SIP テストを送信し、結果を待ってから、人間が判読できる形式で表示します。 このスクリプトを使用して、次のシナリオをテストできます。

- 発信呼び出しと受信呼び出し
- 同時リング
- メディアエスカレーション
- コンサルティングの譲渡

## <a name="download-the-script-and-documentation"></a>スクリプトとドキュメントをダウンロードする

[SIP Tester クライアント のスクリプトとドキュメントをダウンロードします](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。

  > [!NOTE]
  > SIP Tester クライアント スクリプトでは、adal.ps バージョン 3.19.8.1 のみがサポートされます。 新しいバージョンの adal.ps が使用されている場合は、エラーが返されます。
  
  
