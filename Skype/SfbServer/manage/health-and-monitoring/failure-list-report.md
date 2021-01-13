---
title: Skype for Business Server のエラー リスト レポート
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: '概要: Skype for Business Server のエラー リスト レポートについて学習します。'
ms.openlocfilehash: 48654ee827f0d7efcb50bcccc4e1d2f3fdb5422e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816847"
---
# <a name="failure-list-report-in-skype-for-business-server"></a><span data-ttu-id="ad4cf-103">Skype for Business Server のエラー リスト レポート</span><span class="sxs-lookup"><span data-stu-id="ad4cf-103">Failure List Report in Skype for Business Server</span></span> 
 
<span data-ttu-id="ad4cf-104">**概要:** Skype for Business Server のエラー リスト レポートについて学習します。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-104">**Summary:** Learn about the Failure List Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="ad4cf-p101">エラー リスト レポートは、エラーが発生したピアツーピア セッションまたは電話会議セッションに参加した個々の参加者に関する情報を提供します。この情報には、問題が発生したユーザーの URI、エラーに関連付けられている SIP 応答コードおよび診断 ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="ad4cf-107">エラー リスト レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="ad4cf-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="ad4cf-108">エラー リスト レポートにアクセスするには、Skype for Business Server のエラー分布レポートで [次の指標をクリックします](failure-distribution-report.md)。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="ad4cf-109">[トップの診断理由] (セッション)</span><span class="sxs-lookup"><span data-stu-id="ad4cf-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="ad4cf-110">[トップ モダリティ] (セッション)</span><span class="sxs-lookup"><span data-stu-id="ad4cf-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="ad4cf-111">[トップ プール] (セッション))</span><span class="sxs-lookup"><span data-stu-id="ad4cf-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="ad4cf-112">[トップ ソース] (セッション))</span><span class="sxs-lookup"><span data-stu-id="ad4cf-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="ad4cf-113">[トップ コンポーネント] (セッション)</span><span class="sxs-lookup"><span data-stu-id="ad4cf-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="ad4cf-114">[トップの発信元ユーザー] (セッション)</span><span class="sxs-lookup"><span data-stu-id="ad4cf-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="ad4cf-115">[トップの発信先ユーザー] (セッション)</span><span class="sxs-lookup"><span data-stu-id="ad4cf-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="ad4cf-116">[送信元ユーザー エージェント] (セッション)</span><span class="sxs-lookup"><span data-stu-id="ad4cf-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="ad4cf-117">エラー リスト レポートから、ピアツーピア セッションのセッション詳細メトリックをクリックすると [、Skype for Business Server](peer-to-peer-session-detail-report.md) のピアツーピア セッション詳細レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="ad4cf-118">また、電話会議の電話会議の指標をクリックすると、会議詳細レポートにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="ad4cf-119">エラー リスト レポートの活用</span><span class="sxs-lookup"><span data-stu-id="ad4cf-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="ad4cf-p103">エラー リスト レポートでは、マウス ポインターを値の上に置くだけで、それぞれの応答コードまたは診断 ID の説明を表示することができます。たとえば、診断 ID 7025 の上にマウス ポインターを置くと、次の説明がツールチップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="ad4cf-122">Internal server error creating media for user. (ユーザーのメディアの作成中に内部サーバー エラーが発生しました。)</span><span class="sxs-lookup"><span data-stu-id="ad4cf-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="ad4cf-p104">エラー リスト レポートはエラーが発生した 1 つ以上のセッションに参加したすべてのユーザーの一覧を直接取得する直接的な方法を提供せず、エラーが発生したセッションに最も頻繁に参加したユーザーを特定する方法も提供しないことに注意してください (一例を挙げると、エラー リスト レポートにはフィルター処理機能がありません)。ただし、データをエクスポートしてからコンマ区切り値ファイルに変換すると、Windows PowerShell を使用してこのような質問に対する回答を見つけることができます。たとえば、C:\Data\Failure_List.csv という名前の .CSV ファイルにデータを保存するとします。次のコマンドは、このファイルに保存されたデータに基づいて、エラーが発生した 1 つ以上のセッションに参加したすべてのユーザーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-p104">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session. (For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those. For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv. Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="ad4cf-127">このコマンドにより、次にような一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="ad4cf-128">次の 2 つのコマンドは、各ユーザーが参加した、エラーが発生したセッションの総数についてレポートします。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="ad4cf-129">これにより、次のようなデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="ad4cf-130">フィルター</span><span class="sxs-lookup"><span data-stu-id="ad4cf-130">Filters</span></span>

