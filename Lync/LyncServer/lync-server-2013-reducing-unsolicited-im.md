---
title: 'Lync Server 2013: 要請していない IM の削減'
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
ms.openlocfilehash: 5574930d6474a75ca4a35219df7cd2e3e2431b15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>Lync Server 2013 の未承諾 IM の削減

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-12-05_

インテリジェント IM フィルターアプリケーションは、ユーザーの利便性を最小限に抑えながら、最も一般的なウイルスに対して Microsoft Lync Server 2013 の展開を保護するのに役に立ちます。 インテリジェント IM フィルターには、以下の機能があります。

  - 拡張 URL フィルター

  - 拡張ファイル送信フィルター

インテリジェント IM フィルターを使用して、企業ファイアウォールの外側にある未知のエンドポイントから送信された、要求していないか損害を与える可能性のあるインスタント メッセージを禁止するようにフィルターを構成します。フィルターを構成するには、禁止する対象 (たとえば、ハイパーリンクや特定の拡張子のファイルを含むインスタント メッセージ) を判断するための基準を指定します。

インテリジェント IM メッセージフィルターアプリケーションを展開する前に、1つの Lync Server 2013 サーバーから別のサーバーにメッセージをルーティングするときのフィルターオプションの適用方法を理解しておく必要があります。 これらのサーバーが 1 つの組織内に配置されている場合も、組織の境界を越えて配置されている場合も、フィルター オプションが適用される方法は一貫しています。 この一貫性は、カスタマイズされた通知や警告テキストがメッセージに挿入され、サーバー間で送信される方法に適用されます。

推奨されるフィルター処理オプションは、ハイパーリンクを含むインスタントメッセージを許可するが、インテリジェント IM フィルターでリンクを無効にするには、その前にアンダースコアを挿入する必要があることです。 このオプションを選択すると、ハイパーリンクを含む各インスタントメッセージの冒頭に表示されるユーザーに対して通知を作成するオプションが追加されます。

2番目のフィルターオプションは、未変更のハイパーリンクを含むインスタントメッセージを許可することです。 このオプションを選択した場合は、各メッセージに挿入されたユーザーに対して警告を作成するための追加のオプション (推奨) があります。

3番目のオプションは、ハイパーリンクを含むすべてのインスタントメッセージをブロックすることです。 このオプションを選択すると、サーバーはユーザーに警告を送信します。 この警告を記述する必要があります。

</div>

<span> </span>

</div>

</div>

</div>

