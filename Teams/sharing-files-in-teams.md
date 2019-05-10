---
title: マイクロソフトのチームでファイルを共有
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: マイクロソフトのチームでは、共有を制御するのに OneDrive と SharePoint の設定を使用します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69f4ee036c951197e697c1f74bffb5c079d85bc3
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835076"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="014fb-103">マイクロソフトのチームでファイルを共有</span><span class="sxs-lookup"><span data-stu-id="014fb-103">Sharing files in Microsoft Teams</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-article.md)]

<span data-ttu-id="014fb-104">ファイル共有チームの機能は、組織内の他のチームのユーザーとコンテンツを共有するユーザーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="014fb-104">The file sharing features in Teams let users share content with other Teams users in their organization.</span></span> <span data-ttu-id="014fb-105">チームでの共有は、SharePoint と OneDrive もチームで共有を制御するものを設定する SharePoint および OneDrive のように構成された設定に基づいています。</span><span class="sxs-lookup"><span data-stu-id="014fb-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

<span data-ttu-id="014fb-106">共有チームには、次の操作をユーザーことができます。</span><span class="sxs-lookup"><span data-stu-id="014fb-106">Teams sharing lets users do the following:</span></span>

- <span data-ttu-id="014fb-107">OneDrive からファイルを共有します。</span><span class="sxs-lookup"><span data-stu-id="014fb-107">Share files from OneDrive.</span></span>

- <span data-ttu-id="014fb-108">他のユーザーと共有するファイルのアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="014fb-108">Set permissions for files they want to share with others.</span></span>

- <span data-ttu-id="014fb-109">チーム間でファイルを共有します。</span><span class="sxs-lookup"><span data-stu-id="014fb-109">Share files across Teams.</span></span>

- <span data-ttu-id="014fb-110">最近アクセスされたファイルの一覧からファイルを共有する (通常、これらは、ファイル共有で、ユーザーが最も関心がある)。</span><span class="sxs-lookup"><span data-stu-id="014fb-110">Share files from their list of recently accessed files (typically, these are the files users are most interested in sharing).</span></span>

- <span data-ttu-id="014fb-111">チーム内で常にファイルを開くファイルの名前をクリックしたとき。</span><span class="sxs-lookup"><span data-stu-id="014fb-111">Stay within Teams when they click a file name to open a file.</span></span>

<span data-ttu-id="014fb-112">チームには、SharePoint の URL、ブラウザー ファイルを指す URL が短くなります。</span><span class="sxs-lookup"><span data-stu-id="014fb-112">Teams shortens long SharePoint URLS and browser URLS that point to a file.</span></span> <span data-ttu-id="014fb-113">チームでは、ファイル名だけを使用して、ファイルにリンクします。</span><span class="sxs-lookup"><span data-stu-id="014fb-113">Teams uses just the file name to link to a file.</span></span> <span data-ttu-id="014fb-114">さらに、**リンクをコピーする**可能性のあるユーザーのファイルにアクセスできるように他のユーザーに関するすべての混乱を排除する**リンクを取得する**オプションが変更されました。</span><span class="sxs-lookup"><span data-stu-id="014fb-114">Additionally, the **Get link** option has been changed to **Copy link** to eliminate any confusion that users might have about giving others access to a file.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="014fb-115">OneDrive と SharePoint の共有を構成します。</span><span class="sxs-lookup"><span data-stu-id="014fb-115">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="014fb-116">OneDrive と SharePoint でのファイルの共有についての詳細についてなどの共有を構成する方法と、共有のオンとオフを有効にするを参照してください。</span><span class="sxs-lookup"><span data-stu-id="014fb-116">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="014fb-117">[外部の共有の概要](https://docs.microsoft.com/sharepoint/external-sharing-overview)では、ユーザーが共有している相手と共有しているときの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="014fb-117">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="014fb-118">説明[外部共有のオンとオフを有効にする](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)- グローバルと、SharePoint 管理者は、SharePoint と OneDrive の組織レベルの共有の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="014fb-118">[Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="014fb-119">[外部サイトの共有の変更](https://docs.microsoft.com/sharepoint/change-external-sharing-site): 説明グローバルし、SharePoint の管理者は、外部サイトのオンとオフを共有にすることができます。</span><span class="sxs-lookup"><span data-stu-id="014fb-119">[Change external sharing for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="014fb-120">[リンクの種類では、ユーザーが共有へのリンクを取得するときに既定値を変更する](https://docs.microsoft.com/sharepoint/change-default-sharing-link)より制限の厳しいことができるように、既定のリンクの種類を設定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="014fb-120">[Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it is more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="014fb-121">詳細情報</span><span class="sxs-lookup"><span data-stu-id="014fb-121">More information</span></span>

- [<span data-ttu-id="014fb-122">Microsoft Teams との SharePoint Online と OneDrive for Business の連携</span><span class="sxs-lookup"><span data-stu-id="014fb-122">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- <span data-ttu-id="014fb-123">[SharePoint およびチーム: 相乗効果](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。</span><span class="sxs-lookup"><span data-stu-id="014fb-123">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

- [<span data-ttu-id="014fb-124">OneDrive ファイルとフォルダーを共有します。</span><span class="sxs-lookup"><span data-stu-id="014fb-124">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="014fb-125">SharePoint のファイルまたはフォルダーを共有します。</span><span class="sxs-lookup"><span data-stu-id="014fb-125">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)

