---
title: コール パーク
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: 呼び出しを保持するとときに、転送されます一時的な番号に呼び出しが他のユーザーには、それを取得するか、タイムアウトするまでに保持されます。停止の呼び出し用に予約は内線番号の範囲を持つテーブルを構成する必要があります。 これらの内線番号は、仮想の内線番号 (つまり、ユーザーや電話が割り当てられていない内線番号) にする必要があります。 コール パーク アプリケーションを実行する各プールには、拡張機能の 1 つまたは複数の範囲を持つことができます。 これらの範囲は、展開全体でグローバルに一意である必要があります。
ms.openlocfilehash: c3b87225c4cd9fa4c0736ba6ab1ba86ab3405162
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21019611"
---
# <a name="call-park"></a><span data-ttu-id="e3b28-106">コール パーク</span><span class="sxs-lookup"><span data-stu-id="e3b28-106">Call Park</span></span>
 
<span data-ttu-id="e3b28-107">呼び出しを保持するとときに、転送されます一時的な番号に呼び出しが他のユーザーには、それを取得するか、タイムアウトするまでに保持されます。停止の呼び出し用に予約は内線番号の範囲を持つテーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3b28-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="e3b28-108">これらの内線番号は、仮想の内線番号 (つまり、ユーザーや電話が割り当てられていない内線番号) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3b28-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="e3b28-109">コール パーク アプリケーションを実行する各プールには、拡張機能の 1 つまたは複数の範囲を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="e3b28-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="e3b28-110">これらの範囲は、展開全体でグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3b28-110">These ranges must be globally unique across your deployment.</span></span>
  
<span data-ttu-id="e3b28-111">**コール パーク**] ページには、組織に対して定義されたすべてのコール パーク番号範囲の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3b28-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="e3b28-112">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="e3b28-112">Tasks you can perform</span></span>

<span data-ttu-id="e3b28-113">[**コール パーク**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e3b28-113">You can perform the following tasks from the **Call Park** page:</span></span>
  
- <span data-ttu-id="e3b28-114">新しい番号範囲の作成</span><span class="sxs-lookup"><span data-stu-id="e3b28-114">Create a new number range</span></span>
    
- <span data-ttu-id="e3b28-115">既存の番号範囲の変更</span><span class="sxs-lookup"><span data-stu-id="e3b28-115">Change an existing number range</span></span>
    
- <span data-ttu-id="e3b28-116">番号範囲の削除</span><span class="sxs-lookup"><span data-stu-id="e3b28-116">Delete a number range</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="e3b28-117">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="e3b28-117">UI Reference</span></span>

<span data-ttu-id="e3b28-118">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="e3b28-118">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="e3b28-119">**新しい**新しいコール パーク番号範囲を開始します。</span><span class="sxs-lookup"><span data-stu-id="e3b28-119">**New** Starts a new Call Park number range.</span></span>
    
- <span data-ttu-id="e3b28-120">**編集**選択した番号の範囲を編集するためを開いたり、ボックスの一覧ですべての数値の範囲を選択選択した番号の範囲を削除します。</span><span class="sxs-lookup"><span data-stu-id="e3b28-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>
    
- <span data-ttu-id="e3b28-121">**更新**数値の範囲の一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="e3b28-121">**Refresh** Refreshes the list of number ranges.</span></span>
    
<span data-ttu-id="e3b28-122">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="e3b28-122">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="e3b28-123">**名**番号の範囲を識別する一意の名前。</span><span class="sxs-lookup"><span data-stu-id="e3b28-123">**Name** The unique name that identifies the number range.</span></span>
    
- <span data-ttu-id="e3b28-124">**範囲開始**範囲の先頭の数です。</span><span class="sxs-lookup"><span data-stu-id="e3b28-124">**Start range** The beginning number of the range.</span></span>
    
- <span data-ttu-id="e3b28-125">**終了範囲**範囲の終了番号です。</span><span class="sxs-lookup"><span data-stu-id="e3b28-125">**End range** The ending number of the range.</span></span>
    
- <span data-ttu-id="e3b28-126">**宛先**完全修飾ドメイン名 (FQDN) または、ID 番号の範囲のコール パーク アプリケーションをホストするアプリケーション サービスのサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e3b28-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>
    
<span data-ttu-id="e3b28-127">コール パークの特徴と機能についての詳細は、[ビジネスの Skype のコール パークの計画](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3b28-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="e3b28-128">コール パーク番号範囲の操作についての詳細は、[呼び出しの駐車場の電話番号の拡張機能を構成する](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3b28-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>
  

