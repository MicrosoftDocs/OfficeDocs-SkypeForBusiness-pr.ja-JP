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
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="26ab6-103">直接ルーティング セッション ボーダー コントローラー接続をテストする PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="26ab6-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="26ab6-104">SIP Tester クライアントは、直接ルーティング セッション ボーダー コントローラー (SBC) 接続をテストするために使用できる PowerShell スクリプトのサンプルMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="26ab6-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="26ab6-105">このスクリプトでは、顧客ペアのセッション開始プロトコル (SIP) トランクの基本的な機能を直接ルーティングでテストします。</span><span class="sxs-lookup"><span data-stu-id="26ab6-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="26ab6-106">このスクリプトは、SIP テストをテスト ランナーに送信し、結果を待機してから、人間が判読できる形式で表示します。</span><span class="sxs-lookup"><span data-stu-id="26ab6-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="26ab6-107">このスクリプトを使用して、次のシナリオをテストできます。</span><span class="sxs-lookup"><span data-stu-id="26ab6-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="26ab6-108">発信呼び出しと着信呼び出し</span><span class="sxs-lookup"><span data-stu-id="26ab6-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="26ab6-109">同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="26ab6-109">Simultaneous ring</span></span>
- <span data-ttu-id="26ab6-110">メディアのエスカレーション</span><span class="sxs-lookup"><span data-stu-id="26ab6-110">Media escalation</span></span>
- <span data-ttu-id="26ab6-111">コンサルティング転送</span><span class="sxs-lookup"><span data-stu-id="26ab6-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="26ab6-112">スクリプトとドキュメントをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="26ab6-112">Download the script and documentation</span></span>

<span data-ttu-id="26ab6-113">SIP [Tester クライアント スクリプトとドキュメント をダウンロードします](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="26ab6-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="26ab6-114">SIP Tester クライアント スクリプトは、adal.ps 3.19.8.1 のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="26ab6-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="26ab6-115">新しいバージョンのアプリケーションが使用されている場合、adal.ps 返されます。</span><span class="sxs-lookup"><span data-stu-id="26ab6-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
