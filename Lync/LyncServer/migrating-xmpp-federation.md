---
title: XMPP フェデレーションの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5957be57e749cbf8e62532afef669a7404169e7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>XMPP フェデレーションの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

以前のバージョンの Lync Server および Office Communications Server では、XMPP 展開とのフェデレーションを可能にするために、個別のサーバーの役割として展開できる拡張メッセージングおよびプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。 Lync Server 2013 では、XMPP 機能を機能として展開できます。 XMPP 機能は、Lync server 2013 エッジサーバー上で実行される XMPP プロキシとして、または Lync Server 2013 フロントエンドサーバー上で実行される XMPP ゲートウェイとして、次の2つの部分に分けてインストールされます。

移行の観点から、Lync Server ユーザーアカウントを Lync Server 2013 プールに移動し、従来の XMPP ゲートウェイを引き続き使用することができます。 これは、Lync Server 2013 で XMPP フェデレーションパートナーが構成されていない場合にのみ可能です。

要約すると、Lync Server 2010 が Office Communications Server 2007 R2 XMPP ゲートウェイを使用して展開されており、レガシ Lync Server 2010 ユーザーに対して XMPP フェデレーションが有効になっている場合、XMPP フェデレーションを Lync Server 2013 に移行するには、次のようにします。

1.  Lync Server 2013 プールを展開します。

2.  Lync Server 2013 エッジサーバーを展開します。

3.  すべてのユーザーを Lync Server 2013 プールに移動する

4.  エッジ サーバーの XMPP アクセス ポリシーと証明書を作成します。

5.  Lync Server 2013 で XMPP フェデレーションを有効にします。 

6.  Lync Server 2013 XMPP ゲートウェイをポイントするように DNS エントリを更新します。

</div>

<span> </span>

</div>

</div>

</div>

