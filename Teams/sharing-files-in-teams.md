---
title: Microsoft Teams でのファイル共有
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Microsoft Teams では、OneDrive と SharePoint の設定を使用して共有を制御します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ddb342af669f710bfd9d05c8b21290ebc6e0451
ms.sourcegitcommit: da87a3c4c781223ab7de2fb539bb0796dc27ea9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2019
ms.locfileid: "35821052"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="11c75-103">Microsoft Teams でのファイル共有</span><span class="sxs-lookup"><span data-stu-id="11c75-103">Sharing files in Microsoft Teams</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-article.md)]

<span data-ttu-id="11c75-104">Teams のファイル共有機能を使用すると、ユーザーは組織内の他の Teams ユーザーとコンテンツを共有できます。</span><span class="sxs-lookup"><span data-stu-id="11c75-104">The file sharing features in Teams let users share content with other Teams users in their organization.</span></span> <span data-ttu-id="11c75-105">Teams での共有は、SharePoint と OneDrive で構成されている設定に基づいているため、SharePoint と OneDrive のどちらを設定しても、Teams での共有が制御されます。</span><span class="sxs-lookup"><span data-stu-id="11c75-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>
<span data-ttu-id="11c75-106">![Teams と OneDrive for Business と SharePoint の間でファイル共有がどのように動作するかを示す図](media/sharing-files-in-teams-image1.png)</span><span class="sxs-lookup"><span data-stu-id="11c75-106">![Diagram indicating how file sharing works between Teams and OneDrive for Business and SharePoint](media/sharing-files-in-teams-image1.png)</span></span>

<span data-ttu-id="11c75-107">Teams の共有では、ユーザーが次のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="11c75-107">Teams sharing lets users do the following:</span></span>

- <span data-ttu-id="11c75-108">OneDrive からファイルを共有します。</span><span class="sxs-lookup"><span data-stu-id="11c75-108">Share files from OneDrive.</span></span>

- <span data-ttu-id="11c75-109">他のユーザーと共有するファイルのアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="11c75-109">Set permissions for files they want to share with others.</span></span>

- <span data-ttu-id="11c75-110">チーム間でファイルを共有します。</span><span class="sxs-lookup"><span data-stu-id="11c75-110">Share files across Teams.</span></span>

- <span data-ttu-id="11c75-111">最近アクセスしたファイルの一覧からファイルを共有します (通常は、ユーザーが共有に最も関心を持っているファイルです)。</span><span class="sxs-lookup"><span data-stu-id="11c75-111">Share files from their list of recently accessed files (typically, these are the files users are most interested in sharing).</span></span>

- <span data-ttu-id="11c75-112">ファイル名をクリックしてファイルを開くと、チーム内でそのままの状態になります。</span><span class="sxs-lookup"><span data-stu-id="11c75-112">Stay within Teams when they click a file name to open a file.</span></span>

<span data-ttu-id="11c75-113">チームは長い SharePoint URL とファイルを参照するブラウザー URL を短縮します。</span><span class="sxs-lookup"><span data-stu-id="11c75-113">Teams shortens long SharePoint URLS and browser URLS that point to a file.</span></span> <span data-ttu-id="11c75-114">Teams では、ファイル名のみを使用してファイルにリンクします。</span><span class="sxs-lookup"><span data-stu-id="11c75-114">Teams uses just the file name to link to a file.</span></span> <span data-ttu-id="11c75-115">さらに、[リンクの**取得**] オプションが [**リンクのコピー** ] に変更され、他のユーザーがファイルにアクセスするときに発生する可能性のある混乱を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="11c75-115">Additionally, the **Get link** option has been changed to **Copy link** to eliminate any confusion that users might have about giving others access to a file.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="11c75-116">OneDrive と SharePoint の共有を構成する</span><span class="sxs-lookup"><span data-stu-id="11c75-116">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="11c75-117">OneDrive と SharePoint でのファイルの共有について詳しくは、「共有を構成する方法」と「共有を有効または無効にする方法」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="11c75-117">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="11c75-118">[外部共有の概要](https://docs.microsoft.com/sharepoint/external-sharing-overview)-ユーザーが共有している内容や他のユーザーが共有しているときの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="11c75-118">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="11c75-119">[外部共有を有効または無効](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)にする-グローバルと sharepoint の管理者が Sharepoint と OneDrive の組織レベルの共有設定を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="11c75-119">[Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="11c75-120">[サイトの外部共有を変更](https://docs.microsoft.com/sharepoint/change-external-sharing-site)する–グローバルと SharePoint 管理者がサイトの外部共有を有効または無効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="11c75-120">[Change external sharing for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="11c75-121">[ユーザーが共有用のリンクを取得するときの既定のリンクの種類を変更](https://docs.microsoft.com/sharepoint/change-default-sharing-link)する-既定のリンクの種類を設定して、制限を高くする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="11c75-121">[Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it is more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="11c75-122">詳細情報</span><span class="sxs-lookup"><span data-stu-id="11c75-122">More information</span></span>

- [<span data-ttu-id="11c75-123">Microsoft Teams との SharePoint Online と OneDrive for Business の連携</span><span class="sxs-lookup"><span data-stu-id="11c75-123">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- <span data-ttu-id="11c75-124">[SharePoint とチーム: 共同](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)作業がより簡単になります。</span><span class="sxs-lookup"><span data-stu-id="11c75-124">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

- [<span data-ttu-id="11c75-125">OneDrive のファイルとフォルダーを共有する</span><span class="sxs-lookup"><span data-stu-id="11c75-125">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="11c75-126">SharePoint のファイルまたはフォルダーを共有する</span><span class="sxs-lookup"><span data-stu-id="11c75-126">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)

