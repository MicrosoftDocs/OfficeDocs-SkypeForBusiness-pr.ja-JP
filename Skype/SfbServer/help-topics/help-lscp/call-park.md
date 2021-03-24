---
title: コール パーク
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: 呼び出しがパークされている場合、通話は一時的な番号に転送され、呼び出しは誰かが呼び出しを取得するか、または時間が切れるまで保持されます。パークされた呼び出しのために予約する内線番号の範囲を持つテーブルを構成する必要があります。 これらの内線番号は仮想の内線番号 (つまり、ユーザーや電話が割り当てられていない内線番号) にする必要あがります。 コール パーク アプリケーションを実行する各プールには、1 つ以上の範囲の拡張機能を使用できます。 これらの範囲は、展開全体でグローバルに一意である必要があります。
ms.openlocfilehash: 30e0493c065c8bcd16b8d18a625c2650522ee8ee
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095401"
---
# <a name="call-park"></a><span data-ttu-id="ea125-106">コール パーク</span><span class="sxs-lookup"><span data-stu-id="ea125-106">Call Park</span></span>

<span data-ttu-id="ea125-107">呼び出しがパークされている場合、通話は一時的な番号に転送され、呼び出しは誰かが呼び出しを取得するか、または時間が切れるまで保持されます。パークされた呼び出しのために予約する内線番号の範囲を持つテーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea125-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="ea125-108">これらの内線番号は仮想の内線番号 (つまり、ユーザーや電話が割り当てられていない内線番号) にする必要あがります。</span><span class="sxs-lookup"><span data-stu-id="ea125-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="ea125-109">コール パーク アプリケーションを実行する各プールには、1 つ以上の範囲の拡張機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea125-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="ea125-110">これらの範囲は、展開全体でグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea125-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="ea125-111">[ **コール パーク]** ページには、組織に対して定義されているすべての通話パーク番号範囲の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea125-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="ea125-112">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="ea125-112">Tasks you can perform</span></span>

<span data-ttu-id="ea125-113">[**コール パーク**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ea125-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="ea125-114">新しい番号範囲の作成</span><span class="sxs-lookup"><span data-stu-id="ea125-114">Create a new number range</span></span>

- <span data-ttu-id="ea125-115">既存の番号範囲の変更</span><span class="sxs-lookup"><span data-stu-id="ea125-115">Change an existing number range</span></span>

- <span data-ttu-id="ea125-116">番号範囲の削除</span><span class="sxs-lookup"><span data-stu-id="ea125-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="ea125-117">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="ea125-117">UI Reference</span></span>

<span data-ttu-id="ea125-118">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="ea125-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="ea125-119">**New** 新しい通話パーク番号範囲を開始します。</span><span class="sxs-lookup"><span data-stu-id="ea125-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="ea125-120">**編集** 選択した番号範囲を編集用に開き、リスト内のすべての番号範囲を選択するか、選択した番号範囲を削除します。</span><span class="sxs-lookup"><span data-stu-id="ea125-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="ea125-121">**更新** 番号範囲の一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="ea125-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="ea125-122">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="ea125-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="ea125-123">**名前** 番号範囲を識別する一意の名前。</span><span class="sxs-lookup"><span data-stu-id="ea125-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="ea125-124">**開始範囲** 範囲の開始番号。</span><span class="sxs-lookup"><span data-stu-id="ea125-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="ea125-125">**終了範囲** 範囲の終了番号。</span><span class="sxs-lookup"><span data-stu-id="ea125-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="ea125-126">**宛先** 番号範囲のコール パーク アプリケーションをホストする Application サービスの完全修飾ドメイン名 (FQDN) またはサービス ID。</span><span class="sxs-lookup"><span data-stu-id="ea125-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="ea125-127">通話パークの機能の詳細については [、「Plan for Call Park in Skype for Business 2015」を参照してください](../../plan-your-deployment/enterprise-voice-solution/call-park.md)。</span><span class="sxs-lookup"><span data-stu-id="ea125-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="ea125-128">コール パーク番号範囲の操作の詳細については [、「Configure Phone Number Extensions for Parking Call」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)。</span><span class="sxs-lookup"><span data-stu-id="ea125-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).</span></span>