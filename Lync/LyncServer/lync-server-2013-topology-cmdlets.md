---
title: 'Lync Server 2013: トポロジのコマンドレット'
description: 'Lync Server 2013: トポロジのコマンドレット。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology cmdlets
ms:assetid: 3ed739a7-d58d-475d-8240-fa8d2c6dc7e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415648(v=OCS.15)
ms:contentKeyID: 48183942
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f77febaa3beb4acc25bc5bc54dd0d5585fe18fc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549113"
---
# <a name="topology-cmdlets-jn-lync-server-2013"></a><span data-ttu-id="4a4ac-103">トポロジのコマンドレット (Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="4a4ac-103">Topology cmdlets jn Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a4ac-104">_**トピックの最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="4a4ac-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="4a4ac-105">Microsoft Lync Server 2013 に含まれているトポロジのコマンドレットの多くは、セットアップおよびトポロジビルダーで使用するように設計されています。そのため、いくつかのトポロジのコマンドレットを実行すると、管理者が直接呼び出すことはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="4a4ac-105">Many of the topology cmdlets included in Microsoft Lync Server 2013 are designed for use with Setup and Topology Builder; because of that, there are a number of topology cmdlets that administrators will rarely call directly.</span></span> <span data-ttu-id="4a4ac-106">ただし、管理者がこれらのコマンドレットを使用する必要がある場合もあります。たとえば、新しい Kerberos アカウントを作成した後で、 [Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15)) コマンドレットを実行して変更を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a4ac-106">However, there will be times when administrators will be required to use these cmdlets; for example, after creating new Kerberos accounts you must run the [Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15)) cmdlet to cause the changes to take effect.</span></span> <span data-ttu-id="4a4ac-107">さらに、管理者は、Lync Server 2013 が正しくインストールされ、予期したとおりに動作していることを確認するために、 [テスト用](https://technet.microsoft.com/library/Gg398127(v=OCS.15)) のコマンドレットやテスト用の [コンピューター](https://technet.microsoft.com/library/Gg398162(v=OCS.15)) などのコマンドレットを実行することがあります。</span><span class="sxs-lookup"><span data-stu-id="4a4ac-107">In addition, administrators will likely run cmdlets such as [Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15)) and [Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15)) to help ensure that Lync Server 2013 has been correctly installed and is working as expected.</span></span>

<div>

## <a name="topology-cmdlets"></a><span data-ttu-id="4a4ac-108">トポロジのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="4a4ac-108">Topology Cmdlets</span></span>

<span data-ttu-id="4a4ac-109">以下に、Lync Server トポロジの直接管理に関連するコマンドレットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="4a4ac-109">The following is a list of cmdlets that relate directly managing your Lync Server topology:</span></span>

<span data-ttu-id="4a4ac-110">**トポロジ**</span><span class="sxs-lookup"><span data-stu-id="4a4ac-110">**Topology**</span></span>

  - <span></span>  
    <span data-ttu-id="4a4ac-111">[取得-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a4ac-111">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4a4ac-112">[取得-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a4ac-112">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a4ac-113">[設定-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a4ac-113">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4a4ac-114">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a4ac-114">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a4ac-115">[取得-CsTopology テクノロジー](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a4ac-115">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a4ac-116">[発行-CsTopology テクノロジー](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a4ac-116">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a4ac-117">[テスト-CsTopology テクノロジー](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a4ac-117">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4a4ac-118">[エクスポート-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a4ac-118">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a4ac-119">[インポート-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a4ac-119">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4a4ac-120">[Get-csserverversion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a4ac-120">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4a4ac-121">[-CsComputer を無効にする](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a4ac-121">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a4ac-122">[を有効にする-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a4ac-122">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a4ac-123">[-CsComputer の取得](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a4ac-123">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a4ac-124">[テスト-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a4ac-124">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4a4ac-125">[Get-csnetworkinterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a4ac-125">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4a4ac-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a4ac-126">See Also</span></span>


[<span data-ttu-id="4a4ac-127">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="4a4ac-127">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

