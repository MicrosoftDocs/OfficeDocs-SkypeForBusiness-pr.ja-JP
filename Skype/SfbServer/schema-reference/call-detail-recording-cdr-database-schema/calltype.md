---
title: Skype for Business Server 2015 の CallType テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType テーブルは、可能な呼び出しの種類の一覧を格納する静的テーブルです。
ms.openlocfilehash: 992e5682aedf7a0b9063960992197970146c8cfc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296561"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4eedb-103">Skype for Business Server 2015 の CallType テーブル</span><span class="sxs-lookup"><span data-stu-id="4eedb-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4eedb-104">CallType テーブルは、可能な呼び出しの種類の一覧を格納する静的テーブルです。</span><span class="sxs-lookup"><span data-stu-id="4eedb-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="4eedb-105">**列**</span><span class="sxs-lookup"><span data-stu-id="4eedb-105">**Column**</span></span>|<span data-ttu-id="4eedb-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="4eedb-106">**Data Type**</span></span>|<span data-ttu-id="4eedb-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="4eedb-107">**Key/Index**</span></span>|<span data-ttu-id="4eedb-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="4eedb-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4eedb-109">**発信者の Typeid**</span><span class="sxs-lookup"><span data-stu-id="4eedb-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="4eedb-110">int</span><span class="sxs-lookup"><span data-stu-id="4eedb-110">int</span></span>  <br/> |<span data-ttu-id="4eedb-111">Primary</span><span class="sxs-lookup"><span data-stu-id="4eedb-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="4eedb-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="4eedb-112">**CallType**</span></span> <br/> |<span data-ttu-id="4eedb-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="4eedb-113">nvarchar</span></span>  <br/> || <span data-ttu-id="4eedb-114">許可される値:</span><span class="sxs-lookup"><span data-stu-id="4eedb-114">Allowed values:</span></span> <br/>  <span data-ttu-id="4eedb-115">0--不明</span><span class="sxs-lookup"><span data-stu-id="4eedb-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="4eedb-116">1-インスタントメッセージ (im)</span><span class="sxs-lookup"><span data-stu-id="4eedb-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="4eedb-117">2--アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="4eedb-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="4eedb-118">3--オーディオ</span><span class="sxs-lookup"><span data-stu-id="4eedb-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="4eedb-119">4-オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="4eedb-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="4eedb-120">5-ファイル送信</span><span class="sxs-lookup"><span data-stu-id="4eedb-120">5 - File Transfer</span></span> <br/> |
   

