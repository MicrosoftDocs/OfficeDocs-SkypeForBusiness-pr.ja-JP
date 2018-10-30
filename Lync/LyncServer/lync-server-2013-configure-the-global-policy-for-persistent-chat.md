---
title: 'Lync Server 2013: 常設チャットのグローバル ポリシーを構成する'
TOCTitle: 常設チャットのグローバル ポリシーを構成する
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48272243
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 で常設チャットのグローバル ポリシーを構成する

 

_**トピックの最終更新日:** 2012-10-06_

既定のグローバル ポリシーを単独で使用すると、その展開のすべてのユーザー対して 常設チャットの設定を有効にできます。また、サイトやユーザーに関して追加のポリシーを指定して、特定のユーザーやサイトに対して 常設チャットを有効にするか無効にするかを制御することもできます。

グローバル ポリシーは削除できません。 削除しようとすると、構成が既定値にリセットされます。

> [!NOTE]
> 常設チャット サーバーを構成して使用するには、まず、トポロジ ビルダーを使用して 常設チャット サーバー サポートをトポロジに追加してから、そのトポロジを公開する必要があります。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync Server 2013 での展開への常設チャットサーバーの追加</a>」を参照してください。<br />
> 常設チャット サーバーの構成設定を構成するには、「展開」のドキュメントの「<a href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync Server 2013 で常設チャット サーバーのオプションをグローバルに、または常設チャット サーバー プール用に構成する</a>」を参照してください。


## 常設チャットのグローバル ポリシーを構成するには

1.  CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。

2.  \[**スタート**\] メニューから \[ Lync Server コントロール パネル\] を選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。Lync Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「操作」のドキュメントの「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。
    

    > [!IMPORTANT]
    > Windows PowerShell コマンドレットを使用することもできます。詳細については、「展開」のドキュメントの「<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用した常設チャット サーバーの構成</A>」を参照してください。



3.  Lync Server コントロール パネル で、\[**常設チャット**\] をクリックし、\[**常設チャット ポリシー**\] をクリックします。

4.  ポリシーの一覧の \[**グローバル**\] をクリックし、\[**編集**\] をクリックしてから、\[**詳細の表示**\] をクリックします。

5.  \[**編集 常設チャットのポリシー - Global**\] で、以下を実行します。
    
      - グローバルという既定の名前を使用しない場合は、\[**名前**\] でグローバル ポリシーの新しい名前を指定します。
    
      - \[**説明**\] に、ユーザー ポリシーの内容に関する詳細を入力します (たとえば、「\<セントラル サイト名\> のグローバル ポリシー」など)。
    
      - サイト ポリシーまたはユーザー ポリシーで個別に制御するのではなく、すべてのサイトとユーザーについて 常設チャットを制御するには、\[**常設チャットを有効にする**\] チェック ボックスをオンにするかオフにします。

6.  \[**確定**\] をクリックします。

