---
title: Microsoft Teams でのファイル共有
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Microsoft Teams のファイル共有機能について説明します。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138351"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="f9e87-103">Microsoft Teams でのファイル共有</span><span class="sxs-lookup"><span data-stu-id="f9e87-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="f9e87-104">Microsoft Teams では、組織内外の他の Teamsユーザーとコンテンツを共有できます。</span><span class="sxs-lookup"><span data-stu-id="f9e87-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="f9e87-105">Teamsでの共有は、SharePoint と OneDrive に構成されている設定に基づいているため、SharePoint および OneDrive 用の設定が、チームの共有も制御します。</span><span class="sxs-lookup"><span data-stu-id="f9e87-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="f9e87-106">概要</span><span class="sxs-lookup"><span data-stu-id="f9e87-106">Overview</span></span>

<span data-ttu-id="f9e87-107">ユーザーは、OneDrive、アクセス権が与えられているチームやサイトおよびコンピューターからのファイルを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="f9e87-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="f9e87-108">ファイルを共有するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f9e87-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="f9e87-109">チャネルで、[**添付**] (ペーパークリップ アイコン)、[**最近使用した**]、[**Teams とチャネルを参照**] をクリックして、[**OneDrive**] または、[**マイコンピューターから アップロード**] の順にクリックして、共有するファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="f9e87-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="f9e87-110">![ファイルをチャネルから共有しているスクリーンショット](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="f9e87-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="f9e87-111">チャットで、[**添付** ] (ペーパークリップのアイコン) をクリックして、[**OneDrive**] または [**マイコンピューターから アップロード**] を選択して、共有するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f9e87-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="f9e87-112">![チャットからのファイルの共有を示したスクリーンショット](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="f9e87-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="f9e87-113">作成ボックスに共有リンクをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f9e87-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="f9e87-114">![[作成] ボックスにファイルのプレビューを表示しているスクリーンショット](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="f9e87-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a><span data-ttu-id="f9e87-115">ファイル共有機能について知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="f9e87-115">What you need to know about the file sharing experience</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="f9e87-116">共有ファイルと共有リンクのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f9e87-116">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="f9e87-117">ユーザーが OneDrive またはチームとチャネルでファイルを参照してファイルを共有すると、すべての受信者に「[組織レベルに設定されている既定のアクセス許可](https://docs.microsoft.com/sharepoint/change-default-sharing-link)」に準拠してアクセス権が与えられます。</span><span class="sxs-lookup"><span data-stu-id="f9e87-117">When users share a file by browsing to it in OneDrive or teams and channels, all recipients are granted access along with the [default permission that's set at the organization level](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span>

<span data-ttu-id="f9e87-118">ユーザーが共有リンクをコピーして貼り付けたときに、その共有リンクに設定されているアクセス許可が優先され、SharePoint の URL が短くなりファイル名になります。</span><span class="sxs-lookup"><span data-stu-id="f9e87-118">When a user copies and pastes a sharing link, the permissions set on that sharing link are honored and the SharePoint URL is shortened to the file name.</span></span> <span data-ttu-id="f9e87-119">つまり、Teams は、ファイル名だけを使用してファイルにリンクします。</span><span class="sxs-lookup"><span data-stu-id="f9e87-119">In other words, Teams uses just the file name to link to a file.</span></span>

<span data-ttu-id="f9e87-120">ユーザーが Teams 内からファイルを共有する場合、Microsoft 365 の場合と同様に、ファイルにアクセスできるユーザーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f9e87-120">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="f9e87-121">既存のアクセス権を持つユーザー、または特定のユーザー (1:1 チャット、グループチャット、チャネルのユーザーを含む) など、組織内のどのユーザーにもアクセス権を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="f9e87-121">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="f9e87-122">ファイルが共有されている場合はメッセージでファイルのプレビューが表示されます。これには、 **オンラインでオープン**、**ダウンロード**、**リンクをコピー** といった、あらゆるアクションも同時に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9e87-122">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="f9e87-123">既定では、ファイルは [Teams] で開きます。</span><span class="sxs-lookup"><span data-stu-id="f9e87-123">By default, the file opens in Teams.</span></span> <span data-ttu-id="f9e87-124">ユーザーがメッセージを送信する時に、共有リンクがファイルプレビューに変換されていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="f9e87-124">Sometimes, the sharing link may not have converted to a file preview by the time a user sends the message.</span></span> <span data-ttu-id="f9e87-125">ファイルのプレビューはシステムによって作成されますが、このシナリオでは、共有リンクをファイル名のみに縮めてしまうことはありません。</span><span class="sxs-lookup"><span data-stu-id="f9e87-125">The file preview will be generated by the system, but in this scenario, the sharing link won't be shortened to the only the file name.</span></span>

<span data-ttu-id="f9e87-126">ユーザーがチャットやチャネルでファイルを共有すると、一部またはすべての受信者がファイルを表示する権限を持っているか、いないかが通知されます。</span><span class="sxs-lookup"><span data-stu-id="f9e87-126">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="f9e87-127">ファイルを共有する前に、メッセージに表示されるファイルプレビューの横にある矢印をクリックすると、ファイルのアクセス許可を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f9e87-127">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![受信者にアクセス許可がない場合の通知のスクリーンショット](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a><span data-ttu-id="f9e87-129">共有リンクを Teams にコピーする</span><span class="sxs-lookup"><span data-stu-id="f9e87-129">Copy a sharing link in Teams</span></span>

<span data-ttu-id="f9e87-130">Microsoft 365 の場合と同様に、ユーザーは SharePoint 共有リンクをコピーすることも、共有アクセス許可を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="f9e87-130">Users can copy a SharePoint sharing link and change sharing permissions just like they do across Microsoft 365.</span></span> <span data-ttu-id="f9e87-131">既存のアクセス権を持つユーザー、または特定のユーザーなど、組織内のすべてのユーザーにアクセス権を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="f9e87-131">They can give access to anyone, people in your organization, people with existing access, or specific people.</span></span> <span data-ttu-id="f9e87-132">リンクの既定のアクセス許可は、SharePoint サイト レベルの権限を優先しない限り、組織レベルで設定された既定のアクセス許可と同じです。</span><span class="sxs-lookup"><span data-stu-id="f9e87-132">The default permission of the link is the same as the default permission set at the organization level unless SharePoint site level permissions override it.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="f9e87-133">OneDrive と SharePoint の共有を構成する</span><span class="sxs-lookup"><span data-stu-id="f9e87-133">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="f9e87-134">共有を構成する方法、共有を有効または無効にする方法など、OneDrive と SharePoint でファイルを共有する方法の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9e87-134">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="f9e87-135">[外部共有の概要](https://docs.microsoft.com/sharepoint/external-sharing-overview) - 共有する内容と相手に応じて、ユーザーが共有したときの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9e87-135">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="f9e87-136">[共有設定の管理](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - グローバルおよび SharePoint 管理者が、SharePoint および OneDrive の組織レベルの共有設定を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9e87-136">[Manage sharing settings](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="f9e87-137">[サイトの外部共有を有効または無効にする](https://docs.microsoft.com/sharepoint/change-external-sharing-site) –グローバルおよび SharePoint 管理者がサイトの外部共有を有効または無効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9e87-137">[Turn external sharing on or off for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="f9e87-138">[サイトの既定のリンクの種類を変更する](https://docs.microsoft.com/sharepoint/change-default-sharing-link) -制約を厳しくするように既定のリンクの種類を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9e87-138">[Change the default link type for a site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it's more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="f9e87-139">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f9e87-139">More information</span></span>

- [<span data-ttu-id="f9e87-140">Microsoft Teams との SharePoint Online と OneDrive for Business の連携</span><span class="sxs-lookup"><span data-stu-id="f9e87-140">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- [<span data-ttu-id="f9e87-141">SharePoint とTeams: 共同作業の効率化</span><span class="sxs-lookup"><span data-stu-id="f9e87-141">SharePoint and Teams: better together</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [<span data-ttu-id="f9e87-142">OneDrive のファイルとフォルダーの共有</span><span class="sxs-lookup"><span data-stu-id="f9e87-142">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="f9e87-143">SharePoint のファイルまたはフォルダを共有する</span><span class="sxs-lookup"><span data-stu-id="f9e87-143">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
