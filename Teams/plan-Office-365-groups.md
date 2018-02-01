---
title: "Microsoft Teams でチームを作成するときの Office 365 グループの計画"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "パブリックまたはプライベート グループの選択、Teams クライアントと Office 365 管理 Web コンソールのどちらを使用するかの選択、会話の使用に関するチームの指導方法といった Office 365 グループの計画について説明します。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 330cb6e8eb572fc2fb4141a2cea8a0ad6055d309
ms.sourcegitcommit: 9861cc3eca070ef1c6b7375896ae1978a438c772
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2018
---
<a name="plan-for-office-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="be0f2-103">Microsoft Teams でチームを作成するときの Office 365 グループの計画</span><span class="sxs-lookup"><span data-stu-id="be0f2-103">Plan for Office 365 groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="be0f2-p101">Office 365 グループを使用する場合やチームを作成する場合は、チームの使用目的、アクセス権を与えるユーザー、チームに期待する成果を考慮します。チャネル数に応じてコンテンツが分散し、その内容が乏しくなる場合があるため、作成するチャネルの数には特別な注意を払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="be0f2-p101">When considering the use of Office 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve. Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="be0f2-106">Office 365 グループの計画と Microsoft Teams による影響 (または Microsoft Teams に対する影響) に関するディスカッションは次の 2 つのシナリオに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="be0f2-106">There are two scenarios that warrant some discussion around planning of Office 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="be0f2-p102">最初のシナリオは、カスタマーがグループへの時間や労力の投資を積み重ねており、現時点で 2500 人未満のメンバーを含むパブリックとプライベートの両方のグループがサポートされている場合です。既に説明したとおり、チームへのメンバーシップの管理は、Office 365 管理 Web コンソールではなく Teams クライアントを使用して行います。このシナリオにおいて、ユーザーが Office 365 グループのスレッド付きの会話に使い慣れている場合、グループ会話は本質的にはメールであり、チームのチャネルで使用できるチャット メッセージと同じではないことに注意を促すことが重要です。この違いをユーザーに伝え、Outlook または OWA を使ってグループにメールを送信する方法ではなく、Teams の柔軟なチャット メッセージ形式を導入するように提案します。</span><span class="sxs-lookup"><span data-stu-id="be0f2-p102">First, since customers could have existing investments in Groups, we currently support both Public and Private groups of less than 2500 members. As mentioned previously, you want to manage the membership of people to a Team using the Teams client rather than the Office 365 admin web console. Given this scenario, if people are used to threaded conversations in Office 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Team channel. Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="be0f2-p103">2 番目のシナリオは、Office 365 で定義した既存のグループを持たないカスタマが存在する場合です。この場合は、Office 365 管理ポータル、Teams の Web またはデスクトップ クライアントを使用してグループを作成できます。既に説明したとおり、Office 365 グループへの今後のメンバーシップはすべて Teams クライアントを使用して管理します。チームへのメンバーシップによって Office 365 グループへのメンバーシップも定義されるため、この変更点についてユーザーに注意を促す必要があります。</span><span class="sxs-lookup"><span data-stu-id="be0f2-p103">Second, for customers who don’t have existing Groups defined in Office 365, you can either create them using the Office 365 admin portal, the Teams web, or desktop clients. As mentioned previously, manage all future membership to the Office 365 Group using the Teams client. Since membership to a Team is also defining membership to Office 365 Groups, you should prepare people for this change.</span></span>
 


## <a name="teams-respects-office-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="be0f2-114">Teams で順守される Office 365 グループの名前付けポリシー (プライベート プレビューの場合)</span><span class="sxs-lookup"><span data-stu-id="be0f2-114">Teams respects Office 365 Groups naming policy</span></span>
<span data-ttu-id="be0f2-115">管理者によって設定されたすべての Office 365 グループの名前付けポリシーは、ユーザーがチーム名を作成または編集するときに Teams において適用されます。</span><span class="sxs-lookup"><span data-stu-id="be0f2-115">Any Office 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="be0f2-116">これには必須のプレフィックスやサフィックス、禁止された単語の除外などの事項が含まれます。</span><span class="sxs-lookup"><span data-stu-id="be0f2-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="be0f2-117">この機能はプライベート プレビューとして提供されるため、ユーザーがこのプレビューに参加していない場合は、Teams で Office 365 グループの名前付けポリシーを順守することにはなりません。</span><span class="sxs-lookup"><span data-stu-id="be0f2-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Office 365 Groups naming policy.</span></span>

<span data-ttu-id="be0f2-118">詳しくは、「[Office 365 グループの名前付けポリシー](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="be0f2-118">To learn more, read [Office 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="be0f2-119">次の記事には、Office 365 グループの準備と導入に関する情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="be0f2-119">The following articles are a good place to find readiness & adoption content for your Office 365 Groups:</span></span>

-   [<span data-ttu-id="be0f2-120">Get more with groups in Outlook (Outlook でグループを活用する)</span><span class="sxs-lookup"><span data-stu-id="be0f2-120">Get more with groups in Outlook</span></span>](https://support.office.com/en-us/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

<!-- -->

-   [<span data-ttu-id="be0f2-121">グループ メンバーシップを Office 365 管理センターから管理する</span><span class="sxs-lookup"><span data-stu-id="be0f2-121">Manage Group membership in the Office 365 admin center</span></span>](https://support.office.com/en-us/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)
