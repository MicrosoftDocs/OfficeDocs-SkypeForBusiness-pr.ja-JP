---
title: ネットワーク サイトへの場所ポリシーの追加
TOCTitle: ネットワーク サイトへの場所ポリシーの追加
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48271923
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク サイトへの場所ポリシーの追加

 

_**トピックの最終更新日:** 2013-02-24_

以下の例は、「[場所ポリシーの作成](lync-server-2013-create-location-policies.md)」で定義された **Redmond** の場所のポリシーを既存のネットワーク サイトに追加する方法、および **Redmond** の場所のポリシーを使用する新しいネットワーク サイトを作成する方法を示します。

ネットワーク サイトの操作の詳細については、「Lync Server 管理シェル」のドキュメントに記載されている次のコマンドレットを参照してください。

  - **New-CsNetworkSite**

  - **Get-CsNetworkSite**

  - **Set-CsNetworkSite**

  - **Remove-CsNetworkSite**

## 場所のポリシーを既存のネットワーク サイトに割り当てるには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  既存のネットワーク サイトを変更するには、以下のコマンドレットを実行します。
    
    **Redmond** とマークされている場所のポリシーを、**Redmond** という名前の既存のネットワーク サイトに割り当てます。
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

## 場所のポリシーを新しいネットワーク サイトに割り当てるには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  新しいネットワーク サイトを作成するには、以下のコマンドレットを実行します。
    
    ネットワーク地域の新しいネットワーク サイトを作成して、**Redmond** とマークされた場所のポリシーを割り当てます。
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

