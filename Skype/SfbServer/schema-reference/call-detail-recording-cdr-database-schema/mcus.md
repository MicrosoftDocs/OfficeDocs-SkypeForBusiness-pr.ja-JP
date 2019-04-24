---
title: ビジネス サーバー 2015 の Skype の Mcu のテーブル
ms.reviewer: ''
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
ms.openlocfilehash: e051af3a77d4f9b8231c122c596a3b6915f6f3e1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212974"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="07925-105">ビジネス サーバー 2015 の Skype の Mcu のテーブル</span><span class="sxs-lookup"><span data-stu-id="07925-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="07925-106">Mcu はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="07925-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="07925-107">各レコードは、1 つの会議サービスに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="07925-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="07925-108">IM 会議サービス、テレフォニー会議サービス (フロント エンド サーバー上でプロセスとして実行)、および Web 会議サービスおよび A が含まれます/V 会議サービスです。</span><span class="sxs-lookup"><span data-stu-id="07925-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="07925-109">**列**</span><span class="sxs-lookup"><span data-stu-id="07925-109">**Column**</span></span>|<span data-ttu-id="07925-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="07925-110">**Data Type**</span></span>|<span data-ttu-id="07925-111">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="07925-111">**Key/Index**</span></span>|<span data-ttu-id="07925-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="07925-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07925-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="07925-113">**McuId**</span></span> <br/> |<span data-ttu-id="07925-114">int</span><span class="sxs-lookup"><span data-stu-id="07925-114">int</span></span>  <br/> |<span data-ttu-id="07925-115">Primary</span><span class="sxs-lookup"><span data-stu-id="07925-115">Primary</span></span>  <br/> |<span data-ttu-id="07925-116">この会議サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="07925-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="07925-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="07925-117">**McuUri**</span></span> <br/> |<span data-ttu-id="07925-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="07925-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="07925-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="07925-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="07925-120">inyint</span><span class="sxs-lookup"><span data-stu-id="07925-120">inyint</span></span>  <br/> | <span data-ttu-id="07925-121">外部</span><span class="sxs-lookup"><span data-stu-id="07925-121">Foreign</span></span> <br/> |<span data-ttu-id="07925-122">(IMs) の conf:chat や conf:audio などの会議サーバーの種類のビデオです。</span><span class="sxs-lookup"><span data-stu-id="07925-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="07925-123">詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07925-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

