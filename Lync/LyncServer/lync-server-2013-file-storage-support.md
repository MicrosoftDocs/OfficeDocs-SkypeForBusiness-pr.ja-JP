---
title: Lync Server 2013 ファイル記憶域のサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cc2250020b7456515f06bcb308ca4cea4430a56
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="7d79a-102">Lync Server 2013 でのファイル記憶域のサポート</span><span class="sxs-lookup"><span data-stu-id="7d79a-102">File storage support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d79a-103">_**トピックの最終更新日:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="7d79a-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="7d79a-104">Lync Server 2013 は、すべてのファイルストレージに対して同じファイルストアを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d79a-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="7d79a-105">ファイル記憶域のサポートには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d79a-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="7d79a-106">直接接続ストレージ (DAS) または記憶域エリアネットワーク (SAN) (分散ファイルシステム (DFS) を含む)、およびファイルストア用の独立したディスク (RAID) の冗長アレイ上にあるファイル共有。</span><span class="sxs-lookup"><span data-stu-id="7d79a-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="7d79a-107">ストレージ要件の詳細については、「計画」のドキュメントの「 [lync server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスの技術要件](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md)」および「 [lync Server 2013 のディレクターのハードウェアおよびソフトウェア要件](lync-server-2013-hardware-and-software-requirements-for-the-director.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d79a-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="7d79a-108">Windows Server 2008 オペレーティングシステムの DFS の詳細については、「Windows Server 2008 の DFS のステップバイステップガイド[https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d79a-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="7d79a-109">ファイル共有の共有クラスター。</span><span class="sxs-lookup"><span data-stu-id="7d79a-109">A shared cluster for the file share.</span></span> <span data-ttu-id="7d79a-110">共有クラスターを使用する場合は、Windows Server 2008 または Windows Server 2008 R2 を実行しているクラスターサーバーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d79a-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="7d79a-111">以前のバージョンの Windows を実行しているクラスターサーバーを使用すると、一部の機能が使用できなくなる可能性があるアクセス許可の問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="7d79a-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="7d79a-112">ファイル共有を作成するには、クラスター アドミニストレーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d79a-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="7d79a-113">クラスター管理者の使用の詳細については、Microsoft サポート技術情報の記事284838「cluster.exe を使用してサーバークラスターのファイル共有[https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899)を作成する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d79a-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

