---
title: 'Lync Server 2013: 自動検出のサポートを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb83156d319db96a4c6ed79768193a24e5cc3e0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013 での自動検出のサポートの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-21_

Lync Server web services**自動検出サービス**は、lync Server 2010 累積更新プログラム: 2011 年11月に最初に表示されます。 この更新プログラムには、Lync モバイルクライアントの最初のリリースが付随しています。 自動検出サービスは、Mcx サービスと呼ばれるモバイルサービスを公開しています。

自動検出サービスは、すべてのクライアントが利用可能なサービスや機能に関する情報を要求するための1つの場所として機能します。また、完全修飾ドメイン名または web の uri 参照によって、sevices いるリソースに連絡する方法についても説明します。 自動検出はいくつかの機能を公開します。各クライアントは、クライアントが使用できる機能に基づいて要求を行います。 たとえば、デスクトップ Lync 2013 クライアントでは、autodiscvoer を使って外部 web サービスを決定しますが、モビリティ (Mcx) サービスは使用しません。 クライアントが利用可能な機能を使用できるように正しく定義して有効にするには、クライアントが自動検出エントリを効果的に検索して使用できるようにするシナリオを定義する必要があります。 Autodoscover を使用するには、リバースプロキシによって Lync Server web サービスが公開されている必要があります。 DNS レコードは、Lync Server 自動検出サービスと Lync Server web サービスの DNS クエリを解決するように構成されており、その証明書サービスは、特定のシナリオに合わせて適切に構成されています。

<div>


> [!TIP]  
> 自動検出要求/応答の要素の詳細については、「 <A href="lync-server-2013-understanding-autodiscover.md">Lync Server 2013 での自動検出の概要</A>」を参照してください。



</div>

次の情報と表では、自動検出サービスを最大限に活用するために実装する必要がある構成 (存在する場合) について説明します。 次のトピックの情報は、Microsoft Lync Server 2013 に固有の情報です。 Lync Server 2010 のモビリティを計画する方法のガイダンスについては、「 [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113)」を参照してください。 Lync Server 2010 のモバイル機能を導入するには、[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 での自動検出用の DNS の構成](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [Lync Server 2013 で自動検出用の証明書を構成する](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [Lync Server 2013 での自動検出用のリバースプロキシの構成](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [ハイブリッド展開用の Lync Server 2013 での自動検出の構成](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

