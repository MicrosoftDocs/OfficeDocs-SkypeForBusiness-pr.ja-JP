---
title: データSharePoint操作OneDrive方法Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDriveと対話Teams。プライベート チャット ファイル ストレージ&、標準チャネル、およびドキュメント ライブラリ&操作できます。
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 21abc840ddc740d7d842767c6c864d8ff5b598dd
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855956"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a><span data-ttu-id="bc984-103">データSharePoint操作OneDrive方法Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc984-103">How SharePoint and OneDrive interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="bc984-104">Azure Active Directory (A Microsoft 365 AD)、Azure Active Directory グループ、Exchange、Exchange、SharePoint、OneDrive: Microsoft Teams の基礎と対話する方法については、次のセッションをご[覧ください](https://aka.ms/teams-foundations)Microsoft Teams Teams</span><span class="sxs-lookup"><span data-stu-id="bc984-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="bc984-105">Microsoft Teams内の各チームは SharePoint にチーム サイトを持ち、チーム内の各標準チャネルは既定のチーム サイト ドキュメント ライブラリ内のフォルダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="bc984-105">Each team in Microsoft Teams has a team site in SharePoint, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="bc984-106">各[プライベート チャネルは](private-channels.md)、サイトごとに個別のSharePointされます。</span><span class="sxs-lookup"><span data-stu-id="bc984-106">Each [private channel](private-channels.md) gets its own, separate SharePoint site.</span></span>

<span data-ttu-id="bc984-107">会話内で共有されているファイルはドキュメント ライブラリに自動的に追加され、SharePoint で設定されているアクセス許可とファイルのセキュリティ オプションは、Teams 内に自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="bc984-107">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="bc984-108">SharePoint でサイト アドレスを変更した場合の影響の詳細については、「[サイト アドレスを変更する](/sharepoint/change-site-address)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc984-108">To see the impact of changing a site address in SharePoint, read [Change a site address](/sharepoint/change-site-address).</span></span>

<span data-ttu-id="bc984-109">プライベート チャット ファイルは送信者の OneDrive フォルダーに保存され、ファイル共有プロセスの一環としてすべての参加者にアクセス許可が自動的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="bc984-109">Private chat files are stored in the sender's OneDrive folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="bc984-110">ユーザーにライセンスが割り当SharePoint場合、ユーザーはユーザーにOneDriveストレージをMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="bc984-110">If users aren't assigned SharePoint licenses, they don't have OneDrive storage in Microsoft 365.</span></span> <span data-ttu-id="bc984-111">ファイル共有は標準チャネルで機能しますが、ユーザーはチャット内のストレージを使用せずにチャットOneDriveファイルを共有Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="bc984-111">File sharing works in standard channels, but users won't be able to share files in chats without OneDrive storage in Microsoft 365.</span></span>

<span data-ttu-id="bc984-112">ドキュメント ライブラリとドキュメント ライブラリにファイルSharePoint保存OneDrive、組織レベルで構成されたコンプライアンス規則はすべて従います。</span><span class="sxs-lookup"><span data-stu-id="bc984-112">By storing the files in the SharePoint document library and OneDrive, all compliance rules configured at the organization level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="bc984-113">SharePoint Server との統合は、Teams。</span><span class="sxs-lookup"><span data-stu-id="bc984-113">Integration with SharePoint Server is not supported for Teams.</span></span>

<span data-ttu-id="bc984-114">チーム、標準チャネル、ドキュメント ライブラリの関係の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bc984-114">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="bc984-115">すべてのチームに対して SharePoint サイトが作成され、**[共有ドキュメント]** フォルダーがチーム用の既定のフォルダーとして作成されます。</span><span class="sxs-lookup"><span data-stu-id="bc984-115">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="bc984-116">**一般** チャネルを含め各標準チャネル (各チームの既定のチャネル) には、**共有ドキュメント** にフォルダーがあります。</span><span class="sxs-lookup"><span data-stu-id="bc984-116">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![共有ドキュメント フォルダーの図 SharePoint。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="bc984-118">既定のSharePointとドキュメント ライブラリは、別のライブラリに置き換えできません。</span><span class="sxs-lookup"><span data-stu-id="bc984-118">The default SharePoint site and document library can't be replaced with a different one.</span></span>

<span data-ttu-id="bc984-119">各ユーザーについては、他のユーザー (1 対 1 または 1 対多数 ) とのプライベート チャットで共有したすべてのファイルは OneDrive フォルダーの **Microsoft Teams Chat Files** に格納されます。このフォルダーには、指定したユーザーのみにアクセスを制限する権限が自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="bc984-119">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Microsoft Teams Chat Files という名前が付けられた OneDrive フォルダーの図](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="bc984-121">パブリック チームの場合、SharePoint チーム サイトには 「外部ユーザー以外のすべてのユーザー」のアクセスが設定されている点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="bc984-121">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="bc984-122">チームのメンバーではないユーザーの場合、パブリック チームは Teams に表示されません。</span><span class="sxs-lookup"><span data-stu-id="bc984-122">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="bc984-123">ただし、SharePoint チーム サイトの URL を使用して SharePoint チーム サイト上のコンテンツにアクセスすることはできます。</span><span class="sxs-lookup"><span data-stu-id="bc984-123">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="bc984-124">チャネル ファイル タブ</span><span class="sxs-lookup"><span data-stu-id="bc984-124">Channel Files tab</span></span>

<span data-ttu-id="bc984-125">Teams の **[ファイル]** タブは、SharePoint ドキュメント ビューによく似ています。</span><span class="sxs-lookup"><span data-stu-id="bc984-125">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="bc984-126">**[ファイル]** タブでは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="bc984-126">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="bc984-127">**新規** ファイル メニューで追加オプションを確認する。</span><span class="sxs-lookup"><span data-stu-id="bc984-127">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="bc984-128">ファイルをローカル ドライブに同期する。</span><span class="sxs-lookup"><span data-stu-id="bc984-128">Sync files to their local drive.</span></span>
- <span data-ttu-id="bc984-129">**[すべてのドキュメント]** メニューで **[リスト]** ビューを **[コンパクト リスト]**、**[タイル]** ビューに切り替える。</span><span class="sxs-lookup"><span data-stu-id="bc984-129">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="bc984-130">注意が必要なファイル、またはマルウェアのあるファイルを特定する。</span><span class="sxs-lookup"><span data-stu-id="bc984-130">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="bc984-131">ファイルが読み取り専用かどうか、チェックアウト済みかどうかをすぐに確認する。</span><span class="sxs-lookup"><span data-stu-id="bc984-131">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="bc984-132">ファイルをチェックインおよびチェックアウトする。</span><span class="sxs-lookup"><span data-stu-id="bc984-132">Check out and check in files.</span></span>
- <span data-ttu-id="bc984-133">ファイルのピン留め、ピン留め解除、並べ替え順序の変更を行う。</span><span class="sxs-lookup"><span data-stu-id="bc984-133">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="bc984-134">メタデータが必要なファイルを特定する。</span><span class="sxs-lookup"><span data-stu-id="bc984-134">Identify which files need metadata</span></span>
- <span data-ttu-id="bc984-135">豊富なフィルター オプションの中から選択する。</span><span class="sxs-lookup"><span data-stu-id="bc984-135">Choose from many more filter options.</span></span>
- <span data-ttu-id="bc984-136">列見出しに基づいてファイルをグループ化する。</span><span class="sxs-lookup"><span data-stu-id="bc984-136">Group files based on column headings.</span></span>
- <span data-ttu-id="bc984-137">列の設定 (左または右へ移動、非表示) と列の幅を変更する。</span><span class="sxs-lookup"><span data-stu-id="bc984-137">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="bc984-138">既定のリンクの種類の設定</span><span class="sxs-lookup"><span data-stu-id="bc984-138">Default link type setting</span></span>

<span data-ttu-id="bc984-139">ユーザーがファイルを共有した場合に既定で表示される共有リンクの種類は、SharePointされます。</span><span class="sxs-lookup"><span data-stu-id="bc984-139">The type of sharing link shown by default when a user shared a file is set in the SharePoint admin center.</span></span> <span data-ttu-id="bc984-140">詳細については [、「ユーザーが共有用のリンクを取得するときに既定のリンクの種類を変更する」](/sharepoint/change-default-sharing-link) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc984-140">See [Change the default link type when users get links for sharing](/sharepoint/change-default-sharing-link) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bc984-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc984-141">Related topics</span></span>

<span data-ttu-id="bc984-142">[SharePointとTeams: より優れた一緒に](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。</span><span class="sxs-lookup"><span data-stu-id="bc984-142">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

[<span data-ttu-id="bc984-143">ゲストのエクスペリエンスについて</span><span class="sxs-lookup"><span data-stu-id="bc984-143">What the guest experience is like</span></span>](guest-experience.md)