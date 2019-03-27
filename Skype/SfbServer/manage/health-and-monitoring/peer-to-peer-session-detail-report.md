---
title: ビジネス サーバーの Skype でのピア ツー ピア セッション詳細レポート
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: '概要: は、ビジネスのサーバーの Skype でピア ツー ピア セッション詳細レポートについて説明します。'
ms.openlocfilehash: 41d4b7d78c674afbc2136911913e88837a4f5095
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897244"
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a><span data-ttu-id="fcda6-103">ビジネス サーバーの Skype でのピア ツー ピア セッション詳細レポート</span><span class="sxs-lookup"><span data-stu-id="fcda6-103">Peer-to-Peer Session Detail Report in Skype for Business Server</span></span>
 
<span data-ttu-id="fcda6-104">**の概要:** ビジネス サーバーの Skype でピア ツー ピア セッション詳細レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fcda6-104">**Summary:** Learn about the Peer-to-Peer Session Detail Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="fcda6-p101">ピアツーピア セッション詳細レポートは、ピアツーピア セッションに関する詳細情報を提供します。たとえば、インスタント メッセージング セッションを選択すると、セッション中に 2 人のユーザーのそれぞれが送信したメッセージ数がレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcda6-p101">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session. For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="fcda6-107">ピアツーピア セッション詳細レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="fcda6-107">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="fcda6-108">ピアツーピア セッション詳細レポートには、次のいずれかのレポートからアクセスできます (これらのレポートはすべて、監視レポートのホーム ページからアクセスできます)。</span><span class="sxs-lookup"><span data-stu-id="fcda6-108">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>
  
- <span data-ttu-id="fcda6-109">IP 電話在庫レポート</span><span class="sxs-lookup"><span data-stu-id="fcda6-109">IP Phone Inventory Report</span></span>
    
- <span data-ttu-id="fcda6-110">ユーザー アクティビティ レポート</span><span class="sxs-lookup"><span data-stu-id="fcda6-110">User Activity Report</span></span>
    
- <span data-ttu-id="fcda6-111">通話受付管理レポート</span><span class="sxs-lookup"><span data-stu-id="fcda6-111">Call Admission Control Report</span></span>
    
- <span data-ttu-id="fcda6-112">エラー リスト レポート</span><span class="sxs-lookup"><span data-stu-id="fcda6-112">Failure List Report</span></span> 
    
<span data-ttu-id="fcda6-113">ピア ツー ピア セッション詳細レポート内からに診断レポート (詳細) のメトリックをクリックすると、 [Skype のビジネス サーバーの診断レポート](diagnostic-report.md)をアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fcda6-113">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Skype for Business Server](diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="fcda6-114">次のいずれかの指標をクリックしてトップ エラー レポートにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fcda6-114">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>
  
- <span data-ttu-id="fcda6-115">応答</span><span class="sxs-lookup"><span data-stu-id="fcda6-115">Response</span></span>
    
- <span data-ttu-id="fcda6-116">診断 ID</span><span class="sxs-lookup"><span data-stu-id="fcda6-116">Diagnostic ID</span></span>
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="fcda6-117">ピアツーピア セッション詳細レポートの有効活用</span><span class="sxs-lookup"><span data-stu-id="fcda6-117">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="fcda6-p103">ピアツーピア セッション詳細レポートには数多くの指標が含まれています。システム管理者にとって馴染みのないものも多いかもしれませんが、通常は、指標のラベルにマウス ポインターを置くと簡単な説明を示したヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcda6-p103">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators. Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>
  
<span data-ttu-id="fcda6-p104">レポートに表示される実際の指標は、選択したピアツーピア セッションの種類によって決まります。音声ビデオ セッションのレポートに表示される指標は、インスタント メッセージング セッションの指標とは異なります。</span><span class="sxs-lookup"><span data-stu-id="fcda6-p104">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected. An audio/video session will report a different set of metrics than an instant messaging session.</span></span>
  
<span data-ttu-id="fcda6-122">また、応答コードおよび診断 ID の指標にマウス ポインターを置くと、その値の説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcda6-122">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>
  
## <a name="filters"></a><span data-ttu-id="fcda6-123">フィルター</span><span class="sxs-lookup"><span data-stu-id="fcda6-123">Filters</span></span>

