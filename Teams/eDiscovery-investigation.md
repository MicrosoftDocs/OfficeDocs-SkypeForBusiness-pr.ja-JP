---
title: Microsoft Teams のコンテンツに対して電子情報開示の調査を行う
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anach
search.appverid: MET150
description: 訴訟手続きのためにすべての電子保持情報を提出する必要がある場合など、電子情報開示を実施するために必要な手続きについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb3595bba2ae394f4a4c483ba2a447cd3ebbb857
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23867614"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Microsoft Teams のコンテンツに対して電子情報開示の調査を行う
============================

大規模な企業では、すべての電子保持情報 (ESI) の提出を求められる高額賠償を伴う訴訟の処理を行わなければならないことがあります。

すべてのチームの 1 対 1 のチャットまたはグループ チャットは、該当するユーザーのメールボックスにジャーナリングされ、すべてのチャネル メッセージはチームを代表するグループ メールボックスにジャーナリングされます。アップロードされたファイルに関しては、SharePoint Online および OneDrive for Business の電子情報開示の機能によって処理されます。

1.  マイクロソフトのチームのコンテンツを電子的証拠開示調査を実施するには、[この](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)リンクでは、手順 1 を参照してください。

2.  Microsoft Teams データは **IM または Conversations** として Excel 出力に表示されます。Outlook で **.PST** をマウントすることもできます。

    a.  チームの .PST をマウントする場合は、すべての会話が会話履歴のチーム チャット フォルダーに格納されることに注意してください。メッセージの件名はチームとチャネルによって整列されます。次の画像では、Manufacturing Specs チームの Project 7 チャネルに送信した Bob さんのメッセージを確認できます。![Outlook のユーザーのメールボックスにあるチーム チャット フォルダーのスクリーンショット。](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  ユーザーのメールボックスのプライベート チャットは、会話履歴のチーム チャット フォルダーにも格納されています。
