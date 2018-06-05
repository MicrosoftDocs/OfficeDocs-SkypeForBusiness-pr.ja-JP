---
title: Skype for Business Server 2015 のエラー リスト レポート
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: '概要: は、ビジネス サーバー 2015 の Skype のエラーの一覧のレポートについて説明します。'
ms.openlocfilehash: 7cb146569958908e79700e725d473bc246295c9d
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569321"
---
# <a name="failure-list-report-in-skype-for-business-server-2015"></a><span data-ttu-id="e3e7e-103">Skype for Business Server 2015 のエラー リスト レポート</span><span class="sxs-lookup"><span data-stu-id="e3e7e-103">Failure List Report in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e3e7e-104">**の概要:** ビジネス サーバー 2015 の Skype のエラーの一覧のレポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-104">**Summary:** Learn about the Failure List Report in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e3e7e-p101">エラー リスト レポートは、エラーが発生したピアツーピア セッションまたは電話会議セッションに参加した個々の参加者に関する情報を提供します。この情報には、問題が発生したユーザーの URI、エラーに関連付けられている SIP 応答コードおよび診断 ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="e3e7e-107">エラー リスト レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="e3e7e-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="e3e7e-108">エラーの一覧のレポートは、[ビジネス サーバー 2015 の Skype でのエラー分布レポート](failure-distribution-report.md)に次の測定値のいずれかをクリックしてアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server 2015](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="e3e7e-109">トップの診断理由 (セッション)</span><span class="sxs-lookup"><span data-stu-id="e3e7e-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="e3e7e-110">トップのモダリティ (セッション)</span><span class="sxs-lookup"><span data-stu-id="e3e7e-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="e3e7e-111">トップのプール (セッション)</span><span class="sxs-lookup"><span data-stu-id="e3e7e-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="e3e7e-112">トップのソース (セッション)</span><span class="sxs-lookup"><span data-stu-id="e3e7e-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="e3e7e-113">トップのコンポーネント (セッション)</span><span class="sxs-lookup"><span data-stu-id="e3e7e-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="e3e7e-114">トップの発信元ユーザー (セッション)</span><span class="sxs-lookup"><span data-stu-id="e3e7e-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="e3e7e-115">トップの発信先ユーザー (セッション)</span><span class="sxs-lookup"><span data-stu-id="e3e7e-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="e3e7e-116">トップの発信元ユーザー エージェント (セッション)</span><span class="sxs-lookup"><span data-stu-id="e3e7e-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="e3e7e-117">エラーの一覧のレポートからは、ピア ツー ピア セッションのセッションの詳細メトリックをクリックすると、[ビジネス サーバー 2015 の Skype でのピア ツー ピア セッション詳細レポート](peer-to-peer-session-detail-report.md)を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server 2015](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="e3e7e-118">また、電話会議の [電話会議] の指標をクリックすると、会議詳細レポートにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="e3e7e-119">エラー リスト レポートの活用</span><span class="sxs-lookup"><span data-stu-id="e3e7e-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="e3e7e-p103">エラー リスト レポートでは、マウス ポインターを値の上に置くだけで、それぞれの応答コードまたは診断 ID の説明を表示できます。たとえば、診断 ID 7025 の上にマウス ポインターを置くと、次のような説明がヒントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="e3e7e-122">ユーザーのメディアの作成中に内部サーバー エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="e3e7e-123">エラーの一覧のレポートには、直接には、少なくとも 1 つの障害が発生したセッションに参加したすべてのユーザーの一覧を取得する簡単な方法は提供されませんすることが重要も、ユーザーが最も頻繁に関与するかを決定する方法が提供されることで、障害が発生しました。セッションです。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="e3e7e-124">(1 つは、エラーの一覧のレポートがありませんフィルタ リング機能)。ただし、データをエクスポートし、それをコンマ区切り値ファイルに変換する場合は、このような質問に対する回答を検索するのには Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="e3e7e-125">たとえば、データを保存するのです。CSV ファイルでは、C:\Data\Failure_List.csv という名前です。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-125">For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv.</span></span> <span data-ttu-id="e3e7e-126">そのファイルに保存されているデータに基づいて、このコマンドを少なくとも 1 つの障害が発生したセッションに関与したすべてのユーザーの一覧です。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="e3e7e-127">このコマンドを実行すると、次のような一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="e3e7e-128">次の 2 つのコマンドは、各ユーザーが参加した、エラーが発生したセッションの総数についてレポートします。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="e3e7e-129">この結果、次のようなデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="e3e7e-130">フィルター</span><span class="sxs-lookup"><span data-stu-id="e3e7e-130">Filters</span></span>

