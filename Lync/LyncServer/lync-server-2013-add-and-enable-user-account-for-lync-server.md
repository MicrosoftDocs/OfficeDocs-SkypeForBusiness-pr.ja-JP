---
title: Lync Server ユーザー アカウントの追加および有効化
TOCTitle: Lync Server ユーザー アカウントの追加および有効化
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48271466
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server ユーザー アカウントの追加および有効化

 

_**トピックの最終更新日:** 2012-11-02_

Active Directory ユーザーとコンピューターでユーザー アカウントを有効にした後、Lync Server コントロール パネルを使用して、Active Directory ユーザーを Lync Server に追加することによって、新しい Lync Server 2013 ユーザー アカウントを作成および有効化できます。

## 新しい Lync Server ユーザーを追加および有効化するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックします。

4.  \[**ユーザーの有効化**\] をクリックします。

5.  \[**新規 Lync Server ユーザー**\] ダイアログで \[**追加**\] をクリックします。

6.  \[**ユーザーの検索**\] ボックスに、名前、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、電子メール アドレス、ユーザーのプリンシパル名 (UPN)、または対象の Active Directory ユーザー アカウントの電話番号の全体か最初の一部の文字列を入力して、\[**検索**\] をクリックします。

7.  表で、Lync Server に追加するアカウントを選択して、\[**OK**\] をクリックします。

8.  ユーザーをプールに割り当て、詳細情報を指定し、ポリシーを対象のユーザーに割り当て、\[**有効にする**\] をクリックします。

## 関連項目

#### タスク

[Lync Server 2013 ユーザー アカウントの再有効化または無効化](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Lync Server からのユーザー アカウントの削除](lync-server-2013-remove-a-user-account-from-lync-server.md)  

#### その他のリソース

[Lync Server 2013 のユーザーの有効化または無効化](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

