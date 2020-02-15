---
title: XMPP フェデレーションの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b40be7be7382b12165d4cca5a8f651156e2bb7c6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>XMPP フェデレーションの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-16_

以前のバージョンの Office Communications Server では、拡張可能なメッセージングとプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。これは、別のサーバーの役割として展開して、XMPP の展開とのフェデレーションを可能にします。 Lync Server 2013 では、XMPP 機能を機能として展開できます。 XMPP 機能は、Lync server 2013 エッジサーバー上で実行される XMPP プロキシとして、または Lync Server 2013 フロントエンドサーバー上で実行される XMPP ゲートウェイとして、次の2つの部分に分けてインストールされます。

移行の観点から、Office Communications Server 2007 R2 ユーザーアカウントを Lync Server 2013 プールに移動して、Office Communications Server 2007 R2 XMPP ゲートウェイを引き続き使用することができます。 これは、Lync Server 2013 で XMPP フェデレーションパートナーが構成されていない場合にのみ可能です。

要約すると、office communications server が 2007 R2 XMPP ゲートウェイと共に展開されていて、従来の Office Communications Server 2007 R2 ユーザーに対して XMPP フェデレーションが有効になっている場合、XMPP フェデレーションを Lync Server 2013 に移行するには、次のようにします。

1.  Lync Server 2013 プールを展開します。

2.  Lync Server 2013 エッジサーバーを展開します。

3.  すべてのユーザーを Lync Server 2013 プールに移動します。

4.  エッジ サーバーの XMPP アクセス ポリシーと証明書を作成します。

5.  Lync Server 2013 で XMPP フェデレーションを有効にします。 

6.  Lync Server 2013 XMPP ゲートウェイをポイントするように DNS エントリを更新します。

</div>

<span> </span>

</div>

</div>

</div>

