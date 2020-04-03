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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 344bf59d401e43c40c6f643b334c2f34311d6cbe
ms.sourcegitcommit: 8665603fae8408ccbc083dd59cb01936ebe96c58
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2020
ms.locfileid: "43116693"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="612db-103">ダイレクトルーティングセッションの境界コントローラー接続をテストする PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="612db-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="612db-104">SIP Tester クライアントは、Microsoft Teams でダイレクトルーティングセッションの境界コントローラー (SBC) 接続をテストするために使用できるサンプル PowerShell スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="612db-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="612db-105">このスクリプトは、ダイレクトルーティングを使用して、ユーザーペアのセッション開始プロトコル (SIP) トランクの基本的な機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="612db-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="612db-106">このスクリプトは、SIP テストをテストランナーに送信し、結果を待ち、人間が読める形式で提示します。</span><span class="sxs-lookup"><span data-stu-id="612db-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="612db-107">このスクリプトを使用して、次のシナリオをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="612db-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="612db-108">発信通話と着信通話</span><span class="sxs-lookup"><span data-stu-id="612db-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="612db-109">同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="612db-109">Simultaneous ring</span></span>
- <span data-ttu-id="612db-110">メディアのエスカレーション</span><span class="sxs-lookup"><span data-stu-id="612db-110">Media escalation</span></span>
- <span data-ttu-id="612db-111">提案転送</span><span class="sxs-lookup"><span data-stu-id="612db-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="612db-112">スクリプトとドキュメントをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="612db-112">Download the script and documentation</span></span>

<span data-ttu-id="612db-113">[SIP テスターのクライアントスクリプトとドキュメント](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="612db-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="612db-114">SIP Tester クライアントスクリプトは adal.ps バージョン3.19.8.1 のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="612db-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="612db-115">Adal.ps の新しいバージョンが使用されると、エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="612db-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
