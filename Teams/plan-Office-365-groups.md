---
title: チームを作成するときの Microsoft 365 グループの計画
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Teams での Microsoft 365 グループの計画について、グループと Teams の会話の違い&、Teams がグループの名前付けポリシーを尊重する方法などについて説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 7e93b66f9a7a0abc4dfc2e3484818da28a65f36a
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030047"
---
<a name="plan-for-microsoft-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="0c0af-103">Microsoft Teams でチームを作成するときに Microsoft 365 グループを計画する</span><span class="sxs-lookup"><span data-stu-id="0c0af-103">Plan for Microsoft 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="0c0af-104">Microsoft 365 グループの使用を検討する場合、またはチームを作成する場合は、チームの使用目的、アクセス権を持つユーザー、およびチームが達成すると予想される結果を検討します。</span><span class="sxs-lookup"><span data-stu-id="0c0af-104">When considering the use of Microsoft 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="0c0af-105">コンテンツの拡散が薄すぎる (チャネル数が多すぎる) ほど、ユーザーがすぐにオーバーランする可能性がある場合は、作成するチャネルの数に特に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0c0af-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="0c0af-106">Microsoft 365 グループの計画と Microsoft Teams への影響 (または Microsoft Teams による) に関する議論を保証する 2 つのシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="0c0af-106">There are two scenarios that warrant some discussion around planning of Microsoft 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="0c0af-107">最初に、お客様はグループに既存の投資を行う可能性があります。現在、パブリック グループとプライベート グループの両方をサポートしています。現在サポートされているメンバーの数については [、「Microsoft Teams](./limits-specifications-teams.md)の制限と仕様」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0c0af-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups, for the number of members currently supported, please see [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span> <span data-ttu-id="0c0af-108">前述のように、Microsoft 365 管理センターではなく、Teams クライアントを使用してチームに対するユーザーのメンバーシップを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c0af-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Microsoft 365 admin center.</span></span> <span data-ttu-id="0c0af-109">このシナリオを考えると、ユーザーが Microsoft 365 グループでスレッド化された会話に慣れる場合、グループ会話は基本的にメールであり、Teams チャネルのチャット メッセージと同じではない点に気を付け価値があります。</span><span class="sxs-lookup"><span data-stu-id="0c0af-109">Given this scenario, if people are used to threaded conversations in Microsoft 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="0c0af-110">この違いについてユーザーに教育し、Outlook または OWA を使用してグループにメールを送信するよりも、Teams でより柔軟なチャット メッセージ形式を採用する方法を提案します。</span><span class="sxs-lookup"><span data-stu-id="0c0af-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="0c0af-111">次に、Microsoft 365 で定義されている既存のグループをお持ちではないお客様は、Microsoft 365 管理センター、Teams Web、またはデスクトップ クライアントを使用してグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0c0af-111">Second, for customers who don't have existing Groups defined in Microsoft 365, you can either create them using the Microsoft 365 admin center, the Teams web, or desktop clients.</span></span> <span data-ttu-id="0c0af-112">前述のように、Teams クライアントを使用して、Microsoft 365 グループへの今後のすべてのメンバーシップを管理します。</span><span class="sxs-lookup"><span data-stu-id="0c0af-112">As mentioned previously, manage all future membership to the Microsoft 365 group using the Teams client.</span></span> <span data-ttu-id="0c0af-113">チームのメンバーシップも Microsoft 365 グループのメンバーシップを定義していますので、この変更に備える必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c0af-113">Since membership to a team is also defining membership to Microsoft 365 Groups, you should prepare people for this change.</span></span>

## <a name="teams-respects-microsoft-365-groups-naming-policy"></a><span data-ttu-id="0c0af-114">Teams は、Microsoft 365 グループの名前付けポリシーを尊重します。</span><span class="sxs-lookup"><span data-stu-id="0c0af-114">Teams respects Microsoft 365 Groups naming policy</span></span>

<span data-ttu-id="0c0af-115">管理者が設定した Microsoft 365 グループの名前付けポリシーは、ユーザーがチーム名を作成または編集するときに Teams に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0c0af-115">Any Microsoft 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="0c0af-116">これには必須のプレフィックスやサフィックス、禁止された単語の除外などの事項が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0c0af-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

<span data-ttu-id="0c0af-117">詳細については、「Teams での [Microsoft 365 グループの名前付けポリシー」を参照してください](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="0c0af-117">To learn more, read [Microsoft 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="0c0af-118">次の記事は、Microsoft 365 グループの準備と導入のコンテンツを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0c0af-118">The following articles are a good place to find readiness and adoption content for your Microsoft 365 Groups:</span></span>

-   [<span data-ttu-id="0c0af-119">Get more with groups in Outlook (Outlook でグループを活用する)</span><span class="sxs-lookup"><span data-stu-id="0c0af-119">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="0c0af-120">Microsoft 365 管理センターを使用して、Microsoft 365 グループのメンバーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="0c0af-120">Add or remove members from Microsoft 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="0c0af-121">削除されたグループを復元する</span><span class="sxs-lookup"><span data-stu-id="0c0af-121">Restore a deleted group</span></span>](/microsoft-365/admin/create-groups/restore-deleted-group)
