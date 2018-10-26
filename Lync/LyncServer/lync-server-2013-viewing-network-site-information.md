---
title: ネットワーク サイト情報の表示
TOCTitle: ネットワーク サイト情報の表示
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49886878
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク サイト情報の表示

 

_**トピックの最終更新日:** 2013-02-23_

ネットワーク サイトは、通話受付管理 (CAC) または Enhanced 9-1-1 展開の各地域内で構成されるオフィスまたは拠点です。ネットワーク サイトの情報は Lync Server 2013 コントロール パネルまたは Lync Server 管理シェルで表示できます。ネットワーク サイトの作成または変更の詳細については、「[ネットワーク サイトの作成または変更](lync-server-2013-creating-or-modifying-network-sites.md)」を参照してください。

## Lync Server コントロール パネルでネットワーク サイトの情報を表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**サイト**\] をクリックします。

4.  \[**サイト**\] ページで、表示するサイトをクリックします。
    
    > [!NOTE]
    > 一度に表示できるのは 1 つのサイトの情報だけです。


5.  \[**編集**\] メニューの \[**詳細の表示**\] をクリックします。

## Lync Server 管理シェルのコマンドレットを使用してネットワーク サイトの情報を表示するには

ネットワーク サイトの情報を表示するには Get-CsNetworkSite コマンドレットを使用します。このコマンドレットは、Lync Server 2013 管理シェルからも Windows PowerShell のリモート セッションからも実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## ネットワーク サイトの情報を表示するには

  - すべてのネットワーク サイトに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsNetworkSite
    
    コマンドを実行すると次のような情報が表示されます。
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

詳細については、[Get-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSite) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### タスク

[ネットワーク サイトの作成または変更](lync-server-2013-creating-or-modifying-network-sites.md)  
[既存のネットワーク サイトの削除](lync-server-2013-deleting-an-existing-network-site.md)

