---
title: Microsoft Teams でのアプリの更新エクスペリエンス
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: この記事では、Microsoft Teams の Microsoft アプリ、カスタム アプリ、およびサード パーティ製アプリがどのように更新されるかについて説明します。
ms.openlocfilehash: bcd06b9814b03d917014d8136f51a280e30007d1
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272062"
---
# <a name="update-apps-in-microsoft-teams"></a>Microsoft Teams でアプリを更新する

ほとんどの場合、アプリ開発者がアプリの更新プログラムを発行すると、新しいバージョンがユーザーに対して自動的に表示されます。 ただし、[Microsoft Teams マニフェスト](/microsoftteams/platform/resources/schema/manifest-schema)には、完了するためにユーザーの同意が必要な更新プログラムがいくつかあります:

* ボットが追加または削除されました。
* 既存のボットの 「botId」プロパティが変更されました。
* 既存のボットの 「isNotificationOnly」プロパティが変更されました。
* ボットの SupportsCalling、SupportsVideo、および’SupportsFiles 機能が追加されました。
* メッセージング拡張機能が追加されました。
* 新しいコネクタが追加されました。
* 「Authorization」内のアクセス許可が追加または変更されました。

:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="新しいバージョンを使用できます。" lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="アプリのアップグレード オプション。" lightbox="media/manage-your-custom-apps-update2.png":::

> [!NOTE]
> 更新プロセスは、Microsoft アプリ、カスタム アプリ、およびサード パーティ 製アプリのすべてのアプリ更新プログラムに適用されます。
