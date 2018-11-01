---
title: ネットワーク サブネットの削除
TOCTitle: ネットワーク サブネットの削除
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49887128
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク サブネットの削除

 

_**トピックの最終更新日:** 2013-02-21_

次の手順を使用して、サブネットを削除できます。ネットワーク サブネットの作成、変更、または削除は、Lync Server コントロール パネルから行えます。サブネットの作成または変更の詳細については、「[ネットワーク サブネットの作成または変更](lync-server-2013-create-or-modify-network-subnets.md)」を参照してください。

通話受付管理サービス (CAC) を実装している Microsoft Lync Server 2013 の導入では、ほとんどの場合、多数のサブネットが存在するのが一般的です。このため、Lync Server 管理シェル からサブネットを構成するのが最適である場合がほとんどです。ここから、Windows PowerShell コマンドレットの **Import-CSV** と組み合わせて **New-CsNetworkSubnet** を呼び出すことができます。これらのコマンドレットを使用すると、コンマ区切り値 (.csv) ファイルからサブネット設定を読み込み、同時に複数のサブネットを作成することができます。.csv ファイルからサブネットを作成する方法の例は、「[New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。

## ネットワーク サブネットを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\]、\[**サブネット**\] の順にクリックします。

4.  \[**サブネット**\] ページで、削除するサブネットをクリックします。
    
    > [!NOTE]
    > 1 つ以上のサブネットを一度に削除できます。これを実行するには、Ctrl キーを押しながら、複数のサブネットを選択します。または、すべてのサブネットを選択するには、[<strong>編集</strong>] メニューの [<strong>すべて選択</strong>] をクリックします。


5.  \[**編集**\] メニューの \[**削除**\] をクリックします。

6.  \[**OK**\] をクリックします。

## 関連項目

#### タスク

[ネットワーク サブネットの作成または変更](lync-server-2013-create-or-modify-network-subnets.md)

