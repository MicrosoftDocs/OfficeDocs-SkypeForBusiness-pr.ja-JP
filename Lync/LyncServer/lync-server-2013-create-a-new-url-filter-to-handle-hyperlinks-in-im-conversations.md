---
title: IM 会話でのハイパーリンクの処理のための新しい URL フィルターの作成
TOCTitle: IM 会話でのハイパーリンクの処理のための新しい URL フィルターの作成
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48273643
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# IM 会話でのハイパーリンクの処理のための新しい URL フィルターの作成

 

_**トピックの最終更新日:** 2012-09-26_

グローバル URL フィルターを変更する以外にも、Lync Server 2013 展開内の個々のサイトに対して、カスタム URL フィルターを構成できます。URL フィルターの詳細については、「[Lync Server 2013 でのインスタント メッセージング (IM) の URL フィルターおよびファイル送信の構成](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)」を参照してください。

## 新しい URL フィルターを作成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**IM とプレゼンス**\] をクリックし、\[**URL フィルター**\] をクリックします。

4.  \[**URL フィルター**\] ページで \[**新規**\] をクリックします。

5.  \[**サイトの選択**\] で URL フィルターを作成するサイトをクリックしてから、\[**OK**\] をクリックします。

6.  \[**新しい URL フィルター**\] ダイアログ ボックスで、\[**URL フィルターを有効にする**\] チェック ボックスをオンにして、サイトの URL フィルターを有効にします。

7.  \[**ファイル フィルタの編集**\] の \[**禁止するファイル拡張子の種類**\] に一覧表示されている拡張子を持つファイルを含むすべてのアクティブな URL を禁止するには、\[**ファイル拡張子を持つ URL を禁止する**\] チェック ボックスをオンにします。

8.  \[**ハイパーリンクのプレフィックス**\] ドロップダウン リスト ボックスで、インスタント メッセージ会話内の URL の処理方法に対応するオプションをクリックします。
    
    \[**メッセージを許可**\] ボックスでは、送信が許可されているハイパーリンクの送信時に、ユーザーに対して警告メッセージを送信できます。

9.  \[**確定**\] をクリックします。

## 関連項目

#### タスク

[Lync Server 2013 でのインスタント メッセージング (IM) の URL フィルターおよびファイル送信の構成](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[特定のサイト用の新しいファイル送信フィルターの作成](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[既定のファイル送信フィルターの変更](lync-server-2013-modify-the-default-file-transfer-filter.md)  

#### 概念

[既定の URL フィルターの変更](lync-server-2013-modify-the-default-url-filter.md)

