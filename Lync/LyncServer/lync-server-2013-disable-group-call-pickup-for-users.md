---
title: ユーザーのグループ通話ピックアップを無効にする
TOCTitle: ユーザーのグループ通話ピックアップを無効にする
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945638(v=OCS.15)
ms:contentKeyID: 52056642
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ユーザーのグループ通話ピックアップを無効にする

 

_**トピックの最終更新日:** 2013-01-30_

特定ユーザーのグループ通話ピックアップを無効にするには、以下の手順を使用します。

> [!NOTE]
> ユーザーのグループ通話ピックアップを無効にすると、ユーザーに割り当てられた通話ピックアップ グループ番号は保持されません。後で、そのユーザーのグループ通話ピックアップを、再度、有効にする場合、/enablegrouppickup パラメーターを指定して、通話ピックアップ グループ番号を、再度、割り当てる必要があります。


## ユーザーのグループ通話ピックアップを無効にするには

1.  SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。

2.  コマンド ラインで、次のコマンドを実行します。
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    たとえば、次のようになります。
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

## 関連項目

#### タスク

[ユーザーへのグループ通話ピックアップ番号の割り当て](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[ユーザーのグループ通話ピックアップを有効にする](lync-server-2013-enable-group-call-pickup-for-users.md)

