---
title: 'Lync Server 2013: ルームのアドインの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8779e770ca96cbfc34bbbc1f1897df1f5eb9ea03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523054"
---
# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>Lync Server 2013 でのルームのアドインの構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

Lync Server 2013 コントロールパネルで、[**常設チャット**] ページの [**アドイン**] セクションを使用して、url を常設チャットルームに関連付けることができます。 これらの Url は、会話機能拡張ウィンドウのチャットルームの Lync 2013 クライアントに表示されます。 管理者は登録されたアドインの一覧にアドインを追加する必要があり、チャットルームマネージャー/作成者は、ユーザーが Lync 2013 クライアントでこのアップグレードを表示する前に、登録済みのアドインの1つにルームを関連付ける必要があります。

アドインは、ルーム内でのエクスペリエンスを拡張するために使用されます。 一般的なアドインには、株式相場がチャットルームに投稿されたときに受信する Silverlight アプリケーションを指す URL が含まれていることがあります。また、機能拡張ウィンドウで株価情報を表示します。 チャット ルームに OneNote 2013 の URL をアドインとして埋め込んで、"優先事項" や "今日のトピック" などの共有コンテキストを組み込むこともできます。

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>チャット ルームのアドインを構成するには

1.  CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  [ **スタート** ] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開いて管理 URL を入力します。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。
    
    <div>
    

    > [!IMPORTANT]  
    > Windows PowerShell コマンドレットを使用することもできます。 詳細については、「展開」のドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成する</A> 」を参照してください。

    
    </div>

3.  左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。
    
    複数の常設チャットサーバープールを展開する場合は、ドロップダウンリストから適切なプールを選択します。

4.  [**アドイン**] ページで、[**新規**] をクリックします。

5.  **[サービスの選択**] で、アドインを作成する必要がある常設チャットサーバープールに対応するサービスを選択します。 アドインをプール間で移動したり、複数のプールで共有したりすることはできません。

6.  [**新規 アドイン**] で、次の操作を実行します。
    
      - [**名前**] に、新しいアドインの名前を指定します。
    
      - [**URL**] で、アドインに関連付ける URL を指定します。URL には http および https プロトコルのみを使用できます。

7.  [**確定**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)  


[Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成する](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

