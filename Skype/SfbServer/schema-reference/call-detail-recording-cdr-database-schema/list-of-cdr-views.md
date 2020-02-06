---
title: CDR ビューのリスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: ビューは、CDR データベースからデータを返すために使用される最も一般的なシナリオに関する情報に簡単にアクセスできます。 実際の CDR データベーステーブルを使う代わりに、ビューを使ってカスタムレポートを作成することをお勧めします。これは、データベースビューが将来のリリースとの下位互換性を維持する可能性が高いためです。
ms.openlocfilehash: 78bf18fe51cea8937de44c72b39f7c1b81c75544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815125"
---
# <a name="list-of-cdr-views"></a><span data-ttu-id="526b2-104">CDR ビューのリスト</span><span class="sxs-lookup"><span data-stu-id="526b2-104">List of CDR views</span></span>
 
<span data-ttu-id="526b2-105">ビューは、CDR データベースからデータを返すために使用される最も一般的なシナリオに関する情報に簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="526b2-105">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="526b2-106">実際の CDR データベーステーブルを使う代わりに、ビューを使ってカスタムレポートを作成することをお勧めします。これは、データベースビューが将来のリリースとの下位互換性を維持する可能性が高いためです。</span><span class="sxs-lookup"><span data-stu-id="526b2-106">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that's because the database views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="526b2-107">**ビュー名**</span><span class="sxs-lookup"><span data-stu-id="526b2-107">**View Name**</span></span>|<span data-ttu-id="526b2-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="526b2-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="526b2-109">ClientVersions ビュー</span><span class="sxs-lookup"><span data-stu-id="526b2-109">ClientVersions view</span></span>](clientversions-0.md) <br/> |<span data-ttu-id="526b2-110">通信セッションで使用されているクライアントソフトウェア/デバイスについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="526b2-110">Returns information about the client software/devices used in a communication session.</span></span>  <br/> |
|[<span data-ttu-id="526b2-111">ConferenceMessageCount ビュー</span><span class="sxs-lookup"><span data-stu-id="526b2-111">ConferenceMessageCount view</span></span>](conferencemessagecount-0.md) <br/> |<span data-ttu-id="526b2-112">電話会議のユーザーから送信されたメッセージの数に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="526b2-112">Returns information about the number of messages sent by users in a conference.</span></span>  <br/> |
|[<span data-ttu-id="526b2-113">会議ビュー</span><span class="sxs-lookup"><span data-stu-id="526b2-113">Conferences view</span></span>](conferences-0.md) <br/> |<span data-ttu-id="526b2-114">開始時刻、終了時刻、会議開催者などの会議情報を返します。</span><span class="sxs-lookup"><span data-stu-id="526b2-114">Returns conference information, including start time, end time, and conference organizer.</span></span>  <br/> |
|[<span data-ttu-id="526b2-115">ConferenceSessionDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="526b2-115">ConferenceSessionDetails view</span></span>](conferencesessiondetails.md) <br/> |<span data-ttu-id="526b2-116">開始時刻、終了時刻、ユーザー Id、応答コード、診断 Id など、すべての会議セッションのセッションの詳細を返します。</span><span class="sxs-lookup"><span data-stu-id="526b2-116">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span>  <br/> |
|[<span data-ttu-id="526b2-117">ConferenceUris ビュー</span><span class="sxs-lookup"><span data-stu-id="526b2-117">ConferenceUris view</span></span>](conferenceuris-0.md) <br/> |<span data-ttu-id="526b2-118">会議で使用されている会議の Uri に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="526b2-118">Returns information about conference URIs used in a conference</span></span>  <br/> |
|[<span data-ttu-id="526b2-119">ErrorReport ビュー</span><span class="sxs-lookup"><span data-stu-id="526b2-119">ErrorReport view</span></span>](errorreport-0.md) <br/> |<span data-ttu-id="526b2-120">セッション中に発生したエラーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="526b2-120">Returns information about errors that occurred during a session.</span></span>  <br/> |
|[<span data-ttu-id="526b2-121">FileTransfers ビュー</span><span class="sxs-lookup"><span data-stu-id="526b2-121">FileTransfers view</span></span>](filetransfers.md) <br/> |<span data-ttu-id="526b2-122">ファイルの名前、転送が承諾、拒否、またはキャンセルされたかどうかなど、ファイル転送セッションに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="526b2-122">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span>  <br/> |
|[<span data-ttu-id="526b2-123">FocusJoinsAndLeaves ビュー</span><span class="sxs-lookup"><span data-stu-id="526b2-123">FocusJoinsAndLeaves view</span></span>](focusjoinsandleaves-0.md) <br/> |<span data-ttu-id="526b2-124">会議への参加と退席中のアクティビティに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="526b2-124">Returns information about conference join and leave activities.</span></span>  <br/> |
|[<span data-ttu-id="526b2-125">McuJoinsAndLeaves ビュー</span><span class="sxs-lookup"><span data-stu-id="526b2-125">McuJoinsAndLeaves view</span></span>](mcujoinsandleaves-0.md) <br/> |<span data-ttu-id="526b2-126">会議への参加と休暇のアクティビティについての結合された情報を返します (各会議参加は、対応する会議の退出とペアリングされています)。</span><span class="sxs-lookup"><span data-stu-id="526b2-126">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span>  <br/> |
|[<span data-ttu-id="526b2-127">Mcu ビュー</span><span class="sxs-lookup"><span data-stu-id="526b2-127">Mcus view</span></span>](mcus-0.md) <br/> |<span data-ttu-id="526b2-128">会議サーバーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="526b2-128">Returns information about Conferencing servers.</span></span>  <br/> |
|[<span data-ttu-id="526b2-129">メディアビュー</span><span class="sxs-lookup"><span data-stu-id="526b2-129">Media view</span></span>](media-0.md) <br/> |<span data-ttu-id="526b2-130">ピアツーピア通信セッションで使用されているメディアの種類についての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="526b2-130">Returns information about the types of media used in peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="526b2-131">進捗状況レポートビュー</span><span class="sxs-lookup"><span data-stu-id="526b2-131">ProgressReport view</span></span>](progressreport-0.md) <br/> |<span data-ttu-id="526b2-132">完了したセッションに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="526b2-132">Returns information about completed sessions.</span></span>  <br/> |
|[<span data-ttu-id="526b2-133">登録表示</span><span class="sxs-lookup"><span data-stu-id="526b2-133">Registration view</span></span>](registration-0.md) <br/> |<span data-ttu-id="526b2-134">Skype for Business Server 2015 での登録に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="526b2-134">Returns information about registrations with Skype for Business Server 2015.</span></span>  <br/> |
|[<span data-ttu-id="526b2-135">セッションの詳細ビュー</span><span class="sxs-lookup"><span data-stu-id="526b2-135">SessionDetails view</span></span>](sessiondetails-0.md) <br/> |<span data-ttu-id="526b2-136">VoIP 電話、2パーティの IM セッション、またはピアツーピア通信セッションなど、ピアツーピアセッションに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="526b2-136">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="526b2-137">ユーザービュー</span><span class="sxs-lookup"><span data-stu-id="526b2-137">User view</span></span>](user.md) <br/> |<span data-ttu-id="526b2-138">コミュニケーションセッションに参加したユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="526b2-138">Returns information about the users who have participated in communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="526b2-139">VoIPDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="526b2-139">VoIPDetails view</span></span>](voipdetails.md) <br/> |<span data-ttu-id="526b2-140">1つ以上の VoIP (ボイスオーバー IO) ユーザーを含むピアツーピアセッションの情報を返します。</span><span class="sxs-lookup"><span data-stu-id="526b2-140">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span>  <br/> |
   

