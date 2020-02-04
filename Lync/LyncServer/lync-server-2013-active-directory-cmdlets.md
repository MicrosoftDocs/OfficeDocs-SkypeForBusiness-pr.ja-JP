---
title: 'Lync Server 2013: Active Directory コマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory cmdlets
ms:assetid: 313d73cb-f3db-4bc4-8708-de4da1d719c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415640(v=OCS.15)
ms:contentKeyID: 48183769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f77009f20cfbd3e76f5cfc3786bcd9fa9ba2be9b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-cmdlets-in-lync-server-2013"></a><span data-ttu-id="c76b4-102">Lync Server 2013 の Active Directory コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c76b4-102">Active Directory cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c76b4-103">_**最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="c76b4-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="c76b4-104">通常、Active Directory コマンドレットはセットアップで使用され、管理者によって直接呼び出されることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="c76b4-104">The Active Directory cmdlets are typically used by Setup, and will rarely be called directly by an administrator.</span></span> <span data-ttu-id="c76b4-105">ただし、管理者はこれらのコマンドレットを使用して、Microsoft Lync Server 2013 用のドメインまたはフォレストを準備 (または unprepare) し、必要な Active Directory スキーマファイルをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="c76b4-105">However, administrators can use these cmdlets to prepare (or unprepare) a domain or forest for Microsoft Lync Server 2013, and to install the required Active Directory schema files.</span></span>

<div>

## <a name="active-directory-cmdlets"></a><span data-ttu-id="c76b4-106">Active Directory コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c76b4-106">Active Directory Cmdlets</span></span>

<span data-ttu-id="c76b4-107">Lync Server 2013 Active Directory の設定を管理するために直接関連するコマンドレットの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c76b4-107">The following is a list of cmdlets that relate directly to managing Lync Server 2013 Active Directory settings:</span></span>

<span data-ttu-id="c76b4-108">**Active Directory**</span><span class="sxs-lookup"><span data-stu-id="c76b4-108">**Active Directory**</span></span>

  - <span></span>  
    <span data-ttu-id="c76b4-109">[無効-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c76b4-109">[Disable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c76b4-110">[使用できるようにする-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c76b4-110">[Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c76b4-111">[入手-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c76b4-111">[Get-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c76b4-112">[CsAdForest を無効にする](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c76b4-112">[Disable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c76b4-113">[CsAdForest を有効にする](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c76b4-113">[Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c76b4-114">[CsAdForest の入手](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c76b4-114">[Get-CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c76b4-115">[CsAdServerSchema の入手](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c76b4-115">[Get-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c76b4-116">[Install-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c76b4-116">[Install-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c76b4-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c76b4-117">See Also</span></span>


[<span data-ttu-id="c76b4-118">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="c76b4-118">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

