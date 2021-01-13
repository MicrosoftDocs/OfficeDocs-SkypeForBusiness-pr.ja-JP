---
title: 直接ルーティング セッション ボーダー コントローラー接続をテストする PowerShell スクリプト
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: この PowerShell スクリプトサンプルを使用して、Microsoft Teams で直接ルーティング セッション ボーダー コントローラー接続をテストします。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c52febae3d734af49d1b23c7c65ceb0c2f746f7a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834277"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>直接ルーティング セッション ボーダー コントローラー接続をテストする PowerShell スクリプト

SIP テスター クライアントは、Microsoft Teams で直接ルーティング セッション ボーダー コントローラー (SBC) 接続をテストするために使用できる PowerShell スクリプトのサンプルです。 このスクリプトは、顧客がペアリングしたセッション開始プロトコル (SIP) トランクとダイレクト ルーティングの基本的な機能をテストします。

スクリプトは SIP テストをテスト の実行者に送信し、結果を待ち、人間が読み取り可能な形式で表示します。 このスクリプトを使用して、次のシナリオをテストできます。

- 発信通話と着信通話
- 同時呼び出し
- メディアのエスカレーション
- コンサルティングの譲渡

## <a name="download-the-script-and-documentation"></a>スクリプトとドキュメントをダウンロードする

SIP [Tester クライアント スクリプトとドキュメントをダウンロードします](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。

  > [!NOTE]
  > SIP Tester クライアント スクリプトは、adal.ps 3.19.8.1 のみをサポートします。 新しいバージョンのアプリケーションを使用すると、エラー adal.psされます。
  
  
