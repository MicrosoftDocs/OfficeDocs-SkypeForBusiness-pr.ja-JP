---
title: 'Lync Server 2013: CAC のネットワークサイトの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e24932b23b1a9168ed64279f98db125f06ad0e2e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520524"
---
# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>Lync Server 2013 で CAC のネットワークサイトを構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> E9-1-1 またはメディア バイパス用のネットワーク サイトが既に作成されている場合は、既存のネットワーク サイトを変更し、<STRONG>Set-CsNetworkSite</STRONG> コマンドレットを使用して帯域幅ポリシー プロファイルを適用できます。 ネットワークサイトの変更方法の例については、「 <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site In Lync Server 2013</A>」を参照してください。



</div>

*ネットワーク サイト*は、通話受付管理 (CAC)、E9-1-1、およびメディア バイパスが展開される各ネットワーク地域内のオフィスまたは拠点です。  次の手順を使用して、CAC のネットワーク トポロジの例におけるネットワーク サイトに合わせたネットワーク サイトを作成してください。 この手順は、WAN の帯域幅により制約があるために、リアルタイムの音声またはビデオのトラフィック フローを制限する帯域幅ポリシーが必要なネットワーク サイトの作成および構成方法を示します。

CAC の展開の例では、北アメリカ地域に 6 つのサイトがあります。 そのうち Reno、Portland、および Albuquerque の 3 つのサイトは、WAN の帯域幅の制約があります。 その他次の 3 つのサイトでは、WAN の帯域幅の制約が*ありません*: ニューヨーク、シカゴ、およびデトロイト。 その他のネットワークサイトを作成または変更する方法の例については、「 [Lync Server 2013 でネットワークサイトを作成または変更](lync-server-2013-create-or-modify-a-network-site.md)する」を参照してください。

ネットワークトポロジの例を表示するには、「計画」のドキュメントの「 [例: Lync Server 2013 での通話受付管理の要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 」を参照してください。

<div class=" ">


> [!NOTE]  
> 次の手順では、Lync Server 管理シェルを使用してネットワークサイトを作成します。 Lync Server コントロールパネルを使用してネットワークサイトを作成する方法の詳細については、「 <A href="lync-server-2013-create-or-modify-a-network-site.md">create or modify a network site In Lync Server 2013</A>」を参照してください。



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>通話受付管理用のネットワーク サイトを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  **New-CsNetworkSite** コマンドレットを実行してネットワーク サイトを作成し、各サイトに適切な帯域幅ポリシーを適用します。 たとえば、以下を実行します。
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  トポロジの例全体のネットワーク サイトの作成を完了するには、帯域幅の制約がある、EMEA および APAC 地域のネットワーク サイトに対してステップ 2 を繰り返します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

