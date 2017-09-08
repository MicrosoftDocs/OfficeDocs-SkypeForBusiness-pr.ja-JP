---
title: "Microsoft Teams との SharePoint Online と OneDrive for Business の連携 | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: overview
ms.prod: teams
description: "プライベート チャット ファイルの格納方法、チーム、チャネル、ドキュメント ライブラリの関係など、Microsoft Teams  との SharePoint Online と OneDrive for Business の連携について説明します。"
ms.openlocfilehash: e43bd32cb7f999ff5de60b711f04a9eb079cd17c
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2017
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="dae58-103">Microsoft Teams との SharePoint Online と OneDrive for Business の連携</span><span class="sxs-lookup"><span data-stu-id="dae58-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>
=============================================================================

<span data-ttu-id="dae58-p101">Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="dae58-p101">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="dae58-106">プライベート チャット ファイルは**送信者の** OneDrive for Business フォルダーに格納され、権限はファイル共有プロセスの一環としてすべての参加者に付与されます。</span><span class="sxs-lookup"><span data-stu-id="dae58-106">Private chat files are stored in the **sender’s** OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="dae58-p102">テナントで SharePoint Online を有効にしていない場合、Microsoft Teams のユーザーはチームでファイルを共有できないことがあります。プライベート チャットのユーザーも、OneDrive for Business (SharePoint ライセンスに関連付けられている) が SharePoint Online の機能を必要とするため、ファイルを共有できません。</span><span class="sxs-lookup"><span data-stu-id="dae58-p102">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams’ users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="dae58-109">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。</span><span class="sxs-lookup"><span data-stu-id="dae58-109">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span>

<span data-ttu-id="dae58-110">チーム、チャネル、ドキュメント ライブラリの関係の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dae58-110">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="dae58-p103">各チームには SharePoint サイトが作成されます。*共有ドキュメント* フォルダーは、そのチーム用に作成される既定のフォルダーです。各チャネル (各チームの既定のチャネルである**全般**チャネルを含む) には*共有ドキュメント* フォルダー内にフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dae58-p103">For every team, a SharePoint site is created, and the *Shared Documents* folder is the default folder created for the team. Each channel, including the **General** channel, the default channel for each team, has a folder under the *Shared Documents* folder.</span></span>

![](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="dae58-113">各ユーザーについては、他のユーザー (1 対 1 または 1 対多数 ) とのプライベート チャットで共有したすべてのファイルは OneDrive フォルダーの *Microsoft Teams Chat Files* に格納されます。このフォルダーには、指定したユーザーのみにアクセスを制限する権限が自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="dae58-113">For every user, the OneDrive folder *Microsoft Teams Chat Files* is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
