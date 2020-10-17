---
title: Lync Server 2013 IPv6 の技術要件
description: IPv6 の Lync Server 2013 技術要件。
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
ms.openlocfilehash: c54dfbdba56c45f19e7664db075331591c8e87cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559463"
---
# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Lync Server 2013 での IPv6 の技術要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-30_

IPv6 の Lync Server 2013 の構成を計画している場合は、次の要件に留意してください。

  - Lync Server で IPv6 アドレスを使用するには、検出して IPv6 アドレスに解決する必要があるレコードに対してドメインネームシステム (DNS) レコードを作成する必要があります。 IPv6 DNS はホスト AAAA (クアッド A) レコードを使用します。 展開内で IPv4 と IPv6 の両方を使用する場合は、IPv4 用のホスト A レコードと IPv6 用のホスト AAAA レコードの両方を構成し保持するのが最善の方法です。 自身の展開を IPv6 に完全に移行した場合でも、IPv4 を使用する外部ユーザーのために IPv4 DNS ホスト レコードが引き続き必要となる場合があります。
    
    IPv6 DNS ホスト レコードは IPv6 の使用を始める前から展開できます。 クライアントまたはサーバーが IPv6 を使用しない場合、そのレコードは参照されません。 移行時のテクノロジは、どのレコードを使用するかを、移行テクノロジの構成およびポリシーに基づいて判断します。

  - 各 IPv6 アドレスにはスコープがあります。 IPv6 アドレス指定に使用できる3つのスコープは、IPv6 グローバルアドレス (パブリック IPv4 アドレスと類似)、IPv6 固有のローカルアドレス (プライベート IPv4 アドレスの範囲に類似)、IPv6 リンクローカルアドレス (Windows Server の IPv4 の場合は、自動プライベート IP アドレスに似ています) です。 プール内のすべてのサーバーは、同じスコープの IPv6 アドレスを持っている必要があります。

<div>


> [!IMPORTANT]  
> IPv6 は複雑なトピックで、Windows Server レベルおよび Lync Server 2013 レベルで割り当てたアドレスが期待どおりに動作することを確認するために、ネットワークチームとインターネットプロバイダーについて慎重に計画する必要があります。 IPv6 アドレス指定および計画に関するその他のリソースについては、このトピックの最後にあるリンクを参照してください。



</div>

<div>

## <a name="see-also"></a>関連項目


[IP バージョン6アドレス指定アーキテクチャ](https://tools.ietf.org/html/rfc4291)  
[IPv6 グローバルユニキャストアドレス形式](https://tools.ietf.org/html/rfc3587)  
[一意のローカル IPv6 ユニキャストアドレス](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

