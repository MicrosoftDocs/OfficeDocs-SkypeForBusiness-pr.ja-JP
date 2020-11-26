---
title: 直接ルーティング用に Ringback ボットを設定する
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Ringback bot を直接ルーティング用に使用して、通話が確立されているときに発生する可能性のある予期しない silences を防ぐ方法について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26738002ab333d2490ef0dac5674a1f7cdc19efd
ms.sourcegitcommit: 8974cd7a693bc879fed8222f551fd7ce3205dd65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420957"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="ddae2-103">直接ルーティング用に Ringback ボットを設定する</span><span class="sxs-lookup"><span data-stu-id="ddae2-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="ddae2-104">この記事では、Ringback ボットについて説明します。これは、通話の発信に時間がかかる場合に発生する可能性のある予期しない silences を回避するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="ddae2-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="ddae2-105">Ringback bot は、メディア以外のバイパスモードで直接ルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="ddae2-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="ddae2-106">公衆交換電話網 (PSTN) から Teams への着信通話は、確立に予想以上に時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="ddae2-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="ddae2-107">これはさまざまな理由で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ddae2-107">This can occur for various reasons.</span></span> <span data-ttu-id="ddae2-108">この問題が発生した場合、発信者は何も聞こえないか、Teams クライアントが呼び出しを行わないため、一部の通信プロバイダーが通話をキャンセルする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ddae2-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="ddae2-109">Ringback ボットは、このシナリオで発生する可能性のある予期しない silences を回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ddae2-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="ddae2-110">PSTN から Teams クライアントへの着信通話については、Ringback bot は、呼び出し元に対して特徴的な音声信号を再生し、チームが通話の確立プロセス中であることを示します。</span><span class="sxs-lookup"><span data-stu-id="ddae2-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="ddae2-111">Ringback ボットは、Teams バックエンドから早期メディアを生成します。</span><span class="sxs-lookup"><span data-stu-id="ddae2-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="ddae2-112">一部の国と地域では、メディアの流れを開始したときに、通話料金がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ddae2-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="ddae2-113">Ringback ボットを構成する</span><span class="sxs-lookup"><span data-stu-id="ddae2-113">Configure the Ringback bot</span></span>

<span data-ttu-id="ddae2-114">[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway)コマンドレットを使用して、以前に定義したセッション境界コントローラー (SBC) 構成を変更するか、 [CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)コマンドレットを使用して新しい SBC 構成を作成し、 **GenerateRingingWhileLocatingUser** パラメーターと共に Ringback ボットを構成します。</span><span class="sxs-lookup"><span data-stu-id="ddae2-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="ddae2-115">Ringback bot を有効にするには、 **GenerateRingingWhileLocatingUser** パラメーターを [ **$True**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="ddae2-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="ddae2-116">これは既定の値です。</span><span class="sxs-lookup"><span data-stu-id="ddae2-116">This is the default value.</span></span> 

- <span data-ttu-id="ddae2-117">Ringback bot をオフにするには、 **GenerateRingingWhileLocatingUser** パラメーターを [ **$False**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="ddae2-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="ddae2-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ddae2-118">Related topics</span></span>

- [<span data-ttu-id="ddae2-119">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="ddae2-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
