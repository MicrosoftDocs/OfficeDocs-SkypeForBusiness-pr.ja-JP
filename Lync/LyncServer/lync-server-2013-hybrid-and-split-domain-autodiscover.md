---
title: 'Lync Server 2013: ハイブリッドおよび分割ドメイン-自動検出'
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
ms.openlocfilehash: ce38bba4717e3340e7eacf33ce67fc357d208b83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>ハイブリッドおよび分割ドメイン-Lync Server 2013 での自動検出

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-14_

共有 SIP アドレス空間 (*分割ドメイン*展開とも呼ばれます) または*ハイブリッド*展開とも呼ばれる構成で、ユーザーがオンプレミスの展開とオンライン環境を通じて展開されます。 必要な結果は、ホームサーバーが配置されている場所 (オンプレミスまたはオンライン) に関係なく、展開にログインし、ホームサーバーの場所にリダイレクトされることです。 これを実現するために、Lync Server 2013 の自動検出機能を使用して、オンラインユーザーをオンライントポロジにリダイレクトします。 これを行うには、Lync Server 管理シェル、 **Get-CsHostingProvider**コマンドレット、 **Set-cshostingprovider**コマンドレットを使用して、自動検出の UNIFORM resource locator (URL) を構成します。

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>分離ドメイン展開のモビリティ

次の展開された属性を収集して記録する必要があります。

  - Lync Server 管理シェルで、「
    
        Get-CsHostingProvider

  - 結果で、属性**Proxyfqdn**を含むオンラインプロバイダーを見つけます。 たとえば、sipfed.online.lync.com のようになります。

  - ProxyFQDN の値を記録します。

  - オンプレミスの Lync Server コントロールパネルでフェデレーションを有効にして、オンラインプロバイダーとのフェデレーションを許可します。

  - オンラインプロバイダーのフェデレーションを有効にします。 既定では、すべてのオンラインユーザーがドメインフェデレーションを有効にしており、すべてのドメインと通信できます。

  - ブロックされるドメインと許可ドメインを定義する場合は、明示的に許可する、または明示的にブロックするドメインを決定します。

  - オンラインフェデレーションの場合、ファイアウォールの例外、証明書、DNS ホスト (IPv6 を使用している場合は AAAA) を計画する必要があります。 さらに、フェデレーションポリシーを構成する必要があります。 詳細については、「 [Lync server 2013 と Office Communications server フェデレーションの計画](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

