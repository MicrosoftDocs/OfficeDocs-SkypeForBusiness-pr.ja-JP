---
title: Skype for Business Server 2015 の ConferenceMessageCount テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: このテーブル内の各レコードは、1人の IM 会議で1人のユーザーを表し、そのユーザーから送信されたメッセージの数が含まれます。 各会議は、この表の複数のレコードで表されます。ユーザーごとに1つのレコード。
ms.openlocfilehash: ef343536c34b3bd27d71ee37813e4b4e65156094
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296456"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ebcdd-104">Skype for Business Server 2015 の ConferenceMessageCount テーブル</span><span class="sxs-lookup"><span data-stu-id="ebcdd-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ebcdd-105">このテーブル内の各レコードは、1人の IM 会議で1人のユーザーを表し、そのユーザーから送信されたメッセージの数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ebcdd-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="ebcdd-106">各会議は、この表の複数のレコードで表されます。ユーザーごとに1つのレコード。</span><span class="sxs-lookup"><span data-stu-id="ebcdd-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="ebcdd-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ebcdd-107">**Column**</span></span>|<span data-ttu-id="ebcdd-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ebcdd-108">**Data Type**</span></span>|<span data-ttu-id="ebcdd-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="ebcdd-109">**Key/Index**</span></span>|<span data-ttu-id="ebcdd-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="ebcdd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ebcdd-111">**セッション Id**</span><span class="sxs-lookup"><span data-stu-id="ebcdd-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="ebcdd-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ebcdd-112">datetime</span></span>  <br/> |<span data-ttu-id="ebcdd-113">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="ebcdd-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ebcdd-114">会議インスタンスの時刻。</span><span class="sxs-lookup"><span data-stu-id="ebcdd-114">Time of conference instance.</span></span> <span data-ttu-id="ebcdd-115">電話会議インスタンスを一意に識別するために**Sessionidseq**と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="ebcdd-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="ebcdd-116">詳細については、「 [Skype For Business Server 2015 の会議の表](conferences.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebcdd-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ebcdd-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="ebcdd-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="ebcdd-118">int</span><span class="sxs-lookup"><span data-stu-id="ebcdd-118">int</span></span>  <br/> |<span data-ttu-id="ebcdd-119">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="ebcdd-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ebcdd-120">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="ebcdd-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="ebcdd-121">電話会議インスタンスを一意に識別するために**Sessionidtime**と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="ebcdd-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="ebcdd-122">詳細については、「 [Skype For Business Server 2015 の会議の表](conferences.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebcdd-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ebcdd-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="ebcdd-123">**UserId**</span></span> <br/> |<span data-ttu-id="ebcdd-124">int</span><span class="sxs-lookup"><span data-stu-id="ebcdd-124">int</span></span>  <br/> |<span data-ttu-id="ebcdd-125">外部</span><span class="sxs-lookup"><span data-stu-id="ebcdd-125">Foreign</span></span>  <br/> |<span data-ttu-id="ebcdd-126">[[ユーザー] テーブル](users.md)から参照されている、このユーザーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="ebcdd-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="ebcdd-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="ebcdd-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="ebcdd-128">smallint</span><span class="sxs-lookup"><span data-stu-id="ebcdd-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="ebcdd-129">この会議中にこのユーザーによって送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="ebcdd-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

