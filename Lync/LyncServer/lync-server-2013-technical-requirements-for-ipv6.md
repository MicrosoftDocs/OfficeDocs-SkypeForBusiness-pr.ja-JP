---
title: Lync Server 2013 IPv6 の技術要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88e0d822e14ea1792751338bd3606766cc98ab96
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Lync Server 2013 での IPv6 の技術要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-30_

IPv6 の Lync Server 2013 の構成を計画している場合は、次の要件に留意してください。

  - Lync Server で IPv6 アドレスを使用するには、検出して IPv6 アドレスに解決する必要があるレコードに対してドメインネームシステム (DNS) レコードを作成する必要があります。 IPv6 DNS はホスト AAAA (クアッド A) レコードを使用します。 展開内で IPv4 と IPv6 の両方を使用する場合は、IPv4 用のホスト A レコードと IPv6 用のホスト AAAA レコードの両方を構成し保持するのが最善の方法です。 自身の展開を IPv6 に完全に移行した場合でも、IPv4 を使用する外部ユーザーのために IPv4 DNS ホスト レコードが引き続き必要となる場合があります。
    
    IPv6 DNS ホスト レコードは IPv6 の使用を始める前から展開できます。 クライアントまたはサーバーが IPv6 を使用しない場合、そのレコードは参照されません。 移行時のテクノロジは、どのレコードを使用するかを、移行テクノロジの構成およびポリシーに基づいて判断します。

  - 各 IPv6 アドレスにはスコープがあります。 IPv6 アドレス指定に使用できる3つのスコープは、IPv6 グローバルアドレス (パブリック IPv4 アドレスと類似)、IPv6 固有のローカルアドレス (プライベート IPv4 アドレスの範囲に類似)、IPv6 リンクローカルアドレス (自動プライベート IP アドレスに似ています) です。Windows Server for IPv4)。 プール内のすべてのサーバーは、同じスコープの IPv6 アドレスを持っている必要があります。

<div>


> [!IMPORTANT]  
> IPv6 は複雑なトピックで、Windows Server レベルおよび Lync Server 2013 レベルで割り当てたアドレスが期待どおりに動作することを確認するために、ネットワークチームとインターネットプロバイダーについて慎重に計画する必要があります。 IPv6 アドレス指定および計画に関するその他のリソースについては、このトピックの最後にあるリンクを参照してください。



</div>

<div>

## <a name="see-also"></a>関連項目


[IP バージョン6アドレス指定アーキテクチャ](http://tools.ietf.org/html/rfc4291)  
[IPv6 グローバルユニキャストアドレス形式](http://tools.ietf.org/html/rfc3587)  
[一意のローカル IPv6 ユニキャストアドレス](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

