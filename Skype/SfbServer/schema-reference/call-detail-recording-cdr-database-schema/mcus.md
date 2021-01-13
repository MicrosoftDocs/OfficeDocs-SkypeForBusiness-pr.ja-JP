---
title: Skype for Business Server 2015 の Mcus テーブル
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus テーブルはサポート テーブルです。 各レコードには、1 つの会議サービスに関する情報が格納されます。 これには、IM 会議サービスとテレフォニー会議サービス (フロントエンド サーバー上のプロセスとして実行される) や、Web 会議サービスと音声ビデオ会議サービスが含まれます。
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821427"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="56ec8-105">Skype for Business Server 2015 の Mcus テーブル</span><span class="sxs-lookup"><span data-stu-id="56ec8-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="56ec8-106">Mcus テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="56ec8-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="56ec8-107">各レコードには、1 つの会議サービスに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="56ec8-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="56ec8-108">これには、IM 会議サービスとテレフォニー会議サービス (フロントエンド サーバー上のプロセスとして実行される) や、Web 会議サービスと音声ビデオ会議サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="56ec8-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="56ec8-109">**列**</span><span class="sxs-lookup"><span data-stu-id="56ec8-109">**Column**</span></span>|<span data-ttu-id="56ec8-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="56ec8-110">**Data Type**</span></span>|<span data-ttu-id="56ec8-111">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="56ec8-111">**Key/Index**</span></span>|<span data-ttu-id="56ec8-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="56ec8-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="56ec8-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="56ec8-113">**McuId**</span></span> <br/> |<span data-ttu-id="56ec8-114">int</span><span class="sxs-lookup"><span data-stu-id="56ec8-114">int</span></span>  <br/> |<span data-ttu-id="56ec8-115">Primary</span><span class="sxs-lookup"><span data-stu-id="56ec8-115">Primary</span></span>  <br/> |<span data-ttu-id="56ec8-116">この会議サーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="56ec8-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="56ec8-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="56ec8-117">**McuUri**</span></span> <br/> |<span data-ttu-id="56ec8-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="56ec8-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="56ec8-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="56ec8-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="56ec8-120">inyint</span><span class="sxs-lookup"><span data-stu-id="56ec8-120">inyint</span></span>  <br/> | <span data-ttu-id="56ec8-121">外部</span><span class="sxs-lookup"><span data-stu-id="56ec8-121">Foreign</span></span> <br/> |<span data-ttu-id="56ec8-122">会議サーバーの種類 (conf:chat (VM 用) や conf:audio-video など)。</span><span class="sxs-lookup"><span data-stu-id="56ec8-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="56ec8-123">詳細については [、UriTypes の表](uritypes.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56ec8-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

