---
title: Microsoft Teams でチームを作成するときの Office 365 グループの計画
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: パブリックグループとプライベートグループの選択などの Office 365 グループを計画するときに行う必要がある決定事項について説明します。チームクライアントまたは Office 365 管理 web コンソールを使用して、会話の使用についてチームを教育する方法について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 741ed07971d4db69e8cd05581082f0b041cc2ac7
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37567844"
---
<a name="plan-for-office-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="5828e-103">Microsoft Teams でチームを作成するときの Office 365 グループの計画</span><span class="sxs-lookup"><span data-stu-id="5828e-103">Plan for Office 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="5828e-p101">Office 365 グループを使用する場合やチームを作成する場合は、チームの使用目的、アクセス権を与えるユーザー、チームに期待する成果を考慮します。チャネル数に応じてコンテンツが分散し、その内容が乏しくなる場合があるため、作成するチャネルの数には特別な注意を払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5828e-p101">When considering the use of Office 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve. Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="5828e-106">Office 365 グループの計画と Microsoft Teams による影響 (または Microsoft Teams に対する影響) に関するディスカッションは次の 2 つのシナリオに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="5828e-106">There are two scenarios that warrant some discussion around planning of Office 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="5828e-107">最初に、顧客は既存の投資をグループに含めることができるため、現在、5000メンバーより小さいパブリックグループとプライベートグループの両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5828e-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups of less than 5000 members.</span></span> <span data-ttu-id="5828e-108">前に説明したように、Office 365 管理 web コンソールではなく、Teams クライアントを使用して、チームのメンバーのメンバーシップを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5828e-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Office 365 admin web console.</span></span> <span data-ttu-id="5828e-109">このシナリオでは、ユーザーが Office 365 グループでスレッド化された会話に使用している場合は、グループの会話が本質的にメールであり、チームチャネルのチャットメッセージと同じではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5828e-109">Given this scenario, if people are used to threaded conversations in Office 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="5828e-110">この違いについてユーザーを教育して、より柔軟なチャットメッセージ形式を Teams で採用し、Outlook または OWA を使ってグループをメールで送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5828e-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="5828e-111">次に、Office 365 で既存のグループが定義されていないユーザーの場合、Office 365 管理ポータル、Teams web、またはデスクトップクライアントを使用して作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5828e-111">Second, for customers who don’t have existing Groups defined in Office 365, you can either create them using the Office 365 admin portal, the Teams web, or desktop clients.</span></span> <span data-ttu-id="5828e-112">前に説明したように、Teams クライアントを使用して、今後の Office 365 グループへのすべてのメンバーシップを管理します。</span><span class="sxs-lookup"><span data-stu-id="5828e-112">As mentioned previously, manage all future membership to the Office 365 Group using the Teams client.</span></span> <span data-ttu-id="5828e-113">チームのメンバーシップも Office 365 グループへのメンバーシップを定義しているため、この変更についてユーザーを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5828e-113">Since membership to a team is also defining membership to Office 365 Groups, you should prepare people for this change.</span></span>
 


## <a name="teams-respects-office-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="5828e-114">Teams で順守される Office 365 グループの名前付けポリシー (プライベート プレビューの場合)</span><span class="sxs-lookup"><span data-stu-id="5828e-114">Teams respects Office 365 Groups naming policy (in private preview)</span></span>

<span data-ttu-id="5828e-115">管理者によって設定されたすべての Office 365 グループの名前付けポリシーは、ユーザーがチーム名を作成または編集するときに Teams において適用されます。</span><span class="sxs-lookup"><span data-stu-id="5828e-115">Any Office 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="5828e-116">これには必須のプレフィックスやサフィックス、禁止された単語の除外などの事項が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5828e-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="5828e-117">この機能はプライベート プレビューとして提供されるため、ユーザーがこのプレビューに参加していない場合は、Teams で Office 365 グループの名前付けポリシーを順守することにはなりません。</span><span class="sxs-lookup"><span data-stu-id="5828e-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Office 365 Groups naming policy.</span></span>

<span data-ttu-id="5828e-118">詳しくは、「[Office 365 グループの名前付けポリシー](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5828e-118">To learn more, read [Office 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="5828e-119">次の記事は、Office 365 グループの準備および導入のためのコンテンツを見つけるのに最適な場所です。</span><span class="sxs-lookup"><span data-stu-id="5828e-119">The following articles are a good place to find readiness and adoption content for your Office 365 Groups:</span></span>

-   [<span data-ttu-id="5828e-120">Get more with groups in Outlook (Outlook でグループを活用する)</span><span class="sxs-lookup"><span data-stu-id="5828e-120">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="5828e-121">Microsoft 365 管理センターを使用して、Office 365 グループのメンバーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="5828e-121">Add or remove members from Office 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="5828e-122">削除した Office 365 グループを復元する</span><span class="sxs-lookup"><span data-stu-id="5828e-122">Restore a deleted Office 365 Group</span></span>](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)
