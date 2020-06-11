---
title: Exchange Online で許可された送信者ドメインとして Teams の SMTP ドメインを追加する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
f1.keywords:
- NOCSH
description: Exchange Online で許可された送信者ドメインとして Microsoft Teams SMTP ドメインを追加して、チームメンバーに通知を送信する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: b66b58cb14c5205b0ba4a6ff7e95102dc1584579
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689863"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="4d523-103">Microsoft Teams SMTP ドメインを承認済みの送信者ドメインとして Exchange Online に追加する</span><span class="sxs-lookup"><span data-stu-id="4d523-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="4d523-104">管理コンソールで Microsoft 365 グループを作成するか、Outlook を使用して作成したかにかかわらず、グループに追加されているチームメンバーの通知を Exchange Online で送信できます。</span><span class="sxs-lookup"><span data-stu-id="4d523-104">Whether you create a Microsoft 365 group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a group.</span></span> <span data-ttu-id="4d523-105">これらのメッセージは、既定のドメイン SMTP FQDN を表すため、テナントから生成されます。</span><span class="sxs-lookup"><span data-stu-id="4d523-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![グループに追加されたユーザーを示すメッセージヘッダーのスクリーンショット。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="4d523-107">チームは、Microsoft Exchange Online を使用して、チームメンバーが追加されたときに通知をチームメンバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="4d523-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they've been added.</span></span> <span data-ttu-id="4d523-108">SMTP メッセージのドメイン FQDN という違いは、商業用/ビジネス用 @GCC テナントの場合は @email "teams.microsoft.com"、行政テナントの場合は "email.teams.com"、スパムフィルターでキャッチされることがあります。</span><span class="sxs-lookup"><span data-stu-id="4d523-108">The difference being the domain FQDN of the SMTP message is "@email.teams.microsoft.com" for Commercial/Business tenants and "@GCC-email.teams.com" for Government tenants and could be caught by spam filtering.</span></span>

![グループに追加されたユーザーを示すメッセージヘッダーのスクリーンショット。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="4d523-110">最善の結果を得るために、Exchange Online スパム構成の "許可された送信者ドメイン" リストに Microsoft Teams の SMTP ドメインを追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4d523-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your "allowed sender domains" list in your Exchange Online spam configuration:</span></span>

![スパム構成設定の [許可リスト] セクションのスクリーンショット](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
