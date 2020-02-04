---
title: 'Lync Server 2013: 特定のサイト用の新しいファイル転送フィルターを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edaf0afabff9d212cdd3b5353a8e54840979f827
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>Lync Server 2013 で特定のサイト用の新しいファイル転送フィルターを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

グローバルファイル転送フィルターの変更に加えて、Lync Server 2013 展開内の特定のサイト用のカスタムファイル転送フィルターを構成することができます。 ファイル転送フィルターの詳細については、「 [Lync Server 2013 でインスタントメッセージング (IM) のためのファイル送信と URL フィルタリングを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)」を参照してください。

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>特定のサイトのファイル転送フィルターを作成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[ **IM とプレゼンス**] をクリックし、[**ファイルフィルター**] をクリックします。

4.  [**ファイルフィルター** ] ページで、[**新規**] をクリックします。

5.  [**サイトの選択**] ダイアログボックスで、ファイル転送フィルターを作成するサイトをクリックし、[ **OK**] をクリックします。

6.  **新しいファイルフィルター**で、[**ファイルフィルターを有効にする**] チェックボックスをオンにします。

7.  [**ファイル転送**] ドロップダウンリストボックスで、[**ブロック**する] または [**特定の種類のファイルをブロック**する] をクリックします。

8.  [**すべてブロック**] をクリックした場合は、手順10に進みます。

9.  [特定の**種類のファイルをブロック**する] をクリックした場合は、次の操作を行います。
    
    1.  [**選択**] をクリックして、ブロックするファイルの種類の拡張子の既定のリストを変更します。
    
    2.  [ファイルの**種類の選択**] ダイアログボックスで、[ファイルの種類の**拡張子**] の下にあるカテゴリの拡張子を追加または削除して、ブロックまたは許可するファイルの種類を選びます。
    
    3.  ブロックするファイルの種類の拡張子が表示されない場合は、[**ファイルの種類の拡張子を追加する**] の下のテキストボックスに拡張子を入力し、[**追加**] をクリックします。
    
    4.  **[OK]** をクリックします。

10. [**コミット**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのインスタントメッセージング (IM) のファイル転送と URL フィルタリングの構成](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Lync Server 2013 で新しい URL フィルターを作成して、IM 会話のハイパーリンクを処理する](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Lync Server 2013 で既定のファイル転送フィルターを変更する](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Lync Server 2013 で既定の URL フィルターを変更する](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

