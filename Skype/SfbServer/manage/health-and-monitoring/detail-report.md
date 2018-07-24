---
title: ビジネス サーバーの Skype で会議の詳細] レポート
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: '概要: は、会議の詳細] レポートには、Skype ビジネス サーバーの使用について説明します。'
ms.openlocfilehash: ebccaf35464c54eac6c1b8c5a2febf2ebea02b7e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20971316"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="83ce8-103">ビジネス サーバーの Skype で会議の詳細] レポート</span><span class="sxs-lookup"><span data-stu-id="83ce8-103">Conference Detail Report in Skype for Business Server</span></span>
 
<span data-ttu-id="83ce8-104">**の概要:** 会議の詳細] レポートには、Skype ビジネス サーバーの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="83ce8-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>
  
<span data-ttu-id="83ce8-p101">会議詳細レポートには、電話会議に参加したすべてのユーザーに関する詳細な情報が示されます。たとえば、ユーザーが会議に参加した日時、ユーザーが電話会議から退場した日時、ユーザーが電話会議に接続するときに使用したエンドポイントのユーザー エージェントなどの情報を確認できます。各電話会議におけるユーザーの役割 (発表者、参加者など) に関する情報も確認できます。おそらく最も重要なことは、会議への参加と終了が正常に行われたユーザーと正常に行われなかったユーザーを簡単に確認できることです。</span><span class="sxs-lookup"><span data-stu-id="83ce8-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>
  
## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="83ce8-109">会議詳細レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="83ce8-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="83ce8-110">会議詳細レポートには、次のレポートからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="83ce8-110">The Conference Detail Report can be accessed from the following reports:</span></span>
  
- <span data-ttu-id="83ce8-111">[ビジネス サーバーの Skype での受付管理レポートの呼び出し](call-admission-control-report.md)] をクリックして、会議の詳細] のメトリック)</span><span class="sxs-lookup"><span data-stu-id="83ce8-111">The [Call Admission Control Report in Skype for Business Server](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>
    
- <span data-ttu-id="83ce8-112">[Skype ビジネス サーバー用のエラー一覧のレポート](failure-list-report.md)] をクリックして会議の指標)</span><span class="sxs-lookup"><span data-stu-id="83ce8-112">The [Failure List Report in Skype for Business Server](failure-list-report.md) (by clicking the Conference metric)</span></span>
    
- <span data-ttu-id="83ce8-113">[Skype ビジネス サーバー用のユーザー アクティビティ レポート](user-activity-report.md)] をクリックして会議 URI メトリック)</span><span class="sxs-lookup"><span data-stu-id="83ce8-113">The [User Activity Report in Skype for Business Server](user-activity-report.md) (by clicking the Conference URI metric)</span></span>
    
