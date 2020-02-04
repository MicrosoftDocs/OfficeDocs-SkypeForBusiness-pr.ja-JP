---
title: 'Lync Server 2013: ファイル記憶域のサポート'
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
ms.openlocfilehash: 000f3357c8b30b83a2d2cecf74bdbec44d867d96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="4dacf-102">Lync Server 2013 のファイル記憶域のサポート</span><span class="sxs-lookup"><span data-stu-id="4dacf-102">File storage support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dacf-103">_**最終更新日:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="4dacf-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="4dacf-104">Lync Server 2013 では、すべてのファイルストレージに同じファイルストアが使用されます。</span><span class="sxs-lookup"><span data-stu-id="4dacf-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="4dacf-105">ファイル記憶域のサポートには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4dacf-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="4dacf-106">直接接続型記憶域 (DAS) またはストレージエリアネットワーク (SAN) (分散ファイルシステム (DFS) を含む)、またはファイルストア用の独立したディスク (RAID) の冗長アレイ上にあるファイル共有。</span><span class="sxs-lookup"><span data-stu-id="4dacf-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="4dacf-107">記憶域の要件の詳細については、「計画ドキュメントの[Lync server 2013 のディレクターのための](lync-server-2013-hardware-and-software-requirements-for-the-director.md)、lync server 2013 およびハードウェアとソフトウェアの要件」の「[フロントエンドサーバーの技術要件」、「インスタントメッセージング」](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) 、「プレゼンス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dacf-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="4dacf-108">Windows Server 2008 オペレーティングシステム向けの DFS の詳細については、Windows Server 2008 の DFS ステップバイステップガイドを[http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dacf-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="4dacf-109">ファイル共有の共有クラスター。</span><span class="sxs-lookup"><span data-stu-id="4dacf-109">A shared cluster for the file share.</span></span> <span data-ttu-id="4dacf-110">共有クラスターを使用する場合は、Windows Server 2008 または Windows Server 2008 R2 を実行しているクラスターサーバーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dacf-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="4dacf-111">以前のバージョンの Windows を実行しているクラスターサーバーを使用すると、一部の機能が使用できなくなる可能性がある権限の問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="4dacf-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="4dacf-112">クラスター管理者を使用して、ファイル共有を作成します。</span><span class="sxs-lookup"><span data-stu-id="4dacf-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="4dacf-113">クラスター管理者の使用について詳しくは、Microsoft サポート技術情報の記事284838「cluster.exe でサーバークラスターのファイル共有を作成する方法[http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dacf-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

