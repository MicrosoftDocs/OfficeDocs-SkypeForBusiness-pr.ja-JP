---
title: 'Lync Server 2013: ディレクターのハードウェアおよびソフトウェア要件'
description: 'Lync Server 2013: ディレクターのハードウェアおよびソフトウェア要件。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dd868a3a566f1d89b4ada5a16695f8eb02b3b21
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552933"
---
# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="1ca74-103">Lync Server 2013 のディレクターのハードウェアおよびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="1ca74-103">Hardware and software requirements for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ca74-104">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="1ca74-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="1ca74-105">このセクションでは、ディレクターのハードウェアおよびソフトウェア要件と、ディレクターがサポートする併置シナリオについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="1ca74-105">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="1ca74-106">ディレクターのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="1ca74-106">Hardware Requirements for the Director</span></span>

<span data-ttu-id="1ca74-107">次の表に、ディレクターのハードウェア要件を示します。</span><span class="sxs-lookup"><span data-stu-id="1ca74-107">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="1ca74-108">ディレクターのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="1ca74-108">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ca74-109">ハードウェア コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1ca74-109">Hardware component</span></span></th>
<th><span data-ttu-id="1ca74-110">最小要件</span><span class="sxs-lookup"><span data-stu-id="1ca74-110">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ca74-111">CPU</span><span class="sxs-lookup"><span data-stu-id="1ca74-111">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ca74-112">2.0 GHz またはそれ以上の 64 ビット プロセッサ、クアッド コア</span><span class="sxs-lookup"><span data-stu-id="1ca74-112">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="1ca74-113">2.0 GHz またはそれ以上の 64 ビット デュアル プロセッサ、デュアル コア</span><span class="sxs-lookup"><span data-stu-id="1ca74-113">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca74-114">メモリ</span><span class="sxs-lookup"><span data-stu-id="1ca74-114">Memory</span></span></p></td>
<td><p><span data-ttu-id="1ca74-115">4 ギガバイト (GB)</span><span class="sxs-lookup"><span data-stu-id="1ca74-115">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca74-116">ディスク</span><span class="sxs-lookup"><span data-stu-id="1ca74-116">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ca74-117">10K RPM ハード ディスク ドライブ (HDD)</span><span class="sxs-lookup"><span data-stu-id="1ca74-117">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="1ca74-118">10K RPM HDD 以上のパフォーマンスを持つハイパフォーマンス ソリッド ステート ドライブ (SSD)</span><span class="sxs-lookup"><span data-stu-id="1ca74-118">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="1ca74-119">データベース データ ファイル用として 2 x RAID 10 (ストライプおよびミラー)、15K RPM ディスク</span><span class="sxs-lookup"><span data-stu-id="1ca74-119">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca74-120">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="1ca74-120">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ca74-121">1 Gbps (ギガビット/秒) のデュアル ネットワーク アダプター (推奨)</span><span class="sxs-lookup"><span data-stu-id="1ca74-121">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="1ca74-122">1 Gbps の単一ネットワーク アダプター (サポート)</span><span class="sxs-lookup"><span data-stu-id="1ca74-122">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="1ca74-123">ディレクターのソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="1ca74-123">Software Requirements for the Director</span></span>

<span data-ttu-id="1ca74-124">ディレクターの役割は、Lync Server 2013 Enterprise Edition を実行しているサーバーにのみ展開できます。</span><span class="sxs-lookup"><span data-stu-id="1ca74-124">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="1ca74-125">ディレクターには、次のいずれかの64ビットオペレーティングシステムが必要です。</span><span class="sxs-lookup"><span data-stu-id="1ca74-125">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="1ca74-126">Windows Server 2008 R2 Standard オペレーティングシステム Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="1ca74-126">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="1ca74-127">Windows Server 2008 R2 Enterprise オペレーティングシステム Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="1ca74-127">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="1ca74-128">Windows Server 2008 R2 Datacenter オペレーティングシステムと Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="1ca74-128">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="1ca74-129">Windows Server 2012 Standard オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="1ca74-129">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="1ca74-130">Windows Server 2012 Datacenter オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="1ca74-130">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="1ca74-131">Lync Server 2013 では、「 [Lync server 2013 の追加サーバーのサポートと要件](lync-server-2013-additional-server-support-and-requirements.md)」で説明されている次のプログラムと更新プログラムのインストールも必要です。</span><span class="sxs-lookup"><span data-stu-id="1ca74-131">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="1ca74-132">サポートされる配置</span><span class="sxs-lookup"><span data-stu-id="1ca74-132">Supported Collocation</span></span>

<span data-ttu-id="1ca74-133">ディレクターサーバーの役割を、Lync Server 2013 の他のサーバーの役割と併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="1ca74-133">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="1ca74-134">ただし、ディレクターを展開しない場合は、フロントエンドサーバーによって役割が引き受けられます。</span><span class="sxs-lookup"><span data-stu-id="1ca74-134">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

