---
title: Lync Server サイト設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 既存のサイトのプロパティを編集するには、次の操作を行います。
ms.openlocfilehash: 920a159f493e2612c9ad9aa5e5be1e339414bc21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33912002"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="cc963-103">Lync Server サイト設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="cc963-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="cc963-104">既存のサイトのプロパティを編集するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cc963-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="cc963-105">サイトのプロパティ</span><span class="sxs-lookup"><span data-stu-id="cc963-105">Site properties</span></span>

<span data-ttu-id="cc963-106">[サイトのプロパティを変更したり、サイトの名前 (必須)、説明 (省略可能)、市区町村 (省略可能)、州 (省略可能)、および (省略可能) の国/地域コードを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cc963-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="cc963-107">サイトのプロパティに関する詳細については、[ブランチ サイトを追加する、トポロジ](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc963-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="cc963-108">フェデレーション ルートのプロパティ</span><span class="sxs-lookup"><span data-stu-id="cc963-108">Federation Route properties</span></span>

<span data-ttu-id="cc963-109">サイトのフェデレーション ルートの割り当てを設定するには、エッジ サーバーまたはエッジ サーバー プールは、有効なフェデレーション最初必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc963-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="cc963-110">エッジ サーバーまたはプールでフェデレーションが有効でない場合は、サイトのフェデレーション ルートの割り当ての設定は変更されません。</span><span class="sxs-lookup"><span data-stu-id="cc963-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="cc963-111">エッジ サーバーまたはプールでフェデレーション設定を構成すると場合、は、サイト レベルで**有効にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc963-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="cc963-112">フェデレーション ルートとして設定するのにはドロップ ダウン リストからエッジまたはディレクターを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc963-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="cc963-113">この設定は、すべてのサイトに影響されます。</span><span class="sxs-lookup"><span data-stu-id="cc963-113">This setting will affect all sites.</span></span> <span data-ttu-id="cc963-114">このサイトで構成している設定がすべてのサイトに対して適切であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cc963-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc963-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc963-115">See also</span></span>

<span data-ttu-id="cc963-116">詳細については、[外部ユーザー アクセスのトポロジ](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc963-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>


