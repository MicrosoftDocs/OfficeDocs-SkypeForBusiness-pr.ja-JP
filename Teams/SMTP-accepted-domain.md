---
title: "Microsoft チーム SMTP ドメインを追加、承認済みドメインとして Exchange Online"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft チーム SMTP ドメインを追加承認済みドメインとして Exchange Online チーム メンバーに通知を送信する方法を学習します。"
ms.openlocfilehash: 70795d466059233f09bf1eeb61c9a977a311936e
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a><span data-ttu-id="938ef-103">Microsoft チーム SMTP ドメインを追加、承認済みドメインとして Exchange Online</span><span class="sxs-lookup"><span data-stu-id="938ef-103">Add the Microsoft Teams SMTP domain as an accepted domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="938ef-p101">管理コンソールでまたは Outlook を使って、Office 365 グループを作成するかどうか Exchange Online を使って、チームのメンバーをグループに追加される通知を送信します。SMTP FQDN の既定のドメインを表していると、テナントからこれらのメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="938ef-p101">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group. These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![グループにユーザーを示す例 Outlook メール メッセージ ヘッダーのスクリーン ショットが追加されました。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="938ef-p102">チームを使って Microsoft Exchange Online にも追加されたときに、チーム メンバーに通知を送信します。ドメインの FQDN SMTP メッセージの違いは、"@email.teams.microsoft.com"で迷惑メール フィルターによって検出される可能性があります。以下の画像からわかるように、Outlook の画像をブロックなどの標準的なセキュリティ機能や特定のコンテンツの対象となる外部の送信者としてこのメッセージと見なされます。</span><span class="sxs-lookup"><span data-stu-id="938ef-p102">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added. The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” and could be caught by spam filtering. As you can see from the image below, Outlook considers this message as an external sender which is subject to standard security features such as blocking images and certain content.</span></span>

![グループにユーザーを示す例 Outlook メール メッセージ ヘッダーのスクリーン ショットが追加されました。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="938ef-111">最良の結果とシームレスな操作は、Microsoft チーム SMTP ドメイン リストに追加する、"承認済みドメイン] で、Exchange Online の迷惑メールの構成を検討してください。</span><span class="sxs-lookup"><span data-stu-id="938ef-111">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “accepted domains” list in your Exchange Online spam configuration:</span></span>

![許可のスクリーン ショットは、Exchange Online の迷惑メールの設定] セクションを一覧表示します。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
