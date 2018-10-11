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
ms.openlocfilehash: 790872ceaf919d4b58bdbd753dc32e1303b2da63
ms.sourcegitcommit: 08933c8f795048feaa05828e000df5082ac90761
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "25495591"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="94ff3-103">Lync ルーム システム (LRS) デバイスを Skype ルーム システム v2 に移行します。</span><span class="sxs-lookup"><span data-stu-id="94ff3-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span> 
<span data-ttu-id="94ff3-104">Skype ルーム システム バージョン 1 (SRS v1) ソフトウェアとデバイスを Lync ルーム システム (LRS) は[、2018 年 10 月 9 日のサポート終了](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)に達しました。</span><span class="sxs-lookup"><span data-stu-id="94ff3-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="94ff3-105">つまり Skype ルーム システム v1 のソフトウェアは不要になったすべての製品の更新プログラムや修正もはや。</span><span class="sxs-lookup"><span data-stu-id="94ff3-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="94ff3-106">Skype ルーム システム v1 のソフトウェアを使用して Lync ルームのシステム デバイスを持つお客様は Skype ルーム システム バージョン 2 (SRS v2) にそのデバイスをアップグレードするのにはお勧めします。</span><span class="sxs-lookup"><span data-stu-id="94ff3-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="94ff3-107">Skype ルーム システムのバージョン 2 (SRS v2) ソフトウェアでは、会議およびすべての SRS v2 はサポートされているデバイスでの通話のビジネス サーバーとオンラインのサービスの Skype の他のマイクロソフトのチームで動作します。</span><span class="sxs-lookup"><span data-stu-id="94ff3-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="94ff3-108">Skype ルーム システム v1 のソフトウェアのサポートは動作を継続、既存のデバイス**があります**。</span><span class="sxs-lookup"><span data-stu-id="94ff3-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="94ff3-109">ただし、このソフトウェアには、マイクロソフトが修正プログラムをリリースする必要のあるソフトウェアのバグが発生する場合にサポートされません。</span><span class="sxs-lookup"><span data-stu-id="94ff3-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="94ff3-110">ルーム システム V1 の Skype ソフトウェアはまた TLS 1.2 のサポートにアップグレードされません。</span><span class="sxs-lookup"><span data-stu-id="94ff3-110">Skype Room System V1 software will also not be upgraded to support TLS 1.2.</span></span> <span data-ttu-id="94ff3-111">[TLS 1.0 または 1.1 の廃止の準備](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)に関する詳細については。</span><span class="sxs-lookup"><span data-stu-id="94ff3-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> <span data-ttu-id="94ff3-112">Skype ルーム システムの V2 では、TLS 1.2 のサポートを追加して、この非推奨事項から影響を及ぼすことがなく作業を続けます。</span><span class="sxs-lookup"><span data-stu-id="94ff3-112">Skype Room System V2 is adding support for TLS 1.2 and will continue to work without any impact from this deprecation.</span></span>   

