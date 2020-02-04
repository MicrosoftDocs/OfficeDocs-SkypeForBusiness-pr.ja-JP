---
title: 'Lync Server 2013: SNMP アプリケーションを構成する'
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
ms.openlocfilehash: 9e11d79278318c99e1c6a1db3c4609e19553ba4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a><span data-ttu-id="71dd7-102">Lync Server 2013 での SNMP アプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="71dd7-102">Configure an SNMP application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71dd7-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="71dd7-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="71dd7-104">Lync Server 2013 には標準の web サービスインターフェイスが含まれています。これを使用すると、場所情報サービスを、MAC アドレスとポートおよびスイッチ情報を照合する SNMP (簡易ネットワーク管理プロトコル) アプリケーションに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="71dd7-104">Lync Server 2013 includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span>

<span data-ttu-id="71dd7-105">SNMP アプリケーションがインストールされていて、位置情報サービスが位置情報データベースで一致を見つけることができなかった場合、位置情報サービスは、クライアントから提供された MAC アドレスを使ってアプリケーションを自動的に照会します。</span><span class="sxs-lookup"><span data-stu-id="71dd7-105">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="71dd7-106">次に、位置情報サービスは、SNMP アプリケーションによって返されるポートとスイッチの情報を使用して、位置情報データベースをもう一度照会します。</span><span class="sxs-lookup"><span data-stu-id="71dd7-106">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>

<span data-ttu-id="71dd7-107">詳細については、「 [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71dd7-107">For details, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="71dd7-108">MAC アドレスは、Windows 8 を実行しているコンピューターでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="71dd7-108">MAC addresses are not available on computers running Windows 8.</span></span>



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="71dd7-109">SNMP アプリケーションの URL を構成するには</span><span class="sxs-lookup"><span data-stu-id="71dd7-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="71dd7-110">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="71dd7-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="71dd7-111">次のコマンドレットを使用して SNMP アプリケーションの URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="71dd7-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span>
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

