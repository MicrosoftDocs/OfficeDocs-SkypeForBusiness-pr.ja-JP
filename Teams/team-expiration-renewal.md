---
title: Microsoft Teams でのチームの期限切れと更新
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: チームの有効期限と更新について説明し、Microsoft 365 グループの有効期限ポリシーを使用して、Microsoft Teams で使用されていないチームを自動的にクリーンアップする方法について説明します。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 697e36085169e0666e6a821a66c763be39cf9425
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868524"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="7d9d8-103">Microsoft Teams でのチームの期限切れと更新</span><span class="sxs-lookup"><span data-stu-id="7d9d8-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="7d9d8-104">多くのチームがいる組織には、実際には使用されない teams が多いことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="7d9d8-105">これは、製品の実験、短期的なチームのコラボレーション、または組織を離れるチーム所有者など、いくつかの理由で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="7d9d8-106">時間の経過と共に、チームはテナントリソースを蓄積して、負担を作ることができます。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="7d9d8-107">使用されていないチームの数を管理者として指定するには、 [Microsoft 365 グループの有効期限ポリシー](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)を使って、使用していないチームを自動的にクリーンアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 group expiration policy](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="7d9d8-108">Teams はグループによってサポートされているため、グループの有効期限ポリシーはチームにも自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="7d9d8-109">チームに有効期限ポリシーを適用すると、チームの所有者は、チームの有効期限の30日、15日間、1日前にチームの更新の通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="7d9d8-110">チーム所有者は通知を受信したときに、チームの設定で [**今すぐ更新**] をクリックして、チームを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="7d9d8-111">![チーム設定でチームを更新するための [今すぐ更新] ボタンのスクリーンショット](media/team-expiration.png "チーム設定でチームを更新するための [今すぐ更新] ボタンのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="7d9d8-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="7d9d8-112">チーム所有者がチームを更新しない場合は、チームは "ソフト削除" 状態になります。つまり、この状態は、次の30日以内に復元できます。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-112">If the team owner doesn't renew the team, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="7d9d8-113">チームの自動更新</span><span class="sxs-lookup"><span data-stu-id="7d9d8-113">Team auto-renewal</span></span>

<span data-ttu-id="7d9d8-114">更新が期限切れになった場合に、チーム所有者がチームの更新を忘れてしまった可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="7d9d8-115">これらのシナリオでは、チームに適用される有効期限ポリシーが原因で、アクティブな使用中のチームが削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="7d9d8-116">誤って削除されるのを防ぐため、自動更新はグループの有効期限ポリシーのチームに対して自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="7d9d8-117">グループの有効期限ポリシーが設定されると、チーム所有者から手動での介入なしに、少なくとも1つのチームメンバーからのチャネルアクセスを持つすべてのチームが自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="7d9d8-118">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7d9d8-118">Known issues</span></span>

<span data-ttu-id="7d9d8-119">**チームの有効期限と、基になるグループが一致しない**</span><span class="sxs-lookup"><span data-stu-id="7d9d8-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="7d9d8-120">チームを更新する前に、チームをバックアップするグループが最初に更新されます。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="7d9d8-121">更新の一部として、グループに新しい有効期限が設定され、将来の日付になります。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="7d9d8-122">この新しい日付は、Teams にすぐに表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="7d9d8-123">同期には最大24時間かかることがあります。チームとその基になるグループの有効期限の間に不一致がある場合は、24時間待ってからさらにサポートを求めます。</span><span class="sxs-lookup"><span data-stu-id="7d9d8-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>
