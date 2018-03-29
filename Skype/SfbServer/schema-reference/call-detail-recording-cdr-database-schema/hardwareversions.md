---
title: ビジネス サーバー 2015 の Skype での HardwareVersions テーブル
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
ms.openlocfilehash: 1a21d0d46cc64d5b115add8aec05d291d9856a55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="hardwareversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c112d-104">ビジネス サーバー 2015 の Skype での HardwareVersions テーブル</span><span class="sxs-lookup"><span data-stu-id="c112d-104">HardwareVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c112d-105">HardwareVersions はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c112d-105">The HardwareVersions table is a supporting table.</span></span> <span data-ttu-id="c112d-106">各レコードは、1 つのデバイスのハードウェアのバージョンに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="c112d-106">Each record stores information about one device hardware version.</span></span>
  
|<span data-ttu-id="c112d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="c112d-107">**Column**</span></span>|<span data-ttu-id="c112d-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c112d-108">**Data Type**</span></span>|<span data-ttu-id="c112d-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="c112d-109">**Key/Index**</span></span>|<span data-ttu-id="c112d-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="c112d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c112d-111">**バージョン Id**</span><span class="sxs-lookup"><span data-stu-id="c112d-111">**VersionId**</span></span> <br/> |<span data-ttu-id="c112d-112">int</span><span class="sxs-lookup"><span data-stu-id="c112d-112">int</span></span>  <br/> |<span data-ttu-id="c112d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c112d-113">Primary</span></span>  <br/> |<span data-ttu-id="c112d-114">このハードウェアのバージョンを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="c112d-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="c112d-115">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="c112d-115">**Version**</span></span> <br/> |<span data-ttu-id="c112d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c112d-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="c112d-117">ハードウェアのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="c112d-117">Hardware version.</span></span>  <br/> |
   

