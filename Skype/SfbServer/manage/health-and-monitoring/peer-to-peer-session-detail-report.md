---
title: Skype for Business Server のピアツーピアセッションの詳細レポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: '概要: Skype for Business Server のピアツーピアセッションの詳細レポートについて説明します。'
ms.openlocfilehash: 4c6b05e6e4e4110a43c21dbdbbc7f190ecae98ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817776"
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a><span data-ttu-id="0e267-103">Skype for Business Server のピアツーピアセッションの詳細レポート</span><span class="sxs-lookup"><span data-stu-id="0e267-103">Peer-to-Peer Session Detail Report in Skype for Business Server</span></span>
 
<span data-ttu-id="0e267-104">**概要:** Skype for Business Server のピアツーピアセッションの詳細レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0e267-104">**Summary:** Learn about the Peer-to-Peer Session Detail Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="0e267-p101">ピアツーピア セッション詳細レポートは、ピアツーピア セッションに関する詳細情報を提供します。たとえば、インスタント メッセージング セッションを選択すると、セッション中に 2 人のユーザーのそれぞれが送信したメッセージ数がレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e267-p101">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session. For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="0e267-107">ピアツーピア セッション詳細レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="0e267-107">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="0e267-108">ピアツーピア セッション詳細レポートには、次のいずれかのレポートからアクセスできます (これらのレポートはすべて、監視レポートのホーム ページからアクセスできます)。</span><span class="sxs-lookup"><span data-stu-id="0e267-108">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>
  
- <span data-ttu-id="0e267-109">IP 電話在庫レポート</span><span class="sxs-lookup"><span data-stu-id="0e267-109">IP Phone Inventory Report</span></span>
    
- <span data-ttu-id="0e267-110">ユーザー アクティビティ レポート</span><span class="sxs-lookup"><span data-stu-id="0e267-110">User Activity Report</span></span>
    
- <span data-ttu-id="0e267-111">通話受付管理レポート</span><span class="sxs-lookup"><span data-stu-id="0e267-111">Call Admission Control Report</span></span>
    
- <span data-ttu-id="0e267-112">エラー リスト レポート</span><span class="sxs-lookup"><span data-stu-id="0e267-112">Failure List Report</span></span> 
    
<span data-ttu-id="0e267-113">ピアツーピアセッションの詳細レポート内から、診断レポート (詳細) メトリックをクリックして、 [Skype For Business Server の診断レポート](diagnostic-report.md)にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0e267-113">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Skype for Business Server](diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="0e267-114">次のいずれかの指標をクリックしてトップ エラー レポートにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0e267-114">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>
  
- <span data-ttu-id="0e267-115">応答</span><span class="sxs-lookup"><span data-stu-id="0e267-115">Response</span></span>
    
- <span data-ttu-id="0e267-116">診断 ID</span><span class="sxs-lookup"><span data-stu-id="0e267-116">Diagnostic ID</span></span>
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="0e267-117">ピアツーピア セッション詳細レポートの有効活用</span><span class="sxs-lookup"><span data-stu-id="0e267-117">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="0e267-p103">ピアツーピア セッション詳細レポートには数多くの指標が含まれています。システム管理者にとって馴染みのないものも多いかもしれませんが、通常は、指標のラベルにマウス ポインターを置くと簡単な説明を示したヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e267-p103">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators. Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>
  
<span data-ttu-id="0e267-p104">レポートに表示される実際の指標は、選択したピアツーピア セッションの種類によって決まります。音声ビデオ セッションのレポートに表示される指標は、インスタント メッセージング セッションの指標とは異なります。</span><span class="sxs-lookup"><span data-stu-id="0e267-p104">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected. An audio/video session will report a different set of metrics than an instant messaging session.</span></span>
  
<span data-ttu-id="0e267-122">また、応答コードおよび診断 ID の指標にマウス ポインターを置くと、その値の説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e267-122">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>
  
## <a name="filters"></a><span data-ttu-id="0e267-123">フィルター</span><span class="sxs-lookup"><span data-stu-id="0e267-123">Filters</span></span>

<span data-ttu-id="0e267-p105">なし。ピアツーピア セッション詳細レポートはフィルターできません。</span><span class="sxs-lookup"><span data-stu-id="0e267-p105">None. You cannot filter the Peer-to-Peer Session Detail Report.</span></span>
  
## <a name="session-information-metrics"></a><span data-ttu-id="0e267-126">セッション情報の指標</span><span class="sxs-lookup"><span data-stu-id="0e267-126">Session Information Metrics</span></span>

