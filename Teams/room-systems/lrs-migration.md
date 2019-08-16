---
title: Lync Room システムデバイスを Microsoft Teams ルームに移行する
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: このトピックでは、Lync Room System デバイスを移行して Microsoft Teams のルームソフトウェアを使用する方法について説明します。
ms.openlocfilehash: c98d2081c29967c033d705082b4ebbffbd42b3ea
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427961"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="246a6-103">Lync Room System (LRS) デバイスを Microsoft Teams ルームに移行する</span><span class="sxs-lookup"><span data-stu-id="246a6-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="246a6-104">Skype Room System バージョン 1 (SRS v1) ソフトウェアが搭載された Lync Room System (LRS) デバイスは[、2018年10月9日にサポート終了に](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)なりました。</span><span class="sxs-lookup"><span data-stu-id="246a6-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="246a6-105">これにより、Skype Room Systems v1 ソフトウェアは今後、製品の更新や修正プログラムを入手できなくなります。</span><span class="sxs-lookup"><span data-stu-id="246a6-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="246a6-106">Skype Room System v1 ソフトウェアを使用する Lync Room システムデバイスをお使いのお客様は、お客様のデバイスを Microsoft Teams のルームにアップグレードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="246a6-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="246a6-107">Microsoft Teams ルームソフトウェアは、Skype for Business Server やオンラインサービスに加えて、microsoft teams でサポートされているすべてのデバイスで会議や通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="246a6-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="246a6-108">既存のデバイスは、Skype Room System v1 ソフトウェアのサポート終了後も引き続き機能する**可能性があり**ます。</span><span class="sxs-lookup"><span data-stu-id="246a6-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="246a6-109">ただし、このソフトウェアが、Microsoft が修正プログラムをリリースする必要があるソフトウェアバグを発見した場合は、サポートされません。</span><span class="sxs-lookup"><span data-stu-id="246a6-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="246a6-110">SRS v1 は、今後 Microsoft によって廃止される TLS 1.0/1.1 を使用しています。</span><span class="sxs-lookup"><span data-stu-id="246a6-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="246a6-111">[TLS 1.0/1.1 の廃止を準備](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)する方法については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="246a6-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> <span data-ttu-id="246a6-112">Microsoft Teams のルームは、TLS 1.2 のサポートを追加しており、2018年10月31日まで動作し続けます。</span><span class="sxs-lookup"><span data-stu-id="246a6-112">Microsoft Teams Rooms is adding support for TLS 1.2 and will continue to work past October 31, 2018.</span></span> <span data-ttu-id="246a6-113">Skype for Business オンプレミスのお客様は、tls 1.0/1.1 の廃止に関する一般的なガイドラインに関係なく、tls 1.2 のサポートを Microsoft Teams が発表するまで、TLS 1.0/1.1 を無効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="246a6-113">Skype for Business on-premises customers should not disable TLS 1.0/1.1 until Microsoft Teams Rooms announces support for TLS 1.2 regardless of general guidelines on TLS 1.0/1.1 deprecation.</span></span>

## <a name="which-devices-are-affected"></a><span data-ttu-id="246a6-114">影響を受けるデバイス</span><span class="sxs-lookup"><span data-stu-id="246a6-114">Which devices are affected?</span></span>

<span data-ttu-id="246a6-115">この変更の影響を受けるデバイスの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="246a6-115">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="246a6-116">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="246a6-116">Crestron RL</span></span>
- [<span data-ttu-id="246a6-117">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="246a6-117">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="246a6-118">スマートルームシステム</span><span class="sxs-lookup"><span data-stu-id="246a6-118">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="246a6-119">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="246a6-119">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="246a6-120">アップグレードオプション</span><span class="sxs-lookup"><span data-stu-id="246a6-120">Upgrade options</span></span>

<span data-ttu-id="246a6-121">Lync Room Systems を次世代の Microsoft Teams ルームにアップグレードするには、複数のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="246a6-121">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="246a6-122">ハードウェアのトレードインプログラムについて</span><span class="sxs-lookup"><span data-stu-id="246a6-122">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="246a6-123">Crestron は、ユーザーが Lync Room System のすべてのユーザー (たとえば、スマートまたは Polycom LRS) で、 [CRESTRON SR システム](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr)または同等のものにアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="246a6-123">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="246a6-124">このプログラムの詳細を[](https://support.crestron.com/app/answers/answer_view/a_id/1000220)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="246a6-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="246a6-125">[メール](mailto:lrsupgrade@crestron.com)Crestron LRS サポート。</span><span class="sxs-lookup"><span data-stu-id="246a6-125">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="246a6-126">RL2 を Microsoft Teams ルームにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="246a6-126">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="246a6-127">既存の Crestron RL2 (Crestron RL200 とも呼ばれます) ユーザーは、アップグレードキットを取得して、現在の RL2 を RL3 にアップグレードし、デバイスごとに最小のコストを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="246a6-127">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="246a6-128">このプログラムの詳細[はこちら](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="246a6-128">See details of this program [here](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="246a6-129">スマートルームシステムのアップグレード</span><span class="sxs-lookup"><span data-stu-id="246a6-129">SMART Room Systems upgrade</span></span>

<span data-ttu-id="246a6-130">スマート LRS をお使いのお客様の場合は、「Crestron hardware トレードインプログラム」を参照してください。また、Microsoft Teams ルームにアップグレードするための解決策を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="246a6-130">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="246a6-131">このアップグレードは、「製品サポート」の下で SMART Technologies Inc. によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="246a6-131">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="246a6-132">詳細[はこちら](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="246a6-132">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="246a6-133">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="246a6-133">What should you do?</span></span>

<span data-ttu-id="246a6-134">TLS 1.0/1.1 が廃止されてから、上記のアップグレードオプションを使用する前に、Lync Room システムデバイスを Microsoft Teams ルームに更新することを計画しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="246a6-134">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="246a6-135">また、既存のデバイスを、Microsoft Teams のルームで認定された新しいデバイスに置き換えることを検討することもできます。</span><span class="sxs-lookup"><span data-stu-id="246a6-135">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="246a6-136">詳細については、「[会議室デバイス](https://aka.ms/roomdevices)」を参照してください。また、 [Microsoft Teams の会議の要件](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)についてもご覧ください。</span><span class="sxs-lookup"><span data-stu-id="246a6-136">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="246a6-137">タッチとホワイトボードの機能は、Microsoft Teams のルームではまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="246a6-137">Touch and whiteboard functionality is not yet supported in Microsoft Teams Rooms.</span></span> <span data-ttu-id="246a6-138">タッチとホワイトボードのサポートは、現在、Microsoft Teams のルームでサポートされており、2019で追加されます。</span><span class="sxs-lookup"><span data-stu-id="246a6-138">Touch and whiteboard support is currently planned for Microsoft Teams Rooms and will be added in 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="246a6-139">Microsoft Teams のルームソフトウェアでは、2018年12月14日の4.0.64.0 で TLS 1.2 プロトコルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="246a6-139">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="246a6-140">オンプレミスのお客様の場合、Microsoft Teams の TLS 1.2 での通信を有効にするには、Skype for Business Server 2015 累積更新プログラム 9 (CU9) または Skype for Business Server 2019 累積更新プログラム 1 (CU1) が必要です。</span><span class="sxs-lookup"><span data-stu-id="246a6-140">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="246a6-141">クライアントの変更が転送され、下位に準拠しているため、この変更は Skype for Business Online のユーザーに影響を与えないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="246a6-141">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
