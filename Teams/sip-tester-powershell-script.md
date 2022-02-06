---
title: 直接ルーティング セッション ボーダー コントローラー接続をテストする PowerShell スクリプト
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: この PowerShell スクリプト サンプルを使用して、直接ルーティング セッション ボーダー コントローラー接続をテストMicrosoft Teams。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
  - M365-voice
f1.keywords:
  - NOCSH
appliesto:
  - Microsoft Teams
---

# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>直接ルーティング セッション ボーダー コントローラー接続をテストする PowerShell スクリプト

SIP Tester クライアントは PowerShell スクリプトのサンプルで、このスクリプトを使用して、Microsoft Teams で直接ルーティング セッション ボーダー コントローラー (SBC) 接続をテストできます。 このスクリプトでは、顧客ペアのセッション開始プロトコル (SIP) トランクの基本的な機能を直接ルーティングでテストします。

このスクリプトは、SIP テストをテスト ランナーに送信し、結果を待機して、人間が判読できる形式で表示します。 このスクリプトを使用して、次のシナリオをテストできます。

- 発信呼び出しと着信呼び出し
- 同時呼び出し
- メディアのエスカレーション
- コンサルティング転送

## <a name="download-the-script-and-documentation"></a>スクリプトとドキュメントをダウンロードする

[SIP Tester クライアント スクリプトとドキュメントをダウンロードします](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。

  > [!NOTE]
  > SIP Tester クライアント スクリプトは、adal.ps 3.19.8.1 のみをサポートします。 新しいバージョンのアプリケーションが使用されている場合、エラー adal.ps されます。
  
  
