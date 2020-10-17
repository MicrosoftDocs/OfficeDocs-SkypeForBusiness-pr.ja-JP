---
title: 'Lync Server 2013: サブネットとネットワークサイトの関連付け'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f961fef4fb9323c0eef642e4b7e70ede5da4ccf2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532744"
---
# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a>Lync Server 2013 でのサブネットとネットワークサイトの関連付け

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

新しいセッションが開始されている間に、エンドポイントが配置されているネットワークサイトを特定するために、ネットワーク内のすべてのサブネットが特定のネットワークサイトに関連付けられている必要があります。 セッション内の各パーティの場所がわかっている場合は、高度なエンタープライズ Voip 機能がその情報を適用して、通話の設定またはルーティングを処理する方法を決定することができます。

<div>


> [!IMPORTANT]  
> 展開内の音声ビデオ エッジ サーバーの構成済みパブリック IP アドレスはすべて、ネットワーク構成設定に追加する必要があります。 これらの IP アドレスは、マスク値 32 のサブネットとして追加されます。 関連付けられたネットワーク サイトは、適切な構成済みネットワーク サイトに対応する必要があります。 たとえば、中央サイトの Chicago に音声ビデオ エッジ サーバーがある場合、そのサーバーに対応するパブリック IP アドレスは NetworkSiteID Chicago になるなどです。 パブリック IP アドレスの詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Lync Server 2013 の外部の音声ビデオファイアウォールおよびポート要件を決定</A> する」を参照してください。



</div>

<div>


> [!NOTE]  
> 主要状態インジケーター (KHI) 通知が発行され、ネットワークに存在している IP アドレスの一覧を指定します。ここで指定される一覧は、サブネットと関連付けられていないか、IP アドレスを含むサブネットがネットワーク サイトと関連付けられていません。この通知は 8 時間に 1 回しか発行されません。関連する通知の情報および例は以下の通りです。<BR><STRONG>ソース:</STRONG> CS 帯域幅ポリシーサービス (コア)<BR><STRONG>イベント番号:</STRONG> 36034<BR><STRONG>レベル:</STRONG> 2<BR><STRONG>説明:</STRONG> 次の IP アドレスのサブネット: &lt; Ip アドレスの一覧 &gt; が構成されていないか、またはサブネットがネットワークサイトに関連付けられていません。<BR><STRONG>原因:</STRONG> 対応する IP アドレスのサブネットがネットワーク構成設定にないか、またはサブネットがネットワークサイトに関連付けられていません。<BR><STRONG>解決策:</STRONG> IP アドレスのリストに対応するサブネットをネットワーク構成設定に追加し、すべてのサブネットをネットワークサイトに関連付けます。<BR>たとえば、通知に表示された IP アドレス リストが 10.121.248.226 および 10.121.249.20 であった場合、これらの IP アドレスがサブネットに関連付けられていないか、または関連付けられているサブネットがネットワーク サイトに属していないかのどちらかになります。10.121.248.0/24 および 10.121.249.0/24 がこれらのアドレスに対応するサブネットである場合、次の手順でこの問題を解決することができます。 
> <OL>
> <LI>
> <P>IP アドレス 10.121.248.226 が 10.121.248.0/24 サブネットに関連付けられていること、および IP アドレス 10.121.249.20 が 10.121.249.0/24 サブネットに関連付けられていることを確認します。</P>
> <LI>
> <P>10.121.248.0/24 および 10.121.249.0/24 サブネットがそれぞれネットワーク サイトに関連付けられていることを確認します。</P></LI></OL>



</div>

ネットワークサブネットの使用の詳細については、「Lync Server Management Shell」のドキュメントの次のコマンドレットを参照してください。

  - [新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [-CsNetworkSubnet の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [設定-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [-CsNetworkSubnet の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> 多数のサブネットを設定する場合は、コンマ区切り (CSV) ファイルを使用してサブネットをネットワーク サイトに関連付けることをお勧めします。CSV ファイルには、<STRONG>IPAddress</STRONG>、<STRONG>mask</STRONG>、<STRONG>description</STRONG>、<STRONG>NetworkSiteID</STRONG> の 4 つの列が必要です。



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a>管理シェルを使用してサブネットをネットワーク サイトに関連付けるには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  **New-CsNetworkSubnet** コマンドレットを実行して、サブネットをネットワーク サイトに関連付けます。
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    次にその例を示します。
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    この例では、サブネットの 172.11.12.13 とネットワーク サイトの "Chicago" 間の関連付けが作成されました。

3.  トポロジのすべてのサブネットに対して、ステップ 2 を繰り返します。

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>CSV ファイルをインポートしてサブネットをネットワーク サイトに関連付けるには

1.  追加する予定の、すべてのサブネットが含まれた CSV ファイルを作成します。たとえば、次の内容が含まれる、**subnet.csv** という名前のファイルを作成します。
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行して **subnet.csv**をインポートし、そのコンテンツを Lync Server 管理ストアに格納します。
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a>Lync Server コントロール パネルを使用してサブネットをネットワーク サイトに関連付けるには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3.  [**サブネット**] ナビゲーション ボタンをクリックします。

4.  [**新規**] をクリックします。

5.  [**新しいサブネット**] ページで、[**サブネット ID**] をクリックし、サブネットで定義される IP アドレス範囲の最初のアドレスを入力します。このサブネットは、ネットワーク サイトに関連付けるネットワークです。

6.  [**マスク**] をクリックし、サブネットに適用するビットマスクを入力します。

7.  [**ネットワーク サイト ID**] をクリックし、このサブネットを追加する先のサイトのサイト ID を選択します。
    
    <div>
    

    > [!NOTE]  
    > ネットワーク サイトがまだ作成されていない場合、この一覧は空です。 手順の詳細については、「 <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site In Lync Server 2013</A>」を参照してください。 また、<STRONG>Get-CsNetworkSite</STRONG> コマンドレットを実行して、展開のサイト ID を取得することもできます。 詳細については、Lync Server 管理シェルのドキュメントを参照してください。

    
    </div>

8.  必要に応じて、[**説明**] をクリックし、このサブネットを説明する追加情報を入力します。

9.  [**確定**] をクリックします。

その他のサブネットをネットワーク サイトに追加するには、これらのステップを繰り返します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

