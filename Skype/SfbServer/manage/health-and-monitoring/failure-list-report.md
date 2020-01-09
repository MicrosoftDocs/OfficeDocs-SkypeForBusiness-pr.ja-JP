---
title: Skype for Business Server のエラーリストレポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: '概要: Skype for Business Server のエラーリストレポートについて説明します。'
ms.openlocfilehash: d0ba76974d99b123c99e3df40a6850736423ab73
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992824"
---
# <a name="failure-list-report-in-skype-for-business-server"></a><span data-ttu-id="6b284-103">Skype for Business Server のエラーリストレポート</span><span class="sxs-lookup"><span data-stu-id="6b284-103">Failure List Report in Skype for Business Server</span></span> 
 
<span data-ttu-id="6b284-104">**概要:** Skype for Business Server のエラーリストレポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6b284-104">**Summary:** Learn about the Failure List Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="6b284-p101">エラー リスト レポートは、エラーが発生したピアツーピア セッションまたは電話会議セッションに参加した個々の参加者に関する情報を提供します。この情報には、問題が発生したユーザーの URI、エラーに関連付けられている SIP 応答コードおよび診断 ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b284-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="6b284-107">エラー リスト レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="6b284-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="6b284-108">[エラー一覧] レポートにアクセスするには、 [Skype For Business Server のエラー配布レポート](failure-distribution-report.md)で、次のいずれかの指標をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b284-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="6b284-109">トップの診断理由 (セッション)</span><span class="sxs-lookup"><span data-stu-id="6b284-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="6b284-110">トップのモダリティ (セッション)</span><span class="sxs-lookup"><span data-stu-id="6b284-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="6b284-111">トップのプール (セッション)</span><span class="sxs-lookup"><span data-stu-id="6b284-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="6b284-112">トップのソース (セッション)</span><span class="sxs-lookup"><span data-stu-id="6b284-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="6b284-113">トップのコンポーネント (セッション)</span><span class="sxs-lookup"><span data-stu-id="6b284-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="6b284-114">トップの発信元ユーザー (セッション)</span><span class="sxs-lookup"><span data-stu-id="6b284-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="6b284-115">トップの発信先ユーザー (セッション)</span><span class="sxs-lookup"><span data-stu-id="6b284-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="6b284-116">トップの発信元ユーザー エージェント (セッション)</span><span class="sxs-lookup"><span data-stu-id="6b284-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="6b284-117">[エラー一覧] レポートから、 [Skype For Business Server のピアツーピアセッション詳細レポート](peer-to-peer-session-detail-report.md)にアクセスできます。これには、ピアツーピアセッションのセッション詳細メトリックをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b284-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="6b284-118">また、電話会議の [電話会議] の指標をクリックすると、会議詳細レポートにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6b284-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="6b284-119">エラー リスト レポートの活用</span><span class="sxs-lookup"><span data-stu-id="6b284-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="6b284-p103">エラー リスト レポートでは、マウス ポインターを値の上に置くだけで、それぞれの応答コードまたは診断 ID の説明を表示できます。たとえば、診断 ID 7025 の上にマウス ポインターを置くと、次のような説明がヒントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b284-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="6b284-122">ユーザーのメディアの作成中に内部サーバー エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6b284-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="6b284-123">障害リストレポートでは、1つ以上のセッションに参加しているすべてのユーザーの一覧を直接取得する方法はありません。また、どのユーザーが失敗したかを判断する方法も提供されていない点に注意してください。セッション.</span><span class="sxs-lookup"><span data-stu-id="6b284-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="6b284-124">(1 つの問題については、エラーリストレポートにはフィルター機能はありません)。ただし、データをエクスポートして、コンマ区切り値ファイルに変換した場合は、Windows PowerShell を使用して、そのような質問に対する回答を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="6b284-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="6b284-125">たとえば、データをに保存するとします。"C:\ Data\ Failure_List" という CSV ファイル。</span><span class="sxs-lookup"><span data-stu-id="6b284-125">For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv.</span></span> <span data-ttu-id="6b284-126">このコマンドは、そのファイルに保存されているデータに基づいて、1つ以上の失敗したセッションに参加していたすべてのユーザーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="6b284-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="6b284-127">このコマンドを実行すると、次のような一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="6b284-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="6b284-128">次の 2 つのコマンドは、各ユーザーが参加した、エラーが発生したセッションの総数についてレポートします。</span><span class="sxs-lookup"><span data-stu-id="6b284-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="6b284-129">この結果、次のようなデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="6b284-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="6b284-130">フィルター</span><span class="sxs-lookup"><span data-stu-id="6b284-130">Filters</span></span>

