---
title: メディア バイ パスを直接ルーティングの構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 電話システムの直接のルーティングを使用してメディア バイ パスを構成する方法については、このトピックを参照してください。
ms.openlocfilehash: 405f71fd0a1e0ea3e8fec6ee1061786c93fabf1b
ms.sourcegitcommit: 260635a24b282fbdf4a4aeffdb0f4f9be5407ec6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "30631066"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="d0e1e-103">メディア バイ パスを直接ルーティングの構成します。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="d0e1e-104">構成のメディアは、直接ルーティングをバイパスする前に、[メディアの計画に直接ルーティングをバイパス](direct-routing-plan-media-bypass.md)を読んだことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="d0e1e-105">メディアのバイパスを有効にするのには次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="d0e1e-106">任意のセッション ボーダー コント ローラー (SBC) ベンダーがメディア バイ パスがサポートされていてを構成する手順については、SBC のバイパスは、確認します。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="d0e1e-107">SBCs、するもののサポート ・ メディアは、次の回避、および手順についての説明に証明のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="d0e1e-108">次のコマンドを使用してトランク上のメディア バイ パスを有効にする必要があります:**セット CSOnlinePSTNGateway ・ アイデンティティの <sbc_FQDN> - MediaBypass $true**。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="d0e1e-109">必要なポートが開かれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="d0e1e-110">非バイパスのトランクからトランクのバイパスが有効なへの移行します。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="d0e1e-111">一度にすべてのユーザーを切り替えることができますまたは段階的なアプローチを実装することができます (推奨)。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="d0e1e-112">**一度にすべてのユーザーを切り替えます。**</span><span class="sxs-lookup"><span data-stu-id="d0e1e-112">**Switch all users at once.**</span></span> <span data-ttu-id="d0e1e-113">すべての条件を満たしている場合は、バイパス モードをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="d0e1e-114">ただし、運用環境のすべてのユーザーは、同時に切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="d0e1e-115">トランクとポートを構成するときに最初にいくつかの問題が発生する可能性があります、ため、運用環境のユーザー エクスペリエンスの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="d0e1e-116">**Phased アプローチです。(推奨)**。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="d0e1e-117">(別のポート) を持つ同じ SBC の新しい樹幹を作成、テスト、および新しいトランクを指すようにユーザーのオンラインの音声ルーティング ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="d0e1e-118">これは、滑らかな切り替えと中断のないユーザー エクスペリエンスのための推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="d0e1e-119">このアプローチでは、SBC、新しい FQDN 名では、ファイアウォールの設定の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="d0e1e-120">証明書が両方のトランクをサポートしているかどうかを確認する必要があります注意してください。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="d0e1e-121">SAN では、(**sbc1.contoso.com**および**sbc2.contoso.com**) の 2 つの名前またはワイルドカード証明書が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![非バイパスのトランクからトランクのバイパスが有効に移行)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="d0e1e-123">トランクを構成し、移行を実行する方法については、SBC の製造元に問い合わせてからのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- <span data-ttu-id="d0e1e-124">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="d0e1e-124">AudioCodes</span></span>
- <span data-ttu-id="d0e1e-125">リボン</span><span class="sxs-lookup"><span data-stu-id="d0e1e-125">Ribbon</span></span>
- <span data-ttu-id="d0e1e-126">TE ・ システム (AnyNode)</span><span class="sxs-lookup"><span data-stu-id="d0e1e-126">TE-Systems (AnyNode)</span></span>    

<span data-ttu-id="d0e1e-127">今回の発表の時点で、次の SBCs が徹底的なテスト/メディア バイ パスで機能する認定は。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-127">At the moment of this announcement, the following SBCs are fully tested and certified to work with media bypass:</span></span>

- <span data-ttu-id="d0e1e-128">9000 V7.20A.204.222、SBC では M800B/V7.20A.250.003</span><span class="sxs-lookup"><span data-stu-id="d0e1e-128">AudioCodes 9000 V7.20A.204.222, AudioCodes M800B-SBC/ V7.20A.250.003</span></span>

-   <span data-ttu-id="d0e1e-129">リボン</span><span class="sxs-lookup"><span data-stu-id="d0e1e-129">Ribbon</span></span>
    - <span data-ttu-id="d0e1e-130">- xxx 5210 v06.02.xx</span><span class="sxs-lookup"><span data-stu-id="d0e1e-130">5210 v06.02.xx-xxx</span></span> 
    - <span data-ttu-id="d0e1e-131">5400、v06.02.xx xxx</span><span class="sxs-lookup"><span data-stu-id="d0e1e-131">5400, v06.02.xx-xxx</span></span>
    - <span data-ttu-id="d0e1e-132">5110、v06.02.xx xxx</span><span class="sxs-lookup"><span data-stu-id="d0e1e-132">5110, v06.02.xx-xxx</span></span>

-   <span data-ttu-id="d0e1e-133">TE システム AnyNode v 3.16.2</span><span class="sxs-lookup"><span data-stu-id="d0e1e-133">TE-System AnyNode v 3.16.2</span></span> 


## <a name="see-also"></a><span data-ttu-id="d0e1e-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0e1e-134">See also</span></span>

[<span data-ttu-id="d0e1e-135">直接ルーティングでのメディア バイ パスを計画します。</span><span class="sxs-lookup"><span data-stu-id="d0e1e-135">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



