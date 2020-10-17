---
title: 'Lync Server 2013: システム要件の決定'
description: 'Lync Server 2013: システム要件の決定。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determining your system requirements
ms:assetid: 620e81e2-42df-4eda-8498-bd56a14aa0e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398438(v=OCS.15)
ms:contentKeyID: 48184286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ceca8eabb234ae7fd483372ff5e611664ecc4fa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569493"
---
# <a name="determining-your-system-requirements-for-lync-server-2013"></a><span data-ttu-id="855d7-103">Lync Server 2013 のシステム要件を決定する</span><span class="sxs-lookup"><span data-stu-id="855d7-103">Determining your system requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="855d7-104">_**トピックの最終更新日:** 2014-01-02_</span><span class="sxs-lookup"><span data-stu-id="855d7-104">_**Topic Last Modified:** 2014-01-02_</span></span>

<span data-ttu-id="855d7-105">Lync Server を実行しているすべてのサーバーは、特定の最小システム要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="855d7-105">All servers running Lync Server must meet certain minimum system requirements.</span></span> <span data-ttu-id="855d7-106">Lync Server のシステム要件には、サーバーハードウェア、各サーバーにインストールするオペレーティングシステム、およびサーバーにインストールする必要がある Windows 更新プログラムやその他のソフトウェアなど、関連するソフトウェア要件があります。</span><span class="sxs-lookup"><span data-stu-id="855d7-106">System requirements for Lync Server include the server hardware, the operating system to be installed on each server, and related software requirements, such as the Windows updates and other software that must be installed on the servers.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="855d7-107">Lync Server は64ビット版でのみ使用できます。これには、64ビットのハードウェアと64ビット版の Windows Server が必要です。</span><span class="sxs-lookup"><span data-stu-id="855d7-107">Lync Server is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of Windows Server.</span></span> <span data-ttu-id="855d7-108">例外は Microsoft Lync Server 2013 の計画ツールであり、32ビット版で利用できます。</span><span class="sxs-lookup"><span data-stu-id="855d7-108">The exception is the Microsoft Lync Server 2013, Planning Tool, which is available in a 32-bit edition.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="855d7-109">Active Directory のサポート、サポートされているトポロジ、サーバーの併置、およびその他のサポートの問題の詳細については、「 <A href="lync-server-2013-supportability.md">Lync server 2013 のサポートの</A>概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="855d7-109">For details about Active Directory support, supported topologies, server collocation, and other supportability issues, see <A href="lync-server-2013-supportability.md">Supportability for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="855d7-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="855d7-110">In This Section</span></span>

  - [<span data-ttu-id="855d7-111">Lync Server 2013 のサーバーハードウェアプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="855d7-111">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)

  - [<span data-ttu-id="855d7-112">Lync Server 2013 でのサーバーおよびツールのオペレーティングシステムのサポート</span><span class="sxs-lookup"><span data-stu-id="855d7-112">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="855d7-113">Lync Server 2013 でのデータベースソフトウェアのサポート</span><span class="sxs-lookup"><span data-stu-id="855d7-113">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="855d7-114">Lync Server 2013 の追加ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="855d7-114">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="855d7-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="855d7-115">See Also</span></span>


[<span data-ttu-id="855d7-116">Lync Server 2013 でのクライアントとデバイスのハードウェアのサポート</span><span class="sxs-lookup"><span data-stu-id="855d7-116">Client and device hardware support in Lync Server 2013</span></span>](lync-server-2013-client-and-device-hardware-support.md)  
[<span data-ttu-id="855d7-117">Lync Server 2013 のサポート</span><span class="sxs-lookup"><span data-stu-id="855d7-117">Supportability for Lync Server 2013</span></span>](lync-server-2013-supportability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

