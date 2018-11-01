---
title: 'Lync Server 2013: 常設チャットのサイト ポリシーを作成する'
TOCTitle: 常設チャットのサイト ポリシーを作成する
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48271330
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 で常設チャットのサイト ポリシーを作成する

 

_**トピックの最終更新日:** 2012-10-06_

展開したサイトごとに、サイト固有の 常設チャット ポリシーを作成できます。

サイト ポリシーの構成はグローバル ポリシーの構成よりも優先されますが、対象になるのはサイト ポリシーで指定された特定のサイトだけです。

> [!NOTE]
> 常設チャット サーバーを構成して使用するには、まず、トポロジ ビルダーを使用して 常設チャット サーバー サポートをトポロジに追加してから、そのトポロジを公開する必要があります。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync Server 2013 での展開への常設チャットサーバーの追加</a>」を参照してください。<br />
> 常設チャット サーバーの構成設定を構成するには、「展開」のドキュメントの「<a href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync Server 2013 で常設チャット サーバーのオプションをグローバルに、または常設チャット サーバー プール用に構成する</a>」を参照してください。


## サイトの 常設チャット ポリシーを作成するには

1.  CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。

2.  \[**スタート**\] メニューから \[ Lync Server コントロール パネル\] を選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。Lync Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**常設チャット**\] をクリックし、\[**常設チャットのポリシー**\] をクリックします。
    

    > [!IMPORTANT]
    > Windows PowerShell コマンドレットを使用することもできます。詳細については、「展開」のドキュメントの「<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用した常設チャット サーバーの構成</A>」を参照してください。



4.  \[**新規作成**\] をクリックし、\[**サイト ポリシー**\] をクリックします。

5.  \[**サイトの選択**\] でポリシーを適用するサイトをクリックします。

6.  \[**新規 常設チャットのポリシー**\] で、次の操作を実行します。
    
      - \[**名前**\] で、新しいサイト ポリシーの名前 (Redmond など) を指定します。
    
      - \[**説明**\] にサイト ポリシーの内容の詳細 (「Redmond のチャット ルーム ポリシー」など) を入力します。
    
      - サイト ポリシーによって特に制御されていないすべてのサイトの常設チャットを制御するには、\[**常設チャットを有効にする**\] チェック ボックスをオンまたはオフにします。

7.  \[**確定**\] をクリックします。

