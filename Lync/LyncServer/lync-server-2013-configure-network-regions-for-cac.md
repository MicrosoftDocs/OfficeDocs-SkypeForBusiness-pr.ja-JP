---
title: 'Lync Server 2013: CAC のネットワーク地域の構成'
description: 'Lync Server 2013: CAC のネットワーク地域を構成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f016e0c943963ea4ce9739bd486c6996da502e73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577563"
---
# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>Lync Server 2013 で CAC のネットワーク地域を構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

<div>


> [!IMPORTANT]  
> E9-1-1 またはメディア バイパスのネットワーク地域をすでに作成している場合には、<STRONG>Set-CsNetworkRegion</STRONG> コマンドレットを使用して、通話受付管理サービス (CAC) 固有の設定を追加することにより、既存のネットワーク地域を変更します。 ネットワーク地域の変更方法の例については、「 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync Server 2013 でネットワーク地域を作成または変更</A>する」を参照してください。



</div>

*ネットワーク地域*は、CAC、E9-1-1、およびメディア バイパスで使用するネットワーク ハブまたはバックボーンです。 以下の手順に従って、CAC のネットワーク トポロジ例に含まれているネットワーク地域に一致する、ネットワーク地域を作成します。 ネットワークトポロジの例を表示するには、「計画」のドキュメントの「 [例: Lync Server 2013 での通話受付管理の要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 」を参照してください。

CAC のネットワークトポロジの例には、北アメリカ、EMEA、APAC の3つの地域があります。 各地域には、指定した中央サイトがあります。 北米地域の場合、指定された中央サイトはシカゴという名前です。 次の手順では、 **新しい-CsNetworkRegion** コマンドレットを使用して北米地域を作成する方法の例を示します。

<div>


> [!NOTE]  
> 次の手順では、Lync Server 管理シェルを使用してネットワーク地域を作成します。 Lync Server コントロールパネルを使用してネットワーク地域を作成する方法の詳細については、「 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync server 2013 でネットワーク地域を作成または変更</A>する」を参照してください。



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>通話受付管理用のネットワーク地域を作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  作成する必要がある地域ごとに **New-CsNetworkRegion** コマンドレットを実行します。 たとえば、North America を作成するには、次のコマンドレットを実行します。
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  ステップ 2 を繰り返して、EMEA 地域と APAC 地域を作成します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

