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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: このテーブル内の各レコードは、1人の IM 会議で1人のユーザーを表し、そのユーザーから送信されたメッセージの数が含まれます。 各会議は、この表の複数のレコードで表されます。ユーザーごとに1つのレコード。
ms.openlocfilehash: 66651f798d627ef4ea783c4ecf4e7cb8f1adab81
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815375"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9f95f-104">Skype for Business Server 2015 の ConferenceMessageCount テーブル</span><span class="sxs-lookup"><span data-stu-id="9f95f-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9f95f-105">このテーブル内の各レコードは、1人の IM 会議で1人のユーザーを表し、そのユーザーから送信されたメッセージの数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9f95f-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="9f95f-106">各会議は、この表の複数のレコードで表されます。ユーザーごとに1つのレコード。</span><span class="sxs-lookup"><span data-stu-id="9f95f-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="9f95f-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9f95f-107">**Column**</span></span>|<span data-ttu-id="9f95f-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9f95f-108">**Data Type**</span></span>|<span data-ttu-id="9f95f-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="9f95f-109">**Key/Index**</span></span>|<span data-ttu-id="9f95f-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="9f95f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9f95f-111">**セッション Id**</span><span class="sxs-lookup"><span data-stu-id="9f95f-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="9f95f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="9f95f-112">datetime</span></span>  <br/> |<span data-ttu-id="9f95f-113">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="9f95f-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9f95f-114">会議インスタンスの時刻。</span><span class="sxs-lookup"><span data-stu-id="9f95f-114">Time of conference instance.</span></span> <span data-ttu-id="9f95f-115">電話会議インスタンスを一意に識別するために**Sessionidseq**と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f95f-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="9f95f-116">詳細については、「 [Skype For Business Server 2015 の会議の表](conferences.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f95f-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="9f95f-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="9f95f-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="9f95f-118">int</span><span class="sxs-lookup"><span data-stu-id="9f95f-118">int</span></span>  <br/> |<span data-ttu-id="9f95f-119">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="9f95f-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9f95f-120">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="9f95f-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="9f95f-121">電話会議インスタンスを一意に識別するために**Sessionidtime**と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f95f-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="9f95f-122">詳細については、「 [Skype For Business Server 2015 の会議の表](conferences.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f95f-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="9f95f-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="9f95f-123">**UserId**</span></span> <br/> |<span data-ttu-id="9f95f-124">int</span><span class="sxs-lookup"><span data-stu-id="9f95f-124">int</span></span>  <br/> |<span data-ttu-id="9f95f-125">外部</span><span class="sxs-lookup"><span data-stu-id="9f95f-125">Foreign</span></span>  <br/> |<span data-ttu-id="9f95f-126">[[ユーザー] テーブル](users.md)から参照されている、このユーザーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="9f95f-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="9f95f-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="9f95f-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="9f95f-128">smallint</span><span class="sxs-lookup"><span data-stu-id="9f95f-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="9f95f-129">この会議中にこのユーザーによって送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="9f95f-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

