---
title: Skype for Business Server 2015 の会議詳細レポート
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: '概要: は、会議の詳細] レポートには、ビジネス サーバー 2015 の Skype の使用について説明します。'
ms.openlocfilehash: 4c55b2f339aa3d591f01d73d0f60d8fbc0bb483f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="conference-detail-report-in-skype-for-business-server-2015"></a><span data-ttu-id="bed04-103">Skype for Business Server 2015 の会議詳細レポート</span><span class="sxs-lookup"><span data-stu-id="bed04-103">Conference Detail Report in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bed04-104">**の概要:**ビジネス サーバー 2015 の Skype で使用する会議の詳細レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bed04-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="bed04-p101">会議詳細レポートには、電話会議に参加したすべてのユーザーに関する詳細な情報が示されます。たとえば、ユーザーが会議に参加した日時、ユーザーが電話会議から退場した日時、ユーザーが電話会議に接続するときに使用したエンドポイントのユーザー エージェントなどの情報を確認できます。各電話会議におけるユーザーの役割 (発表者、参加者など) に関する情報も確認できます。おそらく最も重要なことは、会議への参加と終了が正常に行われたユーザーと正常に行われなかったユーザーを簡単に確認できることです。</span><span class="sxs-lookup"><span data-stu-id="bed04-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>
  
## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="bed04-109">会議詳細レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="bed04-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="bed04-110">会議詳細レポートには、次のレポートからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bed04-110">The Conference Detail Report can be accessed from the following reports:</span></span>
  
- <span data-ttu-id="bed04-111">[ビジネス サーバー 2015 の Skype での受付管理レポートの呼び出し](call-admission-control-report.md)] をクリックして、会議の詳細] のメトリック)</span><span class="sxs-lookup"><span data-stu-id="bed04-111">The [Call Admission Control Report in Skype for Business Server 2015](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>
    
- <span data-ttu-id="bed04-112">[ビジネス サーバー 2015 の Skype の障害] ボックスの一覧のレポート](failure-list-report.md)] をクリックして会議の指標)</span><span class="sxs-lookup"><span data-stu-id="bed04-112">The [Failure List Report in Skype for Business Server 2015](failure-list-report.md) (by clicking the Conference metric)</span></span>
    
- <span data-ttu-id="bed04-113">[ビジネス サーバー 2015 の Skype でのユーザー アクティビティ レポート](user-activity-report.md)] をクリックして会議 URI メトリック)</span><span class="sxs-lookup"><span data-stu-id="bed04-113">The [User Activity Report in Skype for Business Server 2015](user-activity-report.md) (by clicking the Conference URI metric)</span></span>
    
