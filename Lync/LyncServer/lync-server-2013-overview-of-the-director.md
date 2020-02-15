---
title: 'Lync Server 2013: ディレクターの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55875699e2411527d9202565ae5d31cc72e776f7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a>Lync Server 2013 のディレクターの概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

ディレクターは、ユーザーの要求を認証する Lync Server 2013 を実行しているサーバーですが、ユーザーアカウントをホームにするわけではありません。 必要に応じて、次の2つのシナリオでディレクターを展開できます。

  - エッジサーバーを展開して外部ユーザーのアクセスを有効にする場合は、ディレクターも展開する必要があります。 このシナリオでは、ディレクターが外部ユーザーを認証し、そのトラフィックを内部サーバーに渡します。 ディレクターが外部ユーザーの認証に使用される場合、フロントエンドプールサーバーは、これらのユーザーの認証を実行することによるオーバーヘッドから解放されます。 また、サービス拒否攻撃などの悪意のあるトラフィックから内部フロントエンドプールを保護するのにも役に立ちます。 このような攻撃でネットワークに無効な外部トラフィックが殺到しても、このトラフィックはディレクターで終了します。

  - 中央サイトに複数のフロントエンドプールを展開する場合は、そのサイトにディレクターを追加することで、認証要求を合理化し、パフォーマンスを向上させることができます。 このシナリオでは、すべての要求が最初にディレクターに送信されてから、適切なフロントエンドプールに転送されます。

</div>

<span> </span>

</div>

</div>

</div>

