---
title: 'Lync Server 2013: ルームのアドインの構成'
TOCTitle: ルームのアドインの構成
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48272059
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのルームのアドインの構成

 

_**トピックの最終更新日:** 2013-02-21_

Lync Server 2013 コントロール パネルで、\[**常設チャット**\] ページの \[**アドイン**\] セクションを使用して、URL を 常設チャット ルームに関連付けることができます。これらの URL は、Lync 2013 クライアントのチャット ルームの会話拡張機能ウィンドウに表示されます。管理者は、登録済みアドインの一覧にアドインを追加する必要があります。また、ユーザーが Lync 2013 クライアントでこのアップグレードを表示できるようにするには、チャット ルーム管理者または作成者が登録済みアドインのいずれかにルームを関連付けておく必要があります。

アドインは、ルーム内でのエクスペリエンスを拡張するために使用されます。たとえば、株価情報がチャット ルームに投稿されたことを検知して、拡張機能ウィンドウに株価の履歴を表示する Silverlight アプリケーションを指す URL をアドインに含めることができます。チャット ルームに OneNote 2013 の URL をアドインとして埋め込んで、"優先事項" や "今日のトピック" などの共有コンテキストを組み込むこともできます。

## チャット ルームのアドインを構成するには

1.  CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  \[**スタート**\] メニューから \[ Lync Server コントロール パネル\] を選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。Lync Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。
    

    > [!IMPORTANT]
    > Windows PowerShell コマンドレットを使用することもできます。詳細については、「展開」のドキュメントの「<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用した常設チャット サーバーの構成</A>」を参照してください。



3.  左側のナビゲーション バーで \[**常設チャット**\] をクリックし、\[**アドイン**\] をクリックします。
    
    複数の 常設チャット サーバー プールを展開する場合は、ドロップダウン リストから適切なプールを選択します。

4.  \[**Add-in**\] ページで、\[**New**\] をクリックします。

5.  \[**サービスの選択**\] で、アドインを作成する必要がある 常設チャット サーバー プールに対応するサービスを選択します。アドインは、プール間で移動したり、異なるプール間で共有したりできません。

6.  \[**New Add-in**\] で、次の操作を実行します。
    
      - \[**名前**\] に、新しいアドインの名前を指定します。
    
      - \[**URL**\] に、アドインに関連付ける URL を指定します。URL には、http および https プロトコルのみを使用できます。

7.  \[**確定**\] をクリックします。

## 関連項目

#### タスク

[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)  

#### 概念

[Windows PowerShell コマンドレットを使用した常設チャット サーバーの構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

