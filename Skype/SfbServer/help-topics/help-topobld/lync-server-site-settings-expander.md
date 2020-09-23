---
title: Lync Server サイト設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 69555a04be4125e213ba2eca7afd7255100c0444
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217568"
---
# <a name="lync-server-site-settings-expander"></a>Lync Server サイト設定エキスパンダー

既存のサイトのプロパティを編集するには、次の操作を行います。



## <a name="site-properties"></a>サイトのプロパティ

サイトのプロパティでは、サイト名 (必須)、説明 (省略可能)、市区町村 (省略可能)、都道府県 (省略可能)、および 国/地域コード (省略可能) を変更または修正できます。

サイトのプロパティの詳細については、「[Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx)」を参照してください。

## <a name="federation-route-properties"></a>フェデレーション ルートのプロパティ

サイトのフェデレーションルートの割り当てを設定するには、最初にエッジサーバーまたはエッジサーバープールでフェデレーションを有効にする必要があります。 エッジ サーバーまたはプールでフェデレーションが有効になっていない場合、サイトのフェデレーション ルートの割り当てを変更できません。

エッジサーバーまたはプールでフェデレーション設定が構成されている場合は、サイトレベルで [ **有効** ] を選択します。 次に、ドロップダウンリストから、フェデレーションルートとして設定するエッジまたはディレクターを選択します。

> [!CAUTION]
> この設定はすべてのサイトに影響します。 このサイトで構成している設定がすべてのサイトに適切であることを確認してください。

## <a name="see-also"></a>関連項目

詳細については、「[Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx)」を参照してください。


