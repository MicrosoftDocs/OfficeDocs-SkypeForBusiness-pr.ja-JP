---
title: コール パーク
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: 通話が保留されると、誰かが通話を発信するか、またはタイムアウトするまで、通話が保留中の一時的な電話番号に転送されます。保留中の通話で予約している内線番号の範囲をテーブルに構成する必要があります。 これらの内線番号は、仮想の内線番号 (つまり、ユーザーや電話が割り当てられていない内線番号) にする必要があります。 コールパークアプリケーションを実行する各プールには、1つ以上の拡張機能の範囲を指定できます。 これらの範囲は、展開全体でグローバルに一意である必要があります。
ms.openlocfilehash: d325b1dd2066bd35f6dc9003de4c026a7f925a72
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290137"
---
# <a name="call-park"></a><span data-ttu-id="a4208-106">コール パーク</span><span class="sxs-lookup"><span data-stu-id="a4208-106">Call Park</span></span>

<span data-ttu-id="a4208-107">通話が保留されると、誰かが通話を発信するか、またはタイムアウトするまで、通話が保留中の一時的な電話番号に転送されます。保留中の通話で予約している内線番号の範囲をテーブルに構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4208-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="a4208-108">これらの内線番号は、仮想の内線番号 (つまり、ユーザーや電話が割り当てられていない内線番号) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4208-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="a4208-109">コールパークアプリケーションを実行する各プールには、1つ以上の拡張機能の範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a4208-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="a4208-110">これらの範囲は、展開全体でグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4208-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="a4208-111">[**コールパーク**] ページには、組織で定義されているすべてのコールパーク番号範囲の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4208-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="a4208-112">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="a4208-112">Tasks you can perform</span></span>

<span data-ttu-id="a4208-113">[**コール パーク**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a4208-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="a4208-114">新しい番号範囲の作成</span><span class="sxs-lookup"><span data-stu-id="a4208-114">Create a new number range</span></span>

- <span data-ttu-id="a4208-115">既存の番号範囲の変更</span><span class="sxs-lookup"><span data-stu-id="a4208-115">Change an existing number range</span></span>

- <span data-ttu-id="a4208-116">番号範囲の削除</span><span class="sxs-lookup"><span data-stu-id="a4208-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="a4208-117">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="a4208-117">UI Reference</span></span>

<span data-ttu-id="a4208-118">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="a4208-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="a4208-119">**新規**新しいコールパーク番号の範囲を開始します。</span><span class="sxs-lookup"><span data-stu-id="a4208-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="a4208-120">**編集**編集用に選択した番号範囲を開くか、リスト内のすべての番号範囲を選択するか、選択した番号範囲を削除します。</span><span class="sxs-lookup"><span data-stu-id="a4208-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="a4208-121">**更新**数値範囲の一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="a4208-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="a4208-122">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="a4208-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="a4208-123">**名前**数値の範囲を示す一意の名前。</span><span class="sxs-lookup"><span data-stu-id="a4208-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="a4208-124">**開始範囲**範囲の開始番号。</span><span class="sxs-lookup"><span data-stu-id="a4208-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="a4208-125">**範囲の終了**範囲の終了番号。</span><span class="sxs-lookup"><span data-stu-id="a4208-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="a4208-126">**宛先**番号範囲のコールパークアプリケーションをホストするアプリケーションサービスの完全修飾ドメイン名 (FQDN) またはサービス ID。</span><span class="sxs-lookup"><span data-stu-id="a4208-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="a4208-127">コールパーク機能と機能の詳細については、「 [Skype For business でのコールパークの計画](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4208-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="a4208-128">通話パーク番号範囲の使用について詳しくは、「[パーキング通話用に電話番号の内線番号を設定する](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a4208-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


