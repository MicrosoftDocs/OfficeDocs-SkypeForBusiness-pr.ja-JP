---
title: ネットワーク地域間ルートの作成
TOCTitle: ネットワーク地域間ルートの作成
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48272127
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク地域間ルートの作成

 

_**トピックの最終更新日:** 2012-10-20_

*ネットワーク地域間ルート*では、ネットワーク地域のペア間のルートを定義します。 通話受付管理展開のネットワーク地域の各ペアには、ネットワーク地域間ルートが必要です。 これにより、展開内の各ネットワーク地域が他のすべての地域にアクセスできるようになります。

地域のリンクが地域間の接続に対する帯域幅制限を設定し、地域間ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。

ネットワーク地域間ルートの操作の詳細については、「Lync Server 管理シェル」のドキュメントに記載されている次のコマンドレットを参照してください。

  - [New-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

トポロジの例では、北アメリカ/EMEA、EMEA/APAC、および北アメリカ/APAC の 3 つの各地域ペアにネットワーク地域間ルートを定義する必要があります。

## Lync Server 管理シェルを使用してネットワーク地域間ルートを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  **New-CsNetworkInterRegionRoute** コマンドレットを実行して、必要なルートを定義します。たとえば、以下を実行します。
    
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"

       &nbsp;
    
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"

       &nbsp;
    
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
    
    > [!NOTE]
    > 北アメリカ/APAC 間には直接のネットワーク地域リンクがないため、このネットワーク地域間ルートには 2 つのネットワーク地域リンクが必要です。


## Lync Server コントロール パネルを使用してネットワーク地域間ルートを作成するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックします。

3.  \[**地域ルート**\] ナビゲーション ボタンをクリックします。

4.  \[**新規**\] をクリックします。

5.  \[**新しい地域ルート**\] ページで、\[**名前**\] をクリックし、ネットワーク地域間ルートの名前を入力します。

6.  \[**ネットワーク地域 \#1**\] をクリックし、一覧でネットワーク地域 \#2 にルーティングするネットワーク地域をクリックします。

7.  \[**ネットワーク地域 \#2**\] をクリックし、一覧でネットワーク地域 \#1 にルーティングするネットワーク地域をクリックします。

8.  \[**ネットワーク地域リンク**\] フィールドの横の \[**追加**\] をクリックし、ネットワーク地域間ルートで使用するネットワーク地域リンクを追加します。
    
    > [!NOTE]
    > 2 つのネットワーク地域のルートを作成する場合、その間に直接のネットワーク地域リンクがなければ、必要なすべてのリンクを追加してルートを完成させる必要があります。 たとえば、北アメリカ/APAC 間には直接のネットワーク地域リンクがないため、このネットワーク地域間ルートには 2 つのネットワーク地域リンクが必要です。


9.  \[**確定**\] をクリックします。

10. トポロジのネットワーク地域間ルートを作成するには、他のネットワーク地域間ルートに関してステップ 4 ～ 9 を繰り返します。

