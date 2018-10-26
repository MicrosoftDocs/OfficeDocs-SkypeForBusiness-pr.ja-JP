---
title: 'Lync Server 2013: (オプション) ダイヤルイン会議の設定の検証'
TOCTitle: (オプション) ダイヤルイン会議の設定の検証
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48273213
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (オプション) Lync Server 2013 でのダイヤルイン会議の設定の検証

 

_**トピックの最終更新日:** 2010-11-02_

ダイヤルイン会議構成の最後の確認作業として、どのアクセス番号も使用しないダイヤルイン会議の地域があるダイヤル プランやダイヤルイン会議の地域が指定されていないアクセス番号を検索します。このステップはオプションです。

## どのアクセス番号も使用しないダイヤルイン会議の地域があるダイヤル プランを検索するには

1.  RTCUniversalServerAdmins グループのメンバーか、 **Cs-ServerAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    このコマンドレットは、どのアクセス番号も使用していないダイヤルイン会議の地域がある、すべてのダイヤル プランを返します。

## 地域が割り当てられていないアクセス番号を検索するには

1.  RTCUniversalServerAdmins グループのメンバーか、 **Cs-ServerAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    このコマンドレットは、地域に関連付けられていないダイヤルイン会議のアクセス番号をすべて返します。

