---
title: ウイルス対策スキャンから除外する Teams のファイルとフォルダー
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: 定期的なウイルススキャンから特定のファイルやフォルダーを除外することで、チームのパフォーマンスを向上させます。
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1e890509428b3bfba19f6bfb01916e8ea837147
ms.sourcegitcommit: 0fa50d1cf354d79fbaf16b6aaec60e8d3ab852e8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43579593"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a><span data-ttu-id="cfd80-103">ウイルス対策スキャンから除外する Teams のファイルとフォルダー</span><span class="sxs-lookup"><span data-stu-id="cfd80-103">Teams files and folders to exclude from antivirus scanning</span></span>
=================================

<span data-ttu-id="cfd80-104">ウイルス対策プログラムによって特定の Teams のファイルやフォルダーがスキャンされないようにすることで、チーム展開の全体的なパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="cfd80-104">You can improve the overall performance of your Teams deployment by preventing your antivirus programs from scanning certain Teams files and folders.</span></span> <span data-ttu-id="cfd80-105">これにより、スキャンする必要がないファイルやフォルダーのスキャンに関するシステムリソースの経費を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="cfd80-105">This will avoid the expenditure of system resources on scanning files and folders that don't need to be scanned.</span></span>

> [!NOTE]
> <span data-ttu-id="cfd80-106">ユーザーがファイルをダウンロードしたり、ファイルを共有したりするとき、これらのファイルは、次のセクションに記載されている場所を通過しません。</span><span class="sxs-lookup"><span data-stu-id="cfd80-106">When your users download files or share files with each other, those files don't pass through the locations listed in the following section.</span></span> <span data-ttu-id="cfd80-107">ユーザーがファイルをアップロード、ダウンロード、または共有する場所は、ウイルス対策プログラムによって定期的にスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="cfd80-107">The locations where your users do upload, download, or share files will still be regularly scanned by your antivirus program.</span></span>

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a><span data-ttu-id="cfd80-108">ウイルス対策の安全なリストに追加するファイルとフォルダー</span><span class="sxs-lookup"><span data-stu-id="cfd80-108">Files and folders to add to your antivirus safe lists</span></span>

<span data-ttu-id="cfd80-109">ウイルス対策プログラムでサポートされている手順を使用して、次のファイルとフォルダーをセーフリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="cfd80-109">Use the procedures supported by your antivirus program to add the following files and folders to your safe lists.</span></span> <span data-ttu-id="cfd80-110">こうすることで、これらの場所のウイルススキャンを回避して、システムリソースを節約できます。</span><span class="sxs-lookup"><span data-stu-id="cfd80-110">Doing so will conserve system resources by avoiding antivirus scans of these locations.</span></span>

### <a name="programs"></a><span data-ttu-id="cfd80-111">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="cfd80-111">Programs</span></span>

<span data-ttu-id="cfd80-112">ウイルス対策の安全なリストに次の Teams プログラムを追加します。</span><span class="sxs-lookup"><span data-stu-id="cfd80-112">Add the following Teams programs to your antivirus safe list.</span></span>

<span data-ttu-id="cfd80-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span><span class="sxs-lookup"><span data-stu-id="cfd80-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span></span>

<span data-ttu-id="cfd80-114">**%localappdata%\Microsoft\Teams\Update.exe**</span><span class="sxs-lookup"><span data-stu-id="cfd80-114">**%localappdata%\Microsoft\Teams\Update.exe**</span></span>

