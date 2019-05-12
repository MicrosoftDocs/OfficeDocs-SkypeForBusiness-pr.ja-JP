---
title: DeviceDriver テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: 早い段階はテーブルをサポートします。 デバイスのレンダリングまたは各レコードをいずれかのキャプチャ デバイスで使用されているドライバーを表します。
ms.openlocfilehash: 9a011c7e555bad71f453510dca7c310e2467a505
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920174"
---
# <a name="devicedriver-table"></a><span data-ttu-id="1fd45-104">DeviceDriver テーブル</span><span class="sxs-lookup"><span data-stu-id="1fd45-104">DeviceDriver table</span></span>
 
<span data-ttu-id="1fd45-105">早い段階はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1fd45-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="1fd45-106">デバイスのレンダリングまたは各レコードをいずれかのキャプチャ デバイスで使用されているドライバーを表します。</span><span class="sxs-lookup"><span data-stu-id="1fd45-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="1fd45-107">**列**</span><span class="sxs-lookup"><span data-stu-id="1fd45-107">**Column**</span></span>|<span data-ttu-id="1fd45-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="1fd45-108">**Data Type**</span></span>|<span data-ttu-id="1fd45-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="1fd45-109">**Key/Index**</span></span>|<span data-ttu-id="1fd45-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="1fd45-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1fd45-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="1fd45-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="1fd45-112">int</span><span class="sxs-lookup"><span data-stu-id="1fd45-112">int</span></span>  <br/> |<span data-ttu-id="1fd45-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1fd45-113">Primary</span></span>  <br/> |<span data-ttu-id="1fd45-114">このデバイス ドライバーのレコードを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="1fd45-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="1fd45-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="1fd45-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="1fd45-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="1fd45-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="1fd45-117">一意</span><span class="sxs-lookup"><span data-stu-id="1fd45-117">unique</span></span>  <br/> |<span data-ttu-id="1fd45-118">デバイス ドライバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="1fd45-118">Device driver name.</span></span>  <br/> |
   

