---
title: 既定のファイル送信フィルターの変更
TOCTitle: 既定のファイル送信フィルターの変更
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48272574
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 既定のファイル送信フィルターの変更

 

_**トピックの最終更新日:** 2012-11-01_

Lync Server 2013 では、Lync Server 2013 展開内の次のファイル関連操作の間に特定の種類のファイルを禁止する、グローバル ファイル転送フィルターを利用できます。

  - インスタント メッセージング (IM) 会話中のファイル転送要求

  - Office Live Meeting 2007 クライアントの配布資料機能使用中のファイル アップロードおよびダウンロード

  - 会議中のマルチメディア再生

禁止または許可するファイルの種類に応じて、Lync Server コントロール パネルを使用してグローバル フィルターを変更できます。 ファイル送信フィルターの詳細については、「[Lync Server 2013 でのインスタント メッセージング (IM) の URL フィルターおよびファイル送信の構成](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)」を参照してください。

## 既定のファイル送信フィルターを変更するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**IM とプレゼンス**\] をクリックし、\[**ファイル フィルター**\] をクリックします。

4.  \[**ファイル フィルター**\] ページで、\[**グローバル**\] フィルターをダブルクリックします。

5.  \[**ファイル フィルターの編集**\] で、\[**ファイル フィルターを有効にする**\] チェック ボックスをオンにします。

6.  \[**ファイル転送**\] ドロップダウン リストで、\[**すべて禁止**\] または \[**特定の種類のファイルを禁止する**\] をクリックします。

7.  \[**すべて禁止**\] をクリックした場合は、ステップ 9 へ進みます。

8.  \[**特定の種類のファイルを禁止する**\] をクリックした場合は、次の操作を実行します。
    
    1.  \[**選択**\] をクリックして、禁止する種類のファイル拡張子の既定の一覧を変更します。
    
    2.  \[**ファイルの種類を選択**\] の \[**ファイルの種類の拡張子**\] で、カテゴリの拡張子を追加または削除して、禁止または許可するファイルの種類を選択します。
    
    3.  禁止する種類のファイルの拡張子が見当たらない場合は、\[**ファイルの拡張子を一覧に追加**\] のテキスト ボックスに拡張子を入力して、\[**追加**\] をクリックします。
    
    4.  \[**OK**\] をクリックします。

9.  \[**確定**\] をクリックします。

## 関連項目

#### タスク

[Lync Server 2013 でのインスタント メッセージング (IM) の URL フィルターおよびファイル送信の構成](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[特定のサイト用の新しいファイル送信フィルターの作成](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[IM 会話でのハイパーリンクの処理のための新しい URL フィルターの作成](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  

#### 概念

[既定の URL フィルターの変更](lync-server-2013-modify-the-default-url-filter.md)

