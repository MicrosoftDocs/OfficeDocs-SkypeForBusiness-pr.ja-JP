---
title: 'Lync Server 2013: ルームのアドインの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eb6525f67f22e09c4bf7ea40f575b3981e9a55c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>Lync Server 2013 でのルームのアドインの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

Lync Server 2013 コントロールパネルでは、**常設チャット**ページの [**アドイン**] セクションを使用して、url を常設チャットルームに関連付けることができます。 これらの Url は、会話機能拡張ウィンドウのチャットルームの Lync 2013 クライアントに表示されます。 管理者が、登録されたアドインの一覧にアドインを追加する必要があります。チャットルームマネージャー/作成者は、ユーザーが Lync 2013 クライアントでこのアップグレードを表示する前に、登録されているアドインのいずれかにルームを関連付ける必要があります。

アドインは、ルーム内でのエクスペリエンスを拡張するために使用されます。 一般的なアドインには、株式のティッカーがチャットルームに投稿されたときに受信する Silverlight アプリケーションを指す URL が含まれている場合があります。また、拡張機能ウィンドウには、株式履歴が表示されます。 チャット ルームに OneNote 2013 の URL をアドインとして埋め込んで、"優先事項" や "今日のトピック" などの共有コンテキストを組み込むこともできます。

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>チャット ルームのアドインを構成するには

1.  CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  [**スタート**] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。
    
    <div>
    

    > [!IMPORTANT]  
    > Windows PowerShell コマンドレットを使うこともできます。 詳細については、展開ドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成</A>する」を参照してください。

    
    </div>

3.  左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。
    
    複数の常設チャットサーバープールの展開の場合、ドロップダウンリストから適切なプールを選択します。

4.  [**アドイン**] ページで、[**新規**] をクリックします。

5.  [**サービスの選択**] で、アドインを作成する必要がある常設チャットサーバープールに対応するサービスを選びます。 アドインは、プール間で移動したり、異なるプール間で共有したりできません。

6.  [**新しいアドイン**] で、次の操作を実行します。
    
      - [**名前**] に、新しいアドインの名前を指定します。
    
      - [**URL**] に、アドインに関連付ける URL を指定します。URL には、http および https プロトコルのみを使用できます。

7.  [**コミット**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)  


[Windows PowerShell コマンドレットを使用した常設チャット サーバーの構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

