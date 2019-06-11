---
title: 'Lync Server 2013: ウイルスをスキャンし、ウイルス定義を確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scanning for viruses and checking virus definitions
ms:assetid: 287c0f43-82d1-4c1d-b08f-77112fcb5bfa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720909(v=OCS.15)
ms:contentKeyID: 63969589
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 357c2c2053aca6b7b18a966756ece2768a8e71c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="f7cb1-102">Lync Server 2013 でウイルスのスキャンとウイルス定義の確認を行う</span><span class="sxs-lookup"><span data-stu-id="f7cb1-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7cb1-103">_**最終更新日:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="f7cb1-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="f7cb1-104">IM レベルのウイルス対策製品をインストールすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="f7cb1-105">IM は、ウイルスと悪意のあるソフトウェアの両方を組織全体ですばやく展開するための既知のソースです。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="f7cb1-106">Microsoft Forefront®の Lync Server のセキュリティにより、ウイルス、悪意のあるソフトウェア、ファイルとキーワードのフィルター保護、Office Communications Server とのシームレスな統合などのマルチエンジンスキャンが提供されます。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="f7cb1-107">Lync Server の Forefront Security に加えて、サーバーのファイルシステムを保護するために、ファイルレベルのウイルス対策ソリューションをインストールすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="f7cb1-108">スキャナーエンジンとウイルス定義を最新の状態に保つことは非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="f7cb1-109">更新プログラムの正常性を構成および監視することで、Office Communications Server とファイルシステムの両方の保護に最新のスキャン情報が使用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f7cb1-110">Lync Server 2013 と lync server の Forefront Security を実行しているサーバーでサードパーティのファイルレベルのウイルス対策ソフトウェアを使用している場合は、Forefront Security for Lync Server および Lync Server がインストールされているフォルダーがスキャンされないようにしてください。が破損しています。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="f7cb1-111">除外の完全な一覧について<A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>は、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-111">For the full list of exclusions, see <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

