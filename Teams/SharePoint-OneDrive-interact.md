---
title: Microsoft Teams との SharePoint Online と OneDrive for Business の連携
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: プライベート チャット ファイルの格納方法、チーム、チャネル、ドキュメント ライブラリの関係など、Microsoft Teams との SharePoint Online および OneDrive for Business の連携について説明します。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af1d12eda58dc481ba28bf96ff4ecbfeab8ed5f0
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "37567121"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="b992c-103">Microsoft Teams との SharePoint Online と OneDrive for Business の連携</span><span class="sxs-lookup"><span data-stu-id="b992c-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="b992c-104">TeamsがAzure Active Directory（AAD）、Office 365グループ、Exchange、SharePoint、およびOneDrive for Businessとどのようにやり取りするのかを学ぶために、次のセッションをご覧ください: [Microsoft Teams の基礎](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="b992c-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="b992c-p101">Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="b992c-p101">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="b992c-107">プライベート チャット ファイルは送信者の OneDrive for Business フォルダーに格納され、権限はファイル共有プロセスの一環としてすべての参加者に付与されます。</span><span class="sxs-lookup"><span data-stu-id="b992c-107">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="b992c-108">ユーザーにSharePoint Onlineの有効なライセンスが割り当てられていない場合は、Office 365にOneDrive for Businessのストレージがありません。</span><span class="sxs-lookup"><span data-stu-id="b992c-108">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="b992c-109">ファイル共有は引き続きチャンネルで機能しますが、Office 365のOneDrive for Businessストレージがないと、ユーザーはチャットでファイルを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="b992c-109">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="b992c-110">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。</span><span class="sxs-lookup"><span data-stu-id="b992c-110">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="b992c-111">現時点では、オンプレミスの SharePoint との統合はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b992c-111">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="b992c-112">チーム、チャネル、ドキュメント ライブラリの関係の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b992c-112">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="b992c-p103">各チームには SharePoint サイトが作成されます。**共有ドキュメント** フォルダーは、そのチーム用に作成される既定のフォルダーです。各チャネル (各チームの既定のチャネルである**全般**チャネルを含む) には**共有ドキュメント**内にフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b992c-p103">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team. Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![SharePoint Online の共有ドキュメントフォルダーの図](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="b992c-116">既定の SharePoint サイトとドキュメント ライブラリを別のもので置き換えることは現時点ではできません。</span><span class="sxs-lookup"><span data-stu-id="b992c-116">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="b992c-117">この機能が必要であるという要望をいただきましたので、現在検討中です。</span><span class="sxs-lookup"><span data-stu-id="b992c-117">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="b992c-118">[Teams ロードマップ](https://aka.ms/teamsroadmap)または [Teams UserVoice](https://aka.ms/TeamsUserVoice) をチェックして、今後利用できるようになる機能について継続的に把握します。</span><span class="sxs-lookup"><span data-stu-id="b992c-118">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="b992c-119">既存のSharePointサイトページまたはSharePointドキュメントライブラリにリンクするチームにタブを追加するには：</span><span class="sxs-lookup"><span data-stu-id="b992c-119">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="b992c-120">タブの隣にある + 記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="b992c-120">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="b992c-121">既存のSharePointサイトページには**SharePoint**、あるいは既存のドキュメントライブラリには**Document Library**を選択します。</span><span class="sxs-lookup"><span data-stu-id="b992c-121">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="b992c-122">適切なページまたはドキュメントライブラリを選択してください。</span><span class="sxs-lookup"><span data-stu-id="b992c-122">Select the appropriate page or document library.</span></span>

<span data-ttu-id="b992c-123">各ユーザーについては、他のユーザー (1 対 1 または 1 対多数 ) とのプライベート チャットで共有したすべてのファイルは OneDrive フォルダーの **Microsoft Teams Chat Files** に格納されます。このフォルダーには、指定したユーザーのみにアクセスを制限する権限が自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b992c-123">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Microsoft Teams のチャットファイルという名前の OneDrive フォルダーの図](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="b992c-125">[チャネルファイル] タブ</span><span class="sxs-lookup"><span data-stu-id="b992c-125">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="b992c-126">Teams の [**ファイル**] タブは、SharePoint ドキュメントビューとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="b992c-126">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="b992c-127">[**ファイル**] タブでは、ユーザーは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="b992c-127">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="b992c-128">[**新しい**ファイル] メニューの [その他のオプション] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b992c-128">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="b992c-129">ファイルをローカルドライブに同期します。</span><span class="sxs-lookup"><span data-stu-id="b992c-129">Sync files to their local drive.</span></span>
- <span data-ttu-id="b992c-130">[**すべてのドキュメント**] メニューで、**リスト**ビューから [**コンパクト] リスト**を [**タイル**] ビューに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="b992c-130">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="b992c-131">注意が必要なファイルまたはマルウェアがあるファイルを特定します。</span><span class="sxs-lookup"><span data-stu-id="b992c-131">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="b992c-132">ファイルが読み取り専用であるかチェックアウトされているかをすぐに確認します。</span><span class="sxs-lookup"><span data-stu-id="b992c-132">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="b992c-133">ファイルのチェックアウトとチェックインを行います。</span><span class="sxs-lookup"><span data-stu-id="b992c-133">Check out and check in files.</span></span>
- <span data-ttu-id="b992c-134">ファイルの並べ替え、ピン留めの解除、並べ替え順序の変更を行う。</span><span class="sxs-lookup"><span data-stu-id="b992c-134">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="b992c-135">メタデータが必要なファイルを特定する</span><span class="sxs-lookup"><span data-stu-id="b992c-135">Identify which files need metadata</span></span>
- <span data-ttu-id="b992c-136">さらに多くのフィルターオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b992c-136">Choose from many more filter options.</span></span>
- <span data-ttu-id="b992c-137">列見出しに基づいてファイルをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="b992c-137">Group files based on column headings.</span></span>
- <span data-ttu-id="b992c-138">列の設定を変更する (左または右に移動、非表示)、列幅を変更します。</span><span class="sxs-lookup"><span data-stu-id="b992c-138">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="b992c-139">既定のリンクの種類の設定</span><span class="sxs-lookup"><span data-stu-id="b992c-139">Default link type setting</span></span>

<span data-ttu-id="b992c-140">SharePoint と OneDrive には、ファイルに対して作成されるリンクの既定のリンクの種類を指定する管理者設定があります。</span><span class="sxs-lookup"><span data-stu-id="b992c-140">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="b992c-141">チームでは、管理者が SharePoint と OneDrive 用に設定した設定を再利用することにより、同じ方法を採用しています。</span><span class="sxs-lookup"><span data-stu-id="b992c-141">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="b992c-142">この方法について詳しくは[、「ユーザーが共有のリンクを取得するときの既定のリンクの種類を変更する](https://docs.microsoft.com/sharepoint/change-default-sharing-link)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b992c-142">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="b992c-143">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b992c-143">More information</span></span>

<span data-ttu-id="b992c-144">SharePointがTeams とどのように連携するかの詳細については、[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b992c-144">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="b992c-145">Teams でのゲストのエクスペリエンス詳細については、[What the guest experience is like](guest-experience.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b992c-145">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

