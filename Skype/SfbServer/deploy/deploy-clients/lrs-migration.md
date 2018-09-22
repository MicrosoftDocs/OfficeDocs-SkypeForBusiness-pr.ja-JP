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
ms.openlocfilehash: 954d7893572c1d97506f4b6845792b0b940c3f2b
ms.sourcegitcommit: 6212645c485c41aafe1206bf7d39171ce35837b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2018
ms.locfileid: "24968637"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="7d57a-103">Lync ルーム システム (LRS) デバイスを Skype ルーム システム v2 に移行します。</span><span class="sxs-lookup"><span data-stu-id="7d57a-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span> 
<span data-ttu-id="7d57a-104">Skype ルーム システム バージョン 1 (SRS v1) ソフトウェアとデバイスを Lync ルーム システム (LRS) に到達、2018 年 10 月 9日のサポートは終了します。</span><span class="sxs-lookup"><span data-stu-id="7d57a-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software will reach end of support on October 9, 2018.</span></span> <span data-ttu-id="7d57a-105">つまり、Skype ルームのシステム ソフトウェアは、製品の更新プログラムまたはこの日付以降後の修正プログラムを取得できません。</span><span class="sxs-lookup"><span data-stu-id="7d57a-105">This means Skype Room Systems software will not get any product updates or fixes after this date.</span></span> <span data-ttu-id="7d57a-106">Skype ルーム システム v1 のソフトウェアを使用して Lync ルームのシステム デバイスを持つお客様は Skype ルーム システム バージョン 2 (SRS v2) にそのデバイスをアップグレードするのにはお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7d57a-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="7d57a-107">Skype ルーム システムのバージョン 2 (SRS v2) ソフトウェアでは、会議およびすべての SRS v2 はサポートされているデバイスでの通話のビジネス サーバーとオンラインのサービスの Skype の他のマイクロソフトのチームで動作します。</span><span class="sxs-lookup"><span data-stu-id="7d57a-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="7d57a-108">Skype ルーム システム v1 のソフトウェアのサポートは動作を継続、既存のデバイス**があります**。</span><span class="sxs-lookup"><span data-stu-id="7d57a-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="7d57a-109">このソフトウェア、Microsoft は、修正プログラムをリリースする必要のあるソフトウェアのバグをヒットして最終的にか場合は、既存の通信プロトコルが Skype ルーム システム v1 のソフトウェアの変更で使用されているか、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7d57a-109">This software will eventually hit a software bug that needs Microsoft to release a fix, or may have a case where an existing communication protocol used by Skype Room System v1 software changes or is no longer supported.</span></span> <span data-ttu-id="7d57a-110">このような既知の 1 つの変更は、TLS 1.0 の廃止/1.1 Microsoft Office 365 にします。</span><span class="sxs-lookup"><span data-stu-id="7d57a-110">One such known change is deprecation of TLS 1.0/ 1.1 in Microsoft Office 365.</span></span> <span data-ttu-id="7d57a-111">[TLS 1.0 または 1.1 の廃止の準備](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)に関する詳細については。</span><span class="sxs-lookup"><span data-stu-id="7d57a-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span>  

