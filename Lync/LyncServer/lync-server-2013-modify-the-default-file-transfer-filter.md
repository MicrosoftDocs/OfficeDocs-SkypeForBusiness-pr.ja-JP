---
title: 'Lync Server 2013: 既定のファイル送信フィルターの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 998e14fc0f30b29d0477dc1363f03a84a7ffe775
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>Lync Server 2013 での既定のファイル送信フィルターの変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

Lync Server 2013 には、Lync Server 2013 展開内の次のファイル関連アクティビティで特定の種類のファイルをブロックするグローバルファイル転送フィルターが用意されています。

  - インスタント メッセージング (IM) 会話中のファイル転送要求

  - Office Live Meeting 2007 クライアントの配布資料機能使用中のファイル アップロードおよびダウンロード

  - 会議中のマルチメディア再生

禁止または許可するファイルの種類に応じて、Lync Server コントロールパネルを使用してグローバルフィルターを変更できます。 ファイル転送フィルターの詳細については、「 [Lync Server 2013 でインスタントメッセージング (IM) のファイル転送と URL フィルターを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)」を参照してください。

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>既定のファイル送信フィルターを変更するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**IM とプレゼンス**] をクリックし、[**ファイル フィルター**] をクリックします。

4.  [**ファイル フィルター**] ページで、[**グローバル**] フィルターをダブルクリックします。

5.  [**ファイル フィルターの編集**] で、[**ファイル フィルターを有効にする**] チェック ボックスをオンにします。

6.  [**ファイル転送**] ドロップダウン リストで、[**すべて禁止**] または [**特定の種類のファイルを禁止する**] をクリックします。

7.  [**すべて禁止**] をクリックした場合は、ステップ 9 へ進みます。

8.  [**特定の種類のファイルを禁止する**] をクリックした場合は、次の操作を実行します。
    
    1.  [**選択**] をクリックして、禁止する種類のファイル拡張子の既定の一覧を変更します。
    
    2.  [**ファイルの種類を選択**] の [**ファイルの種類の拡張子**] で、カテゴリの拡張子を追加または削除して、禁止または許可するファイルの種類を選択します。
    
    3.  禁止する種類のファイルの拡張子が見当たらない場合は、[**ファイルの拡張子を一覧に追加**] のテキスト ボックスに拡張子を入力して、[**追加**] をクリックします。
    
    4.  [**OK**] をクリックします。

9.  [**確定**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でインスタントメッセージング (IM) 用のファイル転送および URL フィルターを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Lync Server 2013 で特定のサイトに対して新しいファイル転送フィルターを作成する](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[IM 会話でのハイパーリンクを処理するために Lync Server 2013 で新しい URL フィルターを作成する](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[Lync Server 2013 で既定の URL フィルターを変更する](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

