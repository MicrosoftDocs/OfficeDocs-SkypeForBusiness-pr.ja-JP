---
title: "Microsoft Teams との SharePoint Online と OneDrive for Business の連携 | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: "プライベート チャット ファイルの格納方法、チーム、チャネル、ドキュメント ライブラリの関係など、Microsoft Teams  との SharePoint Online と OneDrive for Business の連携について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: cc4d4f2bd367cce7b3d25d90fdf871e7f1d6982b
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Microsoft Teams との SharePoint Online と OneDrive for Business の連携
=============================================================================

Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。

プライベート チャット ファイルは**送信者の** OneDrive for Business フォルダーに格納され、権限はファイル共有プロセスの一環としてすべての参加者に付与されます。

テナントで SharePoint Online を有効にしていない場合、Microsoft Teams のユーザーはチームでファイルを共有できないことがあります。プライベート チャットのユーザーも、OneDrive for Business (SharePoint ライセンスに関連付けられている) が SharePoint Online の機能を必要とするため、ファイルを共有できません。

SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。

チーム、チャネル、ドキュメント ライブラリの関係の例を次に示します。

各チームには SharePoint サイトが作成されます。*共有ドキュメント* フォルダーは、そのチーム用に作成される既定のフォルダーです。各チャネル (各チームの既定のチャネルである**全般**チャネルを含む) には*共有ドキュメント* フォルダー内にフォルダーが作成されます。

![](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

各ユーザーについては、他のユーザー (1 対 1 または 1 対多数 ) とのプライベート チャットで共有したすべてのファイルは OneDrive フォルダーの *Microsoft Teams Chat Files* に格納されます。このフォルダーには、指定したユーザーのみにアクセスを制限する権限が自動的に設定されます。

![](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
