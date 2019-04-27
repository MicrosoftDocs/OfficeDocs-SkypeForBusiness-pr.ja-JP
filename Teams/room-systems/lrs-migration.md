---
title: Lync ルーム システム デバイスをマイクロソフト チームの会議室に移行します。
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: マイクロソフト チームの会議室のソフトウェアを使用して Lync ルーム システム デバイスを移行する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 2d9187643d8ffa72a843cbd72a47f4fd4a564f6e
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362871"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="78694-103">Lync ルーム システム (LRS) デバイスをマイクロソフト チームの会議室に移行します。</span><span class="sxs-lookup"><span data-stu-id="78694-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="78694-104">Skype ルーム システム バージョン 1 (SRS v1) ソフトウェアとデバイスを Lync ルーム システム (LRS) は[、2018 年 10 月 9 日のサポート終了](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)に達しました。</span><span class="sxs-lookup"><span data-stu-id="78694-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="78694-105">つまり Skype ルーム システム v1 のソフトウェアは不要になったすべての製品の更新プログラムや修正もはや。</span><span class="sxs-lookup"><span data-stu-id="78694-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="78694-106">Skype ルーム システム v1 のソフトウェアを使用して Lync ルームのシステム デバイスを持つお客様はマイクロソフト チームの部屋にそのデバイスをアップグレードするのにはお勧めします。</span><span class="sxs-lookup"><span data-stu-id="78694-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="78694-107">会議およびすべての Microsoft チームの会議室での通話のサービスをビジネスのサーバーとオンラインの Skype の他のマイクロソフトのチームでソフトウェアのしくみをマイクロソフト チームの会議室には、デバイスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="78694-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="78694-108">Skype ルーム システム v1 のソフトウェアのサポートは動作を継続、既存のデバイス**があります**。</span><span class="sxs-lookup"><span data-stu-id="78694-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="78694-109">ただし、このソフトウェアには、マイクロソフトが修正プログラムをリリースする必要のあるソフトウェアのバグが発生する場合にサポートされません。</span><span class="sxs-lookup"><span data-stu-id="78694-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="78694-110">SRS v1 は、TLS 1.0 を使用して/1.1 今後 Microsoft によって推奨されません。</span><span class="sxs-lookup"><span data-stu-id="78694-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="78694-111">[TLS 1.0 または 1.1 の廃止の準備](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)に関する詳細については。</span><span class="sxs-lookup"><span data-stu-id="78694-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> <span data-ttu-id="78694-112">マイクロソフト チームの会議室は TLS 1.2 のサポートを追加して、2018 年 10 月 31日過去の作業を続行します。</span><span class="sxs-lookup"><span data-stu-id="78694-112">Microsoft Teams Rooms is adding support for TLS 1.2 and will continue to work past October 31, 2018.</span></span> <span data-ttu-id="78694-113">Skype ビジネスのオンプレミス マイクロソフト チームの会議室は、TLS 1.0 または 1.1 の廃止に関する一般的なガイドラインに関係なく、TLS 1.2 のサポートを発表するまで顧客する必要があります TLS 1.0 または 1.1 を無効します。</span><span class="sxs-lookup"><span data-stu-id="78694-113">Skype for Business on-premises customers should not disable TLS 1.0/1.1 until Microsoft Teams Rooms announces support for TLS 1.2 regardless of general guidelines on TLS 1.0/1.1 deprecation.</span></span>

## <a name="which-devices-are-affected"></a><span data-ttu-id="78694-114">どのデバイスが影響を受けるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="78694-114">Which devices are affected?</span></span>

