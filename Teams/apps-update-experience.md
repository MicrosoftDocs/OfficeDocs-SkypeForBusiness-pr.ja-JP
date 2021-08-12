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
localization_priority: Normal
search.appverid: MET150
description: アプリを更新する方法については、Microsoft Teams。
ms.openlocfilehash: e271af73800e87ddf5c0f83009fbd85002fc059e8da3f2479198de9ae64ea698
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288405"
---
# <a name="update-apps-in-microsoft-teams"></a>Microsoft Teams でアプリを更新する

ほとんどの場合、アプリ開発者がアプリの更新プログラムを発行すると、ユーザーの新しいバージョンが自動的に表示されます。 ただし、完了するためにユーザーの受け入れを<a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">必要Microsoft Teamsマニフェスト</a>にはいくつかの更新があります。

* ボットが追加または削除されました
* 既存のボットの "botId" プロパティが変更されました
* 既存のボットの "isNotificationOnly" プロパティが変更されました
* ボットの "supportsFiles" プロパティが変更されました
* メッセージング拡張機能が追加または削除されました
* 新しいコネクタが追加されました
* 新しい静的タブが追加されました
* 新しい構成可能なタブが追加されました
* "webApplicationInfo" 内のプロパティが変更されました

![利用可能な新しいバージョン](media/manage-your-custom-apps-update1.png)

![アプリのアップグレード オプション](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> 更新プロセスは、Microsoft アプリ、カスタム アプリ、サード パーティ製アプリのすべてのアプリ更新プログラムに適用されます。 

## <a name="related-topics"></a>関連項目

[アプリを管理する](manage-apps.md)