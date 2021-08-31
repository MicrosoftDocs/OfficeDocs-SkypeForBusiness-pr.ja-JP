---
title: アプリの更新エクスペリエンス (Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
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
description: アプリを更新する方法については、Microsoft Teams。
ms.openlocfilehash: 0755c505a25d4c858afd104331d193edd8b2b27c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726206"
---
# <a name="update-apps-in-microsoft-teams"></a>Microsoft Teams でアプリを更新する

ほとんどの場合、アプリ開発者がアプリの更新プログラムを発行すると、ユーザーの新しいバージョンが自動的に表示されます。 ただし、完了するためにユーザーの受け入れを必要Microsoft Teams<a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">マニフェスト</a>には、いくつかの更新があります。

* ボットが追加または削除されました
* 既存のボットの "botId" プロパティが変更されました
* 既存のボットの "isNotificationOnly" プロパティが変更されました
* ボットの SupportsCalling、SupportsVideo、および SupportsFiles 機能が追加されました
* メッセージング拡張機能が追加されました
* 新しいコネクタが追加されました
* "webApplicationInfo" 内のプロパティが変更されました

![新しいバージョンを使用できます。](media/manage-your-custom-apps-update1.png)

![アプリのアップグレード オプション。](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> 更新プロセスは、Microsoft アプリ、カスタム アプリ、サード パーティ製アプリのすべてのアプリ更新プログラムに適用されます。 

## <a name="related-topics"></a>関連項目

[アプリを管理する](manage-apps.md)
