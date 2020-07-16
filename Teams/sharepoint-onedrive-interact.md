---
title: Microsoft Teams との SharePoint Online と OneDrive for Business の連携
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & Teams での OneDrive for Business の操作プライベートチャットファイルストレージ & チーム、標準チャネル、& ドキュメントライブラリ間の相互作用。
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a66cacf7a60b020b4b56e0824d0a275efdf704f8
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "45140941"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="353ef-103">Microsoft Teams との SharePoint Online と OneDrive for Business の連携</span><span class="sxs-lookup"><span data-stu-id="353ef-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="353ef-104">チームと Azure Active Directory (AAD)、Microsoft 365 グループ、Exchange、SharePoint、および OneDrive for Business がどのように連携するかについては、次のセッションをご覧ください。 [Microsoft Teams の基礎](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="353ef-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="353ef-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span><span class="sxs-lookup"><span data-stu-id="353ef-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="353ef-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span><span class="sxs-lookup"><span data-stu-id="353ef-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="353ef-107">To see the impact of changing a site address in SharePoint, read [Change a site address](https://docs.microsoft.com/sharepoint/change-site-address).</span><span class="sxs-lookup"><span data-stu-id="353ef-107">To see the impact of changing a site address in SharePoint, read [Change a site address](https://docs.microsoft.com/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="353ef-108">この記事は、標準チャネルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="353ef-108">This article applies only to standard channels.</span></span> <span data-ttu-id="353ef-109">プライベート チャネルのアーキテクチャは、標準チャネルとは異なります。</span><span class="sxs-lookup"><span data-stu-id="353ef-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="353ef-110">各プライベート チャネルには、親チームのサイトとは別個の SharePoint サイト コレクションがあります。</span><span class="sxs-lookup"><span data-stu-id="353ef-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="353ef-111">詳しくは、「[Microsoft Teams のプライベート チャネル](private-channels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="353ef-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="353ef-112">プライベートチャットファイルは、送信者の OneDrive for Business フォルダーに保存され、ファイル共有プロセスの一環としてすべての参加者に対してアクセス許可が自動的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="353ef-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="353ef-113">ユーザーが SharePoint Online ライセンスを割り当てて有効にしていない場合、Microsoft 365 または Office 365 の OneDrive for Business ストレージはありません。</span><span class="sxs-lookup"><span data-stu-id="353ef-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="353ef-114">ファイルの共有は、引き続き標準チャネルでの作業を続けますが、Microsoft 365 または Office 365 では、OneDrive for Business ストレージを使わずに、チャットでファイルを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="353ef-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="353ef-115">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。</span><span class="sxs-lookup"><span data-stu-id="353ef-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="353ef-116">現時点で Microsoft Teams の SharePoint オンプレミスとの統合はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="353ef-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="353ef-117">チーム、標準チャネル、ドキュメント ライブラリの関係の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="353ef-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="353ef-118">すべてのチームに対して SharePoint サイトが作成され、**[共有ドキュメント]** フォルダーがチーム用の既定のフォルダーとして作成されます。</span><span class="sxs-lookup"><span data-stu-id="353ef-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="353ef-119">**一般**チャネルを含め各標準チャネル (各チームの既定のチャネル) には、**共有ドキュメント**にフォルダーがあります。</span><span class="sxs-lookup"><span data-stu-id="353ef-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![SharePoint Online の共有ドキュメント フォルダーの図。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="353ef-121">既定の SharePoint サイトとドキュメント ライブラリを別のもので置き換えることは現時点ではできません。</span><span class="sxs-lookup"><span data-stu-id="353ef-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="353ef-122">この機能が必要であるという要望をいただきましたので、現在検討中です。</span><span class="sxs-lookup"><span data-stu-id="353ef-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="353ef-123">[Teams ロードマップ](https://aka.ms/teamsroadmap)または [Teams UserVoice](https://aka.ms/TeamsUserVoice) をチェックして、今後利用できるようになる機能について継続的に把握します。</span><span class="sxs-lookup"><span data-stu-id="353ef-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="353ef-124">既存のSharePointサイトページまたはSharePointドキュメントライブラリにリンクするチームにタブを追加するには：</span><span class="sxs-lookup"><span data-stu-id="353ef-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="353ef-125">タブの隣にある + 記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="353ef-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="353ef-126">既存のSharePointサイトページには**SharePoint**、あるいは既存のドキュメントライブラリには**Document Library**を選択します。</span><span class="sxs-lookup"><span data-stu-id="353ef-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="353ef-127">適切なページまたはドキュメントライブラリを選択してください。</span><span class="sxs-lookup"><span data-stu-id="353ef-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="353ef-128">各ユーザーについては、他のユーザー (1 対 1 または 1 対多数 ) とのプライベート チャットで共有したすべてのファイルは OneDrive フォルダーの **Microsoft Teams Chat Files** に格納されます。このフォルダーには、指定したユーザーのみにアクセスを制限する権限が自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="353ef-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Microsoft Teams Chat Files という名前が付けられた OneDrive フォルダーの図](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="353ef-130">パブリックチームの場合、SharePoint チームサイトには、"外部ユーザー以外のすべてのユーザー" アクセスがプロビジョニングされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="353ef-130">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="353ef-131">パブリックチームは、チームのメンバーでないユーザーのために Teams に表示されません。</span><span class="sxs-lookup"><span data-stu-id="353ef-131">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="353ef-132">ただし、sharepoint チームサイトの URL を使用して SharePoint チームサイトのコンテンツにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="353ef-132">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="353ef-133">チャネル ファイル タブ</span><span class="sxs-lookup"><span data-stu-id="353ef-133">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="353ef-134">Teams の **[ファイル]** タブは、SharePoint ドキュメント ビューによく似ています。</span><span class="sxs-lookup"><span data-stu-id="353ef-134">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="353ef-135">**[ファイル]** タブでは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="353ef-135">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="353ef-136">**新規**ファイル メニューで追加オプションを確認する。</span><span class="sxs-lookup"><span data-stu-id="353ef-136">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="353ef-137">ファイルをローカル ドライブに同期する。</span><span class="sxs-lookup"><span data-stu-id="353ef-137">Sync files to their local drive.</span></span>
- <span data-ttu-id="353ef-138">**[すべてのドキュメント]** メニューで **[リスト]** ビューを **[コンパクト リスト]**、**[タイル]** ビューに切り替える。</span><span class="sxs-lookup"><span data-stu-id="353ef-138">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="353ef-139">注意が必要なファイル、またはマルウェアのあるファイルを特定する。</span><span class="sxs-lookup"><span data-stu-id="353ef-139">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="353ef-140">ファイルが読み取り専用かどうか、チェックアウト済みかどうかをすぐに確認する。</span><span class="sxs-lookup"><span data-stu-id="353ef-140">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="353ef-141">ファイルをチェックインおよびチェックアウトする。</span><span class="sxs-lookup"><span data-stu-id="353ef-141">Check out and check in files.</span></span>
- <span data-ttu-id="353ef-142">ファイルのピン留め、ピン留め解除、並べ替え順序の変更を行う。</span><span class="sxs-lookup"><span data-stu-id="353ef-142">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="353ef-143">メタデータが必要なファイルを特定する。</span><span class="sxs-lookup"><span data-stu-id="353ef-143">Identify which files need metadata</span></span>
- <span data-ttu-id="353ef-144">豊富なフィルター オプションの中から選択する。</span><span class="sxs-lookup"><span data-stu-id="353ef-144">Choose from many more filter options.</span></span>
- <span data-ttu-id="353ef-145">列見出しに基づいてファイルをグループ化する。</span><span class="sxs-lookup"><span data-stu-id="353ef-145">Group files based on column headings.</span></span>
- <span data-ttu-id="353ef-146">列の設定 (左または右へ移動、非表示) と列の幅を変更する。</span><span class="sxs-lookup"><span data-stu-id="353ef-146">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="353ef-147">既定のリンクの種類の設定</span><span class="sxs-lookup"><span data-stu-id="353ef-147">Default link type setting</span></span>

<span data-ttu-id="353ef-148">SharePoint と OneDrive には、ファイル用に作成されたリンクについて既定のリンクの種類を指定するための管理者設定があります。</span><span class="sxs-lookup"><span data-stu-id="353ef-148">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="353ef-149">Teams では、SharePoint と OneDrive の管理者による設定を再利用して、同じアプローチを採用します。</span><span class="sxs-lookup"><span data-stu-id="353ef-149">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="353ef-150">このアプローチについてさらに詳しくは、「[ユーザーが共有のリンクを取得するときの既定のリンクの種類を変更する](https://docs.microsoft.com/sharepoint/change-default-sharing-link)」で説明されています。</span><span class="sxs-lookup"><span data-stu-id="353ef-150">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="353ef-151">詳細情報</span><span class="sxs-lookup"><span data-stu-id="353ef-151">More information</span></span>

<span data-ttu-id="353ef-152">SharePointがTeams とどのように連携するかの詳細については、[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="353ef-152">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="353ef-153">Teams でのゲストのエクスペリエンス詳細については、[What the guest experience is like](guest-experience.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="353ef-153">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>
