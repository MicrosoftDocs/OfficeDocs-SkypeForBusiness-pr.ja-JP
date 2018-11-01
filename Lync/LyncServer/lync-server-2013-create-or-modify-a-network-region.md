---
title: 'Lync Server 2013: ネットワーク領域の作成または変更'
TOCTitle: ネットワーク領域の作成または変更
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48273464
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのネットワーク領域の作成または変更

 

_**トピックの最終更新日:** 2012-10-19_

*ネットワーク地域* は、通話受付管理 (CAC)、E9-1-1、およびメディア バイパスで使用するネットワーク ハブまたはバックボーンです。ネットワーク地域を作成または変更するには、以下の手順に従います。たとえば、1 つの音声機能用に既にネットワーク地域を作成している場合、新しいネットワーク地域を作成する必要はありません。その他の高度なエンタープライズ VoIP 機能は、それらの同じネットワーク地域を使用します。ただし、機能固有の設定を適用するために、既存のネットワーク地域定義を変更することが必要になる場合があります。たとえば、E9-1-1 のネットワーク地域 (関連付けられた中央サイトが不要) を作成済みで、その後に通話受付制御を展開する場合は、ネットワーク地域の定義を変更して中央サイトを指定する必要があります。詳細については、「[CAC のネットワーク地域の構成](lync-server-2013-configure-network-regions-for-cac.md)」を参照してください。

> [!NOTE]
> ネットワーク地域の定義で機能固有の要件については、すべてその機能の「展開」のトピックで説明されています。


ネットワーク地域を使用した作業の詳細については、次のコマンドレットに関する Lync Server 管理シェル のドキュメントを参照してください。

  - [New-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegion)

## ネットワーク地域の作成

通話受付管理、E9-1-1、またはメディア バイパスで使用できるネットワーク地域を作成します。

## Lync Server 管理シェルを使用してネットワーク地域を作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  New-CsNetworkRegion コマンドレットを実行してネットワーク地域を作成します。
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    次に例を示します。
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    この例では、サイト ID が CHICAGO の中央サイトと関連付けられた "NorthAmerica" というネットワーク地域を作成しました。

3.  トポロジでのネットワーク地域の作成を完了するには、ネットワーク地域ごとの設定値を使用してステップ 2 を繰り返します。

## Lync Server コントロール パネルを使用してネットワーク地域を作成するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックします。

3.  \[**地域**\] をクリックします。

4.  \[**新規**\] をクリックします。

5.  \[**新しい地域**\] ページで、\[**名前**\] をクリックしてネットワーク地域の名前を入力します。

6.  \[**中央サイト**\] をクリックし、リストにある中央サイトを 1 つクリックします。

7.  オプションで、\[**説明**\] をクリックして、このネットワーク サイトを説明する追加情報を入力します。

8.  \[**確定**\] をクリックします。

9.  トポロジでのネットワーク地域の作成を完了するには、その他の地域の設定値を使用してステップ 4 ～ 8 を繰り返します。

## ネットワーク地域の変更

既存のネットワーク地域の設定を変更して、基本地域情報に対する変更、または新しい機能で必要な変更に対応します。

## Lync Server 管理シェルを使用してネットワーク地域を変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  Set-CsNetworkRegion コマンドレットを実行して、既存のネットワーク地域を変更します。
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    次に例を示します。
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    この例では、説明を変更することにより、(このトピックの前半で説明した手順を使用して作成した) "NorthAmerica" という既存のネットワーク地域に変更を加えました。"NorthAmerica" 地域の説明があった場合、このコマンドはここでの値で地域の説明を上書きします。説明が設定されていない場合、このコマンドは説明を設定します。

3.  その他のネットワーク地域を変更するには、その他の地域の設定値を使用してステップ 2 を繰り返します。

## Lync Server コントロール パネルを使用してネットワーク地域を変更するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックします。

3.  \[**地域**\] ナビゲーション ボタンをクリックします。

4.  表で、変更するネットワーク地域をクリックします。

5.  \[**編集**\] をクリックして、\[**詳細の表示...**\] をクリックします。

6.  \[**地域の編集**\] ページで、このネットワーク地域の設定の値を必要に応じて変更します。

7.  \[**確定**\] をクリックします。

8.  ネットワーク地域の変更を完了するには、他の地域の設定値を使用してステップ 4 ～ 7 を繰り返します。

