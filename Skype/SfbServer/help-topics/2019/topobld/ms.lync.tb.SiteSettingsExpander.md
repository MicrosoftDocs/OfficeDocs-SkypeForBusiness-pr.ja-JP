---
title: Lync Server サイト設定エキスパンダー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 既存のサイトのプロパティを編集するには、次の操作を行います。
ms.openlocfilehash: 4bcf07ef1b550fb96ce503f31b4026ccc4ae6960
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115377"
---
# <a name="lync-server-site-settings-expander"></a>Lync Server サイト設定エキスパンダー

既存のサイトのプロパティを編集するには、次の操作を行います。



## <a name="site-properties"></a>サイトのプロパティ

サイトのプロパティでは、サイト名 (必須)、説明 (省略可能)、市区町村 (省略可能)、都道府県 (省略可能)、および 国/地域コード (省略可能) を変更または修正できます。

サイトのプロパティの詳細については、「[Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology)」を参照してください。

## <a name="federation-route-properties"></a>フェデレーション ルートのプロパティ

サイト フェデレーション ルートの割り当てを設定するには、まずエッジ サーバーまたはエッジ サーバー プールでフェデレーションを有効にする必要があります。 エッジ サーバーまたはプールでフェデレーションが有効になっていない場合、サイトのフェデレーション ルートの割り当てを変更できません。

エッジ サーバーまたはプールのフェデレーション設定が構成されている場合は、[サイト レベルで **有効にする** ] を選択します。 次に、ドロップダウン リストからエッジまたはディレクターを選択し、フェデレーション ルートとして設定します。

> [!CAUTION]
> この設定はすべてのサイトに影響します。 このサイトで構成している設定がすべてのサイトに適切であることを確認してください。

## <a name="see-also"></a>関連項目

詳細については、「[Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access)」を参照してください。