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
ms.openlocfilehash: a1a5cc6d926e7bc183db9950f1d11c1e3ffcd06c
ms.sourcegitcommit: 85017cf88789c750836780dad2ef707c1c6c39b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58359144"
---
# <a name="update-apps-in-microsoft-teams"></a>Microsoft Teams でアプリを更新する

ほとんどの場合、アプリ開発者がアプリの更新プログラムを発行すると、ユーザーの新しいバージョンが自動的に表示されます。 ただし、完了するためにユーザーの受け入れをMicrosoft Teams<a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">マニフェスト</a>に対する更新プログラムがいくつか含まれています。

* ボットが追加または削除されました
* 既存のボットの "botId" プロパティが変更されました
* 既存のボットの "isNotificationOnly" プロパティが変更されました
* ボットの SupportsCalling、SupportsVideo、および SupportsFiles 機能が追加されました
* メッセージング拡張機能が追加されました
* 新しいコネクタが追加されました
* "webApplicationInfo" 内のプロパティが変更されました

![利用可能な新しいバージョン](media/manage-your-custom-apps-update1.png)

![アプリのアップグレード オプション](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> 更新プロセスは、Microsoft アプリ、カスタム アプリ、およびサード パーティ製アプリのすべてのアプリ更新プログラムに適用されます。 

## <a name="related-topics"></a>関連項目

[アプリを管理する](manage-apps.md)
