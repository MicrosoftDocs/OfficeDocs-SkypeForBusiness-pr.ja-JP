---
title: 複数のサイトとプールの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bee98cdc88a836be8b629d76b5bed57af402a3ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>複数のサイトとプールの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-17_

Lync Server 2013 では、複数サイトと複数プールの展開がサポートされています。 Lync Server 2010 から Lync Server 2013 に複数のプールを移行するプロセスには、以下の点を考慮する必要があります。

1.  Lync Server 2013 パイロットプールを展開した後は、Lync Server 2013 プールに移動するパイロットユーザーのサブセットと、ユーザーの機能を検証するための方法を定義する必要があります。 たとえば、ユーザーをパイロットプールに移動した後、ユーザーの会議ポリシーが Lync Server 2013 に移動されたことを確認します。

2.  パイロットプールにエッジサーバーを展開した後、外部ユーザーが Lync Server 2013 プールと通信できることを検証する必要があります。

3.  Lync server 2010 エッジサーバーから lync Server 2013 エッジサーバーへのフェデレーションルートを移行した後、フェデレーションユーザーが Lync Server 2013 プールと通信できることを検証する必要があります。

4.  ユーザーおよびユーザー以外のすべての連絡先オブジェクトを移動した後、Lync Server 2010 プールが空であることを確認する必要があります。

5.  Lync Server 2010 プールが空であることを確認した後、プールを非アクティブ化することができます。
    
    従来の Lync Server 2010 プールおよびサーバーを非アクティブ化する方法の詳細については、「[フェーズ 8: 従来のプール](phase-8-decommission-legacy-pools.md)を使用停止にする」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

