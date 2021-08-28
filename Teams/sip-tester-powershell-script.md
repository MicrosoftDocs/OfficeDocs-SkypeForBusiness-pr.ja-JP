---
title: 直接ルーティング セッション ボーダー コントローラー接続をテストする PowerShell スクリプト
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: 1258f85219e5ce6c00f8db5dac3a5233ce2c0717
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627099"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>直接ルーティング セッション ボーダー コントローラー接続をテストする PowerShell スクリプト

SIP Tester クライアントは、直接ルーティング セッション ボーダー コントローラー (SBC) 接続をテストするために使用できる PowerShell スクリプトのサンプルMicrosoft Teams。 このスクリプトでは、顧客ペアのセッション開始プロトコル (SIP) トランクの基本的な機能を直接ルーティングでテストします。

このスクリプトは、SIP テストをテスト ランナーに送信し、結果を待機して、人間が判読できる形式で表示します。 このスクリプトを使用して、次のシナリオをテストできます。

- 発信呼び出しと着信呼び出し
- 同時呼び出し
- メディアのエスカレーション
- コンサルティング転送

## <a name="download-the-script-and-documentation"></a>スクリプトとドキュメントをダウンロードする

SIP [Tester クライアント スクリプトとドキュメント をダウンロードします](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。

  > [!NOTE]
  > SIP Tester クライアント スクリプトは、adal.ps 3.19.8.1 のみをサポートします。 新しいバージョンのアプリケーションが使用されている場合、adal.ps 返されます。
  
  
