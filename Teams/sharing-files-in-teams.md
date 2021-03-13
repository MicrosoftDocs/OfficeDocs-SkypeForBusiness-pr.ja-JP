---
title: Microsoft Teams でのファイルとフォルダー共有
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
description: Microsoft Teams のファイルとフォルダー共有機能について説明します。
ms.openlocfilehash: 5b6847c42f13701e289b2efaad4a5489351f339b
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795779"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="828ae-103">Microsoft Teams でのファイル共有</span><span class="sxs-lookup"><span data-stu-id="828ae-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="828ae-104">Microsoft Teams では、組織内外の他の Teamsユーザーとコンテンツを共有できます。</span><span class="sxs-lookup"><span data-stu-id="828ae-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="828ae-105">Teamsでのファイルとフォルダー共有は、SharePoint と OneDrive に構成されている設定に基づいているため、SharePoint および OneDrive 用の設定が、Teams での共有にも影響します。</span><span class="sxs-lookup"><span data-stu-id="828ae-105">Sharing files and folders in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will affect sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="828ae-106">概要</span><span class="sxs-lookup"><span data-stu-id="828ae-106">Overview</span></span>

<span data-ttu-id="828ae-107">ユーザーは、OneDrive、アクセス権が与えられているチームやサイトおよびコンピューターからのファイルを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="828ae-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="828ae-108">ファイルを共有するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="828ae-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="828ae-p103">チャネルで、[**添付**] (ペーパークリップ アイコン)、[**最近使用した**]、[**Teams とチャネルを参照**] をクリックして、[**OneDrive**] または、[**マイコンピューターから アップロード**] の順にクリックして、共有するファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="828ae-p103">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share. </span></span><br> 
    <span data-ttu-id="828ae-110">![ファイルをチャネルから共有しているスクリーンショット](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="828ae-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="828ae-p104">チャットで、[**添付** ] (ペーパークリップのアイコン) をクリックして、[**OneDrive**] または [**マイコンピューターから アップロード**] を選択して、共有するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="828ae-p104">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share. </span></span><br>
    <span data-ttu-id="828ae-112">![チャットからのファイルの共有を示したスクリーンショット](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="828ae-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="828ae-113">作成ボックスに共有リンクをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="828ae-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="828ae-114">![[作成] ボックスにファイルのプレビューを表示しているスクリーンショット](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="828ae-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="828ae-115">共有ファイルと共有リンクのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="828ae-115">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="828ae-116">ユーザーが Teams 内からファイルを共有する場合、Microsoft 365 の場合と同様に、ファイルにアクセスできるユーザーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="828ae-116">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="828ae-117">既存のアクセス権を持つユーザー、または特定のユーザー (1:1 チャット、グループチャット、チャネルのユーザーを含む) など、組織内のどのユーザーにもアクセス権を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="828ae-117">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="828ae-118">ファイルが共有されている場合はメッセージでファイルのプレビューが表示されます。これには、 **オンラインでオープン**、**ダウンロード**、**リンクをコピー** といった、あらゆるアクションも同時に表示されます。</span><span class="sxs-lookup"><span data-stu-id="828ae-118">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="828ae-119">既定では、ファイルは [Teams] で開きます。</span><span class="sxs-lookup"><span data-stu-id="828ae-119">By default, the file opens in Teams.</span></span>

<span data-ttu-id="828ae-120">ユーザーがチャットやチャネルでファイルを共有すると、一部またはすべての受信者がファイルを表示する権限を持っているか、いないかが通知されます。</span><span class="sxs-lookup"><span data-stu-id="828ae-120">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="828ae-121">ファイルを共有する前に、メッセージに表示されるファイルプレビューの横にある矢印をクリックすると、ファイルのアクセス許可を変更できます。</span><span class="sxs-lookup"><span data-stu-id="828ae-121">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![受信者にアクセス許可がない場合の通知のスクリーンショット](media/share-files-permissions.png)

## <a name="related-topics"></a><span data-ttu-id="828ae-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="828ae-123">Related topics</span></span>

[<span data-ttu-id="828ae-124">Microsoft Teams との SharePoint Online と OneDrive for Business の連携</span><span class="sxs-lookup"><span data-stu-id="828ae-124">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

[<span data-ttu-id="828ae-125">サイトの既定のリンクの種類を変更する</span><span class="sxs-lookup"><span data-stu-id="828ae-125">Change the default link type for a site</span></span>](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

[<span data-ttu-id="828ae-126">チームでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="828ae-126">Collaborate with guests in a team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)