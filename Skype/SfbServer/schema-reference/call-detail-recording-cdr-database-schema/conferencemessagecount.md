---
title: Skype for Business Server 2015 の ConferenceMessageCount テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: この表の各レコードは、1 つの IM 会議で 1 人のユーザーを表し、そのユーザーが送信したメッセージの数を含む。 各電話会議は、この表の複数のレコードで表されます。ユーザーごとに 1 つのレコード。
ms.openlocfilehash: b931b45915fc12fb01ea36f81bee62f36914e903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813277"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="7070e-104">Skype for Business Server 2015 の ConferenceMessageCount テーブル</span><span class="sxs-lookup"><span data-stu-id="7070e-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7070e-105">この表の各レコードは、1 つの IM 会議で 1 人のユーザーを表し、そのユーザーが送信したメッセージの数を含む。</span><span class="sxs-lookup"><span data-stu-id="7070e-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="7070e-106">各電話会議は、この表の複数のレコードで表されます。ユーザーごとに 1 つのレコード。</span><span class="sxs-lookup"><span data-stu-id="7070e-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="7070e-107">**列**</span><span class="sxs-lookup"><span data-stu-id="7070e-107">**Column**</span></span>|<span data-ttu-id="7070e-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="7070e-108">**Data Type**</span></span>|<span data-ttu-id="7070e-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="7070e-109">**Key/Index**</span></span>|<span data-ttu-id="7070e-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="7070e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7070e-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="7070e-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="7070e-112">日付型</span><span class="sxs-lookup"><span data-stu-id="7070e-112">datetime</span></span>  <br/> |<span data-ttu-id="7070e-113">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="7070e-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="7070e-114">会議インスタンスの時間。</span><span class="sxs-lookup"><span data-stu-id="7070e-114">Time of conference instance.</span></span> <span data-ttu-id="7070e-115">**SessionIdSeq と組み合わせて使用して**、会議インスタンスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="7070e-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="7070e-116">詳細については [、Skype for Business Server 2015](conferences.md) の電話会議の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7070e-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="7070e-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="7070e-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="7070e-118">int</span><span class="sxs-lookup"><span data-stu-id="7070e-118">int</span></span>  <br/> |<span data-ttu-id="7070e-119">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="7070e-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="7070e-120">会議インスタンスを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="7070e-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="7070e-121">**SessionIdTime と組み合わせて使用し**、会議インスタンスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="7070e-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="7070e-122">詳細については [、Skype for Business Server 2015](conferences.md) の電話会議の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7070e-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="7070e-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="7070e-123">**UserId**</span></span> <br/> |<span data-ttu-id="7070e-124">int</span><span class="sxs-lookup"><span data-stu-id="7070e-124">int</span></span>  <br/> |<span data-ttu-id="7070e-125">外部</span><span class="sxs-lookup"><span data-stu-id="7070e-125">Foreign</span></span>  <br/> |<span data-ttu-id="7070e-126">Users テーブルから参照される、このユーザーを識別する一[意の番号。](users.md)</span><span class="sxs-lookup"><span data-stu-id="7070e-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="7070e-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="7070e-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="7070e-128">smallint</span><span class="sxs-lookup"><span data-stu-id="7070e-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="7070e-129">このユーザーが会議中に送信したメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="7070e-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

