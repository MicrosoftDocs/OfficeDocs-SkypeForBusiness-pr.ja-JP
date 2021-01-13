---
title: DeviceDriver テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: DeviceDriver テーブルは、サポート テーブルです。 各レコードは、キャプチャ デバイスまたはレンダー デバイスが使用するドライバーを表します。
ms.openlocfilehash: 1f83bfd014fa5fb49f4d0f900e01aeecfe2b5f46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823077"
---
# <a name="devicedriver-table"></a><span data-ttu-id="6bb59-104">DeviceDriver テーブル</span><span class="sxs-lookup"><span data-stu-id="6bb59-104">DeviceDriver table</span></span>
 
<span data-ttu-id="6bb59-p102">DeviceDriver テーブルは、サポート テーブルです。各レコードは、キャプチャ デバイスまたはレンダー デバイスが使用するドライバーを表します。</span><span class="sxs-lookup"><span data-stu-id="6bb59-p102">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="6bb59-107">**列**</span><span class="sxs-lookup"><span data-stu-id="6bb59-107">**Column**</span></span>|<span data-ttu-id="6bb59-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="6bb59-108">**Data Type**</span></span>|<span data-ttu-id="6bb59-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="6bb59-109">**Key/Index**</span></span>|<span data-ttu-id="6bb59-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="6bb59-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6bb59-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="6bb59-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="6bb59-112">int</span><span class="sxs-lookup"><span data-stu-id="6bb59-112">int</span></span>  <br/> |<span data-ttu-id="6bb59-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6bb59-113">Primary</span></span>  <br/> |<span data-ttu-id="6bb59-114">このデバイス ドライバー レコードを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="6bb59-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="6bb59-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="6bb59-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="6bb59-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="6bb59-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="6bb59-117">unique</span><span class="sxs-lookup"><span data-stu-id="6bb59-117">unique</span></span>  <br/> |<span data-ttu-id="6bb59-118">デバイス ドライバー名。</span><span class="sxs-lookup"><span data-stu-id="6bb59-118">Device driver name.</span></span>  <br/> |
   

