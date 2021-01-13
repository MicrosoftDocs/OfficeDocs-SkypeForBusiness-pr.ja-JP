---
title: Microsoft Teams でのチームの有効期限と更新
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: チームの有効期限と更新、および Microsoft 365 グループの有効期限ポリシーを使用して、Microsoft Teams で未使用のチームを自動的にクリーンアップする方法について説明します。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b111ddd6b874fef22a7d221f6eb932c4c14c7b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809407"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="0033d-103">Microsoft Teams でのチームの有効期限と更新</span><span class="sxs-lookup"><span data-stu-id="0033d-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="0033d-104">チームの数が多い組織は、実際には使用しないチームを持つ場合が多い。</span><span class="sxs-lookup"><span data-stu-id="0033d-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="0033d-105">これは、製品の実験、チームの短期間の共同作業、または組織を離れるチーム所有者など、いくつかの理由が原因で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0033d-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="0033d-106">時間が経過すると、このようなチームは蓄積し、テナント リソースに負担をかける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0033d-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="0033d-107">使用されていないチームの数を抑制するには、管理者として [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) グループの有効期限ポリシーを使用して、使用されていないチームを自動的にクリーンアップできます。</span><span class="sxs-lookup"><span data-stu-id="0033d-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 group expiration policy](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="0033d-108">チームはグループに基いので、グループの有効期限ポリシーはチームにも自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0033d-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="0033d-109">有効期限ポリシーをチームに適用すると、チームの所有者は、チームの有効期限の 30 日前、15 日前、1 日前にチーム更新の通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0033d-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="0033d-110">チームの所有者が通知を受け取った場合、チームの設定で [今すぐ更新] をクリックしてチームを更新できます。</span><span class="sxs-lookup"><span data-stu-id="0033d-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="0033d-111">![チーム設定でチームを更新する [今すぐ更新] ボタンのスクリーンショット](media/team-expiration.png "チーム設定でチームを更新する [今すぐ更新] ボタンのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="0033d-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="0033d-112">チームの所有者がチームを更新しない場合、有効期限ポリシーが終了するまでチームでそれ以上のアクティビティがない場合、チームは "回復可能な削除" 状態になります。つまり、30 日以内に復元できます。</span><span class="sxs-lookup"><span data-stu-id="0033d-112">If the team owner doesn't renew the team and there is no further activity on the team until the end of the expiration policy, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="0033d-113">チームの自動更新</span><span class="sxs-lookup"><span data-stu-id="0033d-113">Team auto-renewal</span></span>

<span data-ttu-id="0033d-114">更新を忘れたか、更新の期限が切れたため、チームの所有者がチームを更新できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0033d-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="0033d-115">これらのシナリオでは、アクティブに使用されているチームは、チームに適用される有効期限ポリシーのために削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0033d-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="0033d-116">誤って削除されないように、グループの有効期限ポリシー内のチームに対して自動更新が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="0033d-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="0033d-117">グループの有効期限ポリシーが設定されている場合、有効期限前にチーム メンバーから少なくとも 1 つのチャネル 訪問があるチームは、チーム所有者による手動による介入なしで自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="0033d-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="0033d-118">既知の問題</span><span class="sxs-lookup"><span data-stu-id="0033d-118">Known issues</span></span>

<span data-ttu-id="0033d-119">**チームと基になるグループの有効期限が一致しない**</span><span class="sxs-lookup"><span data-stu-id="0033d-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="0033d-120">チームを更新する前に、チームをバックアップするグループが最初に更新されます。</span><span class="sxs-lookup"><span data-stu-id="0033d-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="0033d-121">更新の一環として、グループに将来の日付の新しい有効期限が設定されます。</span><span class="sxs-lookup"><span data-stu-id="0033d-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="0033d-122">この新しい日付は、Teams ですぐには表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0033d-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="0033d-123">同期には最大 24 時間かかる場合があります。チームとその基になるグループの有効期限に不一致がある場合は、さらにサポートを受け取る前に 24 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="0033d-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>
