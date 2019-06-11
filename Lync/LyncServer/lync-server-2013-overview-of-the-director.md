---
title: 'Lync Server 2013: ディレクターの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e1c36cd556dcf641acb4571b5bb349466eb278d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a>Lync Server 2013 のディレクターの概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-08_

ディレクターは、Lync Server 2013 を実行しているサーバーで、ユーザー要求は認証されますが、ユーザーアカウントのホームにはなりません。 次の2つのシナリオでは、必要に応じてディレクターを展開できます。

  - エッジサーバーを展開して外部ユーザーからのアクセスを有効にする場合は、ディレクターも展開する必要があります。 このシナリオでは、ディレクターが外部ユーザーを認証し、そのトラフィックを内部サーバーに渡します。 ディレクターを使用して外部ユーザーを認証すると、フロントエンドプールサーバーは、これらのユーザーの認証を実行するオーバーヘッドから解放されます。 また、サービス拒否攻撃などの悪意のあるトラフィックから、内部のフロントエンドプールを分離することもできます。 このような攻撃で無効な外部トラフィックがネットワークにあふれている場合、このトラフィックはディレクターで終了します。

  - セントラルサイトに複数のフロントエンドプールを展開している場合、そのサイトにディレクターを追加すると、認証要求が簡素化され、パフォーマンスが向上します。 このシナリオでは、すべての要求が最初にディレクターに送られ、適切なフロントエンドプールに転送されます。

</div>

<span> </span>

</div>

</div>

</div>

