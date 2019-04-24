---
title: CDR ビューのリスト
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: ビューでは、CDR データベースからデータを返すために使用される最も一般的なシナリオに関する情報にアクセスする簡単な方法を提供します。 データベース テーブルの実際の CDR を使用する代わりにカスタム ・ レポートを構築するためのビューを使用することをお勧めデータベース ビューとは逆方向の将来のリリースとの互換性を維持する可能性が高いためにです。
ms.openlocfilehash: 7767a80069201e5ec07ea68d4bdef3a6a5977e4d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213009"
---
# <a name="list-of-cdr-views"></a><span data-ttu-id="7f677-104">CDR ビューのリスト</span><span class="sxs-lookup"><span data-stu-id="7f677-104">List of CDR views</span></span>
 
<span data-ttu-id="7f677-105">ビューでは、CDR データベースからデータを返すために使用される最も一般的なシナリオに関する情報にアクセスする簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="7f677-105">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="7f677-106">データベース テーブルの実際の CDR を使用する代わりにカスタム ・ レポートを構築するためのビューを使用することをお勧めデータベース ビューとは逆方向の将来のリリースとの互換性を維持する可能性が高いためにです。</span><span class="sxs-lookup"><span data-stu-id="7f677-106">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that's because the database views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="7f677-107">**ビュー名**</span><span class="sxs-lookup"><span data-stu-id="7f677-107">**View Name**</span></span>|<span data-ttu-id="7f677-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="7f677-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7f677-109">ClientVersions ビュー</span><span class="sxs-lookup"><span data-stu-id="7f677-109">ClientVersions view</span></span>](clientversions-0.md) <br/> |<span data-ttu-id="7f677-110">ソフトウェアとデバイスの通信セッションで使用されているクライアントに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7f677-110">Returns information about the client software/devices used in a communication session.</span></span>  <br/> |
|[<span data-ttu-id="7f677-111">ConferenceMessageCount ビュー</span><span class="sxs-lookup"><span data-stu-id="7f677-111">ConferenceMessageCount view</span></span>](conferencemessagecount-0.md) <br/> |<span data-ttu-id="7f677-112">会議内のユーザーによって送信されたメッセージの数に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7f677-112">Returns information about the number of messages sent by users in a conference.</span></span>  <br/> |
|[<span data-ttu-id="7f677-113">会議を表示します。</span><span class="sxs-lookup"><span data-stu-id="7f677-113">Conferences view</span></span>](conferences-0.md) <br/> |<span data-ttu-id="7f677-114">開始時刻、終了時刻、および会議の開催者を含む会議の情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7f677-114">Returns conference information, including start time, end time, and conference organizer.</span></span>  <br/> |
|[<span data-ttu-id="7f677-115">ConferenceSessionDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="7f677-115">ConferenceSessionDetails view</span></span>](conferencesessiondetails.md) <br/> |<span data-ttu-id="7f677-116">開始と終了時刻、ユーザーの Id、応答コード、および診断の Id を含む、すべての会議セッションのセッションの詳細を返します。</span><span class="sxs-lookup"><span data-stu-id="7f677-116">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span>  <br/> |
|[<span data-ttu-id="7f677-117">ConferenceUris ビュー</span><span class="sxs-lookup"><span data-stu-id="7f677-117">ConferenceUris view</span></span>](conferenceuris-0.md) <br/> |<span data-ttu-id="7f677-118">会議の Uri を使用する会議に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7f677-118">Returns information about conference URIs used in a conference</span></span>  <br/> |
|[<span data-ttu-id="7f677-119">ErrorReport ビュー</span><span class="sxs-lookup"><span data-stu-id="7f677-119">ErrorReport view</span></span>](errorreport-0.md) <br/> |<span data-ttu-id="7f677-120">セッション中に発生したエラーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7f677-120">Returns information about errors that occurred during a session.</span></span>  <br/> |
|[<span data-ttu-id="7f677-121">FileTransfers ビュー</span><span class="sxs-lookup"><span data-stu-id="7f677-121">FileTransfers view</span></span>](filetransfers.md) <br/> |<span data-ttu-id="7f677-122">ファイル名と、転送が受け入れられたかどうかを含む、ファイル転送のセッションに関する情報を返します。 却下済みまたはキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="7f677-122">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span>  <br/> |
|[<span data-ttu-id="7f677-123">FocusJoinsAndLeaves ビュー</span><span class="sxs-lookup"><span data-stu-id="7f677-123">FocusJoinsAndLeaves view</span></span>](focusjoinsandleaves-0.md) <br/> |<span data-ttu-id="7f677-124">結合および休暇の活動の会議に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7f677-124">Returns information about conference join and leave activities.</span></span>  <br/> |
|[<span data-ttu-id="7f677-125">McuJoinsAndLeaves ビュー</span><span class="sxs-lookup"><span data-stu-id="7f677-125">McuJoinsAndLeaves view</span></span>](mcujoinsandleaves-0.md) <br/> |<span data-ttu-id="7f677-126">会議の参加についての情報を組み合わせて、(各会議の参加とペアに対応する会議のままに) 活動の終了を返します。</span><span class="sxs-lookup"><span data-stu-id="7f677-126">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span>  <br/> |
|[<span data-ttu-id="7f677-127">Mcu ビュー</span><span class="sxs-lookup"><span data-stu-id="7f677-127">Mcus view</span></span>](mcus-0.md) <br/> |<span data-ttu-id="7f677-128">会議サーバーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7f677-128">Returns information about Conferencing servers.</span></span>  <br/> |
|[<span data-ttu-id="7f677-129">メディアを表示します。</span><span class="sxs-lookup"><span data-stu-id="7f677-129">Media view</span></span>](media-0.md) <br/> |<span data-ttu-id="7f677-130">ピア ツー ピア通信セッションで使用されるメディアの種類に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7f677-130">Returns information about the types of media used in peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="7f677-131">ProgressReport ビュー</span><span class="sxs-lookup"><span data-stu-id="7f677-131">ProgressReport view</span></span>](progressreport-0.md) <br/> |<span data-ttu-id="7f677-132">完了したセッションに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7f677-132">Returns information about completed sessions.</span></span>  <br/> |
|[<span data-ttu-id="7f677-133">登録の表示</span><span class="sxs-lookup"><span data-stu-id="7f677-133">Registration view</span></span>](registration-0.md) <br/> |<span data-ttu-id="7f677-134">ビジネス サーバー 2015 の Skype での登録に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7f677-134">Returns information about registrations with Skype for Business Server 2015.</span></span>  <br/> |
|[<span data-ttu-id="7f677-135">SessionDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="7f677-135">SessionDetails view</span></span>](sessiondetails-0.md) <br/> |<span data-ttu-id="7f677-136">VoIP VoIP 電話、IM セッションの 2 つのパーティ、または他のピア ツー ピア通信セッションを含め、ピア ツー ピア セッションに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7f677-136">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="7f677-137">ユーザーの表示</span><span class="sxs-lookup"><span data-stu-id="7f677-137">User view</span></span>](user.md) <br/> |<span data-ttu-id="7f677-138">通信セッションに参加しているユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7f677-138">Returns information about the users who have participated in communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="7f677-139">VoIPDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="7f677-139">VoIPDetails view</span></span>](voipdetails.md) <br/> |<span data-ttu-id="7f677-140">VoIP (ボイス オーバー IO) の 1 つ以上のユーザーに関連するピア ツー ピア セッションに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7f677-140">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span>  <br/> |
   