<span data-ttu-id="fcda6-p105">なし。ピアツーピア セッション詳細レポートはフィルターできません。</span><span class="sxs-lookup"><span data-stu-id="fcda6-p105">None. You cannot filter the Peer-to-Peer Session Detail Report.</span></span>
  
## <a name="session-information-metrics"></a><span data-ttu-id="fcda6-126">セッション情報の指標</span><span class="sxs-lookup"><span data-stu-id="fcda6-126">Session Information Metrics</span></span>

<span data-ttu-id="fcda6-127">次の表に、ピアツーピア セッション詳細レポートでセッションごとに提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="fcda6-127">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>
  
<span data-ttu-id="fcda6-128">**セッション情報の指標**</span><span class="sxs-lookup"><span data-stu-id="fcda6-128">**Session Information Metrics**</span></span>

|<span data-ttu-id="fcda6-129">**名前**</span><span class="sxs-lookup"><span data-stu-id="fcda6-129">**Name**</span></span>|<span data-ttu-id="fcda6-130">**説明**</span><span class="sxs-lookup"><span data-stu-id="fcda6-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fcda6-131">**[プールの FQDN]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-131">**Pool FQDN**</span></span> <br/> |<span data-ttu-id="fcda6-132">セッションに関与したレジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN) です。</span><span class="sxs-lookup"><span data-stu-id="fcda6-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span>  <br/> |
|<span data-ttu-id="fcda6-133">**[招待時間]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-133">**Invite time**</span></span> <br/> |<span data-ttu-id="fcda6-134">セッションへの招待が最初に送信された日時です。</span><span class="sxs-lookup"><span data-stu-id="fcda6-134">Date and time the session invitation was originally sent.</span></span>  <br/> |
|<span data-ttu-id="fcda6-135">**[応答時間]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-135">**Response time**</span></span> <br/> |<span data-ttu-id="fcda6-136">招待の承諾を受信した日時です。</span><span class="sxs-lookup"><span data-stu-id="fcda6-136">Date and time that the invitation acceptance was received.</span></span>  <br/> |
|<span data-ttu-id="fcda6-137">**[送信元ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-137">**From user**</span></span> <br/> |<span data-ttu-id="fcda6-138">セッションを開始したユーザーの SIP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="fcda6-138">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="fcda6-139">**[送信元ユーザー エージェント]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-139">**From user agent**</span></span> <br/> |<span data-ttu-id="fcda6-140">セッションを開始したユーザーのエンドポイントで使用されているソフトウェアです。</span><span class="sxs-lookup"><span data-stu-id="fcda6-140">Software used by the endpoint of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="fcda6-141">**[内部の送信元ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-141">**Is From user internal**</span></span> <br/> |<span data-ttu-id="fcda6-142">セッションを開始したユーザーが内部ネットワークにログオンしていたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fcda6-142">Indicates whether the user who initiated the session was logged on to the internal network.</span></span>  <br/> |
|<span data-ttu-id="fcda6-143">**[電話と統合された送信元ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-143">**Is From user integrated with desk phone**</span></span> <br/> |<span data-ttu-id="fcda6-144">セッションを開始したユーザーの使用するエンドポイントがそのユーザーのデスクトップ電話と統合されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fcda6-144">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span>  <br/> |
|<span data-ttu-id="fcda6-145">**[セッションの優先順位]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-145">**Session Priority**</span></span> <br/> |<span data-ttu-id="fcda6-p106">セッションに割り当てられた優先順位です。有効な優先順位として、不明、非緊急、標準、至急、および緊急があります。</span><span class="sxs-lookup"><span data-stu-id="fcda6-p106">Priority assigned to the session. Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span>  <br/> |
|<span data-ttu-id="fcda6-148">**[応答コード]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-148">**Response code**</span></span> <br/> |<span data-ttu-id="fcda6-149">セッションが失敗したときに送信された SIP 応答コードです。</span><span class="sxs-lookup"><span data-stu-id="fcda6-149">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="fcda6-150">**[フロントエンド]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-150">**Front end**</span></span> <br/> |<span data-ttu-id="fcda6-151">電話会議で使用されたフロントエンド サーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="fcda6-151">Name of the Front End Server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="fcda6-152">**[キャプチャ時刻]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-152">**Capture time**</span></span> <br/> |<span data-ttu-id="fcda6-153">セッションの情報が記録された日時です。</span><span class="sxs-lookup"><span data-stu-id="fcda6-153">Date and time that the session information was recorded.</span></span>  <br/> |
|<span data-ttu-id="fcda6-154">**[終了時刻]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-154">**End time**</span></span> <br/> |<span data-ttu-id="fcda6-155">セッションが終了した日時です。</span><span class="sxs-lookup"><span data-stu-id="fcda6-155">Date and time the session ended.</span></span>  <br/> |
|<span data-ttu-id="fcda6-156">**[送信先ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-156">**To user**</span></span> <br/> |<span data-ttu-id="fcda6-157">セッションに招待されたユーザーの SIP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="fcda6-157">SIP address of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="fcda6-158">**[送信先ユーザー エージェント]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-158">**To user agent**</span></span> <br/> |<span data-ttu-id="fcda6-159">セッションに招待されたユーザーのエンドポイントで使用されているソフトウェアです。</span><span class="sxs-lookup"><span data-stu-id="fcda6-159">Software used by the endpoint of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="fcda6-160">**[内部の送信先ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-160">**Is To user internal**</span></span> <br/> |<span data-ttu-id="fcda6-161">セッションに招待されたユーザーが内部ネットワークにログオンしていたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fcda6-161">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span>  <br/> |
|<span data-ttu-id="fcda6-162">**[電話と統合された送信先ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-162">**Is To user integrated with desk phone**</span></span> <br/> |<span data-ttu-id="fcda6-163">セッションに招待されたユーザーの使用するエンドポイントがそのユーザーのデスクトップ電話と統合されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fcda6-163">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span>  <br/> |
|<span data-ttu-id="fcda6-164">**[再試行セッション]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-164">**Is retried session**</span></span> <br/> |<span data-ttu-id="fcda6-165">以前エラーが発生したセッションを再試行するためのセッションかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fcda6-165">Indicates whether the session is an attempt to retry a session that previously failed.</span></span>  <br/> |
|<span data-ttu-id="fcda6-166">**[診断 ID]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-166">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="fcda6-p107">エラーのトラブルシューティングに役立つ情報を得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。マウス ポインターを ID 番号の上に置くと、その ID に関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcda6-p107">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Hold the mouse over the ID number to view additional information about that ID.</span></span>  <br/> |
   
## <a name="metrics-for-modalities"></a><span data-ttu-id="fcda6-169">モダリティの指標</span><span class="sxs-lookup"><span data-stu-id="fcda6-169">Metrics for Modalities</span></span>

<span data-ttu-id="fcda6-170">次の表に、ピアツーピア セッション詳細レポートでセッションのモダリティごとに提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="fcda6-170">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>
  
<span data-ttu-id="fcda6-171">**モダリティの指標**</span><span class="sxs-lookup"><span data-stu-id="fcda6-171">**Metrics for Modalities**</span></span>

|<span data-ttu-id="fcda6-172">**名前**</span><span class="sxs-lookup"><span data-stu-id="fcda6-172">**Name**</span></span>|<span data-ttu-id="fcda6-173">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="fcda6-173">**Can you sort on this item?**</span></span>|<span data-ttu-id="fcda6-174">**説明**</span><span class="sxs-lookup"><span data-stu-id="fcda6-174">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fcda6-175">**[モダリティ]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-175">**Modalities**</span></span> <br/> |<span data-ttu-id="fcda6-176">いいえ</span><span class="sxs-lookup"><span data-stu-id="fcda6-176">No</span></span>  <br/> |<span data-ttu-id="fcda6-p108">セッションで使用されるモダリティです (インスタント メッセージング (IM)、ファイル送信など)。</span><span class="sxs-lookup"><span data-stu-id="fcda6-p108">Modalities used in the session. For example, instant messaging (IM) or file transfer.</span></span>  <br/> |
|<span data-ttu-id="fcda6-179">**[送信元ユーザー メッセージ]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-179">**From user messages**</span></span> <br/> |<span data-ttu-id="fcda6-180">いいえ</span><span class="sxs-lookup"><span data-stu-id="fcda6-180">No</span></span>  <br/> |<span data-ttu-id="fcda6-181">セッションを開始したユーザーが送信したメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="fcda6-181">Number of messages sent by the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="fcda6-182">**[送信先ユーザー メッセージ]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-182">**To user messages**</span></span> <br/> |<span data-ttu-id="fcda6-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="fcda6-183">No</span></span>  <br/> |<span data-ttu-id="fcda6-184">セッションに招待されたユーザーが送信したメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="fcda6-184">Number of messages sent by the user who was invited to join the session.</span></span>  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="fcda6-185">診断レポートの指標</span><span class="sxs-lookup"><span data-stu-id="fcda6-185">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="fcda6-186">次の表に、ピアツーピア セッション詳細レポートで診断レポートごとに提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="fcda6-186">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>
  
<span data-ttu-id="fcda6-187">**診断レポートの指標**</span><span class="sxs-lookup"><span data-stu-id="fcda6-187">**Metrics for Diagnostic Reports**</span></span>

|<span data-ttu-id="fcda6-188">**名前**</span><span class="sxs-lookup"><span data-stu-id="fcda6-188">**Name**</span></span>|<span data-ttu-id="fcda6-189">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="fcda6-189">**Can you sort on this item?**</span></span>|<span data-ttu-id="fcda6-190">**説明**</span><span class="sxs-lookup"><span data-stu-id="fcda6-190">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fcda6-191">**[詳細]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-191">**Detail**</span></span> <br/> |<span data-ttu-id="fcda6-192">いいえ</span><span class="sxs-lookup"><span data-stu-id="fcda6-192">No</span></span>  <br/> |<span data-ttu-id="fcda6-193">この項目をクリックすると、セッションの診断レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcda6-193">When you click this item, the report shows the Diagnostic Report for the session.</span></span>  <br/> |
|<span data-ttu-id="fcda6-194">**[レポート時刻]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-194">**Report time**</span></span> <br/> |<span data-ttu-id="fcda6-195">いいえ</span><span class="sxs-lookup"><span data-stu-id="fcda6-195">No</span></span>  <br/> |<span data-ttu-id="fcda6-196">レポートが記録された日時。</span><span class="sxs-lookup"><span data-stu-id="fcda6-196">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="fcda6-197">**要求**</span><span class="sxs-lookup"><span data-stu-id="fcda6-197">**Request**</span></span> <br/> |<span data-ttu-id="fcda6-198">いいえ</span><span class="sxs-lookup"><span data-stu-id="fcda6-198">No</span></span>  <br/> |<span data-ttu-id="fcda6-p109">SIP 要求の種類です (INVITE、BYE など)。</span><span class="sxs-lookup"><span data-stu-id="fcda6-p109">SIP request type. For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="fcda6-201">**[診断 ID]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-201">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="fcda6-202">いいえ</span><span class="sxs-lookup"><span data-stu-id="fcda6-202">No</span></span>  <br/> |<span data-ttu-id="fcda6-203">SIP メッセージに (ms-diagnostics ヘッダーの形で) 添付された一意の識別子。多くの場合、この情報はトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fcda6-203">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="fcda6-204">**コンテンツの種類**</span><span class="sxs-lookup"><span data-stu-id="fcda6-204">**Content type**</span></span> <br/> |<span data-ttu-id="fcda6-205">いいえ</span><span class="sxs-lookup"><span data-stu-id="fcda6-205">No</span></span>  <br/> |<span data-ttu-id="fcda6-p110">会議で使用されたメディア コンテンツの種類です。たとえば、一般的なコンテンツの種類は "アプリケーション/sdp" です。セッション記述プロトコル (SDP) は、セッションのアナウンス、セッションへの招待、およびその他の形のマルチメディア セッションの開始で使用される標準的なインターネット プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="fcda6-p110">Type of media content used in the conference. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span>  <br/> |
|<span data-ttu-id="fcda6-209">**[レポート作成者]**</span><span class="sxs-lookup"><span data-stu-id="fcda6-209">**Reported by**</span></span> <br/> |<span data-ttu-id="fcda6-210">不可</span><span class="sxs-lookup"><span data-stu-id="fcda6-210">No</span></span>  <br/> |<span data-ttu-id="fcda6-211">問題を報告したコンピューター (クライアントまたはサーバー) です。</span><span class="sxs-lookup"><span data-stu-id="fcda6-211">Computer (that is, client or server) that reported the problem.</span></span>  <br/> |
   

