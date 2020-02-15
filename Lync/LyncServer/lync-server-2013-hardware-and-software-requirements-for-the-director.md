---
title: 'Lync Server 2013: ディレクターのハードウェアおよびソフトウェア要件'
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
ms.openlocfilehash: 32c4e241c7fd991fc217aaf2e1f2bd0ee9e37aab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="847dd-102">Lync Server 2013 のディレクターのハードウェアおよびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="847dd-102">Hardware and software requirements for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="847dd-103">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="847dd-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="847dd-104">このセクションでは、ディレクターのハードウェアおよびソフトウェア要件と、ディレクターがサポートする併置シナリオについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="847dd-104">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="847dd-105">ディレクターのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="847dd-105">Hardware Requirements for the Director</span></span>

<span data-ttu-id="847dd-106">次の表に、ディレクターのハードウェア要件を示します。</span><span class="sxs-lookup"><span data-stu-id="847dd-106">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="847dd-107">ディレクターのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="847dd-107">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="847dd-108">ハードウェア コンポーネント</span><span class="sxs-lookup"><span data-stu-id="847dd-108">Hardware component</span></span></th>
<th><span data-ttu-id="847dd-109">最小要件</span><span class="sxs-lookup"><span data-stu-id="847dd-109">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="847dd-110">CPU</span><span class="sxs-lookup"><span data-stu-id="847dd-110">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="847dd-111">2.0 GHz またはそれ以上の 64 ビット プロセッサ、クアッド コア</span><span class="sxs-lookup"><span data-stu-id="847dd-111">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="847dd-112">2.0 GHz またはそれ以上の 64 ビット デュアル プロセッサ、デュアル コア</span><span class="sxs-lookup"><span data-stu-id="847dd-112">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="847dd-113">メモリ</span><span class="sxs-lookup"><span data-stu-id="847dd-113">Memory</span></span></p></td>
<td><p><span data-ttu-id="847dd-114">4 ギガバイト (GB)</span><span class="sxs-lookup"><span data-stu-id="847dd-114">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="847dd-115">ディスク</span><span class="sxs-lookup"><span data-stu-id="847dd-115">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="847dd-116">10K RPM ハード ディスク ドライブ (HDD)</span><span class="sxs-lookup"><span data-stu-id="847dd-116">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="847dd-117">10K RPM HDD 以上のパフォーマンスを持つハイパフォーマンス ソリッド ステート ドライブ (SSD)</span><span class="sxs-lookup"><span data-stu-id="847dd-117">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="847dd-118">データベース データ ファイル用として 2 x RAID 10 (ストライプおよびミラー)、15K RPM ディスク</span><span class="sxs-lookup"><span data-stu-id="847dd-118">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="847dd-119">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="847dd-119">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="847dd-120">1 Gbps (ギガビット/秒) のデュアル ネットワーク アダプター (推奨)</span><span class="sxs-lookup"><span data-stu-id="847dd-120">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="847dd-121">1 Gbps の単一ネットワーク アダプター (サポート)</span><span class="sxs-lookup"><span data-stu-id="847dd-121">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="847dd-122">ディレクターのソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="847dd-122">Software Requirements for the Director</span></span>

<span data-ttu-id="847dd-123">ディレクターの役割は、Lync Server 2013 Enterprise Edition を実行しているサーバーにのみ展開できます。</span><span class="sxs-lookup"><span data-stu-id="847dd-123">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="847dd-124">ディレクターには、次のいずれかの64ビットオペレーティングシステムが必要です。</span><span class="sxs-lookup"><span data-stu-id="847dd-124">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="847dd-125">Windows Server 2008 R2 Standard オペレーティングシステム Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="847dd-125">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="847dd-126">Windows Server 2008 R2 Enterprise オペレーティングシステム Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="847dd-126">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="847dd-127">Windows Server 2008 R2 Datacenter オペレーティングシステムと Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="847dd-127">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="847dd-128">Windows Server 2012 Standard オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="847dd-128">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="847dd-129">Windows Server 2012 Datacenter オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="847dd-129">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="847dd-130">Lync Server 2013 では、「 [Lync server 2013 の追加サーバーのサポートと要件](lync-server-2013-additional-server-support-and-requirements.md)」で説明されている次のプログラムと更新プログラムのインストールも必要です。</span><span class="sxs-lookup"><span data-stu-id="847dd-130">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="847dd-131">サポートされる配置</span><span class="sxs-lookup"><span data-stu-id="847dd-131">Supported Collocation</span></span>

<span data-ttu-id="847dd-132">ディレクターサーバーの役割を、Lync Server 2013 の他のサーバーの役割と併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="847dd-132">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="847dd-133">ただし、ディレクターを展開しない場合は、フロントエンドサーバーによって役割が引き受けられます。</span><span class="sxs-lookup"><span data-stu-id="847dd-133">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

