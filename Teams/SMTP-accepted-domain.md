---
title: "Microsoft Teams SMTP ドメインを承認済みドメインとして Exchange Online に追加する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams SMTP ドメインを承認済みドメインとして Exchange Online に追加し、チーム メンバーに通知を送信する方法を説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: c33cba163d3395be7214caf5df4e87eaa164e020
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2017
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a><span data-ttu-id="b31b4-103">Microsoft Teams SMTP ドメインを承認済みドメインとして Exchange Online に追加する</span><span class="sxs-lookup"><span data-stu-id="b31b4-103">Add the Microsoft Teams SMTP domain as an accepted domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="b31b4-p101">管理コンソールに Office 365 グループを作成するか、Outlook を使って Office 365 グループを作成するかに関わらず、グループに追加したチーム メンバーへの通知の送信には Exchange Online が使用されます。通知は、既定のドメイン SMTP FQDN であるテナントから生成されます。</span><span class="sxs-lookup"><span data-stu-id="b31b4-p101">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group. These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="b31b4-p102">Teams は追加済みのチーム メンバーに通知を送信するために Microsoft Exchange Online も使用します。SMTP メッセージのドメイン FQDN の場合は、「@email.teams.microsoft.com」という形式が使用され、この形式はスパム フィルタリングによって検出されます。次の画像が示すように、Outlook はこのメッセージを外部送信者として認識し、画像や特定のコンテンツの遮断といった標準的なセキュリティ機能を適用します。</span><span class="sxs-lookup"><span data-stu-id="b31b4-p102">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added. The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” and could be caught by spam filtering. As you can see from the image below, Outlook considers this message as an external sender which is subject to standard security features such as blocking images and certain content.</span></span>

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="b31b4-109">最良の結果と円滑な操作を実現するため、Microsoft Teams SMTP ドメインを Exchange Online スパム構成の「承認済みドメイン」リストに追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b31b4-109">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “accepted domains” list in your Exchange Online spam configuration:</span></span>

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
