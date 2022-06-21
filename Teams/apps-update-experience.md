---
title: Microsoft Teamsでのアプリの更新エクスペリエンス
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
description: この記事では、Microsoft Teamsの Microsoft アプリ、カスタム アプリ、およびサード パーティ製アプリの更新方法について説明します。
ms.openlocfilehash: cf4a062cd035feb0850a64c49a4c2363de0badce
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190317"
---
# <a name="update-apps-in-microsoft-teams"></a>Microsoft Teamsでアプリを更新する

ほとんどの場合、アプリ開発者がアプリの更新プログラムを発行すると、ユーザーに対して新しいバージョンが自動的に表示されます。 ただし、ユーザーの同意を完了する必要がある[Microsoft Teams マニフェスト](/microsoftteams/platform/resources/schema/manifest-schema)にいくつかの更新プログラムがあります。

* ボットが追加または削除されました
* 既存のボットの "botId" プロパティが変更されました
* 既存のボットの "isNotificationOnly" プロパティが変更されました
* ボットの SupportsCalling、SupportsVideo、および SupportsFiles 機能が追加されました
* メッセージング拡張機能が追加されました
* 新しいコネクタが追加されました
* "Authorization" 内のアクセス許可が追加または変更されました

![新しいバージョンを使用できます。](media/manage-your-custom-apps-update1.png)

![アプリのアップグレード オプション。](media/manage-your-custom-apps-update2.png)

> [!NOTE]
> 更新プロセスは、Microsoft アプリ、カスタム アプリ、およびサード パーティアプリのすべてのアプリ更新プログラムに適用されます。
