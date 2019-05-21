---
title: Skype for Business Server 2015 の mcu テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcu テーブルは、サポートテーブルです。 各レコードには、1つの会議サービスに関する情報が格納されます。 これには、IM 会議サービスと、(フロントエンドサーバーでプロセスとして実行される) テレフォニー会議サービス、および Web 会議サービスと A/V 会議サービスを含めることができます。
ms.openlocfilehash: fcd12bcc8da7aa6513d78e1a9c4a6f11930065aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296043"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="466af-105">Skype for Business Server 2015 の mcu テーブル</span><span class="sxs-lookup"><span data-stu-id="466af-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="466af-106">Mcu テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="466af-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="466af-107">各レコードには、1つの会議サービスに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="466af-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="466af-108">これには、IM 会議サービスと、(フロントエンドサーバーでプロセスとして実行される) テレフォニー会議サービス、および Web 会議サービスと A/V 会議サービスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="466af-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="466af-109">**列**</span><span class="sxs-lookup"><span data-stu-id="466af-109">**Column**</span></span>|<span data-ttu-id="466af-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="466af-110">**Data Type**</span></span>|<span data-ttu-id="466af-111">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="466af-111">**Key/Index**</span></span>|<span data-ttu-id="466af-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="466af-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="466af-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="466af-113">**McuId**</span></span> <br/> |<span data-ttu-id="466af-114">int</span><span class="sxs-lookup"><span data-stu-id="466af-114">int</span></span>  <br/> |<span data-ttu-id="466af-115">Primary</span><span class="sxs-lookup"><span data-stu-id="466af-115">Primary</span></span>  <br/> |<span data-ttu-id="466af-116">この会議サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="466af-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="466af-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="466af-117">**McuUri**</span></span> <br/> |<span data-ttu-id="466af-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="466af-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="466af-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="466af-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="466af-120">inyint</span><span class="sxs-lookup"><span data-stu-id="466af-120">inyint</span></span>  <br/> | <span data-ttu-id="466af-121">外部</span><span class="sxs-lookup"><span data-stu-id="466af-121">Foreign</span></span> <br/> |<span data-ttu-id="466af-122">会議サーバーの種類 (例: チャット (Im の場合) または conf: オーディオビデオ)。</span><span class="sxs-lookup"><span data-stu-id="466af-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="466af-123">詳細については、 [UriTypes の表](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="466af-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

