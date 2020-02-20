---
title: IM 会話でのハイパーリンクを処理するための新しい URL フィルターを作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 250533f8de89eb1cd5aaa72d8f66cfd0800a1bc2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>IM 会話でのハイパーリンクを処理するために Lync Server 2013 で新しい URL フィルターを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-26_

グローバル URL フィルターを変更するだけでなく、Lync Server 2013 展開内の個々のサイトに対してカスタム URL フィルターを構成することもできます。 URL フィルターの詳細については、「 [Lync Server 2013 でインスタントメッセージング (IM) のファイル転送と url フィルターを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)」を参照してください。

<div>

## <a name="to-create-a-new-url-filter"></a>新しい URL フィルターを作成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**IM とプレゼンス**] をクリックし、[**URL フィルター**] をクリックします。

4.  [**URL フィルター**] ページで [**新規**] をクリックします。

5.  [**サイトの選択**] で URL フィルターを作成するサイトをクリックしてから、[**OK**] をクリックします。

6.  [**新しい URL フィルター**] ダイアログ ボックスで、[**URL フィルターを有効にする**] チェック ボックスをオンにして、サイトの URL フィルターを有効にします。

7.  [**ファイル フィルタの編集**] の [**禁止するファイル拡張子の種類**] に一覧表示されている拡張子を持つファイルを含むすべてのアクティブな URL を禁止するには、[**ファイル拡張子を持つ URL を禁止する**] チェック ボックスをオンにします。

8.  [**ハイパーリンクのプレフィックス**] ドロップダウン リスト ボックスで、インスタント メッセージ会話内の URL の処理方法に対応するオプションをクリックします。
    
    [**メッセージを許可**] ボックスでは、送信が許可されているハイパーリンクの送信時に、ユーザーに対して警告メッセージを送信できます。

9.  [**確定**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でインスタントメッセージング (IM) 用のファイル転送および URL フィルターを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Lync Server 2013 で特定のサイトに対して新しいファイル転送フィルターを作成する](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Lync Server 2013 での既定のファイル送信フィルターの変更](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Lync Server 2013 で既定の URL フィルターを変更する](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

