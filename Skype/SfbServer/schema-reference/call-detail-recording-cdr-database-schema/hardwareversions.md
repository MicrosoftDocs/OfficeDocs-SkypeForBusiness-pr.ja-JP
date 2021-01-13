---
title: Skype for Business Server 2015 の HardwareVersions テーブル
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
ms.assetid: ca05582b-082c-4bab-9233-36fc9434dbca
description: HardwareVersions テーブルはサポート テーブルです。 各レコードには、1 つのデバイス ハードウェア バージョンに関する情報が格納されます。
ms.openlocfilehash: 2b9ac6b31f0af30e896d2943eaa4065aecdd4de3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821577"
---
# <a name="hardwareversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c5e20-104">Skype for Business Server 2015 の HardwareVersions テーブル</span><span class="sxs-lookup"><span data-stu-id="c5e20-104">HardwareVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c5e20-105">HardwareVersions テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="c5e20-105">The HardwareVersions table is a supporting table.</span></span> <span data-ttu-id="c5e20-106">各レコードには、1 つのデバイス ハードウェア バージョンに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c5e20-106">Each record stores information about one device hardware version.</span></span>
  
|<span data-ttu-id="c5e20-107">**列**</span><span class="sxs-lookup"><span data-stu-id="c5e20-107">**Column**</span></span>|<span data-ttu-id="c5e20-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c5e20-108">**Data Type**</span></span>|<span data-ttu-id="c5e20-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="c5e20-109">**Key/Index**</span></span>|<span data-ttu-id="c5e20-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="c5e20-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c5e20-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="c5e20-111">**VersionId**</span></span> <br/> |<span data-ttu-id="c5e20-112">int</span><span class="sxs-lookup"><span data-stu-id="c5e20-112">int</span></span>  <br/> |<span data-ttu-id="c5e20-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c5e20-113">Primary</span></span>  <br/> |<span data-ttu-id="c5e20-114">このハードウェア バージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="c5e20-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="c5e20-115">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="c5e20-115">**Version**</span></span> <br/> |<span data-ttu-id="c5e20-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c5e20-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="c5e20-117">ハードウェア バージョン。</span><span class="sxs-lookup"><span data-stu-id="c5e20-117">Hardware version.</span></span>  <br/> |
   

