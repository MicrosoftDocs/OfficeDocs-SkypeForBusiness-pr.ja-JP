---
title: Lync ルーム システム デバイスを Skype ルーム システム バージョン 2 に移行します。
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: Skype ルーム システム v2 のソフトウェアを使用して Lync ルーム システム デバイスを移行する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 22693913c613f87c3f11ad5b421d771b661d9b91
ms.sourcegitcommit: 502f85e7920b1a9a14f879d6211e10ad8daba69f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2019
ms.locfileid: "29382472"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="1563b-103">Lync ルーム システム (LRS) デバイスを Skype ルーム システム v2 に移行します。</span><span class="sxs-lookup"><span data-stu-id="1563b-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span>

<span data-ttu-id="1563b-104">Skype ルーム システム バージョン 1 (SRS v1) ソフトウェアとデバイスを Lync ルーム システム (LRS) は[、2018 年 10 月 9 日のサポート終了](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)に達しました。</span><span class="sxs-lookup"><span data-stu-id="1563b-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="1563b-105">つまり Skype ルーム システム v1 のソフトウェアは不要になったすべての製品の更新プログラムや修正もはや。</span><span class="sxs-lookup"><span data-stu-id="1563b-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="1563b-106">Skype ルーム システム v1 のソフトウェアを使用して Lync ルームのシステム デバイスを持つお客様は Skype ルーム システム バージョン 2 (SRS v2) にそのデバイスをアップグレードするのにはお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1563b-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="1563b-107">Skype ルーム システムのバージョン 2 (SRS v2) ソフトウェアでは、会議およびすべての SRS v2 はサポートされているデバイスでの通話のビジネス サーバーとオンラインのサービスの Skype の他のマイクロソフトのチームで動作します。</span><span class="sxs-lookup"><span data-stu-id="1563b-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="1563b-108">Skype ルーム システム v1 のソフトウェアのサポートは動作を継続、既存のデバイス**があります**。</span><span class="sxs-lookup"><span data-stu-id="1563b-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="1563b-109">ただし、このソフトウェアには、マイクロソフトが修正プログラムをリリースする必要のあるソフトウェアのバグが発生する場合にサポートされません。</span><span class="sxs-lookup"><span data-stu-id="1563b-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="1563b-110">SRS v1 は、TLS 1.0 を使用して/1.1 今後 Microsoft によって推奨されません。</span><span class="sxs-lookup"><span data-stu-id="1563b-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="1563b-111">[TLS 1.0 または 1.1 の廃止の準備](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)に関する詳細については。</span><span class="sxs-lookup"><span data-stu-id="1563b-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> <span data-ttu-id="1563b-112">Skype ルーム システムの V2 では、TLS 1.2 のサポートを追加して、2018 年 10 月 31日過去の作業を続行します。</span><span class="sxs-lookup"><span data-stu-id="1563b-112">Skype Room System V2 is adding support for TLS 1.2 and will continue to work past October 31, 2018.</span></span> <span data-ttu-id="1563b-113">ビジネス用の Skype 設置 Skype ルーム システム V2 は、TLS 1.0 または 1.1 の廃止に関する一般的なガイドラインに関係なく、TLS 1.2 のサポートを発表するまでお客様は TLS 1.0 または 1.1 を無効します。</span><span class="sxs-lookup"><span data-stu-id="1563b-113">Skype for Business on-premises customers should not disable TLS 1.0/1.1 until Skype Room System V2 announces support for TLS 1.2 regardless of general guidelines on TLS 1.0/1.1 deprecation.</span></span>

## <a name="which-devices-are-affected"></a><span data-ttu-id="1563b-114">どのデバイスが影響を受けるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="1563b-114">Which devices are affected?</span></span>

<span data-ttu-id="1563b-115">この変更によって影響を受けるデバイスの一覧を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="1563b-115">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="1563b-116">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="1563b-116">Crestron RL</span></span>
- [<span data-ttu-id="1563b-117">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="1563b-117">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="1563b-118">スマート ルーム システム</span><span class="sxs-lookup"><span data-stu-id="1563b-118">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="1563b-119">ポリコム CX8000</span><span class="sxs-lookup"><span data-stu-id="1563b-119">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)


## <a name="upgrade-options"></a><span data-ttu-id="1563b-120">アップグレード オプション</span><span class="sxs-lookup"><span data-stu-id="1563b-120">Upgrade options</span></span>

