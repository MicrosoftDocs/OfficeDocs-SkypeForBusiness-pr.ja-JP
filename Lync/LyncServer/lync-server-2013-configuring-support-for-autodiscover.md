---
title: 'Lync Server 2013: 自動検出のサポートの構成'
description: 'Lync Server 2013: 自動検出のサポートの構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23991f2f9467035f4ba461ff1b6a84fa8ed1a11d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556913"
---
# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013 での自動検出のサポートの構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-21_

Lync Server web services **自動検出サービス** は、lync server 2010 の累積更新プログラム:11 月2011に最初に表示されていました。 この更新プログラムには、Lync Mobile クライアントの最初のリリースが付属していました。 自動検出サービスは、Mcx サービスと呼ばれるモビリティサービスを公開しています。

自動検出サービスは、すべてのクライアントが利用可能なサービスと機能に関する情報を要求するための単一の場所として機能します。また、完全修飾ドメイン名または web uniform resource locator reference によって、その連絡先に連絡する方法についても説明します。 自動検出では多数の機能が公開されており、各クライアントはクライアントが使用できる機能に基づいて要求を行います。 たとえば、デスクトップ Lync 2013 クライアントは autodiscvoer を使用して外部 web サービスを決定しますが、mobility (Mcx) サービスは使用しません。 クライアントで使用可能な機能を使用できるように適切に定義して有効にするには、クライアントが自動検出エントリを効果的に検索して使用できるようにするシナリオを定義する必要があります。 Autodoscover を使用するには、リバースプロキシが Lync Server web サービスを公開する必要があり、その DNS レコードが Lync server 自動検出サービスおよび Lync Server web サービスの DNS クエリを解決するように構成されており、その証明書サービスが特定のシナリオに対して適切に構成されている必要があります。

<div>


> [!TIP]  
> 自動検出要求/応答に含まれる要素の技術的な詳細については、「 <A href="lync-server-2013-understanding-autodiscover.md">Lync Server 2013 の自動検出につい</A>て」を参照してください。



</div>

次の情報と表は、シナリオごとに、自動検出サービスを完全かつ効果的に使用するために実装する必要がある構成 (存在する場合) を定義しています。 以下のトピックの情報は、Microsoft Lync Server 2013 に固有のものです。 Lync Server 2010 のモビリティを計画する方法のガイダンスについては、「」を参照してください [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113) 。 Lync Server 2010 のモビリティを展開するには、「」を参照してください。 [https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での自動検出用の DNS の構成](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [Lync Server 2013 での自動検出用の証明書の構成](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [Lync Server 2013 での自動検出のリバースプロキシの構成](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [Lync Server 2013 でのハイブリッド展開の自動検出の構成](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

