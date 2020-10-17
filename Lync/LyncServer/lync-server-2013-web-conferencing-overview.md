---
title: Lync Server 2013 web 会議の概要
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing overview
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425913(v=OCS.15)
ms:contentKeyID: 48183949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6287b5edd711df845b862b49bc15adb8405e8587
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535364"
---
# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Lync Server 2013 の web 会議の概要

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-30_

Web 会議を利用すると、ユーザーは会議中にドキュメント (PowerPoint プレゼンテーションなど) の共有や共同作業を行うことができます。さらに、ユーザーはデスクトップのすべてまたは一部をお互いにリアルタイムで共有できるため、会議の参加者は同席しているように感じます。

<div>

## <a name="whiteboard-and-annotations"></a>ホワイトボードと注釈

ホワイトボードとは、テキスト、インク、描画、およびイメージを利用した共同作業で使用できる空白のキャンバスです。ホワイトボード上に作成される注釈は、すべての会議の参加者が見ることができます。ホワイトボード機能により、会議の参加者がディスカッション、ブレインストーミング、メモ取りなどを行うことができるようになり、コラボレーションが強化されます。

</div>

<div>

## <a name="polling"></a>投票

ポーリング機能により、発表者が迅速に参加者の意向を判断できるため、コラボレーションが強化されます。オンラインの会議または会話中に、発表者はポーリングを使用して参加者から匿名の応答を収集できます。すべての発表者が結果を見ることができ、結果は非表示にすることもすべての参加者に対して表示することもできます。

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>アプリケーション共有とデスクトップ共有

電話会議中には、マルチモニター環境でデスクトップ全体、個々のアプリケーション、または個別のモニターを共有できます。 また、コンテンツを表示するだけでなく、会議の他の参加者が画面のコントロールを要求し、アクセス許可がある場合は、そのコンテンツを操作することもできます (スクロールおよび編集を含む)。

<div>


> [!NOTE]  
> 会議を表示している参加者が、会議中にコンテンツを引き継ぎ、共有を開始することもできます。



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>PowerPoint 共有

Lync 2010 PowerPoint プレゼンテーションは、2つの方法のいずれかで表示されています。 Lync 2010 を実行しているユーザーの場合、powerpoint プレゼンテーションは powerpoint 97-2003 形式を使用して表示され、PowerPoint viewer の埋め込みコピーを使用して表示されていました。 Lync Web App を実行しているユーザーの場合、PowerPoint プレゼンテーションは動的 HTML ファイルに変換され、これらのカスタマイズされた DHTML ファイルと Silverlight を使用して表示されます。 この方法は通常は有効ですが、いくつかの制限がありました。

  - 埋め込み PowerPoint Viewer (最適な表示環境を提供) は、Windows プラットフォームでのみ使用できます。

  - 多くのモバイルデバイス (広く普及している携帯電話の一部を含む) では、Silverlight はサポートされていません。

  - PowerPoint Viewer と DHTML/Silverlight の方法では、より新しいエディションの PowerPoint で検出されたすべての機能 (画面切り替えや埋め込みビデオなど) がサポートされていません。

PowerPoint プレゼンテーションを表示または表示するユーザーの全体的な操作を改善するために、これらの問題に対処するために、Lync Server 2013 は Office Web Apps および Office Web Apps サーバーを使用して PowerPoint プレゼンテーションを処理します。 特に、この新しいアプローチにより次のことが実現します。

  - 高解像度ディスプレイおよび PowerPoint 機能のサポートの強化 (アニメーション、スライド移行、埋め込みビデオなど)。

  - プレゼンテーションにアクセスできるモバイル デバイスの追加。 Lync Server 2013は、カスタマイズされた DHTML と Silverlight ではなく標準 DHTML と JavaScript を使用して PowerPoint プレゼンテーションをブロードキャストするためです。

  - 適切な特権を持つユーザーが、PowerPoint プレゼンテーション自体とは別にプレゼンテーションをスクロール可能。たとえば、Ken Myer がスライド ショーを表示しているときに、Pilar Ackerman が、その Ken のプレゼンテーションに影響を及ぼさずに必要なスライドを確認できます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

