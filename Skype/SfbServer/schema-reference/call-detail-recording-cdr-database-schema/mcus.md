---
title: ビジネス サーバー 2015 の Skype の Mcu のテーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcu はテーブルをサポートします。 各レコードは、1 つの会議サービスに関する情報を格納します。 IM 会議サービス、テレフォニー会議サービス (フロント エンド サーバー上でプロセスとして実行)、および Web 会議サービスおよび A が含まれます/V 会議サービスです。
ms.openlocfilehash: 6b5df793008fcf7586d62cab77a1b362848374ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930673"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="fc854-105">ビジネス サーバー 2015 の Skype の Mcu のテーブル</span><span class="sxs-lookup"><span data-stu-id="fc854-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fc854-106">Mcu はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="fc854-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="fc854-107">各レコードは、1 つの会議サービスに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="fc854-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="fc854-108">IM 会議サービス、テレフォニー会議サービス (フロント エンド サーバー上でプロセスとして実行)、および Web 会議サービスおよび A が含まれます/V 会議サービスです。</span><span class="sxs-lookup"><span data-stu-id="fc854-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="fc854-109">**列**</span><span class="sxs-lookup"><span data-stu-id="fc854-109">**Column**</span></span>|<span data-ttu-id="fc854-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="fc854-110">**Data Type**</span></span>|<span data-ttu-id="fc854-111">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="fc854-111">**Key/Index**</span></span>|<span data-ttu-id="fc854-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="fc854-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fc854-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="fc854-113">**McuId**</span></span> <br/> |<span data-ttu-id="fc854-114">int</span><span class="sxs-lookup"><span data-stu-id="fc854-114">int</span></span>  <br/> |<span data-ttu-id="fc854-115">Primary</span><span class="sxs-lookup"><span data-stu-id="fc854-115">Primary</span></span>  <br/> |<span data-ttu-id="fc854-116">この会議サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="fc854-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="fc854-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="fc854-117">**McuUri**</span></span> <br/> |<span data-ttu-id="fc854-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="fc854-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="fc854-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="fc854-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="fc854-120">inyint</span><span class="sxs-lookup"><span data-stu-id="fc854-120">inyint</span></span>  <br/> | <span data-ttu-id="fc854-121">外部</span><span class="sxs-lookup"><span data-stu-id="fc854-121">Foreign</span></span> <br/> |<span data-ttu-id="fc854-122">(IMs) の conf:chat や conf:audio などの会議サーバーの種類のビデオです。</span><span class="sxs-lookup"><span data-stu-id="fc854-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="fc854-123">詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc854-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

