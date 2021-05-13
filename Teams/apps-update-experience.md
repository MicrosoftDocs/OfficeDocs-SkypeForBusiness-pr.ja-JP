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
ms.openlocfilehash: b39b831b644b19038b8f4574acf3e5bc5c50d73c
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337827"
---
# <a name="update-apps-in-microsoft-teams"></a><span data-ttu-id="1e52e-103">Microsoft Teams でアプリを更新する</span><span class="sxs-lookup"><span data-stu-id="1e52e-103">Update apps in Microsoft Teams</span></span>

<span data-ttu-id="1e52e-104">ほとんどの場合、アプリ開発者がアプリの更新プログラムを発行すると、ユーザーの新しいバージョンが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e52e-104">In most cases, after app developers publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="1e52e-105">ただし、完了するためにユーザーの受け入れを<a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">必要Microsoft Teamsマニフェスト</a>にはいくつかの更新があります。</span><span class="sxs-lookup"><span data-stu-id="1e52e-105">However, there are some updates to the <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="1e52e-106">ボットが追加または削除されました</span><span class="sxs-lookup"><span data-stu-id="1e52e-106">A bot was added or removed</span></span>
* <span data-ttu-id="1e52e-107">既存のボットの "botId" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="1e52e-107">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="1e52e-108">既存のボットの "isNotificationOnly" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="1e52e-108">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="1e52e-109">ボットの "supportsFiles" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="1e52e-109">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="1e52e-110">メッセージング拡張機能が追加または削除されました</span><span class="sxs-lookup"><span data-stu-id="1e52e-110">A messaging extension was added or removed</span></span>
* <span data-ttu-id="1e52e-111">新しいコネクタが追加されました</span><span class="sxs-lookup"><span data-stu-id="1e52e-111">A new connector was added</span></span>
* <span data-ttu-id="1e52e-112">新しい静的タブが追加されました</span><span class="sxs-lookup"><span data-stu-id="1e52e-112">A new static tab was added</span></span>
* <span data-ttu-id="1e52e-113">新しい構成可能なタブが追加されました</span><span class="sxs-lookup"><span data-stu-id="1e52e-113">A new configurable tab was added</span></span>
* <span data-ttu-id="1e52e-114">"webApplicationInfo" 内のプロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="1e52e-114">Properties inside "webApplicationInfo" changed</span></span>

![利用可能な新しいバージョン](media/manage-your-custom-apps-update1.png)

![アプリのアップグレード オプション](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> <span data-ttu-id="1e52e-117">更新プロセスは、Microsoft アプリ、カスタム アプリ、サード パーティ製アプリのすべてのアプリ更新プログラムに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1e52e-117">The update process applies to all app updates for Microsoft apps, custom apps, and third-party apps.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="1e52e-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1e52e-118">Related topics</span></span>

[<span data-ttu-id="1e52e-119">アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="1e52e-119">Manage apps</span></span>](manage-apps.md)