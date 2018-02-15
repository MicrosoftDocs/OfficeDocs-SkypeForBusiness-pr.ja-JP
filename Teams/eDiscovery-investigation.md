---
title: "Microsoft Teams のコンテンツに対して電子情報開示の調査を行う"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: "訴訟手続きのためにすべての電子保持情報を提出する必要がある場合など、電子情報開示を実施するために必要な手続きについて説明します。"
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ee252bc114ec7972506b8fa6408fcaa33d20a73
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2018
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="d65d6-103">Microsoft Teams のコンテンツに対して電子情報開示の調査を行う</span><span class="sxs-lookup"><span data-stu-id="d65d6-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="d65d6-104">大規模な企業では、すべての電子保持情報 (ESI) の提出を求められる高額賠償を伴う訴訟の処理を行わなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d65d6-104">Large Enterprises are often exposed to high penalty legal proceedings which demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="d65d6-p101">すべてのチームの 1 対 1 のチャットまたはグループ チャットは、該当するユーザーのメールボックスにジャーナリングされ、すべてのチャネル メッセージはチームを代表するグループ メールボックスにジャーナリングされます。アップロードされたファイルに関しては、SharePoint Online および OneDrive for Business の電子情報開示の機能によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="d65d6-p101">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes and all channel messages are journaled through to the group mailbox representing the Team. Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="d65d6-107">Microsoft Teams コンテンツに対して電子情報開示の調査を行うには、[この](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da?ui=en-US&rs=en-US&ad=US#step1)リンクをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d65d6-107">To conduct an eDiscovery investigation with Microsoft Teams content, review [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da?ui=en-US&rs=en-US&ad=US#step1) link.</span></span>

2.  <span data-ttu-id="d65d6-108">Microsoft Teams データは **IM または Conversations** として Excel 出力に表示されます。Outlook で **.PST** をマウントすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d65d6-108">Microsoft Teams data will appear as **IM or Conversations** in the Excel output, or you can mount the **.PST** in Outlook.</span></span>

    <span data-ttu-id="d65d6-p102">a.  チームの .PST をマウントする場合は、すべての会話が会話履歴のチーム チャット フォルダーに格納されることに注意してください。メッセージの件名はチームとチャネルによって整列されます。次の画像では、Manufacturing Specs チームの Project 7 チャネルに送信した Bob さんのメッセージを確認できます。![Outlook のユーザーのメールボックスにあるチーム チャット フォルダーのスクリーンショット。](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="d65d6-p102">a.  When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History. The title of the message aligns to Team and Channel. From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team. ![Screenshot of a Team Chat folder in a user's mailbox in Outlook.](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)</span></span>

3.  <span data-ttu-id="d65d6-114">ユーザーのメールボックスのプライベート チャットは、会話履歴のチーム チャット フォルダーにも格納されています。</span><span class="sxs-lookup"><span data-stu-id="d65d6-114">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>