<span data-ttu-id="1563b-121">Skype ルーム システム (SRS v2) の次の世代に Lync の部屋のシステムをアップグレードするための複数のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="1563b-121">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="1563b-122">Crestron ハードウェアの下取りプログラム</span><span class="sxs-lookup"><span data-stu-id="1563b-122">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="1563b-123">Crestron に、すべての非 Crestron Lync ルーム システムのお客様の[Crestron SR システム](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr)またはそれと同等にアップグレードを提供します。</span><span class="sxs-lookup"><span data-stu-id="1563b-123">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="1563b-124">このプログラムの詳細を参照してください[ここで](https://support.crestron.com/app/answers/answer_view/a_id/1000220)または<!-- For details, -->[電子メール](mailto:lrsupgrade@crestron.com)Crestron LRS のサポート。</span><span class="sxs-lookup"><span data-stu-id="1563b-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-srs-v2"></a><span data-ttu-id="1563b-125">SRS v2 にアップグレードを Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="1563b-125">Crestron RL2 upgrade to SRS v2</span></span>

<span data-ttu-id="1563b-126">Crestron RL2 が (Crestron RL200 とも呼ばれます) の既存のお客様が RL3 を使用する現在の RL2 をアップグレードするのには、アップ グレード キットを入手できます、デバイス 1 台あたりコストを最小限に抑える。</span><span class="sxs-lookup"><span data-stu-id="1563b-126">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="1563b-127">このプログラムの詳細を参照してください[ここで](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)。</span><span class="sxs-lookup"><span data-stu-id="1563b-127">See details of this program [here](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="1563b-128">スマート ルーム システムをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="1563b-128">SMART Room Systems upgrade</span></span>

<span data-ttu-id="1563b-129">Crestron ハードウェアの下取りプログラムとは別のスマート LRS お客様は、マイクロソフトとスマートも担当している Skype ルーム システム v2 にアップグレードするソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="1563b-129">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="1563b-130">スマート テクノロジー社でこのアップグレードを提供します。この[ここで](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1563b-130">This upgrade will be provided by SMART Technologies Inc. Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>

<span data-ttu-id="1563b-131">このオプションを使用するには、お客様はさらに[画面共有の logitech (ロジクール)](https://www.logitech.com/en-us/product/screen-share)アダプターを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1563b-131">To use this option, customers must additionally buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter.</span></span> <span data-ttu-id="1563b-132">マイクロソフトは Skype ルーム システム v2 のソフトウェアで、このアダプターを使用する方法の指示を提供します。</span><span class="sxs-lookup"><span data-stu-id="1563b-132">Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software.</span></span>

<span data-ttu-id="1563b-133">このページをすぐにアップグレードの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="1563b-133">Look for upgrade instructions on this page shortly.</span></span>
  
<!-- 
### Summary of upgrade options

This table lists summary of all available options for existing LRS devices:
-->

## <a name="what-should-you-do"></a><span data-ttu-id="1563b-134">何ですか。</span><span class="sxs-lookup"><span data-stu-id="1563b-134">What should you do?</span></span>

<span data-ttu-id="1563b-135">上記のアップグレード オプションを使用して TLS 1.0 または 1.1 廃止する前に Skype ルーム システム v2 に Lync ルーム システム デバイスを更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1563b-135">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="1563b-136">また、SRS v2 の認定、新しいデバイスと既存のデバイスを置き換えることを検討可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1563b-136">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="1563b-137">詳細については、[ルームのデバイス](https://aka.ms/roomdevices)を参照してくださいし、 [Skype ルーム システム v2 の要件](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1563b-137">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Skype Room Systems v2 requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="1563b-138">タッチとホワイト ボードの機能が Skype ルーム システム v2 でまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1563b-138">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="1563b-139">タッチとホワイト ボードのサポートでは、Skype ルーム システム v2 の計画は、現在と、2019年に追加される予定です。</span><span class="sxs-lookup"><span data-stu-id="1563b-139">Touch and whiteboard support is currently planned for Skype Room System v2 and will be added in 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="1563b-140">ルーム システム V2 の Skype ソフトウェアでは、アプリケーションのバージョン 4.0.64.0 で、2018 年 12 月 14 日の時点で TLS 1.2 プロトコルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1563b-140">Skype Room System V2 software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="1563b-141">設置向けに、Skype ルーム システム V2 の TLS 1.2 経由で通信を有効にする必要があります Skype ビジネス サーバー 2015 累積的な更新プログラム 9 (CU9) または Skype のビジネス サーバー 2019 累積的な更新 1 (CU1)。</span><span class="sxs-lookup"><span data-stu-id="1563b-141">For on-premises customers, enabling communication over TLS 1.2 for Skype Room System V2 requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="1563b-142">変更には影響しません Skype オンライン ビジネスのお客様のクライアントの変更は、前方と後方に準拠します。</span><span class="sxs-lookup"><span data-stu-id="1563b-142">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
