---
title: Skype for Business Server の診断レポート
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
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: '概要: Skype for Business Server の診断レポートについて説明します。'
ms.openlocfilehash: b7739214cf176336e47a5d2e11b36b52ea87eca7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095241"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a><span data-ttu-id="1577f-103">Skype for Business Server の診断レポート</span><span class="sxs-lookup"><span data-stu-id="1577f-103">Diagnostic Report in Skype for Business Server</span></span>
 
<span data-ttu-id="1577f-104">**概要:** Skype for Business Server の診断レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1577f-104">**Summary:** Learn about the Diagnostic Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="1577f-105">診断レポートは、失敗したセッションの診断およびトラブルシューティング情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1577f-105">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="1577f-106">この情報には、セッションが失敗した場合に報告された診断 ID と診断ヘッダーの両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1577f-106">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="1577f-107">診断 ID は SIP メッセージに接続される一意の識別子 (ms-diagnostics ヘッダーの形式) ですが、診断ヘッダーには診断 ID の説明が付属しています。</span><span class="sxs-lookup"><span data-stu-id="1577f-107">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="1577f-108">レポートには、レポート コンポーネントで知られている貴重なトラブルシューティングの詳細が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="1577f-108">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="1577f-109">例:</span><span class="sxs-lookup"><span data-stu-id="1577f-109">For example:</span></span>
  
- <span data-ttu-id="1577f-p102">エラーを生成した PSTN ゲートウェイによって提供された原因コード。発信通話が PSTN ネットワークで失敗すると、ISDN User Part (ISUP) の原因コードが自動的に生成されます。たとえば、PSTN ゲートウェイは原因コード 34 を送信して、通話を完了するための使用可能な回線またはチャネルが存在しないことを示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="1577f-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>
    
- <span data-ttu-id="1577f-113">接続エラーのピアの FQDN、ポート、および Winsock エラー。</span><span class="sxs-lookup"><span data-stu-id="1577f-113">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>
    
- <span data-ttu-id="1577f-p103">DNS 解決エラーで検索されている名前。DNS 解決は、クライアントがネーム サーバーに問い合わせ、指定されたデバイス名に対応する IP アドレスを要求するときにいつでも実行されます。</span><span class="sxs-lookup"><span data-stu-id="1577f-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>
    
## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="1577f-116">診断レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="1577f-116">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="1577f-117">診断レポートにアクセスするには [、Skype for Business Server](peer-to-peer-session-detail-report.md) のピアツーピア セッション詳細レポートまたは会議詳細レポートの診断レポート (詳細) メトリックをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1577f-117">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>
  
## <a name="filters"></a><span data-ttu-id="1577f-118">フィルター</span><span class="sxs-lookup"><span data-stu-id="1577f-118">Filters</span></span>

<span data-ttu-id="1577f-p104">なし。診断レポートにフィルターを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1577f-p104">None. You cannot filter the Diagnostic Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="1577f-121">指標</span><span class="sxs-lookup"><span data-stu-id="1577f-121">Metrics</span></span>

<span data-ttu-id="1577f-122">次の表に、診断レポートで提供されるセッションごとの情報を示します。</span><span class="sxs-lookup"><span data-stu-id="1577f-122">The following table lists the information provided in the Diagnostic Report for each session.</span></span>
  
<span data-ttu-id="1577f-123">**診断レポートの指標**</span><span class="sxs-lookup"><span data-stu-id="1577f-123">**Diagnostic Report Metrics**</span></span>

