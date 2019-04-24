---
title: ビジネス サーバー 2015 の Skype でのダイアログ ボックスのテーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: ダイアログ ボックスのテーブルは、ピア ツー ピア セッションの DialogIDs に関する情報を格納するサポート テーブルです。
ms.openlocfilehash: af7816c202f995e826567391bf32c5c32a2d0d94
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213657"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="7bd5e-103">ビジネス サーバー 2015 の Skype でのダイアログ ボックスのテーブル</span><span class="sxs-lookup"><span data-stu-id="7bd5e-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7bd5e-104">ダイアログ ボックスのテーブルは、ピア ツー ピア セッションの DialogIDs に関する情報を格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="7bd5e-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="7bd5e-105">**列**</span><span class="sxs-lookup"><span data-stu-id="7bd5e-105">**Column**</span></span>|<span data-ttu-id="7bd5e-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="7bd5e-106">**Data Type**</span></span>|<span data-ttu-id="7bd5e-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="7bd5e-107">**Key/Index**</span></span>|<span data-ttu-id="7bd5e-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="7bd5e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7bd5e-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="7bd5e-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="7bd5e-110">datetime</span><span class="sxs-lookup"><span data-stu-id="7bd5e-110">datetime</span></span>  <br/> |<span data-ttu-id="7bd5e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="7bd5e-111">Primary</span></span>  <br/> |<span data-ttu-id="7bd5e-112">セッションの要求の時間セッションを一意に識別するのには SessionIDSeq と組み合わせてを使用します。</span><span class="sxs-lookup"><span data-stu-id="7bd5e-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="7bd5e-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="7bd5e-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="7bd5e-114">int</span><span class="sxs-lookup"><span data-stu-id="7bd5e-114">int</span></span>  <br/> |<span data-ttu-id="7bd5e-115">Primary</span><span class="sxs-lookup"><span data-stu-id="7bd5e-115">Primary</span></span>  <br/> |<span data-ttu-id="7bd5e-116">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="7bd5e-116">ID number to identify the session.</span></span> <span data-ttu-id="7bd5e-117">セッションを一意に識別するのには SessionIDTime と組み合わせてを使用します。</span><span class="sxs-lookup"><span data-stu-id="7bd5e-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="7bd5e-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="7bd5e-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="7bd5e-119">int</span><span class="sxs-lookup"><span data-stu-id="7bd5e-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="7bd5e-120">ExternalID のチェックサムです。</span><span class="sxs-lookup"><span data-stu-id="7bd5e-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="7bd5e-121">このフィールドはデータベース検索の速度を上げるために使用します。</span><span class="sxs-lookup"><span data-stu-id="7bd5e-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="7bd5e-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="7bd5e-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="7bd5e-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="7bd5e-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="7bd5e-124">SIP ダイアログの ID をバイナリとして格納されています。</span><span class="sxs-lookup"><span data-stu-id="7bd5e-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="7bd5e-125">バイナリの形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7bd5e-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="7bd5e-126">ダイアログ; タグからタグに</span><span class="sxs-lookup"><span data-stu-id="7bd5e-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="7bd5e-127">このデータは、この構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="7bd5e-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

