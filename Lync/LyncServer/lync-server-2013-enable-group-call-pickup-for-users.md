---
title: ユーザーのグループ通話ピックアップを有効にする
TOCTitle: ユーザーのグループ通話ピックアップを有効にする
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945620(v=OCS.15)
ms:contentKeyID: 52056554
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ユーザーのグループ通話ピックアップを有効にする

 

_**トピックの最終更新日:** 2013-01-30_

SEFAUtil リソース キット ツールを使用して、ユーザーのグループ通話ピックアップを有効にします。コール パーク オービット テーブル内にある GroupPickup タイプのグループ番号をユーザーに割り当てて、グループ通話ピックアップを有効にする必要があります。SEFAUtil.exe を実行するときに /enablegrouppickup パラメーターを使用して、通話ピックアップのグループ番号の割り当ておよびグループ通話ピックアップの有効化を同時に行います。

## ユーザーのグループ通話ピックアップを有効にするには

1.  SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。

2.  コマンド ラインで、次のコマンドを実行します。
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    たとえば、次のようになります。
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

## 関連項目

#### タスク

[ユーザーへのグループ通話ピックアップ番号の割り当て](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[ユーザーのグループ通話ピックアップを無効にする](lync-server-2013-disable-group-call-pickup-for-users.md)

