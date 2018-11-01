---
title: ネットワーク領域情報の表示
TOCTitle: ネットワーク領域情報の表示
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49886980
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク領域情報の表示

 

_**トピックの最終更新日:** 2013-02-23_

ネットワーク地域は、複数の地理的な領域にまたがるネットワークのさまざまな部分を相互接続します。すべてのネットワーク地域は、セントラル サイトと関連付ける必要があります。セントラル サイトは、通話受付管理 (CAC) 帯域幅ポリシー サービスが実行されているデータ センター サイトです。Lync Server コントロール パネルを使用して、ネットワーク地域を表示できます。ネットワーク地域には、音声とビデオの接続にインターネットを使用する代替パスを許可するかどうかの設定が含まれます。このトピックを使用して、既存のネットワーク地域を表示します。ネットワーク地域の作成または既存のネットワーク地域の変更の詳細については、「[ネットワーク領域の作成または変更](lync-server-2013-creating-or-modifying-network-regions.md)」を参照してください。

## Lync Server コントロール パネルでネットワーク地域に関する情報を表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**地域**\] をクリックします。

4.  \[**地域**\] ページで、表示する地域をクリックします。
    
    > [!NOTE]
    > 一度に 1 つの地域のみを表示できます。


5.  \[**編集**\] メニューの \[**詳細の表示**\] をクリックします。

## Windows PowerShell コマンドレットを使用したネットワーク地域情報の表示

Windows PowerShell および **Get-CsNetworkRegion** コマンドレットを使用してネットワーク地域情報を表示できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## ネットワーク地域情報を表示するには

  - すべてのネットワーク地域に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsNetworkRegion
    
    次のような情報が表示されます。
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

詳細については、[Get-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### タスク

[ネットワーク領域の作成または変更](lync-server-2013-creating-or-modifying-network-regions.md)  
[既存のネットワーク領域の削除](lync-server-2013-deleting-existing-network-regions.md)

