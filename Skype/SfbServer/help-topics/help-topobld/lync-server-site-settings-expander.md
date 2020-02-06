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
- NOCSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 既存のサイトのプロパティを編集するには、次の操作を行います。
ms.openlocfilehash: 2a771aa3ef7627bf6dcde1004fca0e807bbd5f7b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819649"
---
# <a name="lync-server-site-settings-expander"></a>Lync Server サイト設定エキスパンダー

既存のサイトのプロパティを編集するには、次の操作を行います。



## <a name="site-properties"></a>サイトのプロパティ

[サイトのプロパティ] で、サイト名 (必須)、説明 (省略可能)、市区町村 (オプション)、都道府県/州 (オプション)、国/地域コード (オプション) を変更または変更することができます。

サイトのプロパティの詳細については、「[トポロジにブランチサイトを追加する](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx)」を参照してください。

## <a name="federation-route-properties"></a>フェデレーションルートのプロパティ

サイトフェデレーションルートの割り当てを設定するには、まず、エッジサーバーまたはエッジサーバープールでフェデレーションを有効にする必要があります。 エッジサーバーまたはプールでフェデレーションが有効になっていない場合は、サイトのフェデレーションルートの割り当て設定を変更できません。

エッジサーバーまたはプールでフェデレーション設定が構成されている場合は、サイトレベルで [**有効**] を選びます。 次に、ドロップダウンリストから、フェデレーションルートとして設定するエッジまたはディレクターを選択します。

> [!CAUTION]
> この設定は、すべてのサイトに影響します。 このサイトで構成する設定は、すべてのサイトに対して適切であることを確認してください。

## <a name="see-also"></a>関連項目

詳細については、「[外部ユーザーアクセスのトポロジ](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx)」を参照してください。


