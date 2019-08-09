---
title: Skype for Business Server の会議の詳細レポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: '概要: Skype for Business Server で使用されている会議の詳細レポートについて説明します。'
ms.openlocfilehash: 17337624c955dfa174f7b98772fdd836e82891d0
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271399"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="59aec-103">Skype for Business Server の会議の詳細レポート</span><span class="sxs-lookup"><span data-stu-id="59aec-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="59aec-104">**概要:** Skype for Business Server で使用されている会議の詳細レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="59aec-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="59aec-p101">会議詳細レポートには、電話会議に参加したすべてのユーザーに関する詳細な情報が示されます。たとえば、ユーザーが会議に参加した日時、ユーザーが電話会議から退場した日時、ユーザーが電話会議に接続するときに使用したエンドポイントのユーザー エージェントなどの情報を確認できます。各電話会議におけるユーザーの役割 (発表者、参加者など) に関する情報も確認できます。おそらく最も重要なことは、会議への参加と終了が正常に行われたユーザーと正常に行われなかったユーザーを簡単に確認できることです。</span><span class="sxs-lookup"><span data-stu-id="59aec-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="59aec-109">会議詳細レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="59aec-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="59aec-110">会議詳細レポートには、次のレポートからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="59aec-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="59aec-111">[Call Admission Control Report](call-admission-control-report.md) (会議の詳細指標をクリック)</span><span class="sxs-lookup"><span data-stu-id="59aec-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="59aec-112">[Failure List Report](failure-list-report.md) (電話会議指標をクリック)</span><span class="sxs-lookup"><span data-stu-id="59aec-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="59aec-113">[User Activity Report](call-diagnostic-reports-per-user.md) (電話会議 URI 指標をクリック)</span><span class="sxs-lookup"><span data-stu-id="59aec-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="59aec-114">会議詳細レポートからは、診断レポート (詳細) 指標をクリックして [Diagnostic Report](diagnostic-report.md)にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="59aec-114">From the Conference Detail Report you can access the [Diagnostic Report](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="59aec-115">フィルター</span><span class="sxs-lookup"><span data-stu-id="59aec-115">Filters</span></span>

<span data-ttu-id="59aec-p102">なし。会議詳細レポートにはフィルターを適用できません。</span><span class="sxs-lookup"><span data-stu-id="59aec-p102">None. You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="59aec-118">指標</span><span class="sxs-lookup"><span data-stu-id="59aec-118">Metrics</span></span>