<span data-ttu-id="0e267-127">次の表に、ピアツーピア セッション詳細レポートでセッションごとに提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0e267-127">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>
  
<span data-ttu-id="0e267-128">**セッション情報の指標**</span><span class="sxs-lookup"><span data-stu-id="0e267-128">**Session Information Metrics**</span></span>

|<span data-ttu-id="0e267-129">**名前**</span><span class="sxs-lookup"><span data-stu-id="0e267-129">**Name**</span></span>|<span data-ttu-id="0e267-130">**説明**</span><span class="sxs-lookup"><span data-stu-id="0e267-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0e267-131">**[プールの FQDN]**</span><span class="sxs-lookup"><span data-stu-id="0e267-131">**Pool FQDN**</span></span> <br/> |<span data-ttu-id="0e267-132">セッションに関与したレジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN) です。</span><span class="sxs-lookup"><span data-stu-id="0e267-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span>  <br/> |
|<span data-ttu-id="0e267-133">**[招待時間]**</span><span class="sxs-lookup"><span data-stu-id="0e267-133">**Invite time**</span></span> <br/> |<span data-ttu-id="0e267-134">セッションへの招待が最初に送信された日時です。</span><span class="sxs-lookup"><span data-stu-id="0e267-134">Date and time the session invitation was originally sent.</span></span>  <br/> |
|<span data-ttu-id="0e267-135">**[応答時間]**</span><span class="sxs-lookup"><span data-stu-id="0e267-135">**Response time**</span></span> <br/> |<span data-ttu-id="0e267-136">招待の承諾を受信した日時です。</span><span class="sxs-lookup"><span data-stu-id="0e267-136">Date and time that the invitation acceptance was received.</span></span>  <br/> |
|<span data-ttu-id="0e267-137">**[送信元ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="0e267-137">**From user**</span></span> <br/> |<span data-ttu-id="0e267-138">セッションを開始したユーザーの SIP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="0e267-138">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="0e267-139">**[送信元ユーザー エージェント]**</span><span class="sxs-lookup"><span data-stu-id="0e267-139">**From user agent**</span></span> <br/> |<span data-ttu-id="0e267-140">セッションを開始したユーザーのエンドポイントで使用されているソフトウェアです。</span><span class="sxs-lookup"><span data-stu-id="0e267-140">Software used by the endpoint of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="0e267-141">**[内部の送信元ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="0e267-141">**Is From user internal**</span></span> <br/> |<span data-ttu-id="0e267-142">セッションを開始したユーザーが内部ネットワークにログオンしていたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0e267-142">Indicates whether the user who initiated the session was logged on to the internal network.</span></span>  <br/> |
|<span data-ttu-id="0e267-143">**[電話と統合された送信元ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="0e267-143">**Is From user integrated with desk phone**</span></span> <br/> |<span data-ttu-id="0e267-144">セッションを開始したユーザーの使用するエンドポイントがそのユーザーのデスクトップ電話と統合されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0e267-144">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span>  <br/> |
|<span data-ttu-id="0e267-145">**[セッションの優先順位]**</span><span class="sxs-lookup"><span data-stu-id="0e267-145">**Session Priority**</span></span> <br/> |<span data-ttu-id="0e267-p106">セッションに割り当てられた優先順位です。有効な優先順位として、不明、非緊急、標準、至急、および緊急があります。</span><span class="sxs-lookup"><span data-stu-id="0e267-p106">Priority assigned to the session. Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span>  <br/> |
|<span data-ttu-id="0e267-148">**[応答コード]**</span><span class="sxs-lookup"><span data-stu-id="0e267-148">**Response code**</span></span> <br/> |<span data-ttu-id="0e267-149">セッションが失敗したときに送信された SIP 応答コードです。</span><span class="sxs-lookup"><span data-stu-id="0e267-149">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="0e267-150">**[フロントエンド]**</span><span class="sxs-lookup"><span data-stu-id="0e267-150">**Front end**</span></span> <br/> |<span data-ttu-id="0e267-151">電話会議で使用されたフロントエンド サーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="0e267-151">Name of the Front End Server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="0e267-152">**[キャプチャ時刻]**</span><span class="sxs-lookup"><span data-stu-id="0e267-152">**Capture time**</span></span> <br/> |<span data-ttu-id="0e267-153">セッションの情報が記録された日時です。</span><span class="sxs-lookup"><span data-stu-id="0e267-153">Date and time that the session information was recorded.</span></span>  <br/> |
|<span data-ttu-id="0e267-154">**[終了時刻]**</span><span class="sxs-lookup"><span data-stu-id="0e267-154">**End time**</span></span> <br/> |<span data-ttu-id="0e267-155">セッションが終了した日時です。</span><span class="sxs-lookup"><span data-stu-id="0e267-155">Date and time the session ended.</span></span>  <br/> |
|<span data-ttu-id="0e267-156">**[送信先ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="0e267-156">**To user**</span></span> <br/> |<span data-ttu-id="0e267-157">セッションに招待されたユーザーの SIP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="0e267-157">SIP address of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="0e267-158">**[送信先ユーザー エージェント]**</span><span class="sxs-lookup"><span data-stu-id="0e267-158">**To user agent**</span></span> <br/> |<span data-ttu-id="0e267-159">セッションに招待されたユーザーのエンドポイントで使用されているソフトウェアです。</span><span class="sxs-lookup"><span data-stu-id="0e267-159">Software used by the endpoint of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="0e267-160">**[内部の送信先ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="0e267-160">**Is To user internal**</span></span> <br/> |<span data-ttu-id="0e267-161">セッションに招待されたユーザーが内部ネットワークにログオンしていたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0e267-161">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span>  <br/> |
|<span data-ttu-id="0e267-162">**[電話と統合された送信先ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="0e267-162">**Is To user integrated with desk phone**</span></span> <br/> |<span data-ttu-id="0e267-163">セッションに招待されたユーザーの使用するエンドポイントがそのユーザーのデスクトップ電話と統合されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0e267-163">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span>  <br/> |
|<span data-ttu-id="0e267-164">**[再試行セッション]**</span><span class="sxs-lookup"><span data-stu-id="0e267-164">**Is retried session**</span></span> <br/> |<span data-ttu-id="0e267-165">以前エラーが発生したセッションを再試行するためのセッションかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0e267-165">Indicates whether the session is an attempt to retry a session that previously failed.</span></span>  <br/> |
|<span data-ttu-id="0e267-166">**[診断 ID]**</span><span class="sxs-lookup"><span data-stu-id="0e267-166">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="0e267-p107">エラーのトラブルシューティングに役立つ情報を得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。マウス ポインターを ID 番号の上に置くと、その ID に関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e267-p107">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Hold the mouse over the ID number to view additional information about that ID.</span></span>  <br/> |
   
## <a name="metrics-for-modalities"></a><span data-ttu-id="0e267-169">モダリティの指標</span><span class="sxs-lookup"><span data-stu-id="0e267-169">Metrics for Modalities</span></span>

<span data-ttu-id="0e267-170">次の表に、ピアツーピア セッション詳細レポートでセッションのモダリティごとに提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0e267-170">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>
  
<span data-ttu-id="0e267-171">**モダリティの指標**</span><span class="sxs-lookup"><span data-stu-id="0e267-171">**Metrics for Modalities**</span></span>

|<span data-ttu-id="0e267-172">**名前**</span><span class="sxs-lookup"><span data-stu-id="0e267-172">**Name**</span></span>|<span data-ttu-id="0e267-173">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="0e267-173">**Can you sort on this item?**</span></span>|<span data-ttu-id="0e267-174">**説明**</span><span class="sxs-lookup"><span data-stu-id="0e267-174">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e267-175">**[モダリティ]**</span><span class="sxs-lookup"><span data-stu-id="0e267-175">**Modalities**</span></span> <br/> |<span data-ttu-id="0e267-176">いいえ</span><span class="sxs-lookup"><span data-stu-id="0e267-176">No</span></span>  <br/> |<span data-ttu-id="0e267-p108">セッションで使用されるモダリティです (インスタント メッセージング (IM)、ファイル送信など)。</span><span class="sxs-lookup"><span data-stu-id="0e267-p108">Modalities used in the session. For example, instant messaging (IM) or file transfer.</span></span>  <br/> |
|<span data-ttu-id="0e267-179">**[送信元ユーザー メッセージ]**</span><span class="sxs-lookup"><span data-stu-id="0e267-179">**From user messages**</span></span> <br/> |<span data-ttu-id="0e267-180">いいえ</span><span class="sxs-lookup"><span data-stu-id="0e267-180">No</span></span>  <br/> |<span data-ttu-id="0e267-181">セッションを開始したユーザーが送信したメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="0e267-181">Number of messages sent by the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="0e267-182">**[送信先ユーザー メッセージ]**</span><span class="sxs-lookup"><span data-stu-id="0e267-182">**To user messages**</span></span> <br/> |<span data-ttu-id="0e267-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="0e267-183">No</span></span>  <br/> |<span data-ttu-id="0e267-184">セッションに招待されたユーザーが送信したメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="0e267-184">Number of messages sent by the user who was invited to join the session.</span></span>  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="0e267-185">診断レポートの指標</span><span class="sxs-lookup"><span data-stu-id="0e267-185">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="0e267-186">次の表に、ピアツーピア セッション詳細レポートで診断レポートごとに提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0e267-186">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>
  
<span data-ttu-id="0e267-187">**診断レポートの指標**</span><span class="sxs-lookup"><span data-stu-id="0e267-187">**Metrics for Diagnostic Reports**</span></span>

|<span data-ttu-id="0e267-188">**名前**</span><span class="sxs-lookup"><span data-stu-id="0e267-188">**Name**</span></span>|<span data-ttu-id="0e267-189">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="0e267-189">**Can you sort on this item?**</span></span>|<span data-ttu-id="0e267-190">**説明**</span><span class="sxs-lookup"><span data-stu-id="0e267-190">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e267-191">**[詳細]**</span><span class="sxs-lookup"><span data-stu-id="0e267-191">**Detail**</span></span> <br/> |<span data-ttu-id="0e267-192">いいえ</span><span class="sxs-lookup"><span data-stu-id="0e267-192">No</span></span>  <br/> |<span data-ttu-id="0e267-193">この項目をクリックすると、セッションの診断レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e267-193">When you click this item, the report shows the Diagnostic Report for the session.</span></span>  <br/> |
|<span data-ttu-id="0e267-194">**[レポート時刻]**</span><span class="sxs-lookup"><span data-stu-id="0e267-194">**Report time**</span></span> <br/> |<span data-ttu-id="0e267-195">いいえ</span><span class="sxs-lookup"><span data-stu-id="0e267-195">No</span></span>  <br/> |<span data-ttu-id="0e267-196">レポートが記録された日時。</span><span class="sxs-lookup"><span data-stu-id="0e267-196">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="0e267-197">**要求**</span><span class="sxs-lookup"><span data-stu-id="0e267-197">**Request**</span></span> <br/> |<span data-ttu-id="0e267-198">いいえ</span><span class="sxs-lookup"><span data-stu-id="0e267-198">No</span></span>  <br/> |<span data-ttu-id="0e267-p109">SIP 要求の種類です (INVITE、BYE など)。</span><span class="sxs-lookup"><span data-stu-id="0e267-p109">SIP request type. For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="0e267-201">**[診断 ID]**</span><span class="sxs-lookup"><span data-stu-id="0e267-201">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="0e267-202">いいえ</span><span class="sxs-lookup"><span data-stu-id="0e267-202">No</span></span>  <br/> |<span data-ttu-id="0e267-203">SIP メッセージに (ms-diagnostics ヘッダーの形で) 添付された一意の識別子。多くの場合、この情報はトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0e267-203">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="0e267-204">**コンテンツの種類**</span><span class="sxs-lookup"><span data-stu-id="0e267-204">**Content type**</span></span> <br/> |<span data-ttu-id="0e267-205">いいえ</span><span class="sxs-lookup"><span data-stu-id="0e267-205">No</span></span>  <br/> |<span data-ttu-id="0e267-p110">会議で使用されたメディア コンテンツの種類です。たとえば、一般的なコンテンツの種類は "アプリケーション/sdp" です。セッション記述プロトコル (SDP) は、セッションのアナウンス、セッションへの招待、およびその他の形のマルチメディア セッションの開始で使用される標準的なインターネット プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="0e267-p110">Type of media content used in the conference. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span>  <br/> |
|<span data-ttu-id="0e267-209">**[レポート作成者]**</span><span class="sxs-lookup"><span data-stu-id="0e267-209">**Reported by**</span></span> <br/> |<span data-ttu-id="0e267-210">不可</span><span class="sxs-lookup"><span data-stu-id="0e267-210">No</span></span>  <br/> |<span data-ttu-id="0e267-211">問題を報告したコンピューター (クライアントまたはサーバー) です。</span><span class="sxs-lookup"><span data-stu-id="0e267-211">Computer (that is, client or server) that reported the problem.</span></span>  <br/> |
   