## <a name="which-devices-are-affected"></a><span data-ttu-id="7d57a-112">どのデバイスが影響を受けるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="7d57a-112">Which devices are affected?</span></span>
<span data-ttu-id="7d57a-113">この変更によって影響を受けるデバイスの一覧を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="7d57a-113">Here is the list of the devices that are affected by this change:</span></span>
- [<span data-ttu-id="7d57a-114">スマート ルーム システム</span><span class="sxs-lookup"><span data-stu-id="7d57a-114">SMART Room systems</span></span>](https://smartkapp.com/products/smart-room-systems)
- [<span data-ttu-id="7d57a-115">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="7d57a-115">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="7d57a-116">ポリコム CX8000</span><span class="sxs-lookup"><span data-stu-id="7d57a-116">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- <span data-ttu-id="7d57a-117">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="7d57a-117">Crestron RL</span></span>

## <a name="upgrade-options"></a><span data-ttu-id="7d57a-118">アップグレード オプション</span><span class="sxs-lookup"><span data-stu-id="7d57a-118">Upgrade options</span></span>
<span data-ttu-id="7d57a-119">Skype ルーム システム (SRS v2) の次の世代に Lync の部屋のシステムをアップグレードするための複数のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="7d57a-119">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="7d57a-120">Crestron ハードウェアの下取りプログラム</span><span class="sxs-lookup"><span data-stu-id="7d57a-120">Crestron hardware Trade-in program</span></span>
<span data-ttu-id="7d57a-121">Crestron に、すべての非 Crestron Lync ルーム システムのお客様の[Crestron SR システム](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr)またはそれと同等にアップグレードを提供します。</span><span class="sxs-lookup"><span data-stu-id="7d57a-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="7d57a-122">このプログラムの詳細を参照してください[ここで](https://support.crestron.com/app/answers/answer_view/a_id/1000220)または<!-- For details, -->[電子メール](mailto:lrsupgrade@crestron.com)Crestron LRS のサポート。</span><span class="sxs-lookup"><span data-stu-id="7d57a-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="crestron-rl2-to-rl3"></a><span data-ttu-id="7d57a-123">RL3 に Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="7d57a-123">Crestron RL2 to RL3</span></span>
<span data-ttu-id="7d57a-124">Crestron RL2 が (Crestron RL200 とも呼ばれます) の既存のお客様は、RL3 を使用する現在の RL2 をアップグレードするアップグレード パッケージを取得できます、デバイス 1 台あたりコストを最小限に抑える。</span><span class="sxs-lookup"><span data-stu-id="7d57a-124">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade package to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="7d57a-125">このプログラムの詳細を参照してください[ここで](https://support.crestron.com/app/answers/answer_view/a_id/1000220)または<!-- For details, -->[電子メール](mailto:lrsupgrade@crestron.com)Crestron LRS のサポート。</span><span class="sxs-lookup"><span data-stu-id="7d57a-125">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="smart-room-systems-upgrade--diy-program"></a><span data-ttu-id="7d57a-126">スマート ルーム システム アップグレード & DIY プログラム</span><span class="sxs-lookup"><span data-stu-id="7d57a-126">SMART Room Systems upgrade & DIY program</span></span>
<span data-ttu-id="7d57a-127">Crestron ハードウェアの下取りプログラムとは別のスマート LRS お客様は、マイクロソフトとスマートも担当している Skype ルーム システム v2 にアップグレードするソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="7d57a-127">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="7d57a-128">Microsoft は、スマート LRS のお客様の DIY のソリューションをテストしても。</span><span class="sxs-lookup"><span data-stu-id="7d57a-128">Microsoft is also testing a DIY solution for SMART LRS customers.</span></span> <span data-ttu-id="7d57a-129">2018年 10 月を事前にこのページでこれらのプログラムの詳細が提供されます。</span><span class="sxs-lookup"><span data-stu-id="7d57a-129">More details of these programs will be provided on this page in early October 2018.</span></span> <span data-ttu-id="7d57a-130">これらのアップグレードのオプションの更新プログラムを確認することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7d57a-130">Please make sure to check back for updates on these upgrade options.</span></span>

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

## <a name="what-should-you-do"></a><span data-ttu-id="7d57a-131">何ですか。</span><span class="sxs-lookup"><span data-stu-id="7d57a-131">What should you do?</span></span>
<span data-ttu-id="7d57a-132">上記のアップグレード オプションを使用して TLS 1.0 または 1.1 廃止する前に Skype ルーム システム v2 に Lync ルーム システム デバイスを更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7d57a-132">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="7d57a-133">また、SRS v2 の認定、新しいデバイスと既存のデバイスを置き換えることを検討可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d57a-133">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="7d57a-134">[Skype ルーム システム v2 の要件](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d57a-134">See details in [Skype Room Systems v2 requirements](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="7d57a-135">タッチとホワイト ボードの機能が Skype ルーム システム v2 でまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7d57a-135">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="7d57a-136">タッチとホワイト ボードのサポートでは、Skype ルーム システム v2 のバックログし、H1 CY2019 に追加される予定です。</span><span class="sxs-lookup"><span data-stu-id="7d57a-136">Touch and whiteboard support is in the backlog for Skype Room System v2 and will be added in H1 CY2019.</span></span>
