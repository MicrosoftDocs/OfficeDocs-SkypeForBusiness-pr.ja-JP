---
title: Lync Server 2013 での CAC のネットワーク サイトの構成
TOCTitle: Lync Server 2013 での CAC のネットワーク サイトの構成
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48273281
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での CAC のネットワーク サイトの構成

 

_**トピックの最終更新日:** 2012-09-05_


> [!IMPORTANT]
> E9-1-1 またはメディア バイパス用のネットワーク サイトが既に作成されている場合は、既存のネットワーク サイトを変更し、<STRONG>Set-CsNetworkSite</STRONG> コマンドレットを使用して帯域幅ポリシー プロファイルを適用できます。 ネットワーク サイトを変更する方法の例については、「<A href="lync-server-2013-create-or-modify-a-network-site.md">Lync Server 2013 でのネットワーク サイトの作成または変更</A>」を参照してください。



*ネットワーク サイト*は、通話受付管理 (CAC)、E9-1-1、およびメディア バイパスが展開される各ネットワーク地域内のオフィスまたは拠点です。 次の手順を使用して、CAC のネットワーク トポロジの例におけるネットワーク サイトに合わせたネットワーク サイトを作成してください。 この手順は、WAN の帯域幅により制約があるために、リアルタイムの音声またはビデオのトラフィック フローを制限する帯域幅ポリシーが必要なネットワーク サイトの作成および構成方法を示します。

CAC の展開の例では、北アメリカ地域に 6 つのサイトがあります。 そのうち Reno、Portland、および Albuquerque の 3 つのサイトは、WAN の帯域幅の制約があります。その他次の 3 つのサイトでは、WAN の帯域幅の制約が*ありません*: ニューヨーク、シカゴ、およびデトロイト。このような、その他のネットワーク サイトを作成または変更する方法の例については、「[Lync Server 2013 でのネットワーク サイトの作成または変更](lync-server-2013-create-or-modify-a-network-site.md)」を参照してください。

ネットワーク トポロジの例を見る場合は、「計画」のドキュメントの「[例: Lync Server 2013 での通話受付管理の組織要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)」を参照してください。

> [!NOTE]
> 次の手順では、ネットワーク サイトの作成に Lync Server 管理シェルが使用されています。Lync Server コントロール パネルを使用したネットワーク サイトの作成の詳細については、「<a href="lync-server-2013-create-or-modify-a-network-site.md">Lync Server 2013 でのネットワーク サイトの作成または変更</a>」を参照してください。


## 通話受付管理用のネットワーク サイトを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  **New-CsNetworkSite** コマンドレットを実行してネットワーク サイトを作成し、各サイトに適切な帯域幅ポリシーを適用します。たとえば、以下を実行します。
    
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link

       &nbsp;
    
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link

       &nbsp;
    
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link

3.  トポロジの例全体のネットワーク サイトの作成を完了するには、帯域幅の制約がある、EMEA および APAC 地域のネットワーク サイトに対してステップ 2 を繰り返します。

