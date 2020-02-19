---
title: 'Lync Server 2013: ハイブリッドおよびスプリットドメイン自動検出'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d181887ad031a1873b289600de3f59b9d3131dd0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Lync Server 2013 でのハイブリッドおよびスプリットドメインの自動検出

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-14_

共有 SIP アドレススペース (*分割ドメイン*展開または*ハイブリッド*展開とも呼ばれる) は、ユーザーがオンプレミス展開とオンライン環境の間で展開される構成です。 必要な結果は、自分のホームサーバーが配置されている場所 (オンプレミスまたはオンライン) に関係なく、ユーザーが展開にログインして、ホームサーバーの場所にリダイレクトされることです。 これを実現するために、Lync Server 2013 の自動検出機能を使用して、オンラインユーザーをオンライントポロジにリダイレクトします。 これを行うには、Lync Server 管理シェル、 **get-help**コマンドレット、および**Set-CsHostingProvider**コマンドレットを使用して、自動検出の UNIFORM resource locator (URL) を構成します。

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>分割ドメイン展開でのモビリティ

次の展開属性を収集して記録する必要があります。

  - Lync Server 管理シェルで、と入力します。
    
        Get-CsHostingProvider

  - 結果で、属性**Proxyfqdn**を持つオンラインプロバイダーを見つけます。 たとえば、sipfed.online.lync.com のようになります。

  - ProxyFQDN の値を記録します。

  - オンプレミスの Lync Server コントロールパネルでフェデレーションを有効にし、オンラインプロバイダーとのフェデレーションを許可します。

  - オンライン プロバイダーに対してフェデレーションを有効にします。 既定では、すべてのオンラインユーザーがドメインフェデレーションに対して有効になっており、すべてのドメインと通信できます。

  - 禁止ドメインと許可ドメインを定義する場合は、明示的に許可または明示的に禁止するドメインを決定します。

  - オンラインフェデレーションの場合は、ファイアウォール例外、証明書、および DNS ホスト (IPv6 を使用する場合は A または AAAA) のレコードを計画する必要があります。 また、フェデレーション ポリシーを構成する必要もあります。 詳細については、「 [Planning For Lync Server 2013 And Office Communications server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

