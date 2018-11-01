---
title: ユーザーへのグループ通話ピックアップ番号の割り当て
TOCTitle: ユーザーへのグループ通話ピックアップ番号の割り当て
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945647(v=OCS.15)
ms:contentKeyID: 52056685
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ユーザーへのグループ通話ピックアップ番号の割り当て

 

_**トピックの最終更新日:** 2013-01-30_

グループ通話ピックアップ グループの番号をコール パーク オービット テーブルに追加したら、グループをユーザーに割り当てることができます。SEFAUtil (Secondary Extension Feature Activation) リソース キット ツールを使用して、通話ピックアップ グループをユーザーに割り当てます。

> [!NOTE]
> ハイブリッド展開では、グループ通話ピックアップ グループを、オンラインに所属するユーザーに割り当てないでください。オンラインに所属するユーザーはグループ通話ピックアップに参加できません。つまり、オンラインに所属するユーザーへの呼び出しを他のユーザーが応答することや、他のユーザーへの呼び出しをオンラインに所属するユーザーが応答することはできません。


## グループ通話ピックアップ グループをユーザーに割り当てるには

1.  SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。

2.  コマンド ラインで、次のコマンドを実行します。
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    たとえば、次のようになります。
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

## 関連項目

#### タスク

[ユーザーのグループ通話ピックアップを有効にする](lync-server-2013-enable-group-call-pickup-for-users.md)  
[ユーザーのグループ通話ピックアップを無効にする](lync-server-2013-disable-group-call-pickup-for-users.md)

