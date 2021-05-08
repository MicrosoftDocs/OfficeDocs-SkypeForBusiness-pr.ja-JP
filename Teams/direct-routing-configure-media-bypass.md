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
description: すべてのユーザーを一度に切り替電話システム、または段階的なアプローチ (推奨) を実装することで、Microsoft Teams のダイレクト ルーティングを使用してメディア バイパスを構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416897"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="b1b09-103">ダイレクト ルーティングでメディア バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="b1b09-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="b1b09-104">ダイレクト ルーティングを使用してメディア バイパスを構成する前に、「ダイレクト ルーティングを使用したメディア バイパス [の計画」を参照してください](direct-routing-plan-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="b1b09-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="b1b09-105">メディア バイパスを有効にするには、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b09-105">To turn on media bypass, the following conditions must be met:</span></span>

1.    <span data-ttu-id="b1b09-106">選択したセッション ボーダー コントローラー (SBC) ベンダーがメディア バイパスをサポートし、SBC でバイパスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1b09-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="b1b09-107">メディア バイパスをサポートする SBC と手順については、認定に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1b09-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.    <span data-ttu-id="b1b09-108">**Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass**$true コマンドを使用して、トランクでメディア バイパスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b09-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.    <span data-ttu-id="b1b09-109">必要なポートが開いているか確認します。</span><span class="sxs-lookup"><span data-stu-id="b1b09-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="b1b09-110">バイパスされていないトランクからバイパスが有効なトランクに移行する</span><span class="sxs-lookup"><span data-stu-id="b1b09-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="b1b09-111">すべてのユーザーを一度に切り替えるか、段階的なアプローチ (推奨) を実装できます。</span><span class="sxs-lookup"><span data-stu-id="b1b09-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="b1b09-112">**すべてのユーザーを一度に切り替えます。**</span><span class="sxs-lookup"><span data-stu-id="b1b09-112">**Switch all users at once.**</span></span> <span data-ttu-id="b1b09-113">すべての条件が満たされている場合は、バイパス モードをオンにできます。</span><span class="sxs-lookup"><span data-stu-id="b1b09-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="b1b09-114">ただし、すべての実稼働ユーザーが同時に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="b1b09-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="b1b09-115">トランクとポートを構成するときに最初に問題が発生する可能性があります。この場合、実稼働環境のユーザー エクスペリエンスが影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b1b09-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="b1b09-116">**段階的なアプローチ。(推奨)**。</span><span class="sxs-lookup"><span data-stu-id="b1b09-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="b1b09-117">同じ SBC 用の新しいトランクを (別のポートで) 作成し、テストし、新しいトランクを指すユーザーのオンライン音声ルーティング ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="b1b09-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="b1b09-118">これは、スムーズな切り替えと中断のないユーザー エクスペリエンスが可能なので、推奨されるアプローチです。</span><span class="sxs-lookup"><span data-stu-id="b1b09-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="b1b09-119">この方法では、SBC の構成、新しい FQDN 名、ファイアウォールの構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="b1b09-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="b1b09-120">証明書が両方のトランクをサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b09-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="b1b09-121">SAN では、2 つの名前 **(sbc1.contoso.com** と **sbc2.contoso.com)** を持つ必要があります。または、ワイルドカード証明書を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b09-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![バイパスされていないトランクからバイパスが有効なトランクに移行する)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="b1b09-123">トランクを構成して移行を実行する方法については、SBC ベンダーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1b09-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="b1b09-124">AudioCodes デプロイのドキュメント</span><span class="sxs-lookup"><span data-stu-id="b1b09-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="b1b09-125">Oracle デプロイのドキュメント</span><span class="sxs-lookup"><span data-stu-id="b1b09-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="b1b09-126">リボンコミュニケーションの展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="b1b09-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="b1b09-127">TE-Systems (anynode) のデプロイに関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="b1b09-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="b1b09-128">直接ルーティングの認定を受けたセッション ボーダー コントローラー (SBC) の一覧については、「直接ルーティングの認定を受けた [セッション の一覧」を参照してください](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="b1b09-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="b1b09-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b1b09-129">Related topics</span></span>

[<span data-ttu-id="b1b09-130">ダイレクト ルーティングを使用してメディア バイパスを計画する</span><span class="sxs-lookup"><span data-stu-id="b1b09-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



