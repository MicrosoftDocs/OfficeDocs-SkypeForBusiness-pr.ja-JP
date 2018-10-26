---
title: ネットワーク領域ルート情報の表示
TOCTitle: ネットワーク領域ルート情報の表示
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49886913
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク領域ルート情報の表示

 

_**トピックの最終更新日:** 2013-02-23_

通話受付管理 (CAC) 構成内のすべての地域には、他のすべての地域へのアクセス方法がいくつかある必要があります。地域のリンクが地域間の接続に対する帯域幅制限を設定し、物理リンクも表す一方、ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。既存のネットワーク領域ルートを表示するには、Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェルで以下の手順を使用します。ネットワーク地域ルートを作成、または変更する方法の詳細については、「[ネットワーク領域ルートの作成または変更](lync-server-2013-creating-or-modifying-network-region-routes.md)」を参照してください。

## Lync Server コントロール パネルでネットワーク地域ルート情報を表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**地域ルート**\] をクリックします。

4.  \[**地域ルート**\] ページで、変更する地域ルートをクリックします。
    
    > [!NOTE]
    > 一度に表示できる地域ルートは 1 つだけです。


5.  \[**編集**\] メニューの \[**詳細の表示**\] をクリックします。

## Lync Server PowerShell コマンドレットを使用してネットワーク地域ルート情報を表示する

ネットワーク地域ルート情報は、Lync Server PowerShell と Get-CsNetworkInterRegionRoute コマンドレットを使用して表示することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## ネットワーク地域ルート情報を表示する

  - すべてのネットワーク地域ルートの情報を表示するには、Lync Server 管理シェルで以下のコマンドを入力して、次に Enter を押します。
    
        Get-CsNetworkInterRegionRoute
    
    これは次のような情報を返します。
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

詳細については、[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### タスク

[ネットワーク領域ルートの作成または変更](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[既存のネットワーク領域ルートの削除](lync-server-2013-deleting-existing-network-region-routes.md)

