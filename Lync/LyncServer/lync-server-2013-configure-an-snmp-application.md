---
title: 'Lync Server 2013: SNMP アプリケーションを構成する'
description: 'Lync Server 2013: SNMP アプリケーションを構成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7374b61ad85d7ddcb40ef1db535e17f86dea58f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546703"
---
# <a name="configure-an-snmp-application-in-lync-server-2013"></a><span data-ttu-id="e2b36-103">Lync Server 2013 で SNMP アプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="e2b36-103">Configure an SNMP application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2b36-104">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e2b36-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e2b36-105">Lync Server 2013 には、MAC アドレスとポートおよびスイッチ情報を一致させる簡易ネットワーク管理プロトコル (SNMP) アプリケーションに場所情報サービスを接続するために使用できる標準の web サービスインターフェイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e2b36-105">Lync Server 2013 includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span>

<span data-ttu-id="e2b36-106">SNMP アプリケーションがインストールされていて、場所情報サービスが場所データベースで一致を見つけられない場合、場所情報サービスはクライアントによって指定された MAC アドレスを使用して、アプリケーションに対して自動的にクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2b36-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="e2b36-107">その後、場所情報サービスは、SNMP アプリケーションによって返されるポートとスイッチの情報を使用して、場所データベースに再度クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2b36-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>

<span data-ttu-id="e2b36-108">詳細については、「 [set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2b36-108">For details, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e2b36-109">MAC アドレスは、Windows 8 を実行しているコンピューターでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e2b36-109">MAC addresses are not available on computers running Windows 8.</span></span>



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="e2b36-110">SNMP アプリケーションの URL を構成するには</span><span class="sxs-lookup"><span data-stu-id="e2b36-110">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="e2b36-111">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b36-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e2b36-112">次のコマンドレットを使用して SNMP アプリケーションの URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="e2b36-112">Run the following cmdlet to configure the URL for the SNMP application.</span></span>
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

