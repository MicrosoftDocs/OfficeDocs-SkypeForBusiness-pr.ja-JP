---
title: 'Lync Server 2013: システム要件の決定'
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
ms.openlocfilehash: 4798c763732f529de029db217eccd241902459ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determining-your-system-requirements-for-lync-server-2013"></a><span data-ttu-id="3c8de-102">Lync Server 2013 システム要件の決定</span><span class="sxs-lookup"><span data-stu-id="3c8de-102">Determining your system requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c8de-103">_**最終更新日:** 2014-01-02_</span><span class="sxs-lookup"><span data-stu-id="3c8de-103">_**Topic Last Modified:** 2014-01-02_</span></span>

<span data-ttu-id="3c8de-104">Lync Server を実行しているすべてのサーバーは、特定の最小システム要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c8de-104">All servers running Lync Server must meet certain minimum system requirements.</span></span> <span data-ttu-id="3c8de-105">Lync Server のシステム要件には、サーバーハードウェア、各サーバーにインストールされるオペレーティングシステム、および関連するソフトウェア要件 (Windows の更新プログラムや、サーバーにインストールする必要があるその他のソフトウェアなど) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3c8de-105">System requirements for Lync Server include the server hardware, the operating system to be installed on each server, and related software requirements, such as the Windows updates and other software that must be installed on the servers.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3c8de-106">Lync Server は64ビット版でのみ利用できます。これには、64ビットのハードウェアと64ビット版の Windows Server が必要です。</span><span class="sxs-lookup"><span data-stu-id="3c8de-106">Lync Server is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of Windows Server.</span></span> <span data-ttu-id="3c8de-107">この例外は、32ビット版で利用できる Microsoft Lync Server 2013、計画ツールです。</span><span class="sxs-lookup"><span data-stu-id="3c8de-107">The exception is the Microsoft Lync Server 2013, Planning Tool, which is available in a 32-bit edition.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="3c8de-108">Active Directory のサポート、サポートされているトポロジ、サーバーの配置、その他のサポートの問題について詳しくは、「 <A href="lync-server-2013-supportability.md">Lync server 2013 のサポート性</A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3c8de-108">For details about Active Directory support, supported topologies, server collocation, and other supportability issues, see <A href="lync-server-2013-supportability.md">Supportability for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3c8de-109">このセクション中</span><span class="sxs-lookup"><span data-stu-id="3c8de-109">In This Section</span></span>

  - [<span data-ttu-id="3c8de-110">Lync Server 2013 のサーバー ハードウェア プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="3c8de-110">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)

  - [<span data-ttu-id="3c8de-111">Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート</span><span class="sxs-lookup"><span data-stu-id="3c8de-111">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="3c8de-112">Lync Server 2013 でのデータベース ソフトウェアのサポート</span><span class="sxs-lookup"><span data-stu-id="3c8de-112">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="3c8de-113">Lync Server 2013 の追加ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="3c8de-113">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3c8de-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c8de-114">See Also</span></span>


[<span data-ttu-id="3c8de-115">Lync Server 2013 のクライアントとデバイスのハードウェア サポート</span><span class="sxs-lookup"><span data-stu-id="3c8de-115">Client and device hardware support in Lync Server 2013</span></span>](lync-server-2013-client-and-device-hardware-support.md)  
[<span data-ttu-id="3c8de-116">Lync Server 2013 のサポート状況</span><span class="sxs-lookup"><span data-stu-id="3c8de-116">Supportability for Lync Server 2013</span></span>](lync-server-2013-supportability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

