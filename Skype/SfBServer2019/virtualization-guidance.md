---
title: 'Skype for Business Server 2019 の仮想化のサポート '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: Skype for Business Server 2019 の仮想化のサポートについて説明します。'
ms.openlocfilehash: a01f529d80e84df3f7ca844696738b079f78df26
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565956"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="6168e-103">Skype for Business Server 2019 の仮想化のサポート</span><span class="sxs-lookup"><span data-stu-id="6168e-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="6168e-104">仮想化では、Skype for Business Server 2019 がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6168e-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="6168e-105">仮想化がサポートされていますが、いくつかの重要なポイントを覚えておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="6168e-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="6168e-106">仮想 CPU から物理 CPU への1:1 の比率を維持します。</span><span class="sxs-lookup"><span data-stu-id="6168e-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="6168e-107">ゲストサーバーが動作している間は移動しないでください。</span><span class="sxs-lookup"><span data-stu-id="6168e-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="6168e-108">ライブシステムの移行と仮想マシンの移植性はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6168e-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="6168e-109">すべてのホストでハイパースレッディングを無効にします。</span><span class="sxs-lookup"><span data-stu-id="6168e-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="6168e-110">ホストサーバー上で動的メモリを構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="6168e-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="6168e-111">ダイナミックディスクではなく、固定またはパススルーディスクを使用します。</span><span class="sxs-lookup"><span data-stu-id="6168e-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="6168e-112">仮想ゲストに必要なものを超えるハイパーバイザーに対して、6-10% のオーバーヘッドを許可します。</span><span class="sxs-lookup"><span data-stu-id="6168e-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="6168e-113">サポートされているハイパーバイザー</span><span class="sxs-lookup"><span data-stu-id="6168e-113">Supported hypervisors</span></span>

<span data-ttu-id="6168e-114">SfB サーバー2019は、Windows Server 2016 および Windows Server 2019 でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6168e-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="6168e-115">サードパーティのハイパーバイザーの場合は、サーバー仮想化検証プログラム (SVVP) テストに合格した、関連する OS のためのハイパーバイザが必要です。</span><span class="sxs-lookup"><span data-stu-id="6168e-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="6168e-116">SVVP リストの[Windows Server 2016 バージョン](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6168e-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="6168e-117">SVVP リストの[Windows Server 2019 バージョン](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6168e-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
