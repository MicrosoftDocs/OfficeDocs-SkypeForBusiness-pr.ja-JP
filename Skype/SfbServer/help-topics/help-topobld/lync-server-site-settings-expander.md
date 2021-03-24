---
title: Lync Server サイト設定エキスパンダー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 既存のサイトのプロパティを編集するには、次の操作を行います。
ms.openlocfilehash: aedb248bf229af754d2ef8eb9c5e3837c69c808d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104453"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="36175-103">Lync Server サイト設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="36175-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="36175-104">既存のサイトのプロパティを編集するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="36175-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="36175-105">サイトのプロパティ</span><span class="sxs-lookup"><span data-stu-id="36175-105">Site properties</span></span>

<span data-ttu-id="36175-106">サイトのプロパティでは、サイト名 (必須)、説明 (省略可能)、市区町村 (省略可能)、都道府県 (省略可能)、および 国/地域コード (省略可能) を変更または修正できます。</span><span class="sxs-lookup"><span data-stu-id="36175-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="36175-107">サイトのプロパティの詳細については、「[Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36175-107">For details about site properties, see [Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="36175-108">フェデレーション ルートのプロパティ</span><span class="sxs-lookup"><span data-stu-id="36175-108">Federation Route properties</span></span>

<span data-ttu-id="36175-109">サイト フェデレーション ルートの割り当てを設定するには、まずエッジ サーバーまたはエッジ サーバー プールでフェデレーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="36175-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="36175-110">エッジ サーバーまたはプールでフェデレーションが有効になっていない場合、サイトのフェデレーション ルートの割り当てを変更できません。</span><span class="sxs-lookup"><span data-stu-id="36175-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="36175-111">エッジ サーバーまたはプールのフェデレーション設定が構成されている場合は、[サイト レベルで **有効にする** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36175-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="36175-112">次に、ドロップダウン リストからエッジまたはディレクターを選択し、フェデレーション ルートとして設定します。</span><span class="sxs-lookup"><span data-stu-id="36175-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="36175-113">この設定はすべてのサイトに影響します。</span><span class="sxs-lookup"><span data-stu-id="36175-113">This setting will affect all sites.</span></span> <span data-ttu-id="36175-114">このサイトで構成している設定がすべてのサイトに適切であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="36175-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="36175-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="36175-115">See also</span></span>

<span data-ttu-id="36175-116">詳細については、「[Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36175-116">For details, see [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access).</span></span>