---
title: ネットワーク領域リンク情報の表示
TOCTitle: ネットワーク領域リンク情報の表示
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49887012
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク領域リンク情報の表示

 

_**トピックの最終更新日:** 2013-02-23_

通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを表示できます。ネットワーク内の地域は、物理的なワイド エリア ネットワーク (WAN) 接続を経由してリンクされます。Lync Server コントロール パネルを使用して、2 つのネットワーク地域間の既存のリンクを表示できます。ネットワーク地域リンクの作成または変更の詳細については、「[ネットワーク地域リンクの構成](lync-server-2013-configuring-network-region-links.md)」を参照してください。

## Lync Server コントロール パネルでネットワーク地域リンクを表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**地域リンク**\] をクリックします。

4.  \[**地域リンク**\] ページで、表示する地域リンクをクリックします。
    
    > [!NOTE]
    > 一度に情報を表示できる地域リンクは 1 つだけです。


5.  \[**編集**\] メニューの \[**詳細の表示**\] を選択します。

## Lync Server 管理シェル コマンドレットを使用したネットワーク地域リンク情報の表示

ネットワーク地域リンクは、Lync Server 管理シェルと **Get-CsNetworkRegionLink** コマンドレットを使用して表示することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## ネットワーク地域リンク情報を表示するには

  - すべてのネットワーク地域リンクについての情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsNetworkRegionLink
    
    このコマンドは、次のような情報を返します。
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

詳細については、「[Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)」を参照してください。

## 関連項目

#### タスク

[ネットワーク サイトのリンクの構成](lync-server-2013-configuring-network-site-links.md)

