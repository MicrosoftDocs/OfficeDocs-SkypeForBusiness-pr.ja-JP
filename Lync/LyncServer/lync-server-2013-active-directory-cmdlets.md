---
title: 'Lync Server 2013: Active Directory コマンドレット'
description: 'Lync Server 2013: Active Directory コマンドレット。'
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
ms.openlocfilehash: 8c5e87cda24d5517b9c4501523fd06804ea20020
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571083"
---
# <a name="active-directory-cmdlets-in-lync-server-2013"></a><span data-ttu-id="90186-103">Lync Server 2013 での Active Directory のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="90186-103">Active Directory cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90186-104">_**トピックの最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="90186-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="90186-105">Active Directory のコマンドレットは通常はセットアップで使用され、管理者が直接呼び出すことはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="90186-105">The Active Directory cmdlets are typically used by Setup, and will rarely be called directly by an administrator.</span></span> <span data-ttu-id="90186-106">ただし、管理者はこれらのコマンドレットを使用して Microsoft Lync Server 2013 のドメインまたはフォレストを準備 (または unprepare) し、必要な Active Directory スキーマファイルをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="90186-106">However, administrators can use these cmdlets to prepare (or unprepare) a domain or forest for Microsoft Lync Server 2013, and to install the required Active Directory schema files.</span></span>

<div>

## <a name="active-directory-cmdlets"></a><span data-ttu-id="90186-107">Active Directory のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="90186-107">Active Directory Cmdlets</span></span>

<span data-ttu-id="90186-108">Lync Server 2013 Active Directory 設定の管理に直接関連するコマンドレットの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="90186-108">The following is a list of cmdlets that relate directly to managing Lync Server 2013 Active Directory settings:</span></span>

<span data-ttu-id="90186-109">**Active Directory**</span><span class="sxs-lookup"><span data-stu-id="90186-109">**Active Directory**</span></span>

  - <span></span>  
    <span data-ttu-id="90186-110">[無効-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90186-110">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="90186-111">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90186-111">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="90186-112">[取得-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90186-112">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="90186-113">[無効-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90186-113">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="90186-114">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90186-114">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="90186-115">[取得-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90186-115">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="90186-116">[取得-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90186-116">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="90186-117">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90186-117">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="90186-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="90186-118">See Also</span></span>


[<span data-ttu-id="90186-119">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="90186-119">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

