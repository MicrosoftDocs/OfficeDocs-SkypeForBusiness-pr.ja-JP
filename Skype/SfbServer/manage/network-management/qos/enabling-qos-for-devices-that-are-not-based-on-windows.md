---
title: Windows ベースではないデバイスの QoS の有効化
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Windows 以外のオペレーティング システムを使用する組織で使用されているデバイスで QoS を有効にする方法について説明します。
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814177"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="25922-103">Windows ベースではないデバイスに対する Skype for Business Server での QoS の有効化</span><span class="sxs-lookup"><span data-stu-id="25922-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="25922-104">Skype for Business Server をインストールすると、Windows 以外のオペレーティング システムを使用する組織で使用されているデバイスでは、サービスの品質 (QoS) が有効になりません。</span><span class="sxs-lookup"><span data-stu-id="25922-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="25922-105">これを確認するには、Skype for Business ServerManagement シェル内から次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="25922-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="25922-106">メディア構成設定を変更していない場合は、次のような情報を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25922-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="25922-107">EnableQoS プロパティが False (前の出力と同様) に設定されている場合、Windows 以外のオペレーティング システムを使用するコンピューターおよびデバイスではサービスの品質が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="25922-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="25922-108">グローバル スコープでサービスの品質を有効にするには、Skype for Business Server 管理シェル内から次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="25922-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="25922-109">上のコマンドは、グローバル スコープで QoS を有効にしています。ただし、メディア構成設定はサイト スコープにも適用できる点に注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="25922-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="25922-110">サイトのサービス品質を有効にする必要がある場合は、Set-CsMediaConfiguration を呼び出す際に構成設定の ID を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="25922-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="25922-111">たとえば、次のコマンドを実行すると、Redmond サイトの QoS が有効にされます。</span><span class="sxs-lookup"><span data-stu-id="25922-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="25922-112">QoS をサイト スコープで有効にする必要があるかどうかは、状況によって異なります。</span><span class="sxs-lookup"><span data-stu-id="25922-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="25922-113">サイト スコープに割り当てた設定は、グローバル スコープに割り当てた設定に優先します。</span><span class="sxs-lookup"><span data-stu-id="25922-113">That depends.</span></span> <span data-ttu-id="25922-114">たとえば、QoS をグローバル スコープで有効にし、サイト スコープ (Redmond サイト) では無効にしているとします。</span><span class="sxs-lookup"><span data-stu-id="25922-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="25922-115">QoS がグローバル スコープで有効になっているが、サイト スコープで無効になっているとします (Redmond サイトの場合)。</span><span class="sxs-lookup"><span data-stu-id="25922-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="25922-116">その場合、Redmond サイトではサービスの品質が無効になります。これは、サイト設定が優先されるためです。</span><span class="sxs-lookup"><span data-stu-id="25922-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="25922-117">Redmond サイトで QoS を有効にするには、そのサイトに適用されるメディア構成設定を使用して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="25922-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="25922-118">すべてのメディア構成設定 (スコープに関係なく) で QoS を同時に有効にする場合は、LSkype for Business Server 管理シェル内から次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="25922-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="25922-119">EnableQoS プロパティの値を False に設定することで、Windows 以外のオペレーティング システムを使用するデバイスの QoS を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="25922-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="25922-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="25922-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="25922-121">これにより、ネットワーク (Redmond サイトなど) の一部で QoS を実装しながら、ネットワークの他の部分では QoS を無効のままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="25922-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="25922-122">QoS を有効または無効にできるのは、次のWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="25922-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="25922-123">これらのオプションは、Skype for Business Server コントロール パネルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="25922-123">These options are not available in the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="25922-124">iOS Version 6.17 以降の Skype for Business クライアントは、QoS をサポートします。</span><span class="sxs-lookup"><span data-stu-id="25922-124">Skype for Business clients for iOS Version 6.17 and later now support QoS.</span></span>  <span data-ttu-id="25922-125">この QoS 機能は、管理対象ネットワーク上の内部 Skype for Business または Lync プール サーバーに直接登録されている Skype for Business クライアントおよび IP 電話デバイスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="25922-125">This QoS capability is only applicable to Skype for Business clients and IP phone devices which are registered directly to an internal Skype for Business or Lync pool Server on managed networks.</span></span> <span data-ttu-id="25922-126">QoS は、インターネット上でルーティングされるトラフィックには適用されません。</span><span class="sxs-lookup"><span data-stu-id="25922-126">QoS is not applicable for traffic routed over the Internet.</span></span>



