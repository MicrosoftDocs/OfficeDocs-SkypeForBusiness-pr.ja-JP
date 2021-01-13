---
title: CDR ビューのリスト
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: ビューを使用すると、CDR データベースからデータを返すために使用される最も一般的なシナリオについての情報に簡単にアクセスできます。 実際の CDR データベース テーブルを使用する代わりに、カスタム レポートの作成にはビューを使用してください。これは、データベース ビューが将来のリリースとの下位互換性を維持する可能性が高いためです。
ms.openlocfilehash: 0a3b40c9b31bb521075e78a1a8d46479200249d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813157"
---
# <a name="list-of-cdr-views"></a><span data-ttu-id="4dd65-104">CDR ビューのリスト</span><span class="sxs-lookup"><span data-stu-id="4dd65-104">List of CDR views</span></span>
 
<span data-ttu-id="4dd65-105">ビューを使用すると、CDR データベースからデータを返すために使用される最も一般的なシナリオについての情報に簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4dd65-105">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="4dd65-106">実際の CDR データベース テーブルを使用する代わりに、カスタム レポートの作成にはビューを使用してください。これは、データベース ビューが将来のリリースとの下位互換性を維持する可能性が高いためです。</span><span class="sxs-lookup"><span data-stu-id="4dd65-106">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that's because the database views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="4dd65-107">**View Name/ビュー名**</span><span class="sxs-lookup"><span data-stu-id="4dd65-107">**View Name**</span></span>|<span data-ttu-id="4dd65-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="4dd65-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="4dd65-109">ClientVersions ビュー</span><span class="sxs-lookup"><span data-stu-id="4dd65-109">ClientVersions view</span></span>](clientversions-0.md) <br/> |<span data-ttu-id="4dd65-110">通信セッションで使用されているクライアント ソフトウェアおよびデバイスについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4dd65-110">Returns information about the client software/devices used in a communication session.</span></span>  <br/> |
|[<span data-ttu-id="4dd65-111">ConferenceMessageCount ビュー</span><span class="sxs-lookup"><span data-stu-id="4dd65-111">ConferenceMessageCount view</span></span>](conferencemessagecount-0.md) <br/> |<span data-ttu-id="4dd65-112">電話会議でユーザーによって送信されたメッセージ数についての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4dd65-112">Returns information about the number of messages sent by users in a conference.</span></span>  <br/> |
|<span data-ttu-id="4dd65-113">[[電話会議] ビュー](conferences-0.md)</span><span class="sxs-lookup"><span data-stu-id="4dd65-113">[Conferences view](conferences-0.md)</span></span> <br/> |<span data-ttu-id="4dd65-114">開始時刻、終了時刻、電話会議の開催者などの、電話会議情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4dd65-114">Returns conference information, including start time, end time, and conference organizer.</span></span>  <br/> |
|[<span data-ttu-id="4dd65-115">ConferenceSessionDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="4dd65-115">ConferenceSessionDetails view</span></span>](conferencesessiondetails.md) <br/> |<span data-ttu-id="4dd65-116">開始時刻、終了時刻、ユーザー ID、応答コード、診断 ID などの、すべての電話会議セッションのセッション詳細を返します。</span><span class="sxs-lookup"><span data-stu-id="4dd65-116">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span>  <br/> |
|[<span data-ttu-id="4dd65-117">ConferenceUris ビュー</span><span class="sxs-lookup"><span data-stu-id="4dd65-117">ConferenceUris view</span></span>](conferenceuris-0.md) <br/> |<span data-ttu-id="4dd65-118">電話会議で使用される電話会議 URI についての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4dd65-118">Returns information about conference URIs used in a conference</span></span>  <br/> |
|[<span data-ttu-id="4dd65-119">ErrorReport ビュー</span><span class="sxs-lookup"><span data-stu-id="4dd65-119">ErrorReport view</span></span>](errorreport-0.md) <br/> |<span data-ttu-id="4dd65-120">セッション中に発生したエラーについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4dd65-120">Returns information about errors that occurred during a session.</span></span>  <br/> |
|[<span data-ttu-id="4dd65-121">FileTransfers ビュー</span><span class="sxs-lookup"><span data-stu-id="4dd65-121">FileTransfers view</span></span>](filetransfers.md) <br/> |<span data-ttu-id="4dd65-122">ファイル名、送信の状態 (受け入れ、拒否、取り消し) などの、ファイル送信セッションについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4dd65-122">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span>  <br/> |
|[<span data-ttu-id="4dd65-123">FocusJoinsAndLeaves ビュー</span><span class="sxs-lookup"><span data-stu-id="4dd65-123">FocusJoinsAndLeaves view</span></span>](focusjoinsandleaves-0.md) <br/> |<span data-ttu-id="4dd65-124">会議の参加と退出のアクティビティについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4dd65-124">Returns information about conference join and leave activities.</span></span>  <br/> |
|[<span data-ttu-id="4dd65-125">McuJoinsAndLeaves ビュー</span><span class="sxs-lookup"><span data-stu-id="4dd65-125">McuJoinsAndLeaves view</span></span>](mcujoinsandleaves-0.md) <br/> |<span data-ttu-id="4dd65-126">会議の参加と退出のアクティビティを組み合わせた情報を返します (会議の参加と、対応する退出の情報を組み合わせて返します)。</span><span class="sxs-lookup"><span data-stu-id="4dd65-126">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span>  <br/> |
|[<span data-ttu-id="4dd65-127">Mcus ビュー</span><span class="sxs-lookup"><span data-stu-id="4dd65-127">Mcus view</span></span>](mcus-0.md) <br/> |<span data-ttu-id="4dd65-128">電話会議サーバーについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4dd65-128">Returns information about Conferencing servers.</span></span>  <br/> |
|[<span data-ttu-id="4dd65-129">メディア ビュー</span><span class="sxs-lookup"><span data-stu-id="4dd65-129">Media view</span></span>](media-0.md) <br/> |<span data-ttu-id="4dd65-130">ピアツーピアの通信セッションで使用されるメディアの種類についての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4dd65-130">Returns information about the types of media used in peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="4dd65-131">ProgressReport ビュー</span><span class="sxs-lookup"><span data-stu-id="4dd65-131">ProgressReport view</span></span>](progressreport-0.md) <br/> |<span data-ttu-id="4dd65-132">完了したセッションについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4dd65-132">Returns information about completed sessions.</span></span>  <br/> |
|[<span data-ttu-id="4dd65-133">登録ビュー</span><span class="sxs-lookup"><span data-stu-id="4dd65-133">Registration view</span></span>](registration-0.md) <br/> |<span data-ttu-id="4dd65-134">Skype for Business Server 2015 への登録に関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="4dd65-134">Returns information about registrations with Skype for Business Server 2015.</span></span>  <br/> |
|[<span data-ttu-id="4dd65-135">SessionDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="4dd65-135">SessionDetails view</span></span>](sessiondetails-0.md) <br/> |<span data-ttu-id="4dd65-136">VoIP 間の通話、2 者間の IM セッション、その他のピアツーピア通信セッションなど、ピアツーピア セッションについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4dd65-136">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="4dd65-137">ユーザー ビュー</span><span class="sxs-lookup"><span data-stu-id="4dd65-137">User view</span></span>](user.md) <br/> |<span data-ttu-id="4dd65-138">通信セッションに参加したユーザーについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4dd65-138">Returns information about the users who have participated in communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="4dd65-139">VoIPDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="4dd65-139">VoIPDetails view</span></span>](voipdetails.md) <br/> |<span data-ttu-id="4dd65-140">少なくとも一方が VoIP (ボイス オーバー IP) ユーザーであるピアツーピア セッションの情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4dd65-140">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span>  <br/> |
   

