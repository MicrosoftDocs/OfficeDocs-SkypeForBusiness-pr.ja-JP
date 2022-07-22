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
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: この記事では、Microsoft Teams の Microsoft アプリ、カスタム アプリ、サード パーティ製アプリの更新方法について説明します。
ms.openlocfilehash: 27d51a487af918e6fcee2b7806c81d31506bd1af
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958042"
---
# <a name="update-apps-in-microsoft-teams"></a>Microsoft Teams でアプリを更新する

ほとんどの場合、アプリ開発者がアプリの更新プログラムを発行すると、ユーザーに対して新しいバージョンが自動的に表示されます。 ただし、 [Microsoft Teams マニフェスト](/microsoftteams/platform/resources/schema/manifest-schema) には、ユーザーの同意を完了する必要がある更新プログラムがいくつかあります。

* ボットが追加または削除されました。
* 既存のボットの "botId" プロパティが変更されました。
* 既存のボットの "isNotificationOnly" プロパティが変更されました。
* ボットの SupportsCalling、SupportsVideo、および SupportsFiles 機能が追加されました。
* メッセージング拡張機能が追加されました。
* 新しいコネクタが追加されました。
* "Authorization" 内のアクセス許可が追加または変更されました。

:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="利用可能な新しいバージョン。" lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="アプリのアップグレード オプション。" lightbox="media/manage-your-custom-apps-update2.png":::

> [!NOTE]
> 更新プロセスは、Microsoft アプリ、カスタム アプリ、およびサード パーティアプリのすべてのアプリ更新プログラムに適用されます。