<span data-ttu-id="59aec-119">次の表は、会議詳細レポートの [電話会議情報] セクションに提供される情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="59aec-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="59aec-120">**電話会議情報の指標**</span><span class="sxs-lookup"><span data-stu-id="59aec-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="59aec-121">**名前**</span><span class="sxs-lookup"><span data-stu-id="59aec-121">**Name**</span></span>                 | <span data-ttu-id="59aec-122">**説明**</span><span class="sxs-lookup"><span data-stu-id="59aec-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="59aec-123">**[会議 URI]**</span><span class="sxs-lookup"><span data-stu-id="59aec-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="59aec-p103">電話会議に割り当てられる URI。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="59aec-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="59aec-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="59aec-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="59aec-127">**[プールの FQDN]**</span><span class="sxs-lookup"><span data-stu-id="59aec-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="59aec-128">セッションに関係するレジストラー プールまたはエッジ サーバーの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="59aec-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="59aec-129">**[開始時刻]**</span><span class="sxs-lookup"><span data-stu-id="59aec-129">**Start time**</span></span> <br/>     | <span data-ttu-id="59aec-130">会議が開始した日時。</span><span class="sxs-lookup"><span data-stu-id="59aec-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="59aec-131">**[開催者]**</span><span class="sxs-lookup"><span data-stu-id="59aec-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="59aec-132">会議を開催したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="59aec-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="59aec-133">**[終了時刻]**</span><span class="sxs-lookup"><span data-stu-id="59aec-133">**End time**</span></span> <br/>       | <span data-ttu-id="59aec-134">会議が終了した日時。</span><span class="sxs-lookup"><span data-stu-id="59aec-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="59aec-135">次の表は、会議詳細レポートの [電話会議の参加] セクションに提供される情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="59aec-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="59aec-136">**電話会議参加の指標**</span><span class="sxs-lookup"><span data-stu-id="59aec-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="59aec-137">**名前**</span><span class="sxs-lookup"><span data-stu-id="59aec-137">**Name**</span></span>|<span data-ttu-id="59aec-138">**説明**</span><span class="sxs-lookup"><span data-stu-id="59aec-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="59aec-139">**[ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="59aec-139">**User**</span></span> <br/> |<span data-ttu-id="59aec-140">会議に参加したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="59aec-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="59aec-141">**[役割]**</span><span class="sxs-lookup"><span data-stu-id="59aec-141">**Role**</span></span> <br/> |<span data-ttu-id="59aec-142">電話会議の参加者が担った役割 (発表者など)。</span><span class="sxs-lookup"><span data-stu-id="59aec-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="59aec-143">**[接続]**</span><span class="sxs-lookup"><span data-stu-id="59aec-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="59aec-144">参加者のネットワーク接続 (一般には内部送信元または外部送信元)。</span><span class="sxs-lookup"><span data-stu-id="59aec-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="59aec-145">**[参加時間]**</span><span class="sxs-lookup"><span data-stu-id="59aec-145">**Join time**</span></span> <br/> |<span data-ttu-id="59aec-146">参加者が電話会議に参加した日時。</span><span class="sxs-lookup"><span data-stu-id="59aec-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="59aec-147">**[退場時間]**</span><span class="sxs-lookup"><span data-stu-id="59aec-147">**Leave time**</span></span> <br/> |<span data-ttu-id="59aec-148">参加者が電話会議から退出した日時。</span><span class="sxs-lookup"><span data-stu-id="59aec-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="59aec-149">**[ユーザー エージェント]**</span><span class="sxs-lookup"><span data-stu-id="59aec-149">**User agent**</span></span> <br/> |<span data-ttu-id="59aec-150">参加者のエンドポイントによって使用されるソフトウェアの識別子です。</span><span class="sxs-lookup"><span data-stu-id="59aec-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="59aec-151">**[診断レポート]**</span><span class="sxs-lookup"><span data-stu-id="59aec-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="59aec-p104">診断およびトラブルシューティングの情報を提供します。失敗したセッションの SIP 応答コード、診断ヘッダー、電話会議参加時間、診断 ID などがあります。</span><span class="sxs-lookup"><span data-stu-id="59aec-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="59aec-154">次の表に、会議の詳細レポートの [会議のモダリティ] セクションに表示される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="59aec-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="59aec-155">**電話会議のモダリティの指標**</span><span class="sxs-lookup"><span data-stu-id="59aec-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="59aec-156">**名前**</span><span class="sxs-lookup"><span data-stu-id="59aec-156">**Name**</span></span>|<span data-ttu-id="59aec-157">**説明**</span><span class="sxs-lookup"><span data-stu-id="59aec-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="59aec-158">**[ユーザー]**</span><span class="sxs-lookup"><span data-stu-id="59aec-158">**User**</span></span> <br/> |<span data-ttu-id="59aec-159">会議に参加したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="59aec-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="59aec-160">**[参加時間]**</span><span class="sxs-lookup"><span data-stu-id="59aec-160">**Join time**</span></span> <br/> |<span data-ttu-id="59aec-161">参加者が電話会議に参加した日時。</span><span class="sxs-lookup"><span data-stu-id="59aec-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="59aec-162">**[退場時間]**</span><span class="sxs-lookup"><span data-stu-id="59aec-162">**Leave time**</span></span> <br/> |<span data-ttu-id="59aec-163">参加者が電話会議を退場した日時。</span><span class="sxs-lookup"><span data-stu-id="59aec-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="59aec-164">**[電話会議サーバー URI]**</span><span class="sxs-lookup"><span data-stu-id="59aec-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="59aec-165">電話会議で使用された電話会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="59aec-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="59aec-166">**[診断レポート]**</span><span class="sxs-lookup"><span data-stu-id="59aec-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="59aec-p105">診断およびトラブルシューティングの情報を提供します。失敗したセッションの SIP 応答コード、診断ヘッダー、電話会議参加時間、診断 ID などがあります。</span><span class="sxs-lookup"><span data-stu-id="59aec-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


