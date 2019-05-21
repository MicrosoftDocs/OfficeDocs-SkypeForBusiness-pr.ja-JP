---
title: QoE ビューの詳細
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: ビューでは、QoE SQL データベースからデータを返す最も一般的なシナリオがカバーされています。 データベーステーブルに直接アクセスするのではなく、カスタムレポートの作成に使用することをお勧めします。これは、ビューが将来のリリースとの下位互換性を維持する可能性が高いためです。
ms.openlocfilehash: c492b06f2b6e8050e4992837f0f2b7ebba106858
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294755"
---
# <a name="qoe-view-details"></a><span data-ttu-id="9796a-104">QoE ビューの詳細</span><span class="sxs-lookup"><span data-stu-id="9796a-104">QoE view details</span></span>
 
<span data-ttu-id="9796a-105">ビューでは、QoE SQL データベースからデータを返す最も一般的なシナリオがカバーされています。</span><span class="sxs-lookup"><span data-stu-id="9796a-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="9796a-106">データベーステーブルに直接アクセスするのではなく、カスタムレポートの作成に使用することをお勧めします。これは、ビューが将来のリリースとの下位互換性を維持する可能性が高いためです。</span><span class="sxs-lookup"><span data-stu-id="9796a-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="9796a-107">**ビュー名**</span><span class="sxs-lookup"><span data-stu-id="9796a-107">**View Name**</span></span>|<span data-ttu-id="9796a-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="9796a-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="9796a-109">AudioStreamDetail ビュー</span><span class="sxs-lookup"><span data-stu-id="9796a-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="9796a-110">データベース内の各オーディオストリームに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="9796a-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="9796a-111">MediaLine ビュー</span><span class="sxs-lookup"><span data-stu-id="9796a-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="9796a-112">データベース内の各メディア行に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="9796a-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="9796a-113">1つのオーディオセッションには通常、1つのオーディオメディアラインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9796a-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="9796a-114">通常、1つのオーディオとビデオ (A/V) セッションには、1つのオーディオメディアラインと1つのビデオメディアラインが含まれます。ただし、会議デバイスが使用されている場合、または [ギャラリー] ビューを使用している場合は、2つのビデオメディアがセッションに含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9796a-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="9796a-115">NetworkConfigurationSettings ビュー</span><span class="sxs-lookup"><span data-stu-id="9796a-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="9796a-116">ネットワーク構成に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="9796a-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="9796a-117">セッションビュー</span><span class="sxs-lookup"><span data-stu-id="9796a-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="9796a-118">データベースにレコードがあるセッションに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="9796a-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="9796a-119">UserAgent ビュー</span><span class="sxs-lookup"><span data-stu-id="9796a-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="9796a-120">データベースにレコードがあるセッションに関連しているユーザーエージェントに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="9796a-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="9796a-121">VideoStreamDetail ビュー</span><span class="sxs-lookup"><span data-stu-id="9796a-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="9796a-122">データベース内の各ビデオストリームに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="9796a-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

