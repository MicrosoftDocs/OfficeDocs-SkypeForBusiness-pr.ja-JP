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
description: グループとグループの会話Microsoft 365の違いTeamsグループの名前付けポリシーを& Teamsする方法など、Teams グループの計画について説明します。
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
<a name="plan-for-microsoft-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="caf2c-103">チームを作成Microsoft 365グループの計画を立Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="caf2c-103">Plan for Microsoft 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="caf2c-104">Microsoft 365 グループの使用を検討する場合、またはチームを作成するときに、チームが使用される目的、アクセス権を持つユーザー、チームが達成すると予想される結果を検討します。</span><span class="sxs-lookup"><span data-stu-id="caf2c-104">When considering the use of Microsoft 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="caf2c-105">コンテンツが細すぎる (チャンネル数が多すぎる) コンテンツによってユーザーがすぐにオーバーランする可能性がある場合は、作成するチャネルの数に特に注意してください。</span><span class="sxs-lookup"><span data-stu-id="caf2c-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="caf2c-106">グループグループの計画とグループへの影響 (またはグループによる) の計画に関するMicrosoft 365を保証する 2 つのシナリオMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="caf2c-106">There are two scenarios that warrant some discussion around planning of Microsoft 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="caf2c-107">最初に、お客様はグループに既存の投資を行う可能性があります。現在、パブリック グループとプライベート グループの両方がサポートされています。現在サポートされているメンバーの数については、Microsoft Teams の制限と仕様に関するページ[を参照してください](./limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="caf2c-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups, for the number of members currently supported, please see [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span> <span data-ttu-id="caf2c-108">前述のように、管理センターではなく、Teams クライアントを使用してチームへのユーザーのメンバーシップMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="caf2c-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Microsoft 365 admin center.</span></span> <span data-ttu-id="caf2c-109">このシナリオを考えると、ユーザーが Microsoft 365 グループでスレッド化された会話に慣れる場合、グループの会話は基本的に電子メールであり、Teams チャネルのチャット メッセージとは異なっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="caf2c-109">Given this scenario, if people are used to threaded conversations in Microsoft 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="caf2c-110">この違いについてユーザーを教育し、Teams または OWA を使用してグループにメールを送信するよりも柔軟なチャット メッセージ形式を採用Outlook提案します。</span><span class="sxs-lookup"><span data-stu-id="caf2c-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="caf2c-111">2 つ目は、Microsoft 365 で定義されている既存のグループをお持ちではないお客様の場合は、Microsoft 365 管理センター、Teams Web、またはデスクトップ クライアントを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="caf2c-111">Second, for customers who don't have existing Groups defined in Microsoft 365, you can either create them using the Microsoft 365 admin center, the Teams web, or desktop clients.</span></span> <span data-ttu-id="caf2c-112">前述のように、新しいクライアントを使用して、Microsoft 365グループへの今後のすべてのメンバーシップTeamsします。</span><span class="sxs-lookup"><span data-stu-id="caf2c-112">As mentioned previously, manage all future membership to the Microsoft 365 group using the Teams client.</span></span> <span data-ttu-id="caf2c-113">チームのメンバーシップはグループへのメンバーシップも定義Microsoft 365、この変更に備える必要があります。</span><span class="sxs-lookup"><span data-stu-id="caf2c-113">Since membership to a team is also defining membership to Microsoft 365 Groups, you should prepare people for this change.</span></span>

## <a name="teams-respects-microsoft-365-groups-naming-policy"></a><span data-ttu-id="caf2c-114">Teamsグループの名前付Microsoft 365ポリシーに関する問題</span><span class="sxs-lookup"><span data-stu-id="caf2c-114">Teams respects Microsoft 365 Groups naming policy</span></span>

<span data-ttu-id="caf2c-115">管理者Microsoft 365設定されているグループグループの名前付けポリシーは、ユーザーがチーム名を作成または編集Teamsに適用されます。</span><span class="sxs-lookup"><span data-stu-id="caf2c-115">Any Microsoft 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="caf2c-116">これには必須のプレフィックスやサフィックス、禁止された単語の除外などの事項が含まれます。</span><span class="sxs-lookup"><span data-stu-id="caf2c-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

<span data-ttu-id="caf2c-117">詳細については、Microsoft 365 グループの名前付け[ポリシーに関する記事をTeams。](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)</span><span class="sxs-lookup"><span data-stu-id="caf2c-117">To learn more, read [Microsoft 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="caf2c-118">次の記事は、グループグループの準備と導入のコンテンツを見つけるのMicrosoft 365です。</span><span class="sxs-lookup"><span data-stu-id="caf2c-118">The following articles are a good place to find readiness and adoption content for your Microsoft 365 Groups:</span></span>

-   [<span data-ttu-id="caf2c-119">Get more with groups in Outlook (Outlook でグループを活用する)</span><span class="sxs-lookup"><span data-stu-id="caf2c-119">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="caf2c-120">管理者センターを使用してMicrosoft 365グループのメンバーをMicrosoft 365削除する</span><span class="sxs-lookup"><span data-stu-id="caf2c-120">Add or remove members from Microsoft 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="caf2c-121">削除されたグループを復元する</span><span class="sxs-lookup"><span data-stu-id="caf2c-121">Restore a deleted group</span></span>](/microsoft-365/admin/create-groups/restore-deleted-group)
