---
title: Skype for Business Server 2015 のダイアログテーブル
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs テーブルは、ピアツーピアセッションの DialogIDs に関する情報を格納するサポートテーブルです。
ms.openlocfilehash: f6cfc3e078ee8f4492d6f5baf65f66df77d7aedf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815275"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a99b7-103">Skype for Business Server 2015 のダイアログテーブル</span><span class="sxs-lookup"><span data-stu-id="a99b7-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a99b7-104">Dialogs テーブルは、ピアツーピアセッションの DialogIDs に関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="a99b7-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="a99b7-105">**列**</span><span class="sxs-lookup"><span data-stu-id="a99b7-105">**Column**</span></span>|<span data-ttu-id="a99b7-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="a99b7-106">**Data Type**</span></span>|<span data-ttu-id="a99b7-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="a99b7-107">**Key/Index**</span></span>|<span data-ttu-id="a99b7-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="a99b7-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a99b7-109">**セッション Id**</span><span class="sxs-lookup"><span data-stu-id="a99b7-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="a99b7-110">datetime</span><span class="sxs-lookup"><span data-stu-id="a99b7-110">datetime</span></span>  <br/> |<span data-ttu-id="a99b7-111">Primary</span><span class="sxs-lookup"><span data-stu-id="a99b7-111">Primary</span></span>  <br/> |<span data-ttu-id="a99b7-112">セッション要求の時刻。セッションを一意に識別するために SessionIDSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="a99b7-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="a99b7-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="a99b7-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="a99b7-114">int</span><span class="sxs-lookup"><span data-stu-id="a99b7-114">int</span></span>  <br/> |<span data-ttu-id="a99b7-115">Primary</span><span class="sxs-lookup"><span data-stu-id="a99b7-115">Primary</span></span>  <br/> |<span data-ttu-id="a99b7-116">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="a99b7-116">ID number to identify the session.</span></span> <span data-ttu-id="a99b7-117">セッションを一意に識別するために SessionIDTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="a99b7-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="a99b7-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="a99b7-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="a99b7-119">int</span><span class="sxs-lookup"><span data-stu-id="a99b7-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="a99b7-120">ExternalID のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="a99b7-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="a99b7-121">このフィールドは、データベースの検索速度を上げるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a99b7-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="a99b7-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="a99b7-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="a99b7-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="a99b7-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="a99b7-124">SIP ダイアログ ID。バイナリとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="a99b7-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="a99b7-125">バイナリの形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a99b7-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="a99b7-126">ダイアログ; 開始タグからタグへ</span><span class="sxs-lookup"><span data-stu-id="a99b7-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="a99b7-127">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="a99b7-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

