---
title: Lync Server 2013 でサービスのセッションを禁止する
TOCTitle: Lync Server 2013 でサービスのセッションを禁止する
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48272956
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でサービスのセッションを禁止する

 

_**トピックの最終更新日:** 2012-11-01_

Lync Server コントロール パネルを使用し、特定のコンピューター上で実行されているすべての Lync Server 2013 サービスの新しいセッションを禁止したり、特定の Lync Server 2013 サービスの新しいセッションを禁止したりできます。

## コンピューター上のすべての Lync Server サービスの新しいセッションを禁止するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**トポロジ**\] をクリックし、\[**状態**\] をクリックします。

4.  \[**状態**\] ページで、必要に応じて一覧を並べ替えるかまたは検索し、新しいセッションを禁止するサービスを実行しているコンピューターを確認してクリックします。

5.  \[**アクション**\] をクリックします。

6.  \[**すべてのサービスの新しいセッションを禁止**\] をクリックします。

## 特定のサービスの新しいセッションを禁止するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**トポロジ**\] をクリックし、\[**状態**\] をクリックします。

4.  \[**状態**\] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。

5.  \[**プロパティ**\] をクリックします。

6.  必要に応じてサービスの一覧を並べ替え、新しいセッションを禁止するサービスをクリックします。

7.  \[**アクション**\] をクリックします。

8.  \[**サービスの新しいセッションを禁止**\] をクリックします。

9.  \[**閉じる**\] をクリックします。

## 関連項目

#### その他のリソース

[Lync Server 2013 トポロジの管理](lync-server-2013-managing-the-lync-server-topology.md)