<span data-ttu-id="78694-115">この変更によって影響を受けるデバイスの一覧を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="78694-115">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="78694-116">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="78694-116">Crestron RL</span></span>
- [<span data-ttu-id="78694-117">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="78694-117">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="78694-118">スマート ルーム システム</span><span class="sxs-lookup"><span data-stu-id="78694-118">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="78694-119">ポリコム CX8000</span><span class="sxs-lookup"><span data-stu-id="78694-119">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="78694-120">アップグレード オプション</span><span class="sxs-lookup"><span data-stu-id="78694-120">Upgrade options</span></span>

<span data-ttu-id="78694-121">次世代の Microsoft チームの会議室に Lync の部屋のシステムをアップグレードするための複数のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="78694-121">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="78694-122">Crestron ハードウェアの下取りプログラム</span><span class="sxs-lookup"><span data-stu-id="78694-122">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="78694-123">Crestron に、すべての非 Crestron Lync ルーム システム (例: スマートまたはポリコム LRS) [Crestron SR システム](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr)またはそれと同等にアップグレードを提供します。</span><span class="sxs-lookup"><span data-stu-id="78694-123">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="78694-124">このプログラムの詳細を参照してください[ここで](https://support.crestron.com/app/answers/answer_view/a_id/1000220)または</span><span class="sxs-lookup"><span data-stu-id="78694-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="78694-125">[電子メール](mailto:lrsupgrade@crestron.com)Crestron LRS のサポート。</span><span class="sxs-lookup"><span data-stu-id="78694-125">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="78694-126">マイクロソフト チームの会議室に Crestron RL2 のアップグレード</span><span class="sxs-lookup"><span data-stu-id="78694-126">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="78694-127">Crestron RL2 が (Crestron RL200 とも呼ばれます) の既存のお客様が RL3 を使用する現在の RL2 をアップグレードするのには、アップ グレード キットを入手できます、デバイス 1 台あたりコストを最小限に抑える。</span><span class="sxs-lookup"><span data-stu-id="78694-127">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="78694-128">このプログラムの詳細を参照してください[ここで](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)。</span><span class="sxs-lookup"><span data-stu-id="78694-128">See details of this program [here](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="78694-129">スマート ルーム システムをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="78694-129">SMART Room Systems upgrade</span></span>

<span data-ttu-id="78694-130">Crestron ハードウェアの下取りプログラムとは別のスマート LRS の顧客スマートはマイクロソフト チームの部屋にアップグレードするソリューションを提供することにも取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="78694-130">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="78694-131">このアップグレードは、製品サポートでお客様にスマート テクノロジー社で提供されます。</span><span class="sxs-lookup"><span data-stu-id="78694-131">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="78694-132">この[ここで](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78694-132">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="78694-133">何ですか。</span><span class="sxs-lookup"><span data-stu-id="78694-133">What should you do?</span></span>

<span data-ttu-id="78694-134">マイクロソフト チームの会議室に上記のアップグレード オプションを使用して TLS 1.0 または 1.1 廃止する前に Lync ルーム システム デバイスを更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="78694-134">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="78694-135">また、マイクロソフト チームの会議室の認定、新しいデバイスと既存のデバイスを置き換えることを検討可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78694-135">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="78694-136">詳細については、[ルームのデバイス](https://aka.ms/roomdevices)を参照してください、[マイクロソフト チームの会議室の要件](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78694-136">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="78694-137">タッチとホワイト ボードの機能がマイクロソフト チームの会議室でまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="78694-137">Touch and whiteboard functionality is not yet supported in Microsoft Teams Rooms.</span></span> <span data-ttu-id="78694-138">タッチとホワイト ボードのサポートは、マイクロソフト チームの会議室の予定は現在と、2019年に追加される予定です。</span><span class="sxs-lookup"><span data-stu-id="78694-138">Touch and whiteboard support is currently planned for Microsoft Teams Rooms and will be added in 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="78694-139">マイクロソフト チームの会議室のソフトウェアは、アプリケーションのバージョン 4.0.64.0 で、2018 年 12 月 14 日の時点で TLS 1.2 プロトコルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="78694-139">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="78694-140">設置向けに、マイクロソフト チームの会議室の TLS 1.2 経由で通信を有効にする必要があります Skype ビジネス サーバー 2015 累積的な更新プログラム 9 (CU9) または Skype のビジネス サーバー 2019 累積的な更新 1 (CU1)。</span><span class="sxs-lookup"><span data-stu-id="78694-140">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="78694-141">変更には影響しません Skype オンライン ビジネスのお客様のクライアントの変更は、前方と後方に準拠します。</span><span class="sxs-lookup"><span data-stu-id="78694-141">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
