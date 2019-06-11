---
title: IM 会話でハイパーリンクを処理するための新しい URL フィルターを作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f8f9a06dd80f87f2758269ddd2d468aeae2014d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>Lync Server 2013 で新しい URL フィルターを作成して、IM 会話のハイパーリンクを処理する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-26_

グローバル URL フィルターを変更するだけでなく、Lync Server 2013 展開内の個々のサイトのカスタム URL フィルターを構成することができます。 URL フィルタリングの詳細については、「 [Lync Server 2013 でインスタントメッセージング (IM) のファイル転送と URL フィルタリングを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)」を参照してください。

<div>

## <a name="to-create-a-new-url-filter"></a>新しい URL フィルターを作成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[ **IM とプレゼンス**] をクリックし、[ **URL フィルター**] をクリックします。

4.  [ **URL フィルター** ] ページで、[**新規**] をクリックします。

5.  [**サイトの選択**] で、URL フィルターを作成するサイトをクリックし、[ **OK**] をクリックします。

6.  [**新しい Url フィルター** ] ダイアログボックスで、[url フィルターを**有効**にする] チェックボックスをオンにして、サイトの url フィルタリングを有効にします。

7.  [ファイルの種類の**編集**] で、[**ブロックするファイルの種類の拡張子**] の下に一覧表示されている拡張子を持つファイルをブロックするには、[**ファイル拡張子を含む url をブロック**する] チェックボックスをオンにします。

8.  [**ハイパーリンクのプレフィックス**] ドロップダウンリストボックスで、インスタントメッセージの会話で url を処理する方法に対応するオプションをクリックします。
    
    [**許可] メッセージ**ボックスを使用すると、送信が許可されているハイパーリンクを送信するときに、ユーザーに警告メッセージが送信されます。

9.  [**コミット**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのインスタントメッセージング (IM) のファイル転送と URL フィルタリングの構成](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Lync Server 2013 で特定のサイト用の新しいファイル転送フィルターを作成する](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Lync Server 2013 で既定のファイル転送フィルターを変更する](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Lync Server 2013 で既定の URL フィルターを変更する](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

