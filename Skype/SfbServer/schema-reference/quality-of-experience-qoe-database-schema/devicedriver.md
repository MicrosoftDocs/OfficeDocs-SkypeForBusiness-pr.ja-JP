---
title: DeviceDriver テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: DeviceDriver テーブルはサポートされているテーブルです。 各レコードは、キャプチャデバイスまたはレンダーデバイスのいずれかで使用されるドライバーを表します。
ms.openlocfilehash: 6a58bba9edcb0351c929c1406dcbc1ebaedec364
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294979"
---
# <a name="devicedriver-table"></a><span data-ttu-id="fec9c-104">DeviceDriver テーブル</span><span class="sxs-lookup"><span data-stu-id="fec9c-104">DeviceDriver table</span></span>
 
<span data-ttu-id="fec9c-105">DeviceDriver テーブルはサポートされているテーブルです。</span><span class="sxs-lookup"><span data-stu-id="fec9c-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="fec9c-106">各レコードは、キャプチャデバイスまたはレンダーデバイスのいずれかで使用されるドライバーを表します。</span><span class="sxs-lookup"><span data-stu-id="fec9c-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="fec9c-107">**列**</span><span class="sxs-lookup"><span data-stu-id="fec9c-107">**Column**</span></span>|<span data-ttu-id="fec9c-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="fec9c-108">**Data Type**</span></span>|<span data-ttu-id="fec9c-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="fec9c-109">**Key/Index**</span></span>|<span data-ttu-id="fec9c-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="fec9c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fec9c-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="fec9c-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="fec9c-112">int</span><span class="sxs-lookup"><span data-stu-id="fec9c-112">int</span></span>  <br/> |<span data-ttu-id="fec9c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fec9c-113">Primary</span></span>  <br/> |<span data-ttu-id="fec9c-114">このデバイスドライバーレコードを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="fec9c-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="fec9c-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="fec9c-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="fec9c-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fec9c-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="fec9c-117">一意</span><span class="sxs-lookup"><span data-stu-id="fec9c-117">unique</span></span>  <br/> |<span data-ttu-id="fec9c-118">デバイスドライバ名。</span><span class="sxs-lookup"><span data-stu-id="fec9c-118">Device driver name.</span></span>  <br/> |
   

