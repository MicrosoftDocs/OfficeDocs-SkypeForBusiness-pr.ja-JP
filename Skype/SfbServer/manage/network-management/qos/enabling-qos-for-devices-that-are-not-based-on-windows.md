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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Windows 以外のオペレーティング システムを使用する組織で使用するデバイスの QoS を有効にする方法を説明します。
ms.openlocfilehash: 24d27b25112ecc982a6fdc2b8d1874c4be992937
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913057"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="cbca5-103">ビジネス サーバーの Windows ベース以外のデバイスに Skype で QoS を有効にします。</span><span class="sxs-lookup"><span data-stu-id="cbca5-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="cbca5-104">ビジネス サーバーの Skype をインストールするとサービスの品質 (QoS) になって、組織で使用される Windows 以外のオペレーティング システムを使用するすべてのデバイスのです。</span><span class="sxs-lookup"><span data-stu-id="cbca5-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="cbca5-105">ビジネス ServerManagement シェルには、Skype 内で次のコマンドを実行することによってこれを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="cbca5-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="cbca5-106">メディア構成の設定を変更を加えていない場合を想定して、必要がある情報が返されます次のような。</span><span class="sxs-lookup"><span data-stu-id="cbca5-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="cbca5-107">場合は、EnableQoS プロパティは、Windows 以外のオペレーティング システムを使用するコンピューターおよびデバイスの品質のサービスが無効になっていることを意味する (上記の出力) と同様に False に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cbca5-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="cbca5-108">グローバル スコープでは、品質のサービスを有効にするには、ビジネス サーバー管理シェルには、Skype 内で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cbca5-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="cbca5-109">上記のコマンドは、グローバル スコープで QoS を有効にただし、重要なメディアの構成設定はサイト スコープにも適用できます。</span><span class="sxs-lookup"><span data-stu-id="cbca5-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="cbca5-110">サイトの品質のサービスを有効にする場合は、セット CsMediaConfiguration を呼び出すときに構成設定の Id を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbca5-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="cbca5-111">たとえば、このコマンドは、レドモンド サイトの QoS を有効にします。</span><span class="sxs-lookup"><span data-stu-id="cbca5-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="cbca5-112">サイトのスコープで QoS を有効にする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="cbca5-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="cbca5-113">ケースバイケースです。</span><span class="sxs-lookup"><span data-stu-id="cbca5-113">That depends.</span></span> <span data-ttu-id="cbca5-114">サイト スコープに割り当てられている設定は、グローバル スコープに割り当てられている設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cbca5-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="cbca5-115">QoS をグローバル スコープで有効になっているが、(レドモンド サイトの) サイトのスコープで無効にします。</span><span class="sxs-lookup"><span data-stu-id="cbca5-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="cbca5-116">Redmond のサイトの品質のサービスは無効にする場合は、サイトの設定が優先するためです。</span><span class="sxs-lookup"><span data-stu-id="cbca5-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="cbca5-117">レドモンド サイトで QoS を有効にするのには、メディアの構成設定を使用してそのサイトに適用されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbca5-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="cbca5-118">(スコープ) に関係なくすべてのメディア構成設定の QoS を同時に有効にする場合は、ビジネス サーバー管理シェルの場合、LSkype 内からは、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cbca5-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="cbca5-119">Windows 以外のオペレーティング システムを使用して、EnableQoS プロパティの値を False に設定しているデバイスの QoS を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cbca5-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="cbca5-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cbca5-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="cbca5-121">こうことによりでいくつかの部分 (たとえば、レドモンド サイト) で、ネットワークの QoS を実装するためにサービスの品質は、ネットワークのほかの部分を無効にしたまま。</span><span class="sxs-lookup"><span data-stu-id="cbca5-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="cbca5-122">QoS を有効になっているだけと Windows PowerShell を使用して無効にします。</span><span class="sxs-lookup"><span data-stu-id="cbca5-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="cbca5-123">これらのオプションは、ビジネス サーバーのコントロール パネルの Skype でご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="cbca5-123">These options are not available in the Skype for Business Server Control Panel.</span></span>


