---
title: XMPP フェデレーションの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9764554cf9984ceb35878b87032194a51aec3b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>XMPP フェデレーションの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-16_

以前のバージョンの Office Communications Server では、拡張メッセージングとプレゼンスプロトコル (XMPP) ゲートウェイが提供されました。これは、別のサーバーロールとして展開して、XMPP の展開とのフェデレーションを可能にすることができました。 Lync Server 2013 では、機能として XMPP 機能を展開できます。 XMPP 機能は、Lync Server 2013 エッジサーバー上で実行される XMPP プロキシとして、または Lync Server 2013 フロントエンドサーバー上で実行される XMPP ゲートウェイとして、2つの部分でインストールされます。

移行の観点から、Office Communications Server 2007 R2 ユーザーアカウントを Lync Server 2013 プールに移動して、Office Communications Server 2007 R2 XMPP ゲートウェイを引き続き使用することができます。 これは、Lync Server 2013 で XMPP フェデレーションパートナーが構成されていない場合にのみ可能です。

概要では、office communications server が Office Communications Server 2007 R2 XMPP ゲートウェイと共に展開され、従来の Office Communications Server 2007 R2 ユーザーに対して XMPP フェデレーションが有効になっている場合に、XMPP フェデレーションを Lync Server 2013 に移行する方法について説明します。

1.  Lync Server 2013 プールを展開します。

2.  Lync Server 2013 エッジサーバーを展開する。

3.  すべてのユーザーを Lync Server 2013 プールに移動します。

4.  エッジサーバー用の XMPP アクセスポリシーと証明書を作成します。

5.  Lync Server 2013 で XMPP フェデレーションを有効にします。 

6.  Lync Server 2013 XMPP ゲートウェイをポイントするように DNS エントリを更新します。

</div>

<span> </span>

</div>

</div>

</div>

