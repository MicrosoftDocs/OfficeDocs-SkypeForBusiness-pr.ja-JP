---
title: ダイレクト ルーティング用にリングバック ボットをセットアップする
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: 呼び出しが確立されているときに発生する可能性がある予期しない無音を防ぐために、直接ルーティングにリングバック ボットを使用する方法について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ec53f1d4f9cd21d3b28c87c07c1bc91d48b9b58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098423"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="64e4c-103">ダイレクト ルーティング用にリングバック ボットをセットアップする</span><span class="sxs-lookup"><span data-stu-id="64e4c-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="64e4c-104">この記事では、呼び出しの確立に長い時間がかかる場合に発生する可能性がある予期しない無音を回避するために使用できるリングバック ボットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="64e4c-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="64e4c-105">リングバック ボットは、メディア以外のバイパス モードのダイレクト ルーティングで利用できます。</span><span class="sxs-lookup"><span data-stu-id="64e4c-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="64e4c-106">公衆交換電話網 (PSTN) から Teams クライアントへの着信通話は、確立が想定以上に長くなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="64e4c-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="64e4c-107">これは、さまざまな理由で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64e4c-107">This can occur for various reasons.</span></span> <span data-ttu-id="64e4c-108">この場合、発信者は何も聞こえない、Teams クライアントが呼び出されない、一部の通信プロバイダーが通話をキャンセルする場合があります。</span><span class="sxs-lookup"><span data-stu-id="64e4c-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="64e4c-109">リングバック ボットは、このシナリオで発生する可能性がある予期しない無音を回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="64e4c-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="64e4c-110">PSTN から Teams クライアントへの着信通話の場合、リングバック ボットは呼び出し元に対して独自の音声信号を再生し、Teams が通話を確立中を示します。</span><span class="sxs-lookup"><span data-stu-id="64e4c-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="64e4c-111">リングバック ボットは、Teams バックエンドから初期メディアを生成します。</span><span class="sxs-lookup"><span data-stu-id="64e4c-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="64e4c-112">一部の国と地域では、メディアの流れを開始するときに通話料金が請求される場合があります。</span><span class="sxs-lookup"><span data-stu-id="64e4c-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="64e4c-113">リングバック ボットを構成する</span><span class="sxs-lookup"><span data-stu-id="64e4c-113">Configure the Ringback bot</span></span>

<span data-ttu-id="64e4c-114">[Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway)コマンドレットを使用して、以前に定義されたセッション ボーダー コントローラー (SBC) 構成または [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway)コマンドレットを変更し **、GenerateRingingWhileLocatingUser** パラメーターと共に新しい SBC 構成を作成し、リングバック ボットを構成します。</span><span class="sxs-lookup"><span data-stu-id="64e4c-114">Use the [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="64e4c-115">リングバック ボットを有効にする場合は **、GenerateRingingWhileLocatingUser** パラメーターを次に **$True。**</span><span class="sxs-lookup"><span data-stu-id="64e4c-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="64e4c-116">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="64e4c-116">This is the default value.</span></span> 

- <span data-ttu-id="64e4c-117">リングバック ボットをオフにする場合は **、GenerateRingingWhileLocatingUser** パラメーターを **$False。**</span><span class="sxs-lookup"><span data-stu-id="64e4c-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="64e4c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="64e4c-118">Related topics</span></span>

- [<span data-ttu-id="64e4c-119">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="64e4c-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)