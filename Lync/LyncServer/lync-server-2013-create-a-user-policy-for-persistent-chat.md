---
title: 'Lync Server 2013: 常設チャット用のユーザー ポリシーを作成する'
TOCTitle: 常設チャット用のユーザー ポリシーを作成する
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48273202
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 で常設チャット用のユーザー ポリシーを作成する

 

_**トピックの最終更新日:** 2012-10-06_

Lync Server コントロール パネルでは、\[**ユーザー**\] のユーザーに割り当てることができるユーザー ポリシーを定義します。

ユーザー ポリシーは、グローバル ポリシーやサイト ポリシーよりも優先されますが、そのユーザー ポリシーを割り当てられた特定のユーザーのみを対象にします。

> [!NOTE]
> 常設チャット サーバーを構成して使用するには、まず、 トポロジ ビルダーを使用して 常設チャット サーバー サポートをトポロジに追加してから、そのトポロジを公開する必要があります。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync Server 2013 での展開への常設チャットサーバーの追加</a>」を参照してください。<br />
> 常設チャット サーバーの構成設定を構成するには、「展開」のドキュメントの「<a href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync Server 2013 で常設チャット サーバーのオプションをグローバルに、または常設チャット サーバー プール用に構成する</a>」を参照してください。


## 常設チャットのユーザー ポリシーを作成するには

1.  CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。

2.  \[**スタート**\] メニューから \[Lync Server コントロール パネル\] を選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。 Lync Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。
    

    > [!IMPORTANT]
    > Windows PowerShell コマンドレットを使用することもできます。「展開」のドキュメントの「<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用した常設チャット サーバーの構成</A>」を参照してください。



3.  左側のナビゲーション バーで \[**常設チャット**\] をクリックし、\[**常設チャットのポリシー**\] をクリックします。

4.  \[**新規**\] をクリックし、\[**ユーザー ポリシー**\] をクリックします。

5.  \[**新規 常設チャットのポリシー**\] で、次の操作を実行します。
    
      - \[**名前**\] で、新しいユーザー ポリシーの名前を指定します。
    
      - \[**説明**\] に、ユーザー ポリシーの詳細説明 (たとえば、特定のユーザーの 常設チャットのポリシー) を入力します。
    
      - ユーザー ポリシーによる特別な制御を受けないユーザーの常設チャットを制御するには、\[**常設チャットを有効にする**\] チェック ボックスをオンまたはオフにします。

6.  \[**確定**\] をクリックします。

