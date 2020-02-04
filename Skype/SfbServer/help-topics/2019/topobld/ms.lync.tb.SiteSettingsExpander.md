---
title: Lync Server サイト設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 既存のサイトのプロパティを編集するには、次の操作を行います。
ms.openlocfilehash: 20c74cd3842137df5dce35647bdb5ad28b89b4e0
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687970"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="06eef-103">Lync Server サイト設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="06eef-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="06eef-104">既存のサイトのプロパティを編集するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="06eef-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="06eef-105">サイトのプロパティ</span><span class="sxs-lookup"><span data-stu-id="06eef-105">Site properties</span></span>

<span data-ttu-id="06eef-106">[サイトのプロパティ] で、サイト名 (必須)、説明 (省略可能)、市区町村 (オプション)、都道府県/州 (オプション)、国/地域コード (オプション) を変更または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="06eef-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="06eef-107">サイトのプロパティの詳細については、「[トポロジにブランチサイトを追加する](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06eef-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="06eef-108">フェデレーションルートのプロパティ</span><span class="sxs-lookup"><span data-stu-id="06eef-108">Federation Route properties</span></span>

<span data-ttu-id="06eef-109">サイトフェデレーションルートの割り当てを設定するには、まず、エッジサーバーまたはエッジサーバープールでフェデレーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="06eef-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="06eef-110">エッジサーバーまたはプールでフェデレーションが有効になっていない場合は、サイトのフェデレーションルートの割り当て設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="06eef-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="06eef-111">エッジサーバーまたはプールでフェデレーション設定が構成されている場合は、サイトレベルで [**有効**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="06eef-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="06eef-112">次に、ドロップダウンリストから、フェデレーションルートとして設定するエッジまたはディレクターを選択します。</span><span class="sxs-lookup"><span data-stu-id="06eef-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="06eef-113">この設定は、すべてのサイトに影響します。</span><span class="sxs-lookup"><span data-stu-id="06eef-113">This setting will affect all sites.</span></span> <span data-ttu-id="06eef-114">このサイトで構成する設定は、すべてのサイトに対して適切であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="06eef-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="06eef-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="06eef-115">See also</span></span>

<span data-ttu-id="06eef-116">詳細については、「[外部ユーザーアクセスのトポロジ](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06eef-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>


