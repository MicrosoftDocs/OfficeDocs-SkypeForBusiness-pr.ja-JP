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
description: Microsoft Teamsでアプリを更新する方法について説明します。
ms.openlocfilehash: ed9a1de2e182088a20721758c63f8b6d83cc36df
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674999"
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

## <a name="related-topics"></a>関連項目

[アプリを管理する](manage-apps.md)