|<span data-ttu-id="1577f-124">**名前**</span><span class="sxs-lookup"><span data-stu-id="1577f-124">**Name**</span></span>|<span data-ttu-id="1577f-125">**このアイテムを並べ替えることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="1577f-125">**Can you sort on this item?**</span></span>|<span data-ttu-id="1577f-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="1577f-126">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1577f-127">**レポート時刻**</span><span class="sxs-lookup"><span data-stu-id="1577f-127">**Report time**</span></span> <br/> |<span data-ttu-id="1577f-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="1577f-128">No</span></span>  <br/> |<span data-ttu-id="1577f-129">レポートが記録された日時。</span><span class="sxs-lookup"><span data-stu-id="1577f-129">Date and time that the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="1577f-130">**応答コード**</span><span class="sxs-lookup"><span data-stu-id="1577f-130">**Response code**</span></span> <br/> |<span data-ttu-id="1577f-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="1577f-131">No</span></span>  <br/> |<span data-ttu-id="1577f-132">セッションが失敗したときに送信された SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="1577f-132">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="1577f-133">**要求の種類**</span><span class="sxs-lookup"><span data-stu-id="1577f-133">**Request type**</span></span> <br/> |<span data-ttu-id="1577f-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="1577f-134">No</span></span>  <br/> |<span data-ttu-id="1577f-p105">失敗した SIP 要求の種類 (INVITE、BYE、SERVICE など)。</span><span class="sxs-lookup"><span data-stu-id="1577f-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span>  <br/> |
|<span data-ttu-id="1577f-137">**Source**</span><span class="sxs-lookup"><span data-stu-id="1577f-137">**Source**</span></span> <br/> |<span data-ttu-id="1577f-138">いいえ</span><span class="sxs-lookup"><span data-stu-id="1577f-138">No</span></span>  <br/> |<span data-ttu-id="1577f-139">エラーのソース。</span><span class="sxs-lookup"><span data-stu-id="1577f-139">Source of the error.</span></span>  <br/> |
|<span data-ttu-id="1577f-140">**送信元ユーザー URI**</span><span class="sxs-lookup"><span data-stu-id="1577f-140">**From user URI**</span></span> <br/> |<span data-ttu-id="1577f-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="1577f-141">No</span></span>  <br/> |<span data-ttu-id="1577f-142">セッションを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="1577f-142">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="1577f-143">**送信元ユーザー エージェント**</span><span class="sxs-lookup"><span data-stu-id="1577f-143">**From user agent**</span></span> <br/> |<span data-ttu-id="1577f-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="1577f-144">No</span></span>  <br/> |<span data-ttu-id="1577f-145">セッションを開始したユーザーのエンドポイントで使用されているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="1577f-145">Software used by the endpoint of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="1577f-146">[**診断 ID**]</span><span class="sxs-lookup"><span data-stu-id="1577f-146">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="1577f-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="1577f-147">No</span></span>  <br/> |<span data-ttu-id="1577f-148">エラーのトラブルシューティングに役立つ情報を得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。</span><span class="sxs-lookup"><span data-stu-id="1577f-148">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="1577f-149">**コンテンツの種類**</span><span class="sxs-lookup"><span data-stu-id="1577f-149">**Content type**</span></span> <br/> |<span data-ttu-id="1577f-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="1577f-150">No</span></span>  <br/> |<span data-ttu-id="1577f-p106">失敗したメディア コンテンツの種類。たとえば、よく使われるコンテンツの種類は Application/sdp です。セッション記述プロトコル (SDP) は、セッションのアナウンス、セッションの招待、その他のマルチメディア セッション開始形式で使われる標準インターネット プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="1577f-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span>  <br/> |
|<span data-ttu-id="1577f-154">**アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="1577f-154">**Application**</span></span> <br/> |<span data-ttu-id="1577f-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="1577f-155">No</span></span>  <br/> |<span data-ttu-id="1577f-156">エラーに関係するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="1577f-156">Application involved in the error.</span></span>  <br/> |
|<span data-ttu-id="1577f-157">**送信先ユーザー URI**</span><span class="sxs-lookup"><span data-stu-id="1577f-157">**To user URI**</span></span> <br/> |<span data-ttu-id="1577f-158">いいえ</span><span class="sxs-lookup"><span data-stu-id="1577f-158">No</span></span>  <br/> |<span data-ttu-id="1577f-159">セッションに招待されたユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="1577f-159">SIP address of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="1577f-160">**会議参加時間 (ミリ秒)**</span><span class="sxs-lookup"><span data-stu-id="1577f-160">**Conference join times (ms)**</span></span> <br/> |<span data-ttu-id="1577f-161">いいえ</span><span class="sxs-lookup"><span data-stu-id="1577f-161">No</span></span>  <br/> |<span data-ttu-id="1577f-162">ユーザーが会議に参加するのにかかった時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="1577f-162">Amount of time (in milliseconds) it took for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="1577f-163">**診断ヘッダー**</span><span class="sxs-lookup"><span data-stu-id="1577f-163">**Diagnostic header**</span></span> <br/> |<span data-ttu-id="1577f-164">いいえ</span><span class="sxs-lookup"><span data-stu-id="1577f-164">No</span></span>  <br/> |<span data-ttu-id="1577f-165">診断 ID の説明。</span><span class="sxs-lookup"><span data-stu-id="1577f-165">Diagnostic ID description.</span></span>  <br/> |
   
<span data-ttu-id="1577f-166">診断エラーの一覧は [、[Ms-Diagnostics Header] ページに表示されます](/openspecs/office_protocols/ms-ocer/f6787b39-0842-43ca-94a2-6afadda5f0a3)。</span><span class="sxs-lookup"><span data-stu-id="1577f-166">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](/openspecs/office_protocols/ms-ocer/f6787b39-0842-43ca-94a2-6afadda5f0a3).</span></span>
