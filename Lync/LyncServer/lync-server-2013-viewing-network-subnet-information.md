---
title: ネットワーク サブネット情報の表示
TOCTitle: ネットワーク サブネット情報の表示
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49886938
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク サブネット情報の表示

 

_**トピックの最終更新日:** 2013-02-23_

次の手順を使用して、ネットワーク サブネットを表示できます。Lync Server コントロール パネルから、ネットワーク サブネットを作成、変更、または削除できます。ネットワーク サブネットの作成または変更の詳細については、「[ネットワーク サブネットの作成または変更](lync-server-2013-create-or-modify-network-subnets.md)」を参照してください。

## ネットワーク サブネットを表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**サブネット**\] をクリックします。

4.  \[**サブネット**\] ページで、表示するサブネットをクリックします。
    
    > [!NOTE]
    > 一度に表示できるのは 1 つのサブネットのみです。


5.  \[**編集**\] メニューの \[**詳細の表示**\] をクリックします。

## Lync Server PowerShell コマンドレットを使用して、ネットワーク サブネットの構成情報を表示する

Lync Server PowerShell コマンドレットおよび Get-CsNetworkSubnet コマンドレットを使用して、ネットワーク サブネット情報を表示することもできます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## ネットワーク サブネット情報を表示する

  - すべてのネットワーク サブネットの情報を表示するには、Lync Server 管理シェルに次のコマンドを入力し、ENTER を押します。
    
        Get-CsNetworkSubnet
    
    これは次のような情報を返します。
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

詳細については、[Get-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSubnet) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### タスク

[ネットワーク サブネットの作成または変更](lync-server-2013-create-or-modify-network-subnets.md)  
[ネットワーク サブネットの削除](lync-server-2013-deleting-network-subnets.md)