<span data-ttu-id="83ce8-114">[会議の詳細] レポートからは、診断レポート (詳細) のメトリックをクリックすると、 [Skype のビジネス サーバーの診断レポート](diagnostic-report.md)を表示できます。</span><span class="sxs-lookup"><span data-stu-id="83ce8-114">From the Conference Detail Report you can access the [Diagnostic Report in Skype for Business Server](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>
  
## <a name="filters"></a><span data-ttu-id="83ce8-115">フィルター</span><span class="sxs-lookup"><span data-stu-id="83ce8-115">Filters</span></span>

<span data-ttu-id="83ce8-p102">なし。会議詳細レポートにはフィルターを適用できません。</span><span class="sxs-lookup"><span data-stu-id="83ce8-p102">None. You cannot filter on the Conference Detail Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="83ce8-118">指標</span><span class="sxs-lookup"><span data-stu-id="83ce8-118">Metrics</span></span>

<span data-ttu-id="83ce8-119">次の表は、会議詳細レポートの [電話会議情報] セクションに提供される情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="83ce8-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>
  
<span data-ttu-id="83ce8-120">**電話会議情報の指標**</span><span class="sxs-lookup"><span data-stu-id="83ce8-120">**Conference Information Metrics**</span></span>

|<span data-ttu-id="83ce8-121">**名前**</span><span class="sxs-lookup"><span data-stu-id="83ce8-121">**Name**</span></span>|<span data-ttu-id="83ce8-122">**説明**</span><span class="sxs-lookup"><span data-stu-id="83ce8-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="83ce8-123">**[会議 URI]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-123">**Conference URI**</span></span> <br/> |<span data-ttu-id="83ce8-p103">電話会議に割り当てられる URI。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="83ce8-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="83ce8-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="83ce8-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
|<span data-ttu-id="83ce8-127">**[プールの FQDN]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-127">**Pool FQDN**</span></span> <br/> |<span data-ttu-id="83ce8-128">セッションに関係するレジストラー プールまたはエッジ サーバーの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="83ce8-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/> |
|<span data-ttu-id="83ce8-129">**[開始時刻]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-129">**Start time**</span></span> <br/> |<span data-ttu-id="83ce8-130">会議が開始した日時。</span><span class="sxs-lookup"><span data-stu-id="83ce8-130">Date and time that the conference started.</span></span>  <br/> |
|<span data-ttu-id="83ce8-131">**[開催者]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-131">**Organizer**</span></span> <br/> |<span data-ttu-id="83ce8-132">会議を開催したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="83ce8-132">SIP address of the user who organized the conference.</span></span>  <br/> |
|<span data-ttu-id="83ce8-133">**[終了時刻]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-133">**End time**</span></span> <br/> |<span data-ttu-id="83ce8-134">会議が終了した日時。</span><span class="sxs-lookup"><span data-stu-id="83ce8-134">Date and time that the conference ended.</span></span>  <br/> |
   
<span data-ttu-id="83ce8-135">次の表は、会議詳細レポートの [電話会議の参加] セクションに提供される情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="83ce8-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>
  
<span data-ttu-id="83ce8-136">**電話会議参加の指標**</span><span class="sxs-lookup"><span data-stu-id="83ce8-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="83ce8-137">**名前**</span><span class="sxs-lookup"><span data-stu-id="83ce8-137">**Name**</span></span>|<span data-ttu-id="83ce8-138">**説明**</span><span class="sxs-lookup"><span data-stu-id="83ce8-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="83ce8-139">**[ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-139">**User**</span></span> <br/> |<span data-ttu-id="83ce8-140">会議に参加したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="83ce8-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="83ce8-141">**[役割]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-141">**Role**</span></span> <br/> |<span data-ttu-id="83ce8-142">電話会議の参加者が担った役割 (発表者など)。</span><span class="sxs-lookup"><span data-stu-id="83ce8-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="83ce8-143">**[接続]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="83ce8-144">参加者のネットワーク接続 (一般には内部送信元または外部送信元)。</span><span class="sxs-lookup"><span data-stu-id="83ce8-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="83ce8-145">**[参加時間]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-145">**Join time**</span></span> <br/> |<span data-ttu-id="83ce8-146">参加者が電話会議に参加した日時。</span><span class="sxs-lookup"><span data-stu-id="83ce8-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="83ce8-147">**[退場時間]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-147">**Leave time**</span></span> <br/> |<span data-ttu-id="83ce8-148">参加者が電話会議から退出した日時。</span><span class="sxs-lookup"><span data-stu-id="83ce8-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="83ce8-149">**[ユーザー エージェント]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-149">**User agent**</span></span> <br/> |<span data-ttu-id="83ce8-150">参加者のエンドポイントによって使用されるソフトウェアの識別子です。</span><span class="sxs-lookup"><span data-stu-id="83ce8-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="83ce8-151">**[診断レポート]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="83ce8-p104">診断およびトラブルシューティングの情報を提供します。失敗したセッションの SIP 応答コード、診断ヘッダー、電話会議参加時間、診断 ID などがあります。</span><span class="sxs-lookup"><span data-stu-id="83ce8-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |
   
<span data-ttu-id="83ce8-154">会議の様相のセクションで、会議の詳細] レポートの情報を次の表に一覧します。</span><span class="sxs-lookup"><span data-stu-id="83ce8-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>
  
<span data-ttu-id="83ce8-155">**電話会議のモダリティの指標**</span><span class="sxs-lookup"><span data-stu-id="83ce8-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="83ce8-156">**名前**</span><span class="sxs-lookup"><span data-stu-id="83ce8-156">**Name**</span></span>|<span data-ttu-id="83ce8-157">**説明**</span><span class="sxs-lookup"><span data-stu-id="83ce8-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="83ce8-158">**[ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-158">**User**</span></span> <br/> |<span data-ttu-id="83ce8-159">会議に参加したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="83ce8-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="83ce8-160">**[参加時間]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-160">**Join time**</span></span> <br/> |<span data-ttu-id="83ce8-161">参加者が電話会議に参加した日時。</span><span class="sxs-lookup"><span data-stu-id="83ce8-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="83ce8-162">**[退場時間]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-162">**Leave time**</span></span> <br/> |<span data-ttu-id="83ce8-163">参加者が電話会議を退場した日時。</span><span class="sxs-lookup"><span data-stu-id="83ce8-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="83ce8-164">**[電話会議サーバー URI]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="83ce8-165">電話会議で使用された電話会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="83ce8-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="83ce8-166">**[診断レポート]**</span><span class="sxs-lookup"><span data-stu-id="83ce8-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="83ce8-p105">診断およびトラブルシューティングの情報を提供します。失敗したセッションの SIP 応答コード、診断ヘッダー、電話会議参加時間、診断 ID などがあります。</span><span class="sxs-lookup"><span data-stu-id="83ce8-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |
   

