---
title: 複数のサイトとプールの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7412d0ffb1a5d24c2f30b76b987a16903253bfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>複数のサイトとプールの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-08-26_

Lync Server 2013 は、複数サイトと複数プールの展開をサポートしています。 複数のプールを Office Communications Server 2007 R2 から Lync Server 2013 に移行するには、次の点を考慮する必要があります。

1.  Lync Server 2013 パイロットプールを展開した後、Lync Server 2013 プールに移動されるパイロットユーザーのサブセットと、ユーザーの機能を検証するための方法を定義する必要があります。

2.  パイロットプールにエッジサーバーを展開した後、外部ユーザーが Lync Server 2013 プールと通信できることを検証する必要があります。

3.  Office Communications Server 2007 R2 Edge サーバーからのフェデレーションルートを試験的な Lync Server 2013 エッジサーバーに移行した後、フェデレーションされたユーザーが Lync Server 2013 プールと通信できることを検証する必要があります。

4.  すべてのユーザーと非ユーザーの連絡先オブジェクトを移動した後、Office Communications Server 2007 R2 プールが空であることを確認する必要があります。

5.  Office Communications Server 2007 R2 プールが空であることを確認した後、プールを非アクティブ化することができます。
    
    従来の Office Communications Server 2007 R2 プールおよびサーバーを非アクティブ化する方法について詳しくは、「[フェーズ 10: レガシサイトの廃止](phase-10-decommission-legacy-site.md)」をご覧ください。

</div>

<span> </span>

</div>

</div>

</div>

