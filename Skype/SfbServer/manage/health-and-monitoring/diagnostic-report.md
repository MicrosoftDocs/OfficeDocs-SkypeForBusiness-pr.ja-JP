---
title: Skype ビジネス サーバーの診断レポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: '概要: は、Skype のビジネス サーバーの診断レポートについて説明します。'
ms.openlocfilehash: b50be1733eb085bc8a3323cf3fcad028e2f0c6b4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926565"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a><span data-ttu-id="fbe39-103">Skype ビジネス サーバーの診断レポート</span><span class="sxs-lookup"><span data-stu-id="fbe39-103">Diagnostic Report in Skype for Business Server</span></span>
 
<span data-ttu-id="fbe39-104">**の概要:** Skype のビジネス サーバーの診断レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fbe39-104">**Summary:** Learn about the Diagnostic Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="fbe39-105">診断レポートは、失敗したセッションの診断およびトラブルシューティングの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="fbe39-105">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="fbe39-106">この情報には、診断の ID とセッションが失敗したときに報告された診断ヘッダーの両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fbe39-106">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="fbe39-107">診断 ID は、(ms 診断ヘッダーの形式) で診断ヘッダー診断 ID に対して、付属の説明を提供しますが、SIP メッセージに関連付けられた一意の識別子</span><span class="sxs-lookup"><span data-stu-id="fbe39-107">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="fbe39-108">レポートには、レポート コンポーネントによって認識されている重要なトラブルシューティングの詳細も含まれています。</span><span class="sxs-lookup"><span data-stu-id="fbe39-108">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="fbe39-109">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fbe39-109">For example:</span></span>
  
- <span data-ttu-id="fbe39-p102">エラーを生成した PSTN ゲートウェイによって提供された原因コード。発信通話が PSTN ネットワークで失敗すると、ISDN User Part (ISUP) の原因コードが自動的に生成されます。たとえば、PSTN ゲートウェイは原因コード 34 を送信して、通話を完了するための使用可能な回線またはチャネルが存在しないことを示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="fbe39-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>
    
- <span data-ttu-id="fbe39-113">接続エラーのピア FQDN、ポート、および Winsock エラー。</span><span class="sxs-lookup"><span data-stu-id="fbe39-113">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>
    
- <span data-ttu-id="fbe39-p103">DNS 解決エラーで検索されている名前。DNS 解決は、クライアントがネーム サーバーに問い合わせ、指定されたデバイス名に対応する IP アドレスを要求するときにいつでも実行されます。</span><span class="sxs-lookup"><span data-stu-id="fbe39-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>
    
## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="fbe39-116">診断レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="fbe39-116">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="fbe39-117">診断レポートは、[ビジネスのサーバー用の Skype でのピア ツー ピア セッション詳細レポート](peer-to-peer-session-detail-report.md)または、会議の詳細] レポートのいずれかの診断レポート (詳細) のメトリックをクリックしてアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fbe39-117">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>
  
## <a name="filters"></a><span data-ttu-id="fbe39-118">フィルター</span><span class="sxs-lookup"><span data-stu-id="fbe39-118">Filters</span></span>

<span data-ttu-id="fbe39-p104">なし。診断レポートにフィルターを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbe39-p104">None. You cannot filter the Diagnostic Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="fbe39-121">指標</span><span class="sxs-lookup"><span data-stu-id="fbe39-121">Metrics</span></span>

<span data-ttu-id="fbe39-122">次の表に、診断レポートで提供されるセッションごとの情報を示します。</span><span class="sxs-lookup"><span data-stu-id="fbe39-122">The following table lists the information provided in the Diagnostic Report for each session.</span></span>
  
<span data-ttu-id="fbe39-123">**診断レポートの指標**</span><span class="sxs-lookup"><span data-stu-id="fbe39-123">**Diagnostic Report Metrics**</span></span>

