---
title: Roles テーブル
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Roles テーブルは、会議で使用可能な役割 (参加者、発表者など) のリストを格納する静的なテーブルです。
ms.openlocfilehash: 6c5e28ccd2d186b0122d70f91621a3365e6d2b07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809977"
---
# <a name="roles-table"></a><span data-ttu-id="a7e7e-103">Roles テーブル</span><span class="sxs-lookup"><span data-stu-id="a7e7e-103">Roles table</span></span>
 
<span data-ttu-id="a7e7e-104">Roles テーブルは、会議で使用可能な役割 (参加者、発表者など) のリストを格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="a7e7e-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="a7e7e-105">**列**</span><span class="sxs-lookup"><span data-stu-id="a7e7e-105">**Column**</span></span>|<span data-ttu-id="a7e7e-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="a7e7e-106">**Data Type**</span></span>|<span data-ttu-id="a7e7e-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="a7e7e-107">**Key/Index**</span></span>|<span data-ttu-id="a7e7e-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="a7e7e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7e7e-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="a7e7e-109">**RoleId**</span></span> <br/> |<span data-ttu-id="a7e7e-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="a7e7e-110">tinyint</span></span>  <br/> |<span data-ttu-id="a7e7e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="a7e7e-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="a7e7e-112">**役割**</span><span class="sxs-lookup"><span data-stu-id="a7e7e-112">**Role**</span></span> <br/> |<span data-ttu-id="a7e7e-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a7e7e-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="a7e7e-114">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a7e7e-114">Allowed values:</span></span> <br/>  <span data-ttu-id="a7e7e-115">0 - 不明</span><span class="sxs-lookup"><span data-stu-id="a7e7e-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="a7e7e-116">1 - 発表者</span><span class="sxs-lookup"><span data-stu-id="a7e7e-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="a7e7e-117">2 - 参加者</span><span class="sxs-lookup"><span data-stu-id="a7e7e-117">2 - Attendee</span></span> <br/> |
   

