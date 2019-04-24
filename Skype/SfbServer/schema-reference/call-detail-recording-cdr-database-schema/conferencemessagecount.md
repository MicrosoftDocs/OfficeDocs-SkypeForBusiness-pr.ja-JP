---
title: ビジネス サーバー 2015 の Skype での ConferenceMessageCount テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: このテーブルの各レコードは、1 つの IM 会議に 1 人のユーザーを表し、そのユーザーから送信されたメッセージの数が含まれています。 各会議は、このテーブル内の複数のレコードで表されます。ユーザーごとに 1 つのレコードです。
ms.openlocfilehash: 60fa79de17c2db14116bd0ffe211e25a61ec9136
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213278"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c5ceb-104">ビジネス サーバー 2015 の Skype での ConferenceMessageCount テーブル</span><span class="sxs-lookup"><span data-stu-id="c5ceb-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c5ceb-105">このテーブルの各レコードは、1 つの IM 会議に 1 人のユーザーを表し、そのユーザーから送信されたメッセージの数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5ceb-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="c5ceb-106">各会議は、このテーブル内の複数のレコードで表されます。ユーザーごとに 1 つのレコードです。</span><span class="sxs-lookup"><span data-stu-id="c5ceb-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="c5ceb-107">**列**</span><span class="sxs-lookup"><span data-stu-id="c5ceb-107">**Column**</span></span>|<span data-ttu-id="c5ceb-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c5ceb-108">**Data Type**</span></span>|<span data-ttu-id="c5ceb-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="c5ceb-109">**Key/Index**</span></span>|<span data-ttu-id="c5ceb-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="c5ceb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c5ceb-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="c5ceb-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="c5ceb-112">datetime</span><span class="sxs-lookup"><span data-stu-id="c5ceb-112">datetime</span></span>  <br/> |<span data-ttu-id="c5ceb-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="c5ceb-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="c5ceb-114">会議インスタンスの時間です。</span><span class="sxs-lookup"><span data-stu-id="c5ceb-114">Time of conference instance.</span></span> <span data-ttu-id="c5ceb-115">会議のインスタンスを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。</span><span class="sxs-lookup"><span data-stu-id="c5ceb-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="c5ceb-116">[ビジネス サーバー 2015 の Skype での会議のテーブル](conferences.md)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5ceb-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c5ceb-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="c5ceb-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="c5ceb-118">int</span><span class="sxs-lookup"><span data-stu-id="c5ceb-118">int</span></span>  <br/> |<span data-ttu-id="c5ceb-119">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="c5ceb-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="c5ceb-120">会議のインスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="c5ceb-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="c5ceb-121">会議のインスタンスを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。</span><span class="sxs-lookup"><span data-stu-id="c5ceb-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="c5ceb-122">[ビジネス サーバー 2015 の Skype での会議のテーブル](conferences.md)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5ceb-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c5ceb-123">**ユーザー Id**</span><span class="sxs-lookup"><span data-stu-id="c5ceb-123">**UserId**</span></span> <br/> |<span data-ttu-id="c5ceb-124">int</span><span class="sxs-lookup"><span data-stu-id="c5ceb-124">int</span></span>  <br/> |<span data-ttu-id="c5ceb-125">外部</span><span class="sxs-lookup"><span data-stu-id="c5ceb-125">Foreign</span></span>  <br/> |<span data-ttu-id="c5ceb-126">[ユーザー テーブル](users.md)から参照されている、このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="c5ceb-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="c5ceb-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="c5ceb-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="c5ceb-128">smallint</span><span class="sxs-lookup"><span data-stu-id="c5ceb-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="c5ceb-129">この会議中にこのユーザーによって送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="c5ceb-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

