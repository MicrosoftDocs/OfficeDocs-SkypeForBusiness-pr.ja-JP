---
title: ダイレクト ルーティングでメディア バイパスを構成する
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
ms.openlocfilehash: 459ebd80a175fbf2c213a016436a2bf130ae9982
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232697"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="3506b-103">ダイレクト ルーティングでメディア バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="3506b-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="3506b-104">構成のメディアは、直接ルーティングをバイパスする前に、[メディアの計画に直接ルーティングをバイパス](direct-routing-plan-media-bypass.md)を読んだことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3506b-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="3506b-105">メディアのバイパスを有効にするのには次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="3506b-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="3506b-106">任意のセッション ボーダー コント ローラー (SBC) ベンダーがメディア バイ パスがサポートされていてを構成する手順については、SBC のバイパスは、確認します。</span><span class="sxs-lookup"><span data-stu-id="3506b-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="3506b-107">SBCs、するもののサポート ・ メディアは、次の回避、および手順についての説明に証明のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3506b-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="3506b-108">次のコマンドを使用してトランク上のメディア バイ パスを有効にする必要があります:**セット CSOnlinePSTNGateway ・ アイデンティティの <sbc_FQDN> - MediaBypass $true**。</span><span class="sxs-lookup"><span data-stu-id="3506b-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="3506b-109">必要なポートが開かれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3506b-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="3506b-110">非バイパスのトランクからトランクのバイパスが有効なへの移行します。</span><span class="sxs-lookup"><span data-stu-id="3506b-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="3506b-111">一度にすべてのユーザーを切り替えることができますまたは段階的なアプローチを実装することができます (推奨)。</span><span class="sxs-lookup"><span data-stu-id="3506b-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="3506b-112">**一度にすべてのユーザーを切り替えます。**</span><span class="sxs-lookup"><span data-stu-id="3506b-112">**Switch all users at once.**</span></span> <span data-ttu-id="3506b-113">すべての条件を満たしている場合は、バイパス モードをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3506b-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="3506b-114">ただし、運用環境のすべてのユーザーは、同時に切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="3506b-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="3506b-115">トランクとポートを構成するときに最初にいくつかの問題が発生する可能性があります、ため、運用環境のユーザー エクスペリエンスの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="3506b-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="3506b-116">**Phased アプローチです。(推奨)**。</span><span class="sxs-lookup"><span data-stu-id="3506b-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="3506b-117">(別のポート) を持つ同じ SBC の新しい樹幹を作成、テスト、および新しいトランクを指すようにユーザーのオンラインの音声ルーティング ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="3506b-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="3506b-118">これは、滑らかな切り替えと中断のないユーザー エクスペリエンスのための推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="3506b-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="3506b-119">このアプローチでは、SBC、新しい FQDN 名では、ファイアウォールの設定の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="3506b-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="3506b-120">証明書が両方のトランクをサポートしているかどうかを確認する必要があります注意してください。</span><span class="sxs-lookup"><span data-stu-id="3506b-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="3506b-121">SAN では、(**sbc1.contoso.com**および**sbc2.contoso.com**) の 2 つの名前またはワイルドカード証明書が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3506b-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![非バイパスのトランクからトランクのバイパスが有効に移行)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="3506b-123">トランクを構成し、移行を実行する方法については、SBC の製造元に問い合わせてからのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3506b-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- <span data-ttu-id="3506b-124">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="3506b-124">AudioCodes</span></span>
- <span data-ttu-id="3506b-125">リボン</span><span class="sxs-lookup"><span data-stu-id="3506b-125">Ribbon</span></span>
- <span data-ttu-id="3506b-126">TE ・ システム (AnyNode)</span><span class="sxs-lookup"><span data-stu-id="3506b-126">TE-Systems (AnyNode)</span></span>    

<span data-ttu-id="3506b-127">セッション ボーダー コント ローラー (SBCs) が直接ルーティングするための認定のリストは、[リストのセッション Broder コント ローラーが直接ルーティングの認定](direct-routing-border-controllers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3506b-127">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="see-also"></a><span data-ttu-id="3506b-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="3506b-128">See also</span></span>

[<span data-ttu-id="3506b-129">直接ルーティングでのメディア バイ パスを計画します。</span><span class="sxs-lookup"><span data-stu-id="3506b-129">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