<span data-ttu-id="ad4cf-p105">なし。エラー リスト レポートはフィルターできません。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-p105">None. You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="ad4cf-133">指標</span><span class="sxs-lookup"><span data-stu-id="ad4cf-133">Metrics</span></span>

<span data-ttu-id="ad4cf-134">次の表に、失敗した呼び出しごとにエラー リスト レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="ad4cf-135">**エラー リスト レポートの指標**</span><span class="sxs-lookup"><span data-stu-id="ad4cf-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="ad4cf-136">**名前**</span><span class="sxs-lookup"><span data-stu-id="ad4cf-136">**Name**</span></span>|<span data-ttu-id="ad4cf-137">**このアイテムを並べ替えることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ad4cf-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="ad4cf-138">**説明**</span><span class="sxs-lookup"><span data-stu-id="ad4cf-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ad4cf-139">**レポートされた時刻**</span><span class="sxs-lookup"><span data-stu-id="ad4cf-139">**Reported time**</span></span> <br/> |<span data-ttu-id="ad4cf-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="ad4cf-140">No</span></span>  <br/> |<span data-ttu-id="ad4cf-141">レポートが記録された日時です。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="ad4cf-142">**要求**</span><span class="sxs-lookup"><span data-stu-id="ad4cf-142">**Request**</span></span> <br/> |<span data-ttu-id="ad4cf-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="ad4cf-143">No</span></span>  <br/> |<span data-ttu-id="ad4cf-p106">失敗した SIP 要求の種類です (INVITE、BYE など)。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-p106">SIP request type that failed. For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="ad4cf-146">**応答コード**</span><span class="sxs-lookup"><span data-stu-id="ad4cf-146">**Response code**</span></span> <br/> |<span data-ttu-id="ad4cf-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="ad4cf-147">No</span></span>  <br/> |<span data-ttu-id="ad4cf-148">会議にエラーが発生したときに送信された SIP 応答コードです。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="ad4cf-149">[**診断 ID**]</span><span class="sxs-lookup"><span data-stu-id="ad4cf-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="ad4cf-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="ad4cf-150">No</span></span>  <br/> |<span data-ttu-id="ad4cf-151">エラーのトラブルシューティングに役立つ情報を得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="ad4cf-152">[**Join cost time (ms)**] (参加に要した時間 (ミリ秒))</span><span class="sxs-lookup"><span data-stu-id="ad4cf-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="ad4cf-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="ad4cf-153">No</span></span>  <br/> |<span data-ttu-id="ad4cf-154">ユーザーが会議に参加するのに要した時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="ad4cf-155">**送信元ユーザー**</span><span class="sxs-lookup"><span data-stu-id="ad4cf-155">**From user**</span></span> <br/> |<span data-ttu-id="ad4cf-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="ad4cf-156">No</span></span>  <br/> |<span data-ttu-id="ad4cf-157">呼び出しを開始したユーザーの SIP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="ad4cf-158">**送信元ユーザー エージェント**</span><span class="sxs-lookup"><span data-stu-id="ad4cf-158">**From user agent**</span></span> <br/> |<span data-ttu-id="ad4cf-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="ad4cf-159">No</span></span>  <br/> |<span data-ttu-id="ad4cf-160">呼び出しを開始したユーザーのエンドポイントで使用されているソフトウェアです。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="ad4cf-161">**送信先ユーザー**</span><span class="sxs-lookup"><span data-stu-id="ad4cf-161">**To user**</span></span> <br/> |<span data-ttu-id="ad4cf-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="ad4cf-162">No</span></span>  <br/> |<span data-ttu-id="ad4cf-163">呼び出しを受けたユーザーの SIP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="ad4cf-163">SIP address of the user who was being called.</span></span>  <br/> |
   

