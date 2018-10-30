---
title: 既存のネットワーク領域ルートの削除
TOCTitle: 既存のネットワーク領域ルートの削除
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49886977
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 既存のネットワーク領域ルートの削除

 

_**トピックの最終更新日:** 2012-11-01_

通話受付管理 (CAC) 構成内のすべての地域には、他のすべての地域へのアクセス方法がいくつかある必要があります。地域のリンクが地域間の接続に対する帯域幅制限を設定し、物理リンクも表す一方、ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。Lync Server コントロール パネル を使用するとネットワーク地域ルートを構成できます。Lync Server コントロール パネルから、ネットワーク地域ルートを作成、変更、または削除できます。このトピックを使用して、既存のネットワーク地域ルートを削除できます。ネットワーク地域ルートの作成または変更の詳細については、「[ネットワーク領域ルートの作成または変更](lync-server-2013-creating-or-modifying-network-region-routes.md)」を参照してください。

## ネットワーク地域ルートを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**地域ルート**\] をクリックします。

4.  \[**地域ルート**\] ページで、削除する地域ルートをクリックします。
    
    > [!NOTE]
    > 1 つ以上の地域ルートを一度に削除できます。これを実行するには、Ctrl キーを押しながら、複数のルートを選択します。また、すべての地域ルートを選択するには、[<strong>編集</strong>] メニューの [<strong>すべて選択</strong>] をクリックします。


5.  \[**編集**\] メニューの \[**削除**\] をクリックします。

6.  \[**OK**\] をクリックします。

## 関連項目

#### タスク

[ネットワーク領域ルートの作成または変更](lync-server-2013-creating-or-modifying-network-region-routes.md)  

#### 概念

[ネットワーク地域ルートの構成](https://technet.microsoft.com/ja-jp/library/gg133706\(v=ocs.15\))  

#### その他のリソース

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute)

