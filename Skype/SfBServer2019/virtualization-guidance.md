---
title: 'Skype for Business Server 2019 の仮想化のサポート '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: Skype for Business Server 2019 の仮想化のサポートについて説明します。'
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509034"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="3a0f1-103">Skype for Business Server 2019 の仮想化のサポート</span><span class="sxs-lookup"><span data-stu-id="3a0f1-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="3a0f1-104">仮想化では、Skype for Business Server 2019 がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="3a0f1-105">仮想化がサポートされていますが、いくつかの重要なポイントを覚えておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="3a0f1-106">仮想 CPU から物理 CPU への1:1 の比率を維持します。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="3a0f1-107">ゲストサーバーが動作している間は移動しないでください。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="3a0f1-108">ライブシステムの移行と仮想マシンの移植性はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="3a0f1-109">すべてのホストでハイパースレッディングを無効にします。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="3a0f1-110">ホストサーバー上で動的メモリを構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="3a0f1-111">ダイナミックディスクではなく、固定またはパススルーディスクを使用します。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="3a0f1-112">仮想ゲストに必要なものを超えるハイパーバイザーに対して、6-10% のオーバーヘッドを許可します。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="3a0f1-113">サポートされているハイパーバイザー</span><span class="sxs-lookup"><span data-stu-id="3a0f1-113">Supported hypervisors</span></span>

<span data-ttu-id="3a0f1-114">SfB サーバー2019は、Windows Server 2016 および Windows Server 2019 でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="3a0f1-115">サードパーティのハイパーバイザーの場合は、サーバー仮想化検証プログラム (SVVP) テストに合格した、関連する OS のためのハイパーバイザが必要です。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="3a0f1-116">SVVP リストの [Windows Server 2016 バージョン](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="3a0f1-117">SVVP リストの [Windows Server 2019 バージョン](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>

## <a name="stress-and-performance-tool"></a><span data-ttu-id="3a0f1-118">ストレスおよびパフォーマンスツール</span><span class="sxs-lookup"><span data-stu-id="3a0f1-118">Stress and performance tool</span></span>

<span data-ttu-id="3a0f1-119">Skype for Business Server 2019 ストレスおよびパフォーマンスツールには、Skype for business Server 2019 の容量計画を簡素化するツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-119">The Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019.</span></span> <span data-ttu-id="3a0f1-120">Skype for Business Server 2019 ストレスおよびパフォーマンスツールは、次のように役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-120">The Skype for Business Server 2019 Stress and Performance Tool will help you to:</span></span>

- <span data-ttu-id="3a0f1-121">Skype for Business Server 2019 のハードウェア計画を簡略化する</span><span class="sxs-lookup"><span data-stu-id="3a0f1-121">Simplify your hardware planning for Skype for Business Server 2019</span></span>
- <span data-ttu-id="3a0f1-122">パフォーマンスチューニングに関する知識とベストプラクティスを向上させる</span><span class="sxs-lookup"><span data-stu-id="3a0f1-122">Provide you with increased knowledge and best practices for performance tuning</span></span>
- <span data-ttu-id="3a0f1-123">目的の Skype for Business Server 2019 展開のパフォーマンスを測定する</span><span class="sxs-lookup"><span data-stu-id="3a0f1-123">Measure the performance of your intended Skype for Business Server 2019 deployments</span></span>
 
<span data-ttu-id="3a0f1-124">このツールは、 [ここ](https://www.microsoft.com/download/details.aspx?id=101447)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="3a0f1-124">You can download the tool from [here](https://www.microsoft.com/download/details.aspx?id=101447).</span></span>
