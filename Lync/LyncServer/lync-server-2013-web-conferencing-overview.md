---
title: Lync Server 2013 web 会議の概要
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Web conferencing overview
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425913(v=OCS.15)
ms:contentKeyID: 48183949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0b85bc97f5737f980c83c992a6a21eaeaca4e40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Lync Server 2013 での web 会議の概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-30_

Web 会議を使用すると、ユーザーは会議中に PowerPoint プレゼンテーションなどのドキュメントを共有し、共同作業を行うことができます。 さらに、ユーザーはデスクトップのすべてまたは一部をリアルタイムで共有することができます。会議の参加者が、会議の同じ表を通じて収集されたように見えます。

<div>

## <a name="whiteboard-and-annotations"></a>ホワイトボードと注釈

ホワイトボードは、テキスト、インク、描画、画像など、共同作業に使用できる空白のキャンバスです。 ホワイトボードで作成した注釈は、すべての会議参加者に表示されます。 ホワイトボード機能を使用すると、会議の参加者がアイデアのディスカッション、ブレインストーミング、メモの記録などを行うことができ、共同作業が強化されます。

</div>

<div>

## <a name="polling"></a>ポーリング

投票機能は、発表者が参加者の好みをすばやく判断できるようにすることで、コラボレーションを強化します。 オンライン会議と会話中に、発表者はポーリングを使って参加者からの匿名の回答を収集できます。 すべての発表者は結果を表示し、結果を非表示にしたり、すべての参加者に表示したりすることができます。

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>アプリケーション共有とデスクトップ共有

会議中は、マルチモニター環境でデスクトップ全体、個別のアプリケーション、個々のモニターを共有できます。 会議の他の参加者は、コンテンツを表示するだけでなく、画面の制御を要求したり、アクセス許可を付与してコンテンツを操作したりすることもできます (スクロールや編集など)。

<div>


> [!NOTE]  
> 会議を表示している参加者は、会議中にコンテンツを引き継ぎ、共有を開始することもできます。



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>PowerPoint 共有

Lync 2010 の PowerPoint プレゼンテーションは、次の2つの方法のいずれかで表示されています。 Lync 2010 を実行しているユーザーの場合、powerpoint プレゼンテーションは powerpoint 97-2003 形式を使用して表示され、powerpoint viewer の埋め込みコピーを使って表示されていました。 Lync Web App を実行しているユーザーの場合、PowerPoint プレゼンテーションは動的 HTML ファイルに変換され、カスタマイズされた DHTML ファイルと Silverlight の組み合わせを使って表示されました。 通常は有効ですが、この方法にはいくつかの制限がありました。

  - 埋め込まれた PowerPoint Viewer (最適な表示エクスペリエンスを提供) は、Windows プラットフォームでのみ利用できます。

  - 多くのモバイルデバイス (多くの一般的な携帯電話を含む) は、Silverlight をサポートしていません。

  - PowerPoint Viewer と DHTML/Silverlight の方法では、PowerPoint の最新のエディションに含まれているすべての機能 (スライド切り替えと埋め込みビデオなど) はサポートされていません。

このような問題を解決し、PowerPoint プレゼンテーションを表示または表示するユーザーの全体的なエクスペリエンスを向上させるために、Lync Server 2013 は、Office Web Apps と Office Web Apps サーバーを使用して PowerPoint プレゼンテーションを処理します。 この新しいアプローチでは、次のような利点があります。

  - 高解像度では、アニメーション、スライド切り替え、埋め込みビデオなどの PowerPoint 機能のサポートが向上しています。

  - これらのプレゼンテーションにアクセスするための追加のモバイルデバイス。 これは、Lync Server 2013 では、カスタマイズされた DHTML や Silverlight ではなく、標準の DHTML と JavaScript を使って PowerPoint プレゼンテーションをブロードキャストするためです。

  - プレゼンテーション自体に関係なく PowerPoint プレゼンテーションをスクロールするための適切な権限を持つユーザー。 たとえば、Ken Myer がスライドショーを発表しているときに、Pilar Ackerman は、Ken のプレゼンテーションに影響を与えずに、必要なスライドを確認できます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

