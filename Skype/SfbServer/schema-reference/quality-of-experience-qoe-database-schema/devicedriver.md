---
title: DeviceDriver テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: 早い段階はテーブルをサポートします。 デバイスのレンダリングまたは各レコードをいずれかのキャプチャ デバイスで使用されているドライバーを表します。
ms.openlocfilehash: d5882ba853bd4909863fc5da415c993d4b59ea4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="devicedriver-table"></a><span data-ttu-id="bc3a7-104">DeviceDriver テーブル</span><span class="sxs-lookup"><span data-stu-id="bc3a7-104">DeviceDriver table</span></span>
 
<span data-ttu-id="bc3a7-105">早い段階はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bc3a7-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="bc3a7-106">デバイスのレンダリングまたは各レコードをいずれかのキャプチャ デバイスで使用されているドライバーを表します。</span><span class="sxs-lookup"><span data-stu-id="bc3a7-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="bc3a7-107">**列**</span><span class="sxs-lookup"><span data-stu-id="bc3a7-107">**Column**</span></span>|<span data-ttu-id="bc3a7-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="bc3a7-108">**Data Type**</span></span>|<span data-ttu-id="bc3a7-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="bc3a7-109">**Key/Index**</span></span>|<span data-ttu-id="bc3a7-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="bc3a7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bc3a7-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="bc3a7-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="bc3a7-112">int</span><span class="sxs-lookup"><span data-stu-id="bc3a7-112">int</span></span>  <br/> |<span data-ttu-id="bc3a7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="bc3a7-113">Primary</span></span>  <br/> |<span data-ttu-id="bc3a7-114">このデバイス ドライバーのレコードを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="bc3a7-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="bc3a7-115">**早い段階**</span><span class="sxs-lookup"><span data-stu-id="bc3a7-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="bc3a7-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="bc3a7-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="bc3a7-117">一意</span><span class="sxs-lookup"><span data-stu-id="bc3a7-117">unique</span></span>  <br/> |<span data-ttu-id="bc3a7-118">デバイス ドライバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="bc3a7-118">Device driver name.</span></span>  <br/> |
   

