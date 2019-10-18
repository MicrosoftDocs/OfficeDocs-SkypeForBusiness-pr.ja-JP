---
title: ウイルス対策スキャンから除外する Teams ファイルとフォルダー
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
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b4a4591bf25d7ef1a5b6efb9ab83c4508e26110
ms.sourcegitcommit: bcebe833d5ff4fcd3d6246fc5ed80980c6f31d0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37578808"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a><span data-ttu-id="af8e8-103">ウイルス対策スキャンから除外する Teams ファイルとフォルダー</span><span class="sxs-lookup"><span data-stu-id="af8e8-103">Teams files and folders to exclude from antivirus scanning</span></span>
=================================

<span data-ttu-id="af8e8-104">ウイルス対策プログラムによって特定の Teams のファイルやフォルダーがスキャンされないようにすることで、チーム展開の全体的なパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="af8e8-104">You can improve the overall performance of your Teams deployment by preventing your antivirus programs from scanning certain Teams files and folders.</span></span> <span data-ttu-id="af8e8-105">これにより、スキャンする必要がないファイルやフォルダーのスキャンに関するシステムリソースの経費を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="af8e8-105">This will avoid the expenditure of system resources on scanning files and folders that don't need to be scanned.</span></span>

> [!NOTE]
> <span data-ttu-id="af8e8-106">ユーザーがファイルをダウンロードしたり、ファイルを共有したりするとき、これらのファイルは、次のセクションに記載されている場所を通過しません。</span><span class="sxs-lookup"><span data-stu-id="af8e8-106">When your users download files or share files with each other, those files don't pass through the locations listed in the following section.</span></span> <span data-ttu-id="af8e8-107">ユーザーがファイルをアップロード、ダウンロード、または共有する場所は、ウイルス対策プログラムによって定期的にスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="af8e8-107">The locations where your users do upload, download, or share files will still be regularly scanned by your antivirus program.</span></span>

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a><span data-ttu-id="af8e8-108">ウイルス対策の安全なリストに追加するファイルとフォルダー</span><span class="sxs-lookup"><span data-stu-id="af8e8-108">Files and folders to add to your antivirus safe lists</span></span>

<span data-ttu-id="af8e8-109">ウイルス対策プログラムでサポートされている手順を使用して、次のファイルとフォルダーをセーフリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="af8e8-109">Use the procedures supported by your antivirus program to add the following files and folders to your safe lists.</span></span> <span data-ttu-id="af8e8-110">こうすることで、これらの場所のウイルススキャンを回避して、システムリソースを節約できます。</span><span class="sxs-lookup"><span data-stu-id="af8e8-110">Doing so will conserve system resources by avoiding antivirus scans of these locations.</span></span>

### <a name="programs"></a><span data-ttu-id="af8e8-111">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="af8e8-111">Programs</span></span>

<span data-ttu-id="af8e8-112">ウイルス対策の安全なリストに次の Teams プログラムを追加します。</span><span class="sxs-lookup"><span data-stu-id="af8e8-112">Add the following Teams programs to your antivirus safe list.</span></span>

<span data-ttu-id="af8e8-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span><span class="sxs-lookup"><span data-stu-id="af8e8-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span></span>

<span data-ttu-id="af8e8-114">**%localappdata%\Microsoft\Teams\Update.exe**</span><span class="sxs-lookup"><span data-stu-id="af8e8-114">**%localappdata%\Microsoft\Teams\Update.exe**</span></span>

### <a name="folders"></a><span data-ttu-id="af8e8-115">フォルダ</span><span class="sxs-lookup"><span data-stu-id="af8e8-115">Folders</span></span>

<span data-ttu-id="af8e8-116">ウイルス対策の安全なリストに次の Teams フォルダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="af8e8-116">Add the following Teams folders to your antivirus safe list.</span></span>

|<span data-ttu-id="af8e8-117">[カテゴリ]</span><span class="sxs-lookup"><span data-stu-id="af8e8-117">Category</span></span>  |<span data-ttu-id="af8e8-118">場所</span><span class="sxs-lookup"><span data-stu-id="af8e8-118">Location</span></span>  |
|---------|---------|
|<span data-ttu-id="af8e8-119">プログラムファイル</span><span class="sxs-lookup"><span data-stu-id="af8e8-119">Program files</span></span>  |<span data-ttu-id="af8e8-120">%localappdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="af8e8-120">%localappdata%\Microsoft\Teams</span></span>|
|<span data-ttu-id="af8e8-121">データファイル</span><span class="sxs-lookup"><span data-stu-id="af8e8-121">Data files</span></span>     |<span data-ttu-id="af8e8-122">%appdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="af8e8-122">%appdata%\Microsoft\Teams</span></span>\|