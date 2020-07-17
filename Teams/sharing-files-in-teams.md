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
description: Microsoft Teams でのファイル共有のエクスペリエンスについて説明します。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138351"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="b1f13-103">Microsoft Teams でのファイル共有</span><span class="sxs-lookup"><span data-stu-id="b1f13-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="b1f13-104">Microsoft Teams では、ユーザーは組織内外の他の Teams ユーザーとコンテンツを共有できます。</span><span class="sxs-lookup"><span data-stu-id="b1f13-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="b1f13-105">Teams での共有は、SharePoint と OneDrive で構成されている設定に基づいているため、SharePoint と OneDrive のどちらを設定しても、Teams での共有が制御されます。</span><span class="sxs-lookup"><span data-stu-id="b1f13-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="b1f13-106">概要</span><span class="sxs-lookup"><span data-stu-id="b1f13-106">Overview</span></span>

<span data-ttu-id="b1f13-107">ユーザーは、アクセス権を持つチームやサイトから、または自分のコンピューターからファイルを共有できます。</span><span class="sxs-lookup"><span data-stu-id="b1f13-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="b1f13-108">ファイルを共有するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b1f13-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="b1f13-109">チャネルで、[**添付**] (クリップアイコン) をクリックし、[**最近使用**したファイル] を選択し、[**チームとチャネル**]、[ **OneDrive**] を参照するか、[**マイコンピューターからアップロード**] をクリックして、共有するファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="b1f13-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="b1f13-110">![チャネルからのファイルの共有を示すスクリーンショット](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="b1f13-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="b1f13-111">チャットで、[**添付**] (クリップアイコン) をクリック**するか、** [**マイコンピューターからアップロード**] をクリックして、共有するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f13-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="b1f13-112">![チャットからのファイルの共有を示すスクリーンショット](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="b1f13-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="b1f13-113">作成ボックスの共有リンクをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b1f13-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="b1f13-114">![作成ボックスのファイルプレビューを示すスクリーンショット](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="b1f13-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a><span data-ttu-id="b1f13-115">ファイル共有のエクスペリエンスについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="b1f13-115">What you need to know about the file sharing experience</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="b1f13-116">共有ファイルと共有リンクの権限</span><span class="sxs-lookup"><span data-stu-id="b1f13-116">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="b1f13-117">OneDrive またはチームおよびチャネルでファイルを参照してファイルを共有すると、すべての受信者に、[組織レベルで設定された既定のアクセス許可](https://docs.microsoft.com/sharepoint/change-default-sharing-link)が与えられます。</span><span class="sxs-lookup"><span data-stu-id="b1f13-117">When users share a file by browsing to it in OneDrive or teams and channels, all recipients are granted access along with the [default permission that's set at the organization level](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span>

<span data-ttu-id="b1f13-118">ユーザーが共有リンクをコピーして貼り付けると、その共有リンクに設定されているアクセス許可が有効になり、SharePoint URL はファイル名に短縮されます。</span><span class="sxs-lookup"><span data-stu-id="b1f13-118">When a user copies and pastes a sharing link, the permissions set on that sharing link are honored and the SharePoint URL is shortened to the file name.</span></span> <span data-ttu-id="b1f13-119">つまり、Teams はファイル名だけを使ってファイルにリンクします。</span><span class="sxs-lookup"><span data-stu-id="b1f13-119">In other words, Teams uses just the file name to link to a file.</span></span>

<span data-ttu-id="b1f13-120">ユーザーが Teams 内からファイルを共有する場合、Microsoft 365 全体での場合と同様に、ファイルにアクセスできるユーザーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="b1f13-120">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="b1f13-121">ユーザーは、組織内のユーザー、既存のアクセス権を持つユーザー、または特定のユーザーにアクセス権を付与することができます (ユーザーを1:1 チャット、グループチャット、またはチャネルに含めることができます)。</span><span class="sxs-lookup"><span data-stu-id="b1f13-121">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="b1f13-122">ファイルが共有されている場合、ファイルのプレビューは、 **[オンラインで開く**]、[**ダウンロード**]、[**コピー**] などのすべてのファイル操作と共に、メッセージで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b1f13-122">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="b1f13-123">既定では、ファイルは Teams で開きます。</span><span class="sxs-lookup"><span data-stu-id="b1f13-123">By default, the file opens in Teams.</span></span> <span data-ttu-id="b1f13-124">場合によっては、ユーザーがメッセージを送信したときに、共有リンクがファイルプレビューに変換されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="b1f13-124">Sometimes, the sharing link may not have converted to a file preview by the time a user sends the message.</span></span> <span data-ttu-id="b1f13-125">ファイルプレビューはシステムによって生成されますが、このシナリオでは、ファイル名のみに共有リンクを短縮することはできません。</span><span class="sxs-lookup"><span data-stu-id="b1f13-125">The file preview will be generated by the system, but in this scenario, the sharing link won't be shortened to the only the file name.</span></span>

<span data-ttu-id="b1f13-126">ユーザーがチャットまたはチャネルでファイルを共有すると、一部またはすべての受信者にファイルを表示する権限がないかどうかが通知されます。</span><span class="sxs-lookup"><span data-stu-id="b1f13-126">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="b1f13-127">ファイルを共有する前に、ファイルのアクセス許可を変更することができます。これで、メッセージに表示されるファイルプレビューの横にある矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1f13-127">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![受信者が権限を持っていない場合の通知のスクリーンショット](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a><span data-ttu-id="b1f13-129">Teams で共有リンクをコピーする</span><span class="sxs-lookup"><span data-stu-id="b1f13-129">Copy a sharing link in Teams</span></span>

<span data-ttu-id="b1f13-130">ユーザーは、Microsoft 365 と同じように、SharePoint 共有リンクをコピーし、共有権限を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b1f13-130">Users can copy a SharePoint sharing link and change sharing permissions just like they do across Microsoft 365.</span></span> <span data-ttu-id="b1f13-131">組織内のユーザー、既存のアクセス権を持つユーザー、または特定のユーザーにアクセス権を付与することができます。</span><span class="sxs-lookup"><span data-stu-id="b1f13-131">They can give access to anyone, people in your organization, people with existing access, or specific people.</span></span> <span data-ttu-id="b1f13-132">リンクの既定のアクセス許可は、SharePoint のサイトレベルの権限を上書きしない限り、組織レベルで設定された既定の権限セットと同じです。</span><span class="sxs-lookup"><span data-stu-id="b1f13-132">The default permission of the link is the same as the default permission set at the organization level unless SharePoint site level permissions override it.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="b1f13-133">OneDrive と SharePoint の共有を構成する</span><span class="sxs-lookup"><span data-stu-id="b1f13-133">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="b1f13-134">OneDrive と SharePoint でのファイルの共有について詳しくは、「共有を構成する方法」と「共有を有効または無効にする方法」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b1f13-134">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="b1f13-135">[外部共有の概要](https://docs.microsoft.com/sharepoint/external-sharing-overview)-ユーザーが共有している内容や他のユーザーが共有しているときの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1f13-135">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="b1f13-136">[共有設定を管理](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)する-グローバルと sharepoint 管理者が Sharepoint と OneDrive の組織レベルの共有設定を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1f13-136">[Manage sharing settings](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="b1f13-137">[サイトの外部共有を有効または無効](https://docs.microsoft.com/sharepoint/change-external-sharing-site)にする–グローバルと SharePoint 管理者がサイトの外部共有を有効または無効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1f13-137">[Turn external sharing on or off for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="b1f13-138">[サイトの既定のリンクの種類を変更](https://docs.microsoft.com/sharepoint/change-default-sharing-link)する-既定のリンクの種類を設定して、より制限されるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1f13-138">[Change the default link type for a site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it's more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="b1f13-139">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b1f13-139">More information</span></span>

- [<span data-ttu-id="b1f13-140">Microsoft Teams との SharePoint Online と OneDrive for Business の連携</span><span class="sxs-lookup"><span data-stu-id="b1f13-140">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- [<span data-ttu-id="b1f13-141">SharePoint とチーム: 共同作業を効率化する</span><span class="sxs-lookup"><span data-stu-id="b1f13-141">SharePoint and Teams: better together</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [<span data-ttu-id="b1f13-142">OneDrive のファイルとフォルダーを共有する</span><span class="sxs-lookup"><span data-stu-id="b1f13-142">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="b1f13-143">SharePoint のファイルまたはフォルダーを共有する</span><span class="sxs-lookup"><span data-stu-id="b1f13-143">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
