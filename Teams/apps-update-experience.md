---
title: Microsoft Teams でのアプリの更新エクスペリエンス
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
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
ms.localizationpriority: medium
search.appverid: MET150
description: この記事では、Microsoft Teams の Microsoft アプリ、カスタム アプリ、およびサードパーティ アプリが更新される方法と、管理者がそれを促進する方法について説明します。
ms.openlocfilehash: ed91ad441b773833838796d9ea8c71038c842b88
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299046"
---
# <a name="update-apps-in-microsoft-teams"></a>Microsoft Teams でアプリを更新する

ほとんどの場合、アプリの新しいバージョンが Teams ストアで利用可能になった後、アプリはユーザーに対して自動的に更新されます。 ただし、新しいアプリ バージョンのいくつかの特定の変更には、アプリを更新するためのユーザーの同意が必要です。 ユーザーが受け入れることで、機能やアクセスなどの変更を確実に認識できます。 アプリ開発者が Microsoft Teams アプリに対して次の特定の変更を行う場合、エンド ユーザーはアプリの更新プログラムを承認する必要があります。

* ボットが追加されました。
* 既存のボットの `botId` プロパティまたは `isNotificationOnly` プロパティが変更されました。
* ボットの `SupportsCalling`、`SupportsVideo`、および `SupportsFiles` 機能が追加されました。
* メッセージング拡張機能が追加されました。
* 承認内のアクセス許可が追加または変更されました。
* `Id` または `ApplicationPermissionsHash` またはその両方が `webApplicationInfo` 内で変更されています。

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="related-articles"></a>関連記事

* [アプリで行われる更新のマニフェスト スキーマを理解する](/microsoftteams/platform/resources/schema/manifest-schema)。
