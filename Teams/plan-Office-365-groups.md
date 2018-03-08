---
title: "Microsoft のチームでチームを作成するときに、Office 365 グループを計画します。"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "チーム クライアントや、Office 365 管理 web コンソールについての会話を使用して、チームの教育方法を使用して、パブリックとプライベート グループを選択するなどの Office 365 グループを計画するときにする必要があります決定事項について説明します。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 330cb6e8eb572fc2fb4141a2cea8a0ad6055d309
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="plan-for-office-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="a3de8-103">Microsoft チームでチームを作成するときに Office 365 のグループの計画します。</span><span class="sxs-lookup"><span data-stu-id="a3de8-103">Plan for Office 365 groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="a3de8-p101">時または作成チームが、チームとチーム用に使用される、ユーザー アクセスを持っている必要があると、どのような結果を考えると Office 365 グループの使用を検討が達成するために期待しています。支払特別な注意ユーザーとして作成するチャネルの数は、(が多すぎるチャネル) の間でコンテンツ見開き薄すぎるですばやく超過になることができます。</span><span class="sxs-lookup"><span data-stu-id="a3de8-p101">When considering the use of Office 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve. Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="a3de8-106">Office 365 のグループおよび (または、) への影響 Microsoft チームの計画をいくつかのディスカッションを保証する 2 つのシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="a3de8-106">There are two scenarios that warrant some discussion around planning of Office 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="a3de8-p102">最初に、ため、お客様は、グループで、既存の投資を必要があるが、現在、サポートしてより小さい 2500 メンバーのグループをパブリックとプライベートの両方。前述のように、するユーザーを Office 365 管理者 web コンソールではなく、チームのクライアントを使用してチームのメンバーシップを管理します。スレッド化された Office 365 のグループ内の会話に連絡先を使用する場合はこのシナリオでは、指定されたがグループの会話にメールとしないと同じで、チームのチャンネルのチャット メッセージは、基本的ことに注意します。この違いについて、自分のユーザーを教育し、Outlook または OWA を使用してグループをメールではなくチームでより柔軟なチャット メッセージ形式を採用するチュートリアルをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3de8-p102">First, since customers could have existing investments in Groups, we currently support both Public and Private groups of less than 2500 members. As mentioned previously, you want to manage the membership of people to a Team using the Teams client rather than the Office 365 admin web console. Given this scenario, if people are used to threaded conversations in Office 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Team channel. Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="a3de8-p103">次に、Office 365 で定義されている既存のグループを持っていないお客様は、作成することも、Office 365 管理ポータルでは、チーム web またはデスクトップ クライアントを使用しています。前述のように、すべての将来チーム クライアントを使用して Office 365 のグループ メンバーシップを管理します。チーム メンバーが Office 365 グループへのメンバーシップが定義するもために、この変更に対してユーザーを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3de8-p103">Second, for customers who don’t have existing Groups defined in Office 365, you can either create them using the Office 365 admin portal, the Teams web, or desktop clients. As mentioned previously, manage all future membership to the Office 365 Group using the Teams client. Since membership to a Team is also defining membership to Office 365 Groups, you should prepare people for this change.</span></span>
 


## <a name="teams-respects-office-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="a3de8-114">チームは、Office 365 のグループがプライベートのプレビュー版) (のポリシーの名前を付けるを考慮しました。</span><span class="sxs-lookup"><span data-stu-id="a3de8-114">Teams respects Office 365 Groups naming policy (in private preview)</span></span>
<span data-ttu-id="a3de8-p104">ユーザーを作成またはチーム名を編集するときに、管理者によって設定されているポリシーの名前を付け、Office 365 グループをチームで適用されます。必須の略語のような項目が含まれますかサフィックスや除外単語を禁止します。</span><span class="sxs-lookup"><span data-stu-id="a3de8-p104">Any Office 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names. This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="a3de8-117">この機能は、プライベートのプレビューではない場合はこのプレビューの一部、チームがまだに従っているこの Office 365 のグループ ポリシーの名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="a3de8-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Office 365 Groups naming policy.</span></span>

<span data-ttu-id="a3de8-118">詳細については、 [Office 365 グループの名前付けでチームのポリシー](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)をお読みください。</span><span class="sxs-lookup"><span data-stu-id="a3de8-118">To learn more, read [Office 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="a3de8-119">次の記事は、Office 365 グループの準備状況と導入のコンテンツを検索することをおすすめです。</span><span class="sxs-lookup"><span data-stu-id="a3de8-119">The following articles are a good place to find readiness & adoption content for your Office 365 Groups:</span></span>

-   [<span data-ttu-id="a3de8-120">Outlook でグループの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="a3de8-120">Get more with groups in Outlook</span></span>](https://support.office.com/en-us/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

<!-- -->

-   [<span data-ttu-id="a3de8-121">Office 365 管理センターでグループ メンバーシップを管理します。</span><span class="sxs-lookup"><span data-stu-id="a3de8-121">Manage Group membership in the Office 365 admin center</span></span>](https://support.office.com/en-us/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)
