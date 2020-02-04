---
title: XMPP フェデレーションの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b72dabd60ea42a84fcf9b15d1d739bc063ddf1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>XMPP フェデレーションの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

以前のバージョンの Lync Server と Office Communications Server では、拡張されたメッセージング機能とプレゼンスプロトコル (XMPP) ゲートウェイが提供されており、これを個別のサーバーの役割として展開して、XMPP の展開とのフェデレーションを可能にすることができました。 Lync Server 2013 では、機能として XMPP 機能を展開できます。 XMPP 機能は、Lync Server 2013 エッジサーバー上で実行される XMPP プロキシとして、または Lync Server 2013 フロントエンドサーバー上で実行される XMPP ゲートウェイとして、2つの部分でインストールされます。

移行の観点から、Lync Server のユーザーアカウントを Lync Server 2013 プールに移動して、従来の XMPP ゲートウェイを引き続き使用することができます。 これは、Lync Server 2013 で XMPP フェデレーションパートナーが構成されていない場合にのみ可能です。

概要では、Lync Server 2010 が Office Communications Server 2007 R2 XMPP ゲートウェイで展開され、従来の Lync Server 2010 ユーザーに対して XMPP フェデレーションが有効になっている場合、XMPP フェデレーションを Lync Server 2013 に移行します。

1.  Lync Server 2013 プールを展開します。

2.  Lync Server 2013 エッジサーバーを展開する。

3.  すべてのユーザーを Lync Server 2013 プールに移動する

4.  エッジサーバー用の XMPP アクセスポリシーと証明書を作成します。

5.  Lync Server 2013 で XMPP フェデレーションを有効にします。 

6.  Lync Server 2013 XMPP ゲートウェイをポイントするように DNS エントリを更新します。

</div>

<span> </span>

</div>

</div>

</div>

