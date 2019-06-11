---
title: 'Lync Server 2013: 既定のファイル転送フィルターを変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 475f6e9b599af9ba6db80fdb174d3b38e5df6b00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>Lync Server 2013 で既定のファイル転送フィルターを変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

Lync Server 2013 では、Lync Server 2013 の展開における次のファイル関連のアクティビティ中に、特定の種類のファイルをブロックするグローバルファイル転送フィルターが提供されています。

  - インスタントメッセージング (IM) 会話中のファイル送信要求

  - Office Live Meeting 2007 クライアントで配布資料機能を使用しているときにファイルのアップロードとダウンロードを行う

  - 会議中のマルチメディア再生

ブロックまたは許可するファイルの種類に応じて、Lync Server コントロールパネルを使用してグローバルフィルターを変更できます。 ファイル転送フィルターの詳細については、「 [Lync Server 2013 でインスタントメッセージング (IM) のためのファイル送信と URL フィルタリングを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)」を参照してください。

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>既定のファイル転送フィルターを変更するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[ **IM とプレゼンス**] をクリックし、[**ファイルフィルター**] をクリックします。

4.  [**ファイルフィルター** ] ページで、**グローバル**フィルターをダブルクリックします。

5.  [**ファイルフィルターの編集**] で、[**ファイルフィルターを有効にする**] チェックボックスをオンにします。

6.  [**ファイル転送**] ドロップダウンリストボックスで、[**ブロック**する] または [**特定の種類のファイルをブロック**する] をクリックします。

7.  [**すべてブロック**] をクリックした場合は、手順9に進みます。

8.  [特定の**種類のファイルをブロック**する] をクリックした場合は、次の操作を行います。
    
    1.  [**選択**] をクリックして、ブロックするファイルの種類の拡張子の既定のリストを変更します。
    
    2.  [ファイルの**種類の選択**] で、ブロックまたは削除するファイルの種類を [ファイルの**種類の拡張子**] の下にあるカテゴリから選びます。
    
    3.  ブロックするファイルの種類の拡張子が表示されない場合は、[**ファイルの種類の拡張子を追加する**] の下のテキストボックスに拡張子を入力し、[**追加**] をクリックします。
    
    4.  **[OK]** をクリックします。

9.  [**コミット**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのインスタントメッセージング (IM) のファイル転送と URL フィルタリングの構成](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Lync Server 2013 で特定のサイト用の新しいファイル転送フィルターを作成する](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Lync Server 2013 で新しい URL フィルターを作成して、IM 会話のハイパーリンクを処理する](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[Lync Server 2013 で既定の URL フィルターを変更する](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

