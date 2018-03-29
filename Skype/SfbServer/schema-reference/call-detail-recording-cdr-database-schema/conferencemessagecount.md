---
title: ビジネス サーバー 2015 の Skype での ConferenceMessageCount テーブル
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
ms.openlocfilehash: 6b9dfcf0743c03e69726bb501cc7a4a961bf5df8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="34388-104">ビジネス サーバー 2015 の Skype での ConferenceMessageCount テーブル</span><span class="sxs-lookup"><span data-stu-id="34388-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="34388-105">このテーブルの各レコードは、1 つの IM 会議に 1 人のユーザーを表し、そのユーザーから送信されたメッセージの数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="34388-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="34388-106">各会議は、このテーブル内の複数のレコードで表されます。ユーザーごとに 1 つのレコードです。</span><span class="sxs-lookup"><span data-stu-id="34388-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="34388-107">**列**</span><span class="sxs-lookup"><span data-stu-id="34388-107">**Column**</span></span>|<span data-ttu-id="34388-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="34388-108">**Data Type**</span></span>|<span data-ttu-id="34388-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="34388-109">**Key/Index**</span></span>|<span data-ttu-id="34388-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="34388-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="34388-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="34388-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="34388-112">datetime</span><span class="sxs-lookup"><span data-stu-id="34388-112">datetime</span></span>  <br/> |<span data-ttu-id="34388-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="34388-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="34388-114">会議インスタンスの時間です。</span><span class="sxs-lookup"><span data-stu-id="34388-114">Time of conference instance.</span></span> <span data-ttu-id="34388-115">会議のインスタンスを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。</span><span class="sxs-lookup"><span data-stu-id="34388-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="34388-116">[ビジネス サーバー 2015 の Skype での会議のテーブル](conferences.md)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34388-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="34388-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="34388-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="34388-118">int</span><span class="sxs-lookup"><span data-stu-id="34388-118">int</span></span>  <br/> |<span data-ttu-id="34388-119">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="34388-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="34388-120">会議のインスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="34388-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="34388-121">会議のインスタンスを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。</span><span class="sxs-lookup"><span data-stu-id="34388-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="34388-122">[ビジネス サーバー 2015 の Skype での会議のテーブル](conferences.md)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34388-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="34388-123">**ユーザー Id**</span><span class="sxs-lookup"><span data-stu-id="34388-123">**UserId**</span></span> <br/> |<span data-ttu-id="34388-124">int</span><span class="sxs-lookup"><span data-stu-id="34388-124">int</span></span>  <br/> |<span data-ttu-id="34388-125">外部</span><span class="sxs-lookup"><span data-stu-id="34388-125">Foreign</span></span>  <br/> |<span data-ttu-id="34388-126">[ユーザー テーブル](users.md)から参照されている、このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="34388-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="34388-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="34388-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="34388-128">smallint</span><span class="sxs-lookup"><span data-stu-id="34388-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="34388-129">この会議中にこのユーザーによって送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="34388-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

