---
title: ネットワーク領域リンクの削除
TOCTitle: ネットワーク領域リンクの削除
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49887028
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク領域リンクの削除

 

_**トピックの最終更新日:** 2012-11-01_

通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを公正できます。ネットワーク内の地域は、物理的なワイド エリア ネットワーク (WAN) 接続を経由してリンクされます。Lync Server コントロール パネルを使用して、2 つのネットワーク地域間の既存のリンクを削除できます。ネットワーク地域リンクの作成または変更の詳細については、「[ネットワーク地域リンクの構成](lync-server-2013-configuring-network-region-links.md)」を参照してください。

## ネットワーク地域リンクを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**地域リンク**\] をクリックします。

4.  \[**地域リンク**\] ページで、削除する地域リンクをクリックします。
    
    > [!NOTE]
    > 1 つ以上の地域リンクを一度に削除できます。これを実行するには、Ctrl キーを押しながら、複数の地域リンクを選択します。また、すべての地域リンクを選択するには、[<strong>編集</strong>] メニューの [<strong>すべて選択</strong>] をクリックします。


5.  \[**編集**\] メニューの \[**削除**\] を選択します。

6.  \[**OK**\] をクリックします。

## 関連項目

#### タスク

[ネットワーク地域リンクの構成](lync-server-2013-configuring-network-region-links.md)

