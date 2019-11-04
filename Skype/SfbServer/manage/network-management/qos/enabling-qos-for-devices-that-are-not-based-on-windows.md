---
title: Windows に基づかないデバイスの QoS の有効化
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Windows 以外のオペレーティングシステムを使用している組織で使用されているデバイスの QoS を有効にする方法について説明します。
ms.openlocfilehash: 956fff0e7fc69b1950e35261c02f9f44977510ce
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "37341943"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="b7e68-103">Windows ベースではないデバイスのために Skype for Business Server で QoS を有効にする</span><span class="sxs-lookup"><span data-stu-id="b7e68-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="b7e68-104">Skype for Business Server をインストールすると、Windows 以外のオペレーティングシステムを使用しているすべてのデバイスで、QoS (Quality of Service) が有効になりません。</span><span class="sxs-lookup"><span data-stu-id="b7e68-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="b7e68-105">これを確認するには、Skype for Business ServerManagement Shell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b7e68-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="b7e68-106">メディア構成の設定を変更していない場合は、次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7e68-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="b7e68-107">EnableQoS プロパティが False に設定されている場合 (上記の出力の場合)、Windows 以外のオペレーティングシステムを使用するコンピューターやデバイスではサービスの品質が有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="b7e68-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="b7e68-108">グローバルスコープでサービスの品質を有効にするには、Skype for Business Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b7e68-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="b7e68-109">上のコマンドはグローバルスコープで QoS を有効にします。ただし、メディア構成の設定はサイトのスコープにも適用できることに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7e68-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="b7e68-110">サイトのサービス品質を有効にする必要がある場合は、Set-CsMediaConfiguration を呼び出すときに、構成設定の Id を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7e68-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="b7e68-111">たとえば、次のコマンドは、Redmond サイトの QoS を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b7e68-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="b7e68-112">サイトスコープで QoS を有効にする必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="b7e68-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="b7e68-113">ケースバイケースです。</span><span class="sxs-lookup"><span data-stu-id="b7e68-113">That depends.</span></span> <span data-ttu-id="b7e68-114">サイトの範囲に割り当てられている設定は、グローバルスコープに割り当てられている設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="b7e68-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="b7e68-115">グローバルスコープで QoS が有効になっているが、サイトのスコープ (Redmond サイト) で無効になっているとします。</span><span class="sxs-lookup"><span data-stu-id="b7e68-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="b7e68-116">その場合、Redmond サイトのサービスの品質は無効になります。これは、サイトの設定が優先されるためです。</span><span class="sxs-lookup"><span data-stu-id="b7e68-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="b7e68-117">Redmond サイトの QoS を有効にするには、そのサイトに適用されているメディア構成設定を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7e68-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="b7e68-118">スコープに関係なく、すべてのメディア構成設定で QoS を同時に有効にするには、LSkype for Business Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b7e68-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="b7e68-119">Windows 以外のオペレーティングシステムを使用しているデバイスでは、EnableQoS プロパティの値を False に設定することにより、QoS を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b7e68-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="b7e68-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b7e68-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="b7e68-121">これにより、ネットワークの他の部分でサービスの品質を無効にしたまま、ネットワークの一部の部分 (レドモンドサイトなど) に QoS を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="b7e68-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="b7e68-122">QoS を有効または無効にするには、Windows PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7e68-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="b7e68-123">これらのオプションは、Skype for Business Server コントロールパネルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b7e68-123">These options are not available in the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="b7e68-124">IOS バージョン6.17 以降の Skype for Business クライアントで、QoS がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b7e68-124">Skype for Business clients for iOS Version 6.17 and later now support QoS.</span></span>  <span data-ttu-id="b7e68-125">この QoS 機能は、Skype for Business クライアントと、管理されたネットワーク上の内部の Skype for Business または Lync プールサーバーに直接登録される IP 電話デバイスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b7e68-125">This QoS capability is only applicable to Skype for Business clients and IP phone devices which are registered directly to an internal Skype for Business or Lync pool Server on managed networks.</span></span> <span data-ttu-id="b7e68-126">QoS は、インターネット経由でルーティングされるトラフィックには適用されません。</span><span class="sxs-lookup"><span data-stu-id="b7e68-126">QoS is not applicable for traffic routed over the Internet.</span></span>



