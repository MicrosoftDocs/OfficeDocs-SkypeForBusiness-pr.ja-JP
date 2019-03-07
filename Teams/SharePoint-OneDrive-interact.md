---
title: Microsoft Teams との SharePoint Online と OneDrive for Business の連携
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: プライベート チャット ファイルの格納方法、チーム、チャネル、ドキュメント ライブラリの関係など、Microsoft Teams との SharePoint Online および OneDrive for Business の連携について説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1d9bb769c1ad99f0990192ed0bdad69af71dd8c5
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460277"
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="9ce4c-103">Microsoft Teams との SharePoint Online と OneDrive for Business の連携</span><span class="sxs-lookup"><span data-stu-id="9ce4c-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>
=============================================================================

> [!Tip]
> <span data-ttu-id="9ce4c-104">チームが Azure Active Directory (AAD)、Office 365 のグループ、Exchange、SharePoint およびビジネスのための OneDrive とどのように対話する方法については、次のセッションを監視する:[マイクロソフトのチームの基礎](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="9ce4c-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="9ce4c-p101">Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-p101">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="9ce4c-107">プライベート チャット ファイルは送信者の OneDrive for Business フォルダーに格納され、権限はファイル共有プロセスの一環としてすべての参加者に付与されます。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-107">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="9ce4c-108">ユーザーは、割り当てられているし、SharePoint Online のライセンスでは有効になっていない、Office 365 でのビジネス ・ ストレージの OneDrive はありません。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-108">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="9ce4c-109">ファイルの共有は、チャネルで作業する続行されますが、ユーザーが Office 365 でのビジネス ・ ストレージの OneDrive にチャットでファイルを共有できません。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-109">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="9ce4c-110">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-110">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="9ce4c-111">この時点でマイクロソフトのチームは、Sharepoint の設置型との統合がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-111">Integration with Sharepoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="9ce4c-112">チーム、チャネル、ドキュメント ライブラリの関係の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-112">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="9ce4c-p103">各チームには SharePoint サイトが作成されます。**共有ドキュメント** フォルダーは、そのチーム用に作成される既定のフォルダーです。各チャネル (各チームの既定のチャネルである**全般**チャネルを含む) には**共有ドキュメント**内にフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-p103">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team. Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Microsoft Teams のチームとそのチャネルに対応する SharePoint Online の共有ドキュメント フォルダーを示す図。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="9ce4c-116">既定の SharePoint サイトとドキュメント ライブラリを別のもので置き換えることは現時点ではできません。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-116">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="9ce4c-117">この機能が必要であるという要望をいただきましたので、現在検討中です。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-117">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="9ce4c-118">[Teams ロードマップ](https://aka.ms/teamsroadmap)または [Teams UserVoice](https://aka.ms/TeamsUserVoice) をチェックして、今後利用できるようになる機能について継続的に把握します。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-118">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="9ce4c-119">タブを既存の SharePoint サイト ページに、または、既存の SharePoint ドキュメント ライブラリへのリンクをチームに追加するのには</span><span class="sxs-lookup"><span data-stu-id="9ce4c-119">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="9ce4c-120">タブの横にあるプラス記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-120">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="9ce4c-121">既存の SharePoint サイト ページの**SharePoint**または既存のドキュメント ライブラリの**ドキュメント ライブラリ**のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-121">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="9ce4c-122">適切なページまたはドキュメント ライブラリを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-122">Select the appropriate page or document library.</span></span>

<span data-ttu-id="9ce4c-123">各ユーザーについては、他のユーザー (1 対 1 または 1 対多数 ) とのプライベート チャットで共有したすべてのファイルは OneDrive フォルダーの **Microsoft Teams Chat Files** に格納されます。このフォルダーには、指定したユーザーのみにアクセスを制限する権限が自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-123">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![各ユーザーのチャットに対応する、Microsoft Teams Chat Files という名前が付けられた OneDrive フォルダーの図。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<a name="more-information"></a><span data-ttu-id="9ce4c-125">詳細情報</span><span class="sxs-lookup"><span data-stu-id="9ce4c-125">More information</span></span>
----------------

<span data-ttu-id="9ce4c-126">チームの SharePoint の機能の詳細についてを参照してください[SharePoint およびチーム: 相乗効果](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。</span><span class="sxs-lookup"><span data-stu-id="9ce4c-126">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>


