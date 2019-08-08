---
title: ダイレクト ルーティングでメディア バイパスを構成する
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: このトピックでは、電話システムのダイレクトルーティングでメディアバイパスを構成する方法について説明します。
ms.openlocfilehash: d3991973932ec3ced2ef1a365a7060e2d9449f40
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237483"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="15dc6-103">ダイレクト ルーティングでメディア バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="15dc6-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="15dc6-104">ダイレクトルーティングを使用してメディアバイパスを構成する前に、[ダイレクトルーティングによるメディアバイパスの計画](direct-routing-plan-media-bypass.md)があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="15dc6-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="15dc6-105">メディアのバイパスを有効にするには、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="15dc6-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="15dc6-106">セッション境界コントローラー (SBC) ベンダーがメディアバイパスをサポートしていることを確認し、SBC でバイパスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="15dc6-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="15dc6-107">SBCs の詳細については、認定ページを参照してください。このページでは、メディアのバイパスがサポートされているものと手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="15dc6-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="15dc6-108">次のコマンドを使用して、トランクでメディアバイパスを有効にする必要があります: **CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**。</span><span class="sxs-lookup"><span data-stu-id="15dc6-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="15dc6-109">必要なポートが開かれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="15dc6-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="15dc6-110">非バイパスの trunks からバイパス対応の trunks に移行する</span><span class="sxs-lookup"><span data-stu-id="15dc6-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="15dc6-111">一度にすべてのユーザーを切り替えることができます。また、段階的なアプローチを実装することもできます (推奨)。</span><span class="sxs-lookup"><span data-stu-id="15dc6-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="15dc6-112">**一度にすべてのユーザーを切り替える。**</span><span class="sxs-lookup"><span data-stu-id="15dc6-112">**Switch all users at once.**</span></span> <span data-ttu-id="15dc6-113">すべての条件が満たされた場合は、バイパスモードをオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="15dc6-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="15dc6-114">ただし、すべての運用ユーザーが同時に切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="15dc6-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="15dc6-115">Trunks とポートを構成するときに、最初にいくつかの問題が発生する可能性があるため、実稼働ユーザーエクスペリエンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="15dc6-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="15dc6-116">**段階的アプローチ。(推奨)**。</span><span class="sxs-lookup"><span data-stu-id="15dc6-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="15dc6-117">同じ SBC (別のポートを持つ) に新しいトランクを作成し、テストして、ユーザーが新しいトランクをポイントするようにオンラインボイスルーティングポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="15dc6-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="15dc6-118">これは、スムーズな移行と中断のないユーザーエクスペリエンスを実現するために推奨されるアプローチです。</span><span class="sxs-lookup"><span data-stu-id="15dc6-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="15dc6-119">この方法では、SBC、新しい FQDN 名、ファイアウォールの構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="15dc6-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="15dc6-120">注: 証明書で trunks の両方がサポートされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15dc6-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="15dc6-121">SAN では、2つの名前 (**sbc1.contoso.com**と**sbc2.contoso.com**) を使用するか、ワイルドカード証明書を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="15dc6-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![非バイパスの trunks からバイパス対応の trunks に移行する](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="15dc6-123">Trunks を構成して移行を実行する方法については、「SBC ベンダーのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15dc6-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="15dc6-124">AudioCodes の展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="15dc6-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="15dc6-125">Oracle 展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="15dc6-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="15dc6-126">リボンの通信展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="15dc6-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="15dc6-127">TE システム (anynode) の展開ドキュメント</span><span class="sxs-lookup"><span data-stu-id="15dc6-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="15dc6-128">直接ルーティング用に認定したセッション境界コントローラー (SBCs) の一覧については、「[直接ルーティング用に認定済みのセッション罫線ありコントローラーの一覧](direct-routing-border-controllers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15dc6-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="see-also"></a><span data-ttu-id="15dc6-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="15dc6-129">See also</span></span>

[<span data-ttu-id="15dc6-130">ダイレクトルーティングによるメディアバイパスの計画</span><span class="sxs-lookup"><span data-stu-id="15dc6-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



