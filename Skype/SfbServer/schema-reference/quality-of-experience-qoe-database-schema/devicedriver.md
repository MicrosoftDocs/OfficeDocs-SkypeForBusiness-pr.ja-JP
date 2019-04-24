---
title: DeviceDriver テーブル
ms.reviewer: ''
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
ms.openlocfilehash: e985c594f0c1ad21bc95d266f908ed77a46ff76a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212257"
---
# <a name="devicedriver-table"></a><span data-ttu-id="37968-104">DeviceDriver テーブル</span><span class="sxs-lookup"><span data-stu-id="37968-104">DeviceDriver table</span></span>
 
<span data-ttu-id="37968-105">早い段階はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="37968-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="37968-106">デバイスのレンダリングまたは各レコードをいずれかのキャプチャ デバイスで使用されているドライバーを表します。</span><span class="sxs-lookup"><span data-stu-id="37968-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="37968-107">**列**</span><span class="sxs-lookup"><span data-stu-id="37968-107">**Column**</span></span>|<span data-ttu-id="37968-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="37968-108">**Data Type**</span></span>|<span data-ttu-id="37968-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="37968-109">**Key/Index**</span></span>|<span data-ttu-id="37968-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="37968-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="37968-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="37968-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="37968-112">int</span><span class="sxs-lookup"><span data-stu-id="37968-112">int</span></span>  <br/> |<span data-ttu-id="37968-113">Primary</span><span class="sxs-lookup"><span data-stu-id="37968-113">Primary</span></span>  <br/> |<span data-ttu-id="37968-114">このデバイス ドライバーのレコードを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="37968-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="37968-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="37968-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="37968-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="37968-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="37968-117">一意</span><span class="sxs-lookup"><span data-stu-id="37968-117">unique</span></span>  <br/> |<span data-ttu-id="37968-118">デバイス ドライバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="37968-118">Device driver name.</span></span>  <br/> |
   

