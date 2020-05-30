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
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: すべてのユーザーを一度に切り替えるか、段階的な方法 (推奨) を実装して、Microsoft Teams の電話システムダイレクトルーティングでメディアバイパスを構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416897"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="f24ca-103">ダイレクト ルーティングでメディア バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="f24ca-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="f24ca-104">ダイレクトルーティングを使用してメディアバイパスを構成する前に、[ダイレクトルーティングによるメディアバイパスの計画](direct-routing-plan-media-bypass.md)があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f24ca-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="f24ca-105">メディアのバイパスを有効にするには、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f24ca-105">To turn on media bypass, the following conditions must be met:</span></span>

1.    <span data-ttu-id="f24ca-106">セッション境界コントローラー (SBC) ベンダーがメディアバイパスをサポートしていることを確認し、SBC でバイパスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f24ca-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="f24ca-107">SBCs の詳細については、認定ページを参照してください。このページでは、メディアのバイパスがサポートされているものと手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="f24ca-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.    <span data-ttu-id="f24ca-108">次のコマンドを使用して、トランクでメディアバイパスを有効にする必要があります: **CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**。</span><span class="sxs-lookup"><span data-stu-id="f24ca-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.    <span data-ttu-id="f24ca-109">必要なポートが開かれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f24ca-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="f24ca-110">非バイパスの trunks からバイパス対応の trunks に移行する</span><span class="sxs-lookup"><span data-stu-id="f24ca-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="f24ca-111">一度にすべてのユーザーを切り替えることができます。また、段階的なアプローチを実装することもできます (推奨)。</span><span class="sxs-lookup"><span data-stu-id="f24ca-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="f24ca-112">**一度にすべてのユーザーを切り替える。**</span><span class="sxs-lookup"><span data-stu-id="f24ca-112">**Switch all users at once.**</span></span> <span data-ttu-id="f24ca-113">すべての条件が満たされた場合は、バイパスモードをオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f24ca-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="f24ca-114">ただし、すべての運用ユーザーが同時に切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="f24ca-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="f24ca-115">Trunks とポートを構成するときに、最初にいくつかの問題が発生する可能性があるため、実稼働ユーザーエクスペリエンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f24ca-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="f24ca-116">**段階的アプローチ。(推奨)**。</span><span class="sxs-lookup"><span data-stu-id="f24ca-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="f24ca-117">同じ SBC (別のポートを持つ) に新しいトランクを作成し、テストして、ユーザーが新しいトランクをポイントするようにオンラインボイスルーティングポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="f24ca-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="f24ca-118">これは、スムーズな移行と中断のないユーザーエクスペリエンスを実現するために推奨されるアプローチです。</span><span class="sxs-lookup"><span data-stu-id="f24ca-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="f24ca-119">この方法では、SBC、新しい FQDN 名、ファイアウォールの構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="f24ca-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="f24ca-120">注: 証明書で trunks の両方がサポートされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f24ca-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="f24ca-121">SAN では、2つの名前 (**sbc1.contoso.com**と**sbc2.contoso.com**) を使用するか、ワイルドカード証明書を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f24ca-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![非バイパスの trunks からバイパス対応の trunks に移行する](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="f24ca-123">Trunks を構成して移行を実行する方法については、「SBC ベンダーのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f24ca-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="f24ca-124">AudioCodes の展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="f24ca-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="f24ca-125">Oracle 展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="f24ca-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="f24ca-126">リボンの通信展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="f24ca-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="f24ca-127">TE システム (anynode) の展開ドキュメント</span><span class="sxs-lookup"><span data-stu-id="f24ca-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="f24ca-128">直接ルーティング用に認定したセッション境界コントローラー (SBCs) の一覧については、「[直接ルーティング用に認定済みのセッション罫線ありコントローラーの一覧](direct-routing-border-controllers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f24ca-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="f24ca-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="f24ca-129">Related topics</span></span>

[<span data-ttu-id="f24ca-130">ダイレクトルーティングによるメディアバイパスの計画</span><span class="sxs-lookup"><span data-stu-id="f24ca-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



