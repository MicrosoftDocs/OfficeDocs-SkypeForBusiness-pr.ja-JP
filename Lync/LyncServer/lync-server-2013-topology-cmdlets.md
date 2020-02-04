---
title: 'Lync Server 2013: トポロジコマンドレット'
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
ms.openlocfilehash: b7524098f256587820beaabe31a8162591ba595d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-cmdlets-jn-lync-server-2013"></a><span data-ttu-id="f0911-102">トポロジコマンドレット、Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0911-102">Topology cmdlets jn Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0911-103">_**最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="f0911-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="f0911-104">Microsoft Lync Server 2013 に含まれているトポロジコマンドレットの多くは、セットアップおよびトポロジビルダーでの使用を目的として設計されています。そのため、多くの場合、管理者が直接呼び出すことがほとんどないトポロジのコマンドレットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f0911-104">Many of the topology cmdlets included in Microsoft Lync Server 2013 are designed for use with Setup and Topology Builder; because of that, there are a number of topology cmdlets that administrators will rarely call directly.</span></span> <span data-ttu-id="f0911-105">ただし、管理者がこれらのコマンドレットを使用することが必要になる場合もあります。たとえば、新しい Kerberos アカウントを作成した後、変更を有効にするには、 [CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0911-105">However, there will be times when administrators will be required to use these cmdlets; for example, after creating new Kerberos accounts you must run the [Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15)) cmdlet to cause the changes to take effect.</span></span> <span data-ttu-id="f0911-106">さらに、管理者は、Lync Server 2013 が正しくインストールされ、予期したとおりに動作していることを確認するために、[テスト用の CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))ツールやテスト用の[コンピューター](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))などのコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0911-106">In addition, administrators will likely run cmdlets such as [Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15)) and [Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15)) to help ensure that Lync Server 2013 has been correctly installed and is working as expected.</span></span>

<div>

## <a name="topology-cmdlets"></a><span data-ttu-id="f0911-107">トポロジのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="f0911-107">Topology Cmdlets</span></span>

<span data-ttu-id="f0911-108">Lync Server トポロジの直接管理に関連するコマンドレットの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f0911-108">The following is a list of cmdlets that relate directly managing your Lync Server topology:</span></span>

<span data-ttu-id="f0911-109">**トポロジ**</span><span class="sxs-lookup"><span data-stu-id="f0911-109">**Topology**</span></span>

  - <span></span>  
    <span data-ttu-id="f0911-110">[取得-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0911-110">[Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0911-111">[CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0911-111">[Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0911-112">[Set-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0911-112">[Set-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0911-113">[有効にする-CsTopology テクノロジー](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0911-113">[Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0911-114">[CsTopology テクノロジー](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0911-114">[Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0911-115">[公開-CsTopology テクノロジー](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0911-115">[Publish-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0911-116">[テスト-CsTopology テクノロジー](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0911-116">[Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0911-117">[エクスポート-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0911-117">[Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0911-118">[インポート-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0911-118">[Import-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0911-119">[Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0911-119">[Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0911-120">[CsComputer を無効にする](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0911-120">[Disable-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0911-121">[CsComputer を有効にする](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0911-121">[Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0911-122">[CsComputer の入手](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0911-122">[Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0911-123">[CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0911-123">[Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0911-124">[Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0911-124">[Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f0911-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0911-125">See Also</span></span>


[<span data-ttu-id="f0911-126">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="f0911-126">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

