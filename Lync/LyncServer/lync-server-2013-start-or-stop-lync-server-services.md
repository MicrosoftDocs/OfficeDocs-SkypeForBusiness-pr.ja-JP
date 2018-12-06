---
title: Lync Server 2013 サービスの開始または停止
TOCTitle: Lync Server 2013 サービスの開始または停止
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48271436
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 サービスの開始または停止

 

_**トピックの最終更新日:** 2014-02-05_

Lync Server コントロール パネルを使用して、特定のコンピューター上で実行されているすべての Lync Server 2013 サービス、または特定のサービスを開始または停止できます。

## コンピューター上のすべての Lync Server サービスを開始または停止するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**トポロジ**\] をクリックし、\[**状態**\] をクリックします。

4.  \[**状態**\] ページで、必要に応じてリストを並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを見つけ、クリックします。

5.  \[**アクション**\] をクリックします。

6.  \[**すべてのサービスの開始**\] または \[**すべてのサービスの停止**\] をクリックします。

## 特定のサービスを開始または停止するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**トポロジ**\] をクリックし、\[**状態**\] をクリックします。

4.  \[**状態**\] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。

5.  \[**プロパティ**\] をクリックします。

6.  必要に応じて、サービスのリストを並べ替え、開始または停止するサービスをクリックします。

7.  \[**アクション**\] をクリックします。

8.  \[**サービスの開始**\] または \[**サービスの停止**\] をクリックします。

9.  \[**閉じる**\] をクリックします。

## 関連項目

#### タスク

[Lync Server 2013 でサービスのセッションを禁止する](lync-server-2013-prevent-sessions-for-services.md)  

#### その他のリソース

[Lync Server 2013 トポロジの管理](lync-server-2013-managing-the-lync-server-topology.md)

