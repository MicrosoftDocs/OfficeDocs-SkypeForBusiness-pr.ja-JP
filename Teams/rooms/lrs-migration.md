---
title: Lync Room システムデバイスを Microsoft Teams Rooms に移行する
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: このトピックでは、 Lync Room システムデバイスを移行して、Microsoft Teams Rooms のソフトウェアを使用する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d8da14f2d5f3ec75c6a9fb9c03a33d7e83cd1aed
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662622"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="74563-103">Microsoft Teams Rooms にLync Room System (LRS) デバイスを移行する</span><span class="sxs-lookup"><span data-stu-id="74563-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="74563-104">Skype Room System バージョン1 (SRS v1) ソフトウェアを搭載した Lync Room System (LRS) デバイスは、[2018年10月9日にサポートが終了しました](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)。</span><span class="sxs-lookup"><span data-stu-id="74563-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="74563-105">これは、Skype ミーティング システム V1 ソフトウェアがもはや製品の更新プログラムや修正を取得しなくなることを意味します。</span><span class="sxs-lookup"><span data-stu-id="74563-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="74563-106">Skype ミーティング システム V1 ソフトウェアを使用している Lync Room System デバイスをお持ちのお客様には、デバイスを Microsoft Teams Rooms にアップグレードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="74563-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="74563-107">Microsoft Teams Rooms のソフトウェアは、Skype for Business Server、会議のためのオンラインサービス、Microsoft Teams Rooms にサポートされたデバイスと同じく、Microsoft Teamsと連携します。</span><span class="sxs-lookup"><span data-stu-id="74563-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="74563-108">Skype 会議システムv1のソフトウェアサポートが終了しても、既存のデバイス が引き続き動作する **かもしれません**。</span><span class="sxs-lookup"><span data-stu-id="74563-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="74563-109">ただし、このソフトウェアにMicrosoft の修正プログラムのリリースが必要とされるソフトウェアバグが発見された場合は、サポートされません。</span><span class="sxs-lookup"><span data-stu-id="74563-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="74563-110">SRS v1 は、今後 Microsoft によって廃止される予定の TLS 1.0/1.1 を使用します。</span><span class="sxs-lookup"><span data-stu-id="74563-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="74563-111">[TLS 1.0/1.1 の廃止を準備する](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608) について参照してください。</span><span class="sxs-lookup"><span data-stu-id="74563-111">You can learn more about [preparing for TLS 1.0/1.1 deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> 

## <a name="which-devices-are-affected"></a><span data-ttu-id="74563-112">どのデバイスが影響を受けますか?</span><span class="sxs-lookup"><span data-stu-id="74563-112">Which devices are affected?</span></span>

<span data-ttu-id="74563-113">この変更の影響を受けるデバイスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="74563-113">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="74563-114">Crestron SR</span><span class="sxs-lookup"><span data-stu-id="74563-114">Crestron RL</span></span>
- [<span data-ttu-id="74563-115">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="74563-115">Crestron RL2</span></span>](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="74563-116">SMART Roomシステム</span><span class="sxs-lookup"><span data-stu-id="74563-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="74563-117">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="74563-117">Polycom CX8000</span></span>](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="74563-118">アップグレード方法</span><span class="sxs-lookup"><span data-stu-id="74563-118">Upgrade options</span></span>

<span data-ttu-id="74563-119">Microsoft Teams Rooms の次世代に、Lync Room システムをアップグレードする方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="74563-119">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="74563-120">Crestronハードウェアの下取りプログラム</span><span class="sxs-lookup"><span data-stu-id="74563-120">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="74563-121">Crestronは、 [Crestron SR システム](https://www.crestron.com/products/featured-solutions/crestron-sr)へアップグレードします。 または、非Crestron Lync Room Systemのお客様(例：SmartまたはPolycom LRS)に対しては、同等のアップグレードを提供します。</span><span class="sxs-lookup"><span data-stu-id="74563-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="74563-122">このプログラムの詳細については、[こちら](https://support.crestron.com/app/answers/answer_view/a_id/1000220)をご覧 ください。または、</span><span class="sxs-lookup"><span data-stu-id="74563-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="74563-123">[メール](mailto:lrsupgrade@crestron.com) Creon LRS サポート。</span><span class="sxs-lookup"><span data-stu-id="74563-123">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="74563-124">Crestron RL2 を Microsoft Teams Rooms にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="74563-124">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="74563-125">既存の Crestron RL2 (Crestron RL200 とも呼ばれます)の お客様は、デバイスあたりのコストを最小限に抑えるために、現在の RL2をRL3にアップグレードするためのアップグレードキットを 入手できます。</span><span class="sxs-lookup"><span data-stu-id="74563-125">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="74563-126">このプログラムの詳細については、[こちら](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="74563-126">See details of this program [here](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="74563-127">SMART Roomシステムアップグレード</span><span class="sxs-lookup"><span data-stu-id="74563-127">SMART Room Systems upgrade</span></span>

<span data-ttu-id="74563-128">SMART LRS のお客様のために、Crestron hardware の下取りプログラムとは別に、Microsoft Teams Rooms にアップグレードするためのソリューションをSMARTは提供しています。</span><span class="sxs-lookup"><span data-stu-id="74563-128">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="74563-129">このアップグレードは、製品サポートの対象のお客様に対して、SMART Technologies Inc. が提供します。</span><span class="sxs-lookup"><span data-stu-id="74563-129">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="74563-130">詳細については、[こちら](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74563-130">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="74563-131">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="74563-131">What should you do?</span></span>

<span data-ttu-id="74563-132">以前に説明したアップグレードオプションを使用して、TLS 1.0/1.1 が廃止される前に、Lync Room Systemデバイスを Microsoft Teams Rooms に更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="74563-132">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="74563-133">また、既存のデバイスを、Microsoft Teams Rooms 用の新しい承認済デバイスに置き換えることもできます。</span><span class="sxs-lookup"><span data-stu-id="74563-133">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="74563-134">詳細については、「[ミーティングの デバイス](https://aka.ms/roomdevices) 」を参照してください。また、「[Microsoft Teams Rooms の要件](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74563-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  


> [!NOTE]
> <span data-ttu-id="74563-135">Microsoft Teams Rooms のソフトウェアは、アプリバージョン4.0.64.0 を使用して2018年12月14日に TLS 1.2 プロトコルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="74563-135">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="74563-136">オンプレミスのお客様の場合は、Microsoft Teams Rooms の TLS 1.2 経由の通信を有効にするには、Skype for Business Server 2015 累積更新プログラム 9 (CU9) または Skype for Business Server 2019 累積更新プログラム 1 (CU1) が必要です。</span><span class="sxs-lookup"><span data-stu-id="74563-136">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="74563-137">クライアントの変更は、前方および後方準拠として行われるため、変更は Skype for Business Online の顧客には影響しません。</span><span class="sxs-lookup"><span data-stu-id="74563-137">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
