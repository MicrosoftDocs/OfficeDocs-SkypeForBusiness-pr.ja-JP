---
title: ビジネス サーバー 2015 の Skype での HardwareVersions テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca05582b-082c-4bab-9233-36fc9434dbca
description: HardwareVersions はテーブルをサポートします。 各レコードは、1 つのデバイスのハードウェアのバージョンに関する情報を格納します。
ms.openlocfilehash: 93eb75278958cba72a4a521c588445e4fadb2e3f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892675"
---
# <a name="hardwareversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9fb83-104">ビジネス サーバー 2015 の Skype での HardwareVersions テーブル</span><span class="sxs-lookup"><span data-stu-id="9fb83-104">HardwareVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9fb83-105">HardwareVersions はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9fb83-105">The HardwareVersions table is a supporting table.</span></span> <span data-ttu-id="9fb83-106">各レコードは、1 つのデバイスのハードウェアのバージョンに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="9fb83-106">Each record stores information about one device hardware version.</span></span>
  
|<span data-ttu-id="9fb83-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9fb83-107">**Column**</span></span>|<span data-ttu-id="9fb83-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9fb83-108">**Data Type**</span></span>|<span data-ttu-id="9fb83-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="9fb83-109">**Key/Index**</span></span>|<span data-ttu-id="9fb83-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="9fb83-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9fb83-111">**バージョン Id**</span><span class="sxs-lookup"><span data-stu-id="9fb83-111">**VersionId**</span></span> <br/> |<span data-ttu-id="9fb83-112">int</span><span class="sxs-lookup"><span data-stu-id="9fb83-112">int</span></span>  <br/> |<span data-ttu-id="9fb83-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9fb83-113">Primary</span></span>  <br/> |<span data-ttu-id="9fb83-114">このハードウェアのバージョンを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="9fb83-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="9fb83-115">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="9fb83-115">**Version**</span></span> <br/> |<span data-ttu-id="9fb83-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9fb83-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="9fb83-117">ハードウェアのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="9fb83-117">Hardware version.</span></span>  <br/> |
   

