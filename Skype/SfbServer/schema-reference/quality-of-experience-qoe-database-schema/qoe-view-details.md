---
title: QoE ビューの詳細
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: ビューでは、QoE の SQL データベースからデータを返すための最も一般的なシナリオを説明します。 データベース テーブルに直接アクセスするのではなく、カスタム レポートを作成するために使用されるビューをお勧めビューは、下位の将来のリリースとの互換性を維持する可能性が高いためにです。
ms.openlocfilehash: 2726900a1fc31c6e69571123c87137b3291a507e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924865"
---
# <a name="qoe-view-details"></a><span data-ttu-id="17b31-104">QoE ビューの詳細</span><span class="sxs-lookup"><span data-stu-id="17b31-104">QoE view details</span></span>
 
<span data-ttu-id="17b31-105">ビューでは、QoE の SQL データベースからデータを返すための最も一般的なシナリオを説明します。</span><span class="sxs-lookup"><span data-stu-id="17b31-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="17b31-106">データベース テーブルに直接アクセスするのではなく、カスタム レポートを作成するために使用されるビューをお勧めビューは、下位の将来のリリースとの互換性を維持する可能性が高いためにです。</span><span class="sxs-lookup"><span data-stu-id="17b31-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="17b31-107">**ビュー名**</span><span class="sxs-lookup"><span data-stu-id="17b31-107">**View Name**</span></span>|<span data-ttu-id="17b31-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="17b31-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="17b31-109">AudioStreamDetail ビュー</span><span class="sxs-lookup"><span data-stu-id="17b31-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="17b31-110">各オーディオ ストリームに関する情報をデータベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="17b31-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="17b31-111">MediaLine ビュー</span><span class="sxs-lookup"><span data-stu-id="17b31-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="17b31-112">各メディアの明細行に関する情報をデータベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="17b31-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="17b31-113">通常、1 つのオーディオ セッションには、オーディオ メディアの 1 つの行が含まれています。</span><span class="sxs-lookup"><span data-stu-id="17b31-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="17b31-114">1 つのオーディオおよびビデオ (A/V) セッションでは通常 1 つのオーディオ メディアの行と 1 つのビデオ メディア ラインです。ただし、セッション可能性がありますが含まれている 2 つのビデオ メディア ライン会議用デバイスが使用されている場合、またはギャラリーのビューを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="17b31-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="17b31-115">NetworkConfigurationSettings ビュー</span><span class="sxs-lookup"><span data-stu-id="17b31-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="17b31-116">ネットワーク構成に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="17b31-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="17b31-117">セッションの表示</span><span class="sxs-lookup"><span data-stu-id="17b31-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="17b31-118">データベースにレコードが存在しているセッションに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="17b31-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="17b31-119">UserAgent ビュー</span><span class="sxs-lookup"><span data-stu-id="17b31-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="17b31-120">データベースにレコードが存在するセッションに関係しているユーザー エージェントに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="17b31-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="17b31-121">VideoStreamDetail ビュー</span><span class="sxs-lookup"><span data-stu-id="17b31-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="17b31-122">各ビデオ ストリームの情報をデータベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="17b31-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

