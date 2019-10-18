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
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6df8ee654696ceef89c36a354d943c97139bf8b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568678"
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