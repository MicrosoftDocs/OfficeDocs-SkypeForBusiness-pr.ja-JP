---
title: CAC のネットワーク地域の構成
TOCTitle: CAC のネットワーク地域の構成
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48273918
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# CAC のネットワーク地域の構成

 

_**トピックの最終更新日:** 2012-09-21_


> [!IMPORTANT]
> E9-1-1 またはメディア バイパスのネットワーク地域をすでに作成している場合には、<STRONG>Set-CsNetworkRegion</STRONG> コマンドレットを使用して、通話受付管理サービス (CAC) 固有の設定を追加することにより、既存のネットワーク地域を変更します。ネットワーク地域を変更する別の方法の例については、「<A href="lync-server-2013-create-or-modify-a-network-region.md">Lync Server 2013 でのネットワーク領域の作成または変更</A>」を参照してください。



*ネットワーク地域*は、CAC、E9-1-1、およびメディア バイパスで使用するネットワーク ハブまたはバックボーンです。以下の手順に従って、CAC のネットワーク トポロジ例に含まれているネットワーク地域に一致する、ネットワーク地域を作成します。ネットワーク トポロジの例を見る場合は、「計画」のドキュメントの「[例: Lync Server 2013 での通話受付管理の組織要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)」を参照してください。

CAC のネットワーク トポロジ例には 3 つの地域があります。北アメリカ、EMEA、および APAC。各地域には中央サイトが指定されています。North America 地域では、指定された中央サイトの名前は CHICAGO です。以下の手順では、**New-CsNetworkRegion** コマンドレッドを使用して North America 地域を作成する方法の例を挙げます。

> [!NOTE]
> 次の手順では、ネットワーク地域の作成に Lync Server 管理シェル が使用されています。Lync Server コントロール パネル を使用してネットワーク地域を作成するには、「<a href="lync-server-2013-create-or-modify-a-network-region.md">Lync Server 2013 でのネットワーク領域の作成または変更</a>」を参照してください。


## 通話受付管理用のネットワーク地域を作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  作成する必要がある地域ごとに **New-CsNetworkRegion** コマンドレットを実行します。たとえば、North America を作成するには、次のコマンドレットを実行します。
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  ステップ 2 を繰り返して、EMEA 地域と APAC 地域を作成します。