<span data-ttu-id="e3e7e-p105">なし。エラー リスト レポートにフィルターを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-p105">None. You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="e3e7e-133">指標</span><span class="sxs-lookup"><span data-stu-id="e3e7e-133">Metrics</span></span>

<span data-ttu-id="e3e7e-134">次の表に、失敗した呼び出しごとにエラー リスト レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="e3e7e-135">**エラー] ボックスの一覧のレポートの判断基準**</span><span class="sxs-lookup"><span data-stu-id="e3e7e-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="e3e7e-136">**名**</span><span class="sxs-lookup"><span data-stu-id="e3e7e-136">**Name**</span></span>|<span data-ttu-id="e3e7e-137">**この項目を並べ替えることができますか。**</span><span class="sxs-lookup"><span data-stu-id="e3e7e-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="e3e7e-138">**説明**</span><span class="sxs-lookup"><span data-stu-id="e3e7e-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e3e7e-139">**レポートされた時刻**</span><span class="sxs-lookup"><span data-stu-id="e3e7e-139">**Reported time**</span></span> <br/> |<span data-ttu-id="e3e7e-140">不可</span><span class="sxs-lookup"><span data-stu-id="e3e7e-140">No</span></span>  <br/> |<span data-ttu-id="e3e7e-141">レポートが記録された日時。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="e3e7e-142">**要求**</span><span class="sxs-lookup"><span data-stu-id="e3e7e-142">**Request**</span></span> <br/> |<span data-ttu-id="e3e7e-143">不可</span><span class="sxs-lookup"><span data-stu-id="e3e7e-143">No</span></span>  <br/> |<span data-ttu-id="e3e7e-p106">失敗した SIP 要求の種類 (INVITE、BYE など)。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-p106">SIP request type that failed. For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="e3e7e-146">**応答コード**</span><span class="sxs-lookup"><span data-stu-id="e3e7e-146">**Response code**</span></span> <br/> |<span data-ttu-id="e3e7e-147">不可</span><span class="sxs-lookup"><span data-stu-id="e3e7e-147">No</span></span>  <br/> |<span data-ttu-id="e3e7e-148">会議にエラーが発生したときに送信された SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="e3e7e-149">**診断 ID**</span><span class="sxs-lookup"><span data-stu-id="e3e7e-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="e3e7e-150">不可</span><span class="sxs-lookup"><span data-stu-id="e3e7e-150">No</span></span>  <br/> |<span data-ttu-id="e3e7e-151">SIP メッセージに (ms-diagnostics ヘッダーの形で) 添付された一意の識別子。多くの場合、この情報はトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="e3e7e-152">**参加コスト時間 (ミリ秒)**</span><span class="sxs-lookup"><span data-stu-id="e3e7e-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="e3e7e-153">不可</span><span class="sxs-lookup"><span data-stu-id="e3e7e-153">No</span></span>  <br/> |<span data-ttu-id="e3e7e-154">ユーザーが会議に参加するのに要した時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="e3e7e-155">**移動元ユーザー**</span><span class="sxs-lookup"><span data-stu-id="e3e7e-155">**From user**</span></span> <br/> |<span data-ttu-id="e3e7e-156">不可</span><span class="sxs-lookup"><span data-stu-id="e3e7e-156">No</span></span>  <br/> |<span data-ttu-id="e3e7e-157">呼び出しを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="e3e7e-158">**送信元ユーザー エージェント**</span><span class="sxs-lookup"><span data-stu-id="e3e7e-158">**From user agent**</span></span> <br/> |<span data-ttu-id="e3e7e-159">不可</span><span class="sxs-lookup"><span data-stu-id="e3e7e-159">No</span></span>  <br/> |<span data-ttu-id="e3e7e-160">呼び出しを開始したユーザーのエンドポイントで使用されているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="e3e7e-161">**対象ユーザー**</span><span class="sxs-lookup"><span data-stu-id="e3e7e-161">**To user**</span></span> <br/> |<span data-ttu-id="e3e7e-162">不可</span><span class="sxs-lookup"><span data-stu-id="e3e7e-162">No</span></span>  <br/> |<span data-ttu-id="e3e7e-163">呼び出しを受けたユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="e3e7e-163">SIP address of the user who was being called.</span></span>  <br/> |
   

