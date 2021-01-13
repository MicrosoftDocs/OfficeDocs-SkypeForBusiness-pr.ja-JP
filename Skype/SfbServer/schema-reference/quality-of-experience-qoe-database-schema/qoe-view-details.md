---
title: QoE ビューの詳細
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
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: ビューは、QoE データベースからデータを返す最も一般的SQLします。 データベース テーブルに直接アクセスするのではなく、カスタム レポートを作成するために使用するビューをお勧めします。これは、ビューが将来のリリースとの下位互換性を維持する可能性が高いためです。
ms.openlocfilehash: cabe483da624d801b9b87d51ba61caed7a22f7d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834477"
---
# <a name="qoe-view-details"></a><span data-ttu-id="f29d0-104">QoE ビューの詳細</span><span class="sxs-lookup"><span data-stu-id="f29d0-104">QoE view details</span></span>
 
<span data-ttu-id="f29d0-105">ビューは、QoE データベースからデータを返す最も一般的SQLします。</span><span class="sxs-lookup"><span data-stu-id="f29d0-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="f29d0-106">データベース テーブルに直接アクセスするのではなく、カスタム レポートを作成するために使用するビューをお勧めします。これは、ビューが将来のリリースとの下位互換性を維持する可能性が高いためです。</span><span class="sxs-lookup"><span data-stu-id="f29d0-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="f29d0-107">**View Name/ビュー名**</span><span class="sxs-lookup"><span data-stu-id="f29d0-107">**View Name**</span></span>|<span data-ttu-id="f29d0-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="f29d0-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="f29d0-109">AudioStreamDetail ビュー</span><span class="sxs-lookup"><span data-stu-id="f29d0-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="f29d0-110">データベース内の各オーディオ ストリームについての情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="f29d0-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="f29d0-111">MediaLine ビュー</span><span class="sxs-lookup"><span data-stu-id="f29d0-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="f29d0-112">データベース内の各メディア ラインについての情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="f29d0-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="f29d0-113">通常、1 つの音声セッションに 1 つの音声メディア ラインが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f29d0-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="f29d0-114">また、通常は 1 つの音声ビデオ (A/V) セッションに 1 つの音声メディア ラインと 1 つのビデオ メディア ラインが含まれますが、会議デバイスまたはギャラリー ビューが使用される場合は、セッションに 2 つのビデオ メディア ラインが含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="f29d0-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="f29d0-115">NetworkConfigurationSettings ビュー</span><span class="sxs-lookup"><span data-stu-id="f29d0-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="f29d0-116">ネットワーク構成についての情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="f29d0-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="f29d0-117">セッション ビュー</span><span class="sxs-lookup"><span data-stu-id="f29d0-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="f29d0-118">データベース内のレコードを持つセッションについての情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="f29d0-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="f29d0-119">UserAgent ビュー</span><span class="sxs-lookup"><span data-stu-id="f29d0-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="f29d0-120">データベース内のレコードを持つセッションに関与しているユーザー エージェントについての情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="f29d0-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="f29d0-121">VideoStreamDetail ビュー</span><span class="sxs-lookup"><span data-stu-id="f29d0-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="f29d0-122">データベース内の各ビデオ ストリームについての情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="f29d0-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

