---
title: Skype for Business Server 2015 の Dialogs テーブル
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs テーブルは、ピアツーピア セッションの DialogID に関する情報を格納するサポート テーブルです。
ms.openlocfilehash: a4f0bb8c63e165985ef09af8f9aafa071529bf1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816047"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="1edcf-103">Skype for Business Server 2015 の Dialogs テーブル</span><span class="sxs-lookup"><span data-stu-id="1edcf-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1edcf-104">Dialogs テーブルは、ピアツーピア セッションの DialogID に関する情報を格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="1edcf-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="1edcf-105">**列**</span><span class="sxs-lookup"><span data-stu-id="1edcf-105">**Column**</span></span>|<span data-ttu-id="1edcf-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="1edcf-106">**Data Type**</span></span>|<span data-ttu-id="1edcf-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="1edcf-107">**Key/Index**</span></span>|<span data-ttu-id="1edcf-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="1edcf-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1edcf-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="1edcf-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="1edcf-110">日付型</span><span class="sxs-lookup"><span data-stu-id="1edcf-110">datetime</span></span>  <br/> |<span data-ttu-id="1edcf-111">Primary</span><span class="sxs-lookup"><span data-stu-id="1edcf-111">Primary</span></span>  <br/> |<span data-ttu-id="1edcf-112">セッション要求の時刻。セッションを一意に識別するために SessionIDSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="1edcf-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="1edcf-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="1edcf-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="1edcf-114">int</span><span class="sxs-lookup"><span data-stu-id="1edcf-114">int</span></span>  <br/> |<span data-ttu-id="1edcf-115">Primary</span><span class="sxs-lookup"><span data-stu-id="1edcf-115">Primary</span></span>  <br/> |<span data-ttu-id="1edcf-116">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="1edcf-116">ID number to identify the session.</span></span> <span data-ttu-id="1edcf-117">セッションを一意に識別するために SessionIDTime と組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="1edcf-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="1edcf-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="1edcf-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="1edcf-119">int</span><span class="sxs-lookup"><span data-stu-id="1edcf-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="1edcf-120">ExternalID のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="1edcf-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="1edcf-121">このフィールドは、データベース検索の速度を向上するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1edcf-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="1edcf-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="1edcf-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="1edcf-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="1edcf-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="1edcf-124">バイナリとして格納される SIP ダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="1edcf-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="1edcf-125">バイナリの形式は次の形式です。</span><span class="sxs-lookup"><span data-stu-id="1edcf-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="1edcf-126">dialog;from-tag;to-tag</span><span class="sxs-lookup"><span data-stu-id="1edcf-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="1edcf-127">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="1edcf-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

