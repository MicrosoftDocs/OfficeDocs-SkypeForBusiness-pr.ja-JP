---
title: 'Lync Server 2013: 未承諾 IM の削減'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0f8326d6fa9f85b202e0ea2dcbe3fed63a723aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>Lync Server 2013 での未承諾 IM の削減

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-12-05_

インテリジェント IM フィルターアプリケーションは、ユーザーエクスペリエンスの低下を最小限に抑えて、Microsoft Lync Server 2013 の展開を最も一般的なウイルスと保護するのに役立ちます。 インテリジェント IM フィルターでは、次の機能が提供されます。

  - 強化された URL フィルター

  - 拡張されたファイル転送フィルター機能

インテリジェント IM フィルターを使用して、組織外のエンドポイントからの不要または有害なインスタントメッセージをブロックするようにフィルターを設定します。 フィルターを設定するには、ハイパーリンクを含むインスタントメッセージや特定の拡張子のファイルなど、ブロックする必要があるものを決定するために使用する条件を指定します。

インテリジェント IM メッセージフィルターアプリケーションを展開する前に、メッセージが Lync Server 2013 サーバー間でルーティングされるときのフィルターオプションの適用方法を理解しておく必要があります。 これらのフィルターオプションの適用方法は、サーバーが1つの組織内に配置されているか、組織の境界を超えているかに関係なく一貫しています。 この一貫性は、カスタマイズされた通知や警告テキストがメッセージに挿入され、サーバー間で送信される方法に適用されます。

推奨されるフィルターオプションは、ハイパーリンクを使用してインスタントメッセージを許可することですが、インテリジェント IM フィルターを使用して、リンクを無効にするには、その前にアンダースコアを挿入する必要があります。 このオプションを選ぶと、ハイパーリンクが設定されている各インスタントメッセージの先頭に表示されるユーザーへの通知を作成するオプションが追加されます。

2番目のフィルターオプションは、ハイパーリンクを変更せずにインスタントメッセージを送信できるようにすることです。 このオプションを選択すると、各メッセージに挿入されたユーザーに警告を作成するための追加オプション (推奨) が表示されます。

3番目のオプションは、ハイパーリンクを含むすべてのインスタントメッセージをブロックすることです。 このオプションを選択すると、サーバーはユーザーに警告を送信します。 この警告は、作成する必要があります。

</div>

<span> </span>

</div>

</div>

</div>

