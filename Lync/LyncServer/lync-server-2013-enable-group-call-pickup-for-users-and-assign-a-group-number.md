---
title: ユーザーに対するグループ通話ピックアップの有効化とグループ番号の割り当て
TOCTitle: ユーザーに対するグループ通話ピックアップの有効化とグループ番号の割り当て
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945650(v=OCS.15)
ms:contentKeyID: 52056699
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ユーザーに対するグループ通話ピックアップの有効化とグループ番号の割り当て

 

_**トピックの最終更新日:** 2013-01-30_

通話ピックアップ グループの番号をコール パーク オービット テーブルに追加した後、グループの番号をユーザーに割り当て、そのユーザーに対してグループ通話ピックアップを有効にします。Secondary Extension Feature Activation (SEFAUtil) リソース キット ツールを使用して、グループ番号を割り当て、グループ通話ピックアップを有効にします。

> [!NOTE]
> ハイブリッド展開では、グループ通話ピックアップ グループを、オンラインに所属するユーザーに割り当てないでください。オンラインに所属するユーザーはグループ通話ピックアップに参加できません。つまり、オンラインに所属するユーザーへの呼び出しを他のユーザーが応答することや、他のユーザーへの呼び出しをオンラインに所属するユーザーが応答することはできません。


## グループ番号を割り当て、ユーザーに対してグループ通話ピックアップを有効にするには

1.  SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。

2.  コマンド ラインで、次のコマンドを実行します。
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    たとえば、グループ番号 199 をユーザーに割り当てるには
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

## 関連項目

#### タスク

[ユーザーのグループ通話ピックアップを無効にする](lync-server-2013-disable-group-call-pickup-for-users.md)

