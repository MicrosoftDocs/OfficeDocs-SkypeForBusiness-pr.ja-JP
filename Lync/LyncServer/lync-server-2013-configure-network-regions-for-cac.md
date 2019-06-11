---
title: 'Lync Server 2013: CAC のネットワーク領域を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 773bae62596143c0e974ae02f2bd643172a99ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>Lync Server 2013 での CAC のネットワーク領域の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

<div>


> [!IMPORTANT]  
> E9-1 または media バイパスのネットワーク領域を既に作成している場合は、 <STRONG>Set-CsNetworkRegion</STRONG>コマンドレットを使用して、通話受付制御 (CAC) に固有の設定を追加して、既存のネットワーク領域を変更することができます。 ネットワーク領域を変更する方法の例については、「 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync Server 2013 でネットワークの領域を作成または変更</A>する」を参照してください。



</div>

*ネットワーク領域*とは、CAC、E9、および media バイパスを構成するために使用されるネットワークハブまたはバックボーンのことです。 次の手順を使用して、CAC のネットワークトポロジ例でネットワーク領域に合わせてネットワーク領域を作成します。 ネットワークトポロジの例については、「例: 計画ドキュメントで[Lync Server 2013 の通話受付制御の要件を収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)する」を参照してください。

CAC のネットワークトポロジの例としては、北米、EMEA、APAC の3つの領域があります。 各地域には、指定したセントラルサイトがあります。 北米地域の場合、指定されたセントラルサイトはシカゴという名称になります。 次の手順では、**新しい-CsNetworkRegion**コマンドレットを使用して北米地域を作成する方法の例を示します。

<div>


> [!NOTE]  
> 次の手順では、Lync Server 管理シェルを使ってネットワーク領域を作成します。 Lync Server コントロールパネルを使用してネットワークの領域を作成する方法について詳しくは、「 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync server 2013 でネットワークの領域を作成または変更</A>する」をご覧ください。



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>通話受付制御用のネットワークの領域を作成するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  作成する必要がある各領域について、**新しい CsNetworkRegion**コマンドレットを実行します。 たとえば、北米地域を作成するには、次を実行します。
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  手順2を繰り返して、ネットワーク領域、EMEA、APAC を作成します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

