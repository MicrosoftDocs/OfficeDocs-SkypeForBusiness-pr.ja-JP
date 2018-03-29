---
title: ビジネス サーバー 2015 の Skype の Mcu のテーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcu はテーブルをサポートします。 各レコードは、1 つの会議サービスに関する情報を格納します。 IM 会議サービス、テレフォニー会議サービス (フロント エンド サーバー上でプロセスとして実行)、および Web 会議サービスおよび A が含まれます/V 会議サービスです。
ms.openlocfilehash: 2a85d46e733d230dc7c8096c8804146b19766bcf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5c20e-105">ビジネス サーバー 2015 の Skype の Mcu のテーブル</span><span class="sxs-lookup"><span data-stu-id="5c20e-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5c20e-106">Mcu はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5c20e-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="5c20e-107">各レコードは、1 つの会議サービスに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="5c20e-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="5c20e-108">IM 会議サービス、テレフォニー会議サービス (フロント エンド サーバー上でプロセスとして実行)、および Web 会議サービスおよび A が含まれます/V 会議サービスです。</span><span class="sxs-lookup"><span data-stu-id="5c20e-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="5c20e-109">**列**</span><span class="sxs-lookup"><span data-stu-id="5c20e-109">**Column**</span></span>|<span data-ttu-id="5c20e-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5c20e-110">**Data Type**</span></span>|<span data-ttu-id="5c20e-111">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="5c20e-111">**Key/Index**</span></span>|<span data-ttu-id="5c20e-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="5c20e-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5c20e-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="5c20e-113">**McuId**</span></span> <br/> |<span data-ttu-id="5c20e-114">int</span><span class="sxs-lookup"><span data-stu-id="5c20e-114">int</span></span>  <br/> |<span data-ttu-id="5c20e-115">Primary</span><span class="sxs-lookup"><span data-stu-id="5c20e-115">Primary</span></span>  <br/> |<span data-ttu-id="5c20e-116">この会議サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="5c20e-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="5c20e-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="5c20e-117">**McuUri**</span></span> <br/> |<span data-ttu-id="5c20e-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="5c20e-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="5c20e-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="5c20e-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="5c20e-120">inyint</span><span class="sxs-lookup"><span data-stu-id="5c20e-120">inyint</span></span>  <br/> | <span data-ttu-id="5c20e-121">外部</span><span class="sxs-lookup"><span data-stu-id="5c20e-121">Foreign</span></span> <br/> |<span data-ttu-id="5c20e-122">(IMs) の conf:chat や conf:audio などの会議サーバーの種類のビデオです。</span><span class="sxs-lookup"><span data-stu-id="5c20e-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="5c20e-123">詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c20e-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

