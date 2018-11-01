---
title: 'Lync Server 2013: ネットワーク サイトとサブネットの関連付け'
TOCTitle: ネットワーク サイトとサブネットの関連付け
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48273214
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのネットワーク サイトとサブネットの関連付け

 

_**トピックの最終更新日:** 2014-10-20_

ネットワーク内のすべてのサブネットが、特定のネットワーク サイトに関連付けられている必要があります。サブネット情報は、新しいセッションの開始時に、エンドポイントが存在するネットワーク サイトを判断するために使用されるからです。セッションの各パーティの場所が分かっている場合、高度な エンタープライズ VoIP 機能はその情報を適用して、呼び出しのセットアップやルーティングの処理方法を決定します。


> [!IMPORTANT]
> 展開内の音声ビデオ エッジ サーバーの構成済みパブリック IP アドレスはすべて、ネットワーク構成設定に追加する必要があります。これらの IP アドレスは、マスク値 32 のサブネットとして追加されます。関連付けられたネットワーク サイトは、適切な構成済みネットワーク サイトに対応する必要があります。たとえば、中央サイトの Chicago に音声ビデオ エッジ サーバーがある場合、そのサーバーに対応するパブリック IP アドレスは NetworkSiteID Chicago になるなどです。パブリック IP アドレスの詳細については、「計画」のドキュメントの「<A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する</A>」を参照してください。



> [!NOTE]  
> 主要状態インジケーター (KHI) 通知が発行され、ネットワークに存在している IP アドレスの一覧を指定します。ここで指定される一覧は、サブネットと関連付けられていないか、IP アドレスを含むサブネットがネットワーク サイトと関連付けられていません。この通知は 8 時間に 1 回しか発行されません。関連する通知の情報および例は以下の通りです。<br />
> <strong>ソース :</strong> CS 帯域幅ポリシー サービス (コア)<br />
> <strong>イベント番号 :</strong> 36034<br />
> <strong>レベル :</strong> 2<br />
> <strong>概要 :</strong> 次の IP アドレスのサブネット: &lt;IP アドレスのリスト&gt; は構成されていないか、またはサブネットがネットワーク サイトに関連付けられていません。<br />
> <strong>原因 :</strong> 対応する IP アドレスのサブネットがネットワーク構成設定にないか、サブネットがネットワーク サイトに関連付けられていません。<br />
> <strong>解決方法 :</strong> IP アドレス リストに対応するサブネットをネットワーク構成設定に追加し、すべてのサブネットをネットワーク サイトに関連付けます。<br />
> たとえば、通知に表示された IP アドレス リストが 10.121.248.226 および 10.121.249.20 であった場合、これらの IP アドレスがサブネットに関連付けられていないか、または関連付けられているサブネットがネットワーク サイトに属していないかのどちらかになります。10.121.248.0/24 および 10.121.249.0/24 がこれらのアドレスに対応するサブネットである場合、次の手順でこの問題を解決することができます。
> <ol><li><p>IP アドレス 10.121.248.226 が 10.121.248.0/24 サブネットに関連付けられていること、および IP アドレス 10.121.249.20 が 10.121.249.0/24 サブネットに関連付けられていることを確認します。</p></li>
> <li><p>10.121.248.0/24 および 10.121.249.0/24 サブネットがそれぞれネットワーク サイトに関連付けられていることを確認します。</p></li></ol>


ネットワーク サブネットの設定の詳細については、「Lync Server 管理シェル」のドキュメントに記載されている次のコマンドレットを参照してください。

  - [New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet)

  - [Get-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSubnet)

  - [Set-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkSubnet)

  - [Remove-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkSubnet)


> [!TIP]
> 多数のサブネットを設定する場合は、カンマ区切り (CSV) ファイルを使用してサブネットをネットワーク サイトに関連付けることをお勧めします。CSV ファイルには、 <STRONG>IPAddress</STRONG>、 <STRONG>mask</STRONG>、 <STRONG>description</STRONG>、 <STRONG>NetworkSiteID</STRONG> の 4 つの列が必要です。



## 管理シェルを使用してサブネットをネットワーク サイトに関連付けるには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  **New-CsNetworkSubnet** コマンドレットを実行して、サブネットをネットワーク サイトに関連付けます。
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    次に例を示します。
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    この例では、サブネットの 172.11.12.13 とネットワーク サイトの "Chicago" 間の関連付けが作成されました。

3.  トポロジのすべてのサブネットに対して、ステップ 2 を繰り返します。

## CSV ファイルをインポートしてサブネットをネットワーク サイトに関連付けるには

1.  追加する予定の、すべてのサブネットが含まれた CSV ファイルを作成します。たとえば、次の内容が含まれる、 **subnet.csv** という名前のファイルを作成します。
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  次のコマンドレットを実行して **subnet.csv** をインポートし、その内容を Lync Server の管理ストアに保存します。
    
        import-csv subnet.csv | foreach {New-CsNetworkSubnet $_IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

## Lync Server コントロール パネルを使用してサブネットをネットワーク サイトに関連付けるには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックします。

3.  \[**サブネット**\] ナビゲーション ボタンをクリックします。

4.  \[**新規**\] をクリックします。

5.  \[**新しいサブネット**\] ページで、\[**サブネット ID**\] をクリックし、サブネットで定義される IP アドレス範囲の最初のアドレスを入力します。このサブネットは、ネットワーク サイトに関連付けるネットワークです。

6.  \[**マスク**\] をクリックし、サブネットに適用するビットマスクを入力します。

7.  \[**ネットワーク サイト ID**\] をクリックし、このサブネットを追加する先のサイトのサイト ID を選択します。
    
    > [!NOTE]
    > ネットワーク サイトがまだ作成されていない場合、この一覧は空です。手順の詳細については、「<a href="lync-server-2013-create-or-modify-a-network-site.md">Lync Server 2013 でのネットワーク サイトの作成または変更</a>」を参照してください。また、 <strong>Get-CsNetworkSite</strong> コマンドレットを実行して、展開のサイト ID を取得することもできます。詳細については、 Lync Server 管理シェルのドキュメントを参照してください。


8.  必要に応じて、\[**説明**\] をクリックし、このサブネットを説明する追加情報を入力します。

9.  \[**確定**\] をクリックします。

その他のサブネットをネットワーク サイトに追加するには、これらのステップを繰り返します。

