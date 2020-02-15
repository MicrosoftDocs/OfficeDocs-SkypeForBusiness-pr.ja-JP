---
title: 複数のサイトとプールの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97bd53e884d4b66b8197ef2672d6ffdca39d4cea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>複数のサイトとプールの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-08-26_

Lync Server 2013 では、複数サイトと複数プールの展開がサポートされています。 複数のプールを Office Communications Server 2007 R2 から Lync Server 2013 に移行する際には、以下の点を考慮する必要があります。

1.  Lync Server 2013 パイロットプールを展開した後は、Lync Server 2013 プールに移動するパイロットユーザーのサブセットと、ユーザーの機能を検証するための方法を定義する必要があります。

2.  パイロットプールにエッジサーバーを展開した後、外部ユーザーが Lync Server 2013 プールと通信できることを検証する必要があります。

3.  Office Communications Server 2007 R2 エッジサーバーからのフェデレーションルートを、パイロット Lync Server 2013 エッジサーバーに移行した後、フェデレーションユーザーが Lync Server 2013 プールと通信できることを検証する必要があります。

4.  ユーザーおよびユーザー以外のすべての連絡先オブジェクトを移動した後、Office Communications Server 2007 R2 プールが空であることを確認する必要があります。

5.  Office Communications Server 2007 R2 プールが空であることを確認した後、プールを非アクティブ化することができます。
    
    従来の Office Communications Server 2007 R2 プールおよびサーバーを非アクティブ化する方法の詳細については、「[フェーズ 10: 従来のサイト](phase-10-decommission-legacy-site.md)を使用停止にする」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

