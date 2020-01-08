---
title: 'Lync Server 2013: CAC 用のネットワークサイトを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b678cab0ea8b473e6ea33ab5db951b105a11fa78
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>Lync Server 2013 での CAC 用のネットワークサイトの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> E9-1 または media バイパス用のネットワークサイトを既に作成している場合は、 <STRONG>Set-CsNetworkSite</STRONG>コマンドレットを使用して、既存のネットワークサイトを変更して帯域幅ポリシープロファイルを適用することができます。 ネットワークサイトを変更する方法の例については、「 <A href="lync-server-2013-create-or-modify-a-network-site.md">Lync Server 2013 でネットワークサイトを作成または変更</A>する」を参照してください。



</div>

[*ネットワークサイト*] は、通話受付制御 (CAC)、E9、および media バイパスの展開の各ネットワーク領域内の事業所または場所です。 次の手順を使用して、CAC のネットワークトポロジの例でネットワークサイトに合わせてネットワークサイトを作成します。 次の手順では、WAN の帯域幅に制約があるネットワークサイトを作成して構成する方法について説明します。そのため、リアルタイムの音声またはビデオのトラフィックフローを制限する帯域幅ポリシーが必要です。

CAC の展開例では、北米地域には6つのサイトがあります。 これら3つのサイトは、WAN の帯域幅 (Reno、ポートランド、およびアルバカーキ) によって制限されています。 他の3つのサイトは、WAN の帯域幅によって制約されることは*ありません*。ニューヨーク、シカゴ、デトロイト。 他のネットワークサイトを作成または変更する方法の例については、「 [Lync Server 2013 でネットワークサイトを作成または変更](lync-server-2013-create-or-modify-a-network-site.md)する」を参照してください。

ネットワークトポロジの例については、「例: 計画ドキュメントで[Lync Server 2013 の通話受付制御の要件を収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)する」を参照してください。

<div class=" ">


> [!NOTE]  
> 次の手順では、Lync Server 管理シェルを使ってネットワークサイトを作成します。 Lync Server コントロールパネルを使用してネットワークサイトを作成する方法について詳しくは、「 <A href="lync-server-2013-create-or-modify-a-network-site.md">Lync server 2013 でネットワークサイトを作成または変更</A>する」をご覧ください。



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>通話受付制御用のネットワークサイトを作成するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  **新しい-CsNetworkSite**コマンドレットを実行して、ネットワークサイトを作成し、各サイトに適切な帯域幅ポリシープロファイルを適用します。 たとえば、以下を実行します。
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  トポロジ全体のネットワークサイトの作成を完了するには、EMEA と APAC 地域の帯域幅制約のあるネットワークサイトについて、手順2を繰り返します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