## <a name="which-devices-are-affected"></a><span data-ttu-id="94ff3-113">どのデバイスが影響を受けるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="94ff3-113">Which devices are affected?</span></span>
<span data-ttu-id="94ff3-114">この変更によって影響を受けるデバイスの一覧を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="94ff3-114">Here is the list of the devices that are affected by this change:</span></span>
- [<span data-ttu-id="94ff3-115">スマート ルーム システム</span><span class="sxs-lookup"><span data-stu-id="94ff3-115">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="94ff3-116">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="94ff3-116">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="94ff3-117">ポリコム CX8000</span><span class="sxs-lookup"><span data-stu-id="94ff3-117">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- <span data-ttu-id="94ff3-118">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="94ff3-118">Crestron RL</span></span>

## <a name="upgrade-options"></a><span data-ttu-id="94ff3-119">アップグレード オプション</span><span class="sxs-lookup"><span data-stu-id="94ff3-119">Upgrade options</span></span>
<span data-ttu-id="94ff3-120">Skype ルーム システム (SRS v2) の次の世代に Lync の部屋のシステムをアップグレードするための複数のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="94ff3-120">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="94ff3-121">Crestron ハードウェアの下取りプログラム</span><span class="sxs-lookup"><span data-stu-id="94ff3-121">Crestron hardware Trade-in program</span></span>
<span data-ttu-id="94ff3-122">Crestron に、すべての非 Crestron Lync ルーム システムのお客様の[Crestron SR システム](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr)またはそれと同等にアップグレードを提供します。</span><span class="sxs-lookup"><span data-stu-id="94ff3-122">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="94ff3-123">このプログラムの詳細を参照してください[ここで](https://support.crestron.com/app/answers/answer_view/a_id/1000220)または<!-- For details, -->[電子メール](mailto:lrsupgrade@crestron.com)Crestron LRS のサポート。</span><span class="sxs-lookup"><span data-stu-id="94ff3-123">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="crestron-rl2-to-rl3"></a><span data-ttu-id="94ff3-124">RL3 に Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="94ff3-124">Crestron RL2 to RL3</span></span>
<span data-ttu-id="94ff3-125">Crestron RL2 が (Crestron RL200 とも呼ばれます) の既存のお客様は、RL3 を使用する現在の RL2 をアップグレードするアップグレード パッケージを取得できます、デバイス 1 台あたりコストを最小限に抑える。</span><span class="sxs-lookup"><span data-stu-id="94ff3-125">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade package to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="94ff3-126">このプログラムの詳細を参照してください[ここで](https://support.crestron.com/app/answers/answer_view/a_id/1000220)または<!-- For details, -->[電子メール](mailto:lrsupgrade@crestron.com)Crestron LRS のサポート。</span><span class="sxs-lookup"><span data-stu-id="94ff3-126">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="94ff3-127">スマート ルーム システムをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="94ff3-127">SMART Room Systems upgrade</span></span> 
<span data-ttu-id="94ff3-128">Crestron ハードウェアの下取りプログラムとは別のスマート LRS お客様は、マイクロソフトとスマートも担当している Skype ルーム システム v2 にアップグレードするソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="94ff3-128">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="94ff3-129">スマート テクノロジー社でこのアップグレードを提供します。この[ここで](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94ff3-129">This upgrade will be provided by SMART Technologies Inc. Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>

<!--  
For later 
### Do-It-Yourself
A Do-It-Yourself option is also available for customers with upgrade to Windows 10 and Skype Room Systems v2 software. Windows 10 Enterprise Licenses are available through [approved resellers](https://www.microsoft.com/en-us/Licensing/how-to-buy/how-to-buy.aspx) and Skype Room System V2 software will be available through this guide. 
 
  
To use this option however, customers must additionaly buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter. Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software. 


Look for upgrade instructions on this page shortly. 
  
### Summary of upgrade options
This table lists summary of all available options for existing LRS devices:
<!--  For later 
| Upgrade Option | SMART Room Systems | Crestron RL2 | Polycom CX8000 | Crestron RL |
|:--- |:--- |:--- |:--- |:--- |
|**Crestron hardware </br>Trade-in program**|Available|Available|Available|Available|
|**Crestron RL3**|Not Available|Available|Not Available|Not Available|
|**Do-It-Yourself**|Available|Not Available|Not Available|Not Available|
| | | | | |
-->

## <a name="what-should-you-do"></a><span data-ttu-id="94ff3-130">何ですか。</span><span class="sxs-lookup"><span data-stu-id="94ff3-130">What should you do?</span></span>
<span data-ttu-id="94ff3-131">上記のアップグレード オプションを使用して TLS 1.0 または 1.1 廃止する前に Skype ルーム システム v2 に Lync ルーム システム デバイスを更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="94ff3-131">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="94ff3-132">また、SRS v2 の認定、新しいデバイスと既存のデバイスを置き換えることを検討可能性があります。</span><span class="sxs-lookup"><span data-stu-id="94ff3-132">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="94ff3-133">詳細については、[ルームのデバイス](https://aka.ms/roomdevices)を参照してくださいし、 [Skype ルーム システム v2 の要件](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94ff3-133">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Skype Room Systems v2 requirements](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="94ff3-134">タッチとホワイト ボードの機能が Skype ルーム システム v2 でまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="94ff3-134">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="94ff3-135">タッチとホワイト ボードのサポートでは、Skype ルーム システム v2 のバックログし、H1 CY2019 に追加される予定です。</span><span class="sxs-lookup"><span data-stu-id="94ff3-135">Touch and whiteboard support is in the backlog for Skype Room System v2 and will be added in H1 CY2019.</span></span>

> [!NOTE]
> <span data-ttu-id="94ff3-136">ルーム システム V2 の Skype ソフトウェアは、現在 TLS 1.2 プロトコルをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="94ff3-136">Skype Room System V2 software currently does not support TLS 1.2 protocol.</span></span> <span data-ttu-id="94ff3-137">TLS 1.2 のサポートを選択し、作業中は、TLS 1.1/1/0 の前に完了する廃止。</span><span class="sxs-lookup"><span data-stu-id="94ff3-137">TLS 1.2 support is being worked on and will be completed before TLS 1/0/1.1 deprecation.</span></span> <span data-ttu-id="94ff3-138">SRS v2 に顧客 upgradging SRS v2 アプリケーションの最新バージョンを実行しているルームのデバイスに TLS 1.0 または 1.1 の廃止の影響を与える表示されません。</span><span class="sxs-lookup"><span data-stu-id="94ff3-138">Customers upgradging to SRS v2 will not see any impact of TLS 1.0/1.1 deprecation on Room devices running latest version of SRS v2 app.</span></span>