<span data-ttu-id="bed04-114">[会議の詳細] レポートからは、診断レポート (詳細) のメトリックをクリックすると、[ビジネス サーバー 2015 の Skype で診断レポート](diagnostic-report.md)を表示できます。</span><span class="sxs-lookup"><span data-stu-id="bed04-114">From the Conference Detail Report you can access the [Diagnostic Report in Skype for Business Server 2015](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>
  
## <a name="filters"></a><span data-ttu-id="bed04-115">フィルター</span><span class="sxs-lookup"><span data-stu-id="bed04-115">Filters</span></span>

<span data-ttu-id="bed04-p102">なし。会議詳細レポートにはフィルターを適用できません。</span><span class="sxs-lookup"><span data-stu-id="bed04-p102">None. You cannot filter on the Conference Detail Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="bed04-118">指標</span><span class="sxs-lookup"><span data-stu-id="bed04-118">Metrics</span></span>

<span data-ttu-id="bed04-119">次の表は、会議詳細レポートの [電話会議情報] セクションに提供される情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="bed04-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>
  
<span data-ttu-id="bed04-120">**会議情報の測定値**</span><span class="sxs-lookup"><span data-stu-id="bed04-120">**Conference Information Metrics**</span></span>

|<span data-ttu-id="bed04-121">**名**</span><span class="sxs-lookup"><span data-stu-id="bed04-121">**Name**</span></span>|<span data-ttu-id="bed04-122">**説明**</span><span class="sxs-lookup"><span data-stu-id="bed04-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bed04-123">**[会議 URI]**</span><span class="sxs-lookup"><span data-stu-id="bed04-123">**Conference URI**</span></span> <br/> |<span data-ttu-id="bed04-p103">電話会議に割り当てられる URI。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bed04-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="bed04-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="bed04-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
|<span data-ttu-id="bed04-127">**[プールの FQDN]**</span><span class="sxs-lookup"><span data-stu-id="bed04-127">**Pool FQDN**</span></span> <br/> |<span data-ttu-id="bed04-128">セッションに関係するレジストラー プールまたはエッジ サーバーの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="bed04-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/> |
|<span data-ttu-id="bed04-129">**[開始時刻]**</span><span class="sxs-lookup"><span data-stu-id="bed04-129">**Start time**</span></span> <br/> |<span data-ttu-id="bed04-130">会議が開始した日時。</span><span class="sxs-lookup"><span data-stu-id="bed04-130">Date and time that the conference started.</span></span>  <br/> |
|<span data-ttu-id="bed04-131">**[開催者]**</span><span class="sxs-lookup"><span data-stu-id="bed04-131">**Organizer**</span></span> <br/> |<span data-ttu-id="bed04-132">会議を開催したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="bed04-132">SIP address of the user who organized the conference.</span></span>  <br/> |
|<span data-ttu-id="bed04-133">**[終了時刻]**</span><span class="sxs-lookup"><span data-stu-id="bed04-133">**End time**</span></span> <br/> |<span data-ttu-id="bed04-134">会議が終了した日時。</span><span class="sxs-lookup"><span data-stu-id="bed04-134">Date and time that the conference ended.</span></span>  <br/> |
   
<span data-ttu-id="bed04-135">次の表は、会議詳細レポートの [電話会議の参加] セクションに提供される情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="bed04-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>
  
<span data-ttu-id="bed04-136">**会議への参加基準**</span><span class="sxs-lookup"><span data-stu-id="bed04-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="bed04-137">**名**</span><span class="sxs-lookup"><span data-stu-id="bed04-137">**Name**</span></span>|<span data-ttu-id="bed04-138">**説明**</span><span class="sxs-lookup"><span data-stu-id="bed04-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bed04-139">**[ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="bed04-139">**User**</span></span> <br/> |<span data-ttu-id="bed04-140">会議に参加したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="bed04-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="bed04-141">**[役割]**</span><span class="sxs-lookup"><span data-stu-id="bed04-141">**Role**</span></span> <br/> |<span data-ttu-id="bed04-142">電話会議の参加者が担った役割 (発表者など)。</span><span class="sxs-lookup"><span data-stu-id="bed04-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="bed04-143">**[接続]**</span><span class="sxs-lookup"><span data-stu-id="bed04-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="bed04-144">参加者のネットワーク接続 (一般には内部送信元または外部送信元)。</span><span class="sxs-lookup"><span data-stu-id="bed04-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="bed04-145">**[参加時間]**</span><span class="sxs-lookup"><span data-stu-id="bed04-145">**Join time**</span></span> <br/> |<span data-ttu-id="bed04-146">参加者が電話会議に参加した日時。</span><span class="sxs-lookup"><span data-stu-id="bed04-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="bed04-147">**[退場時間]**</span><span class="sxs-lookup"><span data-stu-id="bed04-147">**Leave time**</span></span> <br/> |<span data-ttu-id="bed04-148">参加者が電話会議から退出した日時。</span><span class="sxs-lookup"><span data-stu-id="bed04-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="bed04-149">**[ユーザー エージェント]**</span><span class="sxs-lookup"><span data-stu-id="bed04-149">**User agent**</span></span> <br/> |<span data-ttu-id="bed04-150">参加者のエンドポイントによって使用されるソフトウェアの識別子です。</span><span class="sxs-lookup"><span data-stu-id="bed04-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="bed04-151">**[診断レポート]**</span><span class="sxs-lookup"><span data-stu-id="bed04-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="bed04-p104">診断およびトラブルシューティングの情報を提供します。失敗したセッションの SIP 応答コード、診断ヘッダー、電話会議参加時間、診断 ID などがあります。</span><span class="sxs-lookup"><span data-stu-id="bed04-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |
   
<span data-ttu-id="bed04-154">会議の様相のセクションで、会議の詳細] レポートの情報を次の表に一覧します。</span><span class="sxs-lookup"><span data-stu-id="bed04-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>
  
<span data-ttu-id="bed04-155">**会議の様相の評価尺度**</span><span class="sxs-lookup"><span data-stu-id="bed04-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="bed04-156">**名**</span><span class="sxs-lookup"><span data-stu-id="bed04-156">**Name**</span></span>|<span data-ttu-id="bed04-157">**説明**</span><span class="sxs-lookup"><span data-stu-id="bed04-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bed04-158">**[ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="bed04-158">**User**</span></span> <br/> |<span data-ttu-id="bed04-159">会議に参加したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="bed04-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="bed04-160">**[参加時間]**</span><span class="sxs-lookup"><span data-stu-id="bed04-160">**Join time**</span></span> <br/> |<span data-ttu-id="bed04-161">参加者が電話会議に参加した日時。</span><span class="sxs-lookup"><span data-stu-id="bed04-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="bed04-162">**[退場時間]**</span><span class="sxs-lookup"><span data-stu-id="bed04-162">**Leave time**</span></span> <br/> |<span data-ttu-id="bed04-163">参加者が電話会議を退場した日時。</span><span class="sxs-lookup"><span data-stu-id="bed04-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="bed04-164">**[電話会議サーバー URI]**</span><span class="sxs-lookup"><span data-stu-id="bed04-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="bed04-165">電話会議で使用された電話会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="bed04-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="bed04-166">**[診断レポート]**</span><span class="sxs-lookup"><span data-stu-id="bed04-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="bed04-p105">診断およびトラブルシューティングの情報を提供します。失敗したセッションの SIP 応答コード、診断ヘッダー、電話会議参加時間、診断 ID などがあります。</span><span class="sxs-lookup"><span data-stu-id="bed04-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |
   

