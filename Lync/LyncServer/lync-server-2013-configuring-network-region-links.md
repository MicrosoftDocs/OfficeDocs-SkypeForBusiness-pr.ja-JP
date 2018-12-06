---
title: ネットワーク地域リンクの構成
TOCTitle: ネットワーク地域リンクの構成
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48272895
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク地域リンクの構成

 

_**トピックの最終更新日:** 2012-11-01_

通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを構成できます。ネットワーク内の地域は、物理的なワイド エリア ネットワーク (WAN) 接続を経由してリンクされます。Lync Server コントロール パネルを使用して 2 つのネットワーク地域間のリンクを定義し、これらの地域間のオーディオ接続およびビデオ接続の帯域幅制限を設定できます。既存のネットワーク地域リンクの削除の詳細については、「[ネットワーク領域リンクの削除](lync-server-2013-deleting-network-region-links.md)」を参照してください。

## ネットワーク地域リンクを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**地域リンク**\] をクリックします。

4.  \[**地域リンク**\] ページで、\[**新規**\] をクリックします。

5.  \[**新しい地域リンク**\] で、\[**名前**\] フィールドに値を入力します。
    
    > [!NOTE]
    > この値は、Lync Server 2013 展開内で一意である必要があります。


6.  \[**ネットワーク地域 \#1**\] ドロップダウン リストから、リンクする 2 つの地域の一方を選択します。

7.  \[**ネットワーク地域 \#2**\] ドロップダウン リストから、リンクするもう一方の地域を選択します。この地域は、\[ネットワーク地域 \#1\] で選択した地域とは別の地域である必要があります。

8.  (オプション) これらの地域間の音声またはビデオ通話に帯域幅制限を設定する場合は、\[**帯域幅ポリシー**\] ドロップダウン リストで帯域幅ポリシー プロファイルを選択します。

9.  \[**確定**\] をクリックします。

## ネットワーク地域リンクを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**地域リンク**\] をクリックします。

4.  \[**地域リンク**\] ページで、変更する地域リンクをクリックします。

5.  \[**編集**\] メニューの \[**詳細の表示**\] をクリックします。

6.  \[**地域リンクの編集**\] で、リンクする地域やこのリンクの帯域幅ポリシー プロファイルを変更できます。

7.  \[**確定**\] をクリックします。

## 関連項目

#### タスク

[ネットワーク領域リンクの削除](lync-server-2013-deleting-network-region-links.md)  

#### その他のリソース

[New-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegionLink)  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegionLink)  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

