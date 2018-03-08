---
title: "Microsoft チームの SharePoint Online と OneDrive for Business の対話方法"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "SharePoint Online と OneDrive for Business のファイルが保存されている場合、個人のチャットなどの Microsoft チームとの間の関係チーム、チャネル、およびドキュメント ライブラリでの操作について説明します。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: b7d9ffad23c8f26d7d95c3f31df4ff0307517179
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="9e998-103">Microsoft チームの SharePoint Online と OneDrive for Business の対話方法</span><span class="sxs-lookup"><span data-stu-id="9e998-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>
=============================================================================

<span data-ttu-id="9e998-p101">Microsoft チームの各チームが、SharePoint Online でチーム サイトと、チーム内の各チャンネルが既定のチーム サイト ドキュメント ライブラリ内のフォルダーを取得します。スレッド内で共有されているファイルは、ドキュメント ライブラリに自動的に追加し、[アクセス許可とファイルのセキュリティ オプションではチーム内で自動的に反映します。</span><span class="sxs-lookup"><span data-stu-id="9e998-p101">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="9e998-106">非公開チャット ファイルは**送信者**の OneDrive for Business のフォルダーに保存し、権限が自動的に与えられているすべての参加者にプロセスを共有するファイルの一部としてします。</span><span class="sxs-lookup"><span data-stu-id="9e998-106">Private chat files are stored in the **sender’s** OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="9e998-p102">SharePoint Online のテナントで有効化をお持ちでない場合は、Microsoft チームのユーザーは、チーム内のファイルを共有できません。秘密チャット内のユーザーもファイルを共有できないため、OneDrive for Business (これは SharePoint ライセンスに関連します) がその機能に必要なします。</span><span class="sxs-lookup"><span data-stu-id="9e998-p102">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams’ users can't share files in teams. Users in private chat also can't share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="9e998-109">ファイルを保存すると、SharePoint Online ドキュメント ライブラリと OneDrive for Business で、テナント レベルで構成されているすべての法令遵守のルールに行われます。</span><span class="sxs-lookup"><span data-stu-id="9e998-109">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span>

<span data-ttu-id="9e998-110">次に、チーム、チャネル、およびドキュメント ライブラリの間のリレーションシップの例を示します。</span><span class="sxs-lookup"><span data-stu-id="9e998-110">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="9e998-p103">すべてのチームの SharePoint サイトが作成され、[*共有ドキュメント*] フォルダーがチーム用に作成された既定のフォルダー。**全般**チャンネル、チームごとに既定のチャンネルを含め、各チャネルでは、[*共有ドキュメント*] フォルダーをフォルダーがあります。</span><span class="sxs-lookup"><span data-stu-id="9e998-p103">For every team, a SharePoint site is created, and the *Shared Documents* folder is the default folder created for the team. Each channel, including the **General** channel, the default channel for each team, has a folder under the *Shared Documents* folder.</span></span>

![共有ドキュメントをチームと Microsoft チームでそのチャンネルの設定で SharePoint Online フォルダーの図。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="9e998-114">すべてのユーザーの OneDrive フォルダー *Microsoft チーム チャット ファイル*を使用して、内で共有される秘密チャット (1:1 または 1 対多) は、他のユーザーと、意図したユーザーにのみアクセスの制限が自動的に構成されているアクセス許可を持つすべてのファイルを格納します。</span><span class="sxs-lookup"><span data-stu-id="9e998-114">For every user, the OneDrive folder *Microsoft Teams Chat Files* is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![OneDrive フォルダーの図では、Microsoft チーム チャット ファイルの各ユーザーのチャットという名前です。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
