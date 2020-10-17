---
title: 'Lync Server 2013: 特定のサイト用の新しいファイル送信フィルターの作成'
description: 'Lync Server 2013: 特定のサイト用の新しいファイル送信フィルターを作成します。'
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
ms.openlocfilehash: d3b5003711c2f2e74b726809fba5da6d9fd0aa57
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554703"
---
# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>Lync Server 2013 で特定のサイトに対して新しいファイル転送フィルターを作成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-18_

グローバルファイル転送フィルターを変更するだけでなく、Lync Server 2013 展開内の特定のサイトに対してカスタムファイル転送フィルターを構成できます。 ファイル転送フィルターの詳細については、「 [Lync Server 2013 でインスタントメッセージング (IM) のファイル転送と URL フィルターを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)」を参照してください。

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>特定のサイトに対してファイル送信フィルタを作成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**IM とプレゼンス**] をクリックし、[**ファイル フィルター**] をクリックします。

4.  [**ファイル フィルタ**] ページで [**新規**] をクリックします。

5.  [**サイトの選択**] ダイアログ ボックスで、ファイル送信フィルタを作成するサイトをクリックしてから、[**OK**] をクリックします。

6.  [**新しいファイル フィルタ**] で、[**ファイル フィルタを有効にする**] チェック ボックスをオンにします。

7.  [**ファイル送信**] ドロップダウン リスト ボックスで、[**すべて禁止**] または [**特定の種類のファイルを禁止**] をクリックします。

8.  [**すべて禁止**] をクリックした場合は、ステップ 10 へ進みます。

9.  [**特定の種類のファイルを禁止する**] をクリックした場合は、次の操作を実行します。
    
    1.  [**選択**] をクリックして、禁止する種類のファイル拡張子の既定の一覧を変更します。
    
    2.  [**ファイルの種類を選択**] ダイアログ ボックスで、[**ファイル拡張子**] の下のカテゴリから拡張子を追加するか削除して、禁止または許可するファイルの種類を選択します。
    
    3.  禁止する種類のファイルの拡張子が見当たらない場合は、[**ファイルの拡張子を一覧に追加**] のテキスト ボックスに拡張子を入力して、[**追加**] をクリックします。
    
    4.  [**OK**] をクリックします。

10. [**確定**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でインスタントメッセージング (IM) 用のファイル転送および URL フィルターを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[IM 会話でのハイパーリンクを処理するために Lync Server 2013 で新しい URL フィルターを作成する](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Lync Server 2013 での既定のファイル送信フィルターの変更](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Lync Server 2013 で既定の URL フィルターを変更する](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

