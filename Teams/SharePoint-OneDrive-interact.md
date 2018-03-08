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
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Microsoft チームの SharePoint Online と OneDrive for Business の対話方法
=============================================================================

Microsoft チームの各チームが、SharePoint Online でチーム サイトと、チーム内の各チャンネルが既定のチーム サイト ドキュメント ライブラリ内のフォルダーを取得します。スレッド内で共有されているファイルは、ドキュメント ライブラリに自動的に追加し、[アクセス許可とファイルのセキュリティ オプションではチーム内で自動的に反映します。

非公開チャット ファイルは**送信者**の OneDrive for Business のフォルダーに保存し、権限が自動的に与えられているすべての参加者にプロセスを共有するファイルの一部としてします。

SharePoint Online のテナントで有効化をお持ちでない場合は、Microsoft チームのユーザーは、チーム内のファイルを共有できません。秘密チャット内のユーザーもファイルを共有できないため、OneDrive for Business (これは SharePoint ライセンスに関連します) がその機能に必要なします。

ファイルを保存すると、SharePoint Online ドキュメント ライブラリと OneDrive for Business で、テナント レベルで構成されているすべての法令遵守のルールに行われます。

次に、チーム、チャネル、およびドキュメント ライブラリの間のリレーションシップの例を示します。

すべてのチームの SharePoint サイトが作成され、[*共有ドキュメント*] フォルダーがチーム用に作成された既定のフォルダー。**全般**チャンネル、チームごとに既定のチャンネルを含め、各チャネルでは、[*共有ドキュメント*] フォルダーをフォルダーがあります。

![共有ドキュメントをチームと Microsoft チームでそのチャンネルの設定で SharePoint Online フォルダーの図。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

すべてのユーザーの OneDrive フォルダー *Microsoft チーム チャット ファイル*を使用して、内で共有される秘密チャット (1:1 または 1 対多) は、他のユーザーと、意図したユーザーにのみアクセスの制限が自動的に構成されているアクセス許可を持つすべてのファイルを格納します。

![OneDrive フォルダーの図では、Microsoft チーム チャット ファイルの各ユーザーのチャットという名前です。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
