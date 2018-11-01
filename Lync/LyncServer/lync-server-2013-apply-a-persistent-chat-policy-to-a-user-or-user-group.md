---
title: 'Lync Server 2013: 常設チャット ポリシーをユーザーまたはユーザー グループに適用する'
TOCTitle: 常設チャット ポリシーをユーザーまたはユーザー グループに適用する
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48272678
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 で常設チャット ポリシーをユーザーまたはユーザー グループに適用する

 

_**トピックの最終更新日:** 2012-10-06_

Lync Server 2013 でユーザーが有効になっている場合、適切なポリシーを特定のユーザーに適用し、 常設チャット サーバーに対してユーザーを有効または無効にできます。

> [!NOTE]
> 常設チャット サーバーを構成して使用するには、まず、 トポロジ ビルダーを使用して 常設チャット サーバー サポートをトポロジに追加してから、そのトポロジを公開する必要があります。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync Server 2013 での展開への常設チャットサーバーの追加</a>」を参照してください。<br />
> 常設チャット サーバーの構成設定を構成するには、「展開」のドキュメントの「<a href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync Server 2013 で常設チャット サーバーのオプションをグローバルに、または常設チャット サーバー プール用に構成する</a>」を参照してください。


このトピックの手順を使用して、以前に作成した 常設チャット ユーザー ポリシーを、1 つ以上のユーザー アカウントまたはユーザー グループに適用します。

## 常設チャットのユーザー ポリシーをユーザー アカウントに適用するには

1.  CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。

2.  \[**スタート**\] メニューから \[Lync Server コントロール パネル\] を選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。 Lync Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、\[**編集**\] をクリックして、\[**詳細の表示**\] をクリックします。

5.  \[**常設チャット ポリシー**\] の \[**Lync Server ユーザーの編集**\] で、適用する常設チャット ユーザー ポリシーを選択します。
    
    > [!NOTE]
    > [<strong>&lt;自動&gt;</strong>] 設定では、既定の有効なポリシーが適用されます。これらの設定はサーバーによって自動的に適用されます。


6.  \[**確定**\] をクリックします。