<span data-ttu-id="6b284-p105">なし。エラー リスト レポートにフィルターを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="6b284-p105">None. You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="6b284-133">指標</span><span class="sxs-lookup"><span data-stu-id="6b284-133">Metrics</span></span>

<span data-ttu-id="6b284-134">次の表に、失敗した呼び出しごとにエラー リスト レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="6b284-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="6b284-135">**エラー リスト レポートの指標**</span><span class="sxs-lookup"><span data-stu-id="6b284-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="6b284-136">**名前**</span><span class="sxs-lookup"><span data-stu-id="6b284-136">**Name**</span></span>|<span data-ttu-id="6b284-137">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="6b284-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="6b284-138">**説明**</span><span class="sxs-lookup"><span data-stu-id="6b284-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6b284-139">**レポートされた時刻**</span><span class="sxs-lookup"><span data-stu-id="6b284-139">**Reported time**</span></span> <br/> |<span data-ttu-id="6b284-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="6b284-140">No</span></span>  <br/> |<span data-ttu-id="6b284-141">レポートが記録された日時。</span><span class="sxs-lookup"><span data-stu-id="6b284-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="6b284-142">**要求**</span><span class="sxs-lookup"><span data-stu-id="6b284-142">**Request**</span></span> <br/> |<span data-ttu-id="6b284-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="6b284-143">No</span></span>  <br/> |<span data-ttu-id="6b284-p106">失敗した SIP 要求の種類 (INVITE、BYE など)。</span><span class="sxs-lookup"><span data-stu-id="6b284-p106">SIP request type that failed. For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="6b284-146">**応答コード**</span><span class="sxs-lookup"><span data-stu-id="6b284-146">**Response code**</span></span> <br/> |<span data-ttu-id="6b284-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="6b284-147">No</span></span>  <br/> |<span data-ttu-id="6b284-148">会議にエラーが発生したときに送信された SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="6b284-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="6b284-149">**診断 ID**</span><span class="sxs-lookup"><span data-stu-id="6b284-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="6b284-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="6b284-150">No</span></span>  <br/> |<span data-ttu-id="6b284-151">SIP メッセージに (ms-diagnostics ヘッダーの形で) 添付された一意の識別子。多くの場合、この情報はトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6b284-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="6b284-152">**参加コスト時間 (ミリ秒)**</span><span class="sxs-lookup"><span data-stu-id="6b284-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="6b284-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="6b284-153">No</span></span>  <br/> |<span data-ttu-id="6b284-154">ユーザーが会議に参加するのに要した時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="6b284-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="6b284-155">**移動元ユーザー**</span><span class="sxs-lookup"><span data-stu-id="6b284-155">**From user**</span></span> <br/> |<span data-ttu-id="6b284-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="6b284-156">No</span></span>  <br/> |<span data-ttu-id="6b284-157">呼び出しを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="6b284-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="6b284-158">**送信元ユーザー エージェント**</span><span class="sxs-lookup"><span data-stu-id="6b284-158">**From user agent**</span></span> <br/> |<span data-ttu-id="6b284-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="6b284-159">No</span></span>  <br/> |<span data-ttu-id="6b284-160">呼び出しを開始したユーザーのエンドポイントで使用されているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="6b284-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="6b284-161">**対象ユーザー**</span><span class="sxs-lookup"><span data-stu-id="6b284-161">**To user**</span></span> <br/> |<span data-ttu-id="6b284-162">不可</span><span class="sxs-lookup"><span data-stu-id="6b284-162">No</span></span>  <br/> |<span data-ttu-id="6b284-163">呼び出しを受けたユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="6b284-163">SIP address of the user who was being called.</span></span>  <br/> |
   

