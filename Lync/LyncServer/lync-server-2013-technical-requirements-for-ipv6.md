---
title: 'Lync Server 2013: IPv6 の技術要件'
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
ms.openlocfilehash: e0688319a1b37dbd609a2f2051b3b8c6dfc6a2d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Lync Server 2013 の IPv6 の技術要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-30_

Lync Server 2013 を IPv6 用に構成する場合は、次の要件を念頭に置いてください。

  - Lync Server で IPv6 アドレスを使用するには、IPv6 アドレスを検出し、解決する必要があるレコードに対して、ドメインネームシステム (DNS) レコードを作成する必要があります。 IPv6 DNS はホスト AAAA (クアッド A) レコードを使用します。 展開内で IPv4 と IPv6 の両方を使用する場合は、IPv4 用のホスト A レコードと IPv6 用のホスト AAAA レコードの両方を構成し保持するのが最善の方法です。 自身の展開を IPv6 に完全に移行した場合でも、IPv4 を使用する外部ユーザーのために IPv4 DNS ホスト レコードが引き続き必要となる場合があります。
    
    IPv6 DNS ホスト レコードは IPv6 の使用を始める前から展開できます。クライアントまたはサーバーが IPv6 を使用しない場合、そのレコードは参照されません。移行時のテクノロジは、どのレコードを使用するかを、移行テクノロジの構成およびポリシーに基づいて判断します。

  - 各 IPv6 アドレスにはスコープがあります。 IPv6 アドレス指定に使用できる3つのスコープは、IPv6 グローバルアドレス (パブリック IPv4 アドレスに似ています)、ipv6 固有のローカルアドレス (プライベート IPv4 アドレス範囲に類似)、IPv6 リンクローカルアドレス (自動プライベート IP アドレスに似ています) です。Windows Server (IPv4 の場合)。 プール内のすべてのサーバーに、同じスコープの IPv6 アドレスが含まれている必要があります。

<div>


> [!IMPORTANT]  
> IPv6 は複雑なトピックであり、ネットワークチームとインターネットプロバイダーによる慎重な計画を行う必要があります。これにより、Windows Server レベルで割り当てるアドレスと Lync Server 2013 レベルで自分が意図したとおりに動作することを確認することができます。 IPv6 のアドレス指定と計画に関するその他のリソースについては、このトピックの最後にあるリンクを参照してください。



</div>

<div>

## <a name="see-also"></a>関連項目


[IP バージョン6アドレス体系](http://tools.ietf.org/html/rfc4291)  
[IPv6 グローバルユニキャストアドレス形式](http://tools.ietf.org/html/rfc3587)  
[一意のローカル IPv6 ユニキャストアドレス](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