|<span data-ttu-id="fbe39-124">**名前**</span><span class="sxs-lookup"><span data-stu-id="fbe39-124">**Name**</span></span>|<span data-ttu-id="fbe39-125">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="fbe39-125">**Can you sort on this item?**</span></span>|<span data-ttu-id="fbe39-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="fbe39-126">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fbe39-127">**レポート時刻**</span><span class="sxs-lookup"><span data-stu-id="fbe39-127">**Report time**</span></span> <br/> |<span data-ttu-id="fbe39-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe39-128">No</span></span>  <br/> |<span data-ttu-id="fbe39-129">レポートが記録された日時。</span><span class="sxs-lookup"><span data-stu-id="fbe39-129">Date and time that the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="fbe39-130">**応答コード**</span><span class="sxs-lookup"><span data-stu-id="fbe39-130">**Response code**</span></span> <br/> |<span data-ttu-id="fbe39-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe39-131">No</span></span>  <br/> |<span data-ttu-id="fbe39-132">セッションが失敗したときに送信された SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="fbe39-132">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="fbe39-133">**要求の種類**</span><span class="sxs-lookup"><span data-stu-id="fbe39-133">**Request type**</span></span> <br/> |<span data-ttu-id="fbe39-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe39-134">No</span></span>  <br/> |<span data-ttu-id="fbe39-p105">失敗した SIP 要求の種類 (INVITE、BYE、SERVICE など)。</span><span class="sxs-lookup"><span data-stu-id="fbe39-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span>  <br/> |
|<span data-ttu-id="fbe39-137">**ソース**</span><span class="sxs-lookup"><span data-stu-id="fbe39-137">**Source**</span></span> <br/> |<span data-ttu-id="fbe39-138">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe39-138">No</span></span>  <br/> |<span data-ttu-id="fbe39-139">エラーのソース。</span><span class="sxs-lookup"><span data-stu-id="fbe39-139">Source of the error.</span></span>  <br/> |
|<span data-ttu-id="fbe39-140">**送信元ユーザー URI**</span><span class="sxs-lookup"><span data-stu-id="fbe39-140">**From user URI**</span></span> <br/> |<span data-ttu-id="fbe39-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe39-141">No</span></span>  <br/> |<span data-ttu-id="fbe39-142">セッションを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="fbe39-142">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="fbe39-143">**送信元ユーザー エージェント**</span><span class="sxs-lookup"><span data-stu-id="fbe39-143">**From user agent**</span></span> <br/> |<span data-ttu-id="fbe39-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe39-144">No</span></span>  <br/> |<span data-ttu-id="fbe39-145">セッションを開始したユーザーのエンドポイントで使用されているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="fbe39-145">Software used by the endpoint of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="fbe39-146">**診断 ID**</span><span class="sxs-lookup"><span data-stu-id="fbe39-146">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="fbe39-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe39-147">No</span></span>  <br/> |<span data-ttu-id="fbe39-148">SIP メッセージに (ms-diagnostics ヘッダーの形で) 添付された一意の識別子。多くの場合、この情報はトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fbe39-148">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="fbe39-149">**コンテンツの種類**</span><span class="sxs-lookup"><span data-stu-id="fbe39-149">**Content type**</span></span> <br/> |<span data-ttu-id="fbe39-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe39-150">No</span></span>  <br/> |<span data-ttu-id="fbe39-p106">失敗したメディア コンテンツの種類。たとえば、よく使われるコンテンツの種類は Application/sdp です。セッション記述プロトコル (SDP) は、セッションのアナウンス、セッションの招待、その他のマルチメディア セッション開始形式で使われる標準インターネット プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="fbe39-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span>  <br/> |
|<span data-ttu-id="fbe39-154">**アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="fbe39-154">**Application**</span></span> <br/> |<span data-ttu-id="fbe39-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe39-155">No</span></span>  <br/> |<span data-ttu-id="fbe39-156">エラーに関係するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="fbe39-156">Application involved in the error.</span></span>  <br/> |
|<span data-ttu-id="fbe39-157">**送信先ユーザー URI**</span><span class="sxs-lookup"><span data-stu-id="fbe39-157">**To user URI**</span></span> <br/> |<span data-ttu-id="fbe39-158">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe39-158">No</span></span>  <br/> |<span data-ttu-id="fbe39-159">セッションに招待されたユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="fbe39-159">SIP address of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="fbe39-160">**会議参加時間 (ミリ秒)**</span><span class="sxs-lookup"><span data-stu-id="fbe39-160">**Conference join times (ms)**</span></span> <br/> |<span data-ttu-id="fbe39-161">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe39-161">No</span></span>  <br/> |<span data-ttu-id="fbe39-162">ユーザーが会議に参加するのにかかった時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="fbe39-162">Amount of time (in milliseconds) it took for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="fbe39-163">**診断ヘッダー**</span><span class="sxs-lookup"><span data-stu-id="fbe39-163">**Diagnostic header**</span></span> <br/> |<span data-ttu-id="fbe39-164">不可</span><span class="sxs-lookup"><span data-stu-id="fbe39-164">No</span></span>  <br/> |<span data-ttu-id="fbe39-165">診断 ID の説明。</span><span class="sxs-lookup"><span data-stu-id="fbe39-165">Diagnostic ID description.</span></span>  <br/> |
   
<span data-ttu-id="fbe39-166">[Ms 診断ヘッダー ページ](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx)の診断エラーの一覧が見つかります。</span><span class="sxs-lookup"><span data-stu-id="fbe39-166">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx).</span></span>
  

