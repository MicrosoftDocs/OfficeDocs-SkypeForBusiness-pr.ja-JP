---
title: 仲介サーバーの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80c6dbc55e41324ad9c3e7d83bb593d8b8e93c64
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a>仲介サーバーの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

マージウィザードを実行すると、仲介サーバーが Lync Server 2013 パイロットトポロジに統合されます。 ただし、Office Communications Server 2007 R2 プールは Lync Server 2013 仲介サーバーと通信できないため、すべてのユーザーを移行した後に、Lync Server 2013 仲介サーバーを構成します。 サイドバイサイドの移行中に、Lync Server 2013 プールは、Office Communications Server 2007 R2 仲介サーバーと通信します。

Lync Server 2013 仲介サーバーを構成する場合は、Office Communications Server 2007 R2 ゲートウェイもアップグレードまたは置換する必要があります。 Office Communications Server 2007 R2 ゲートウェイは、Lync Server 2013 仲介サーバーをサポートしていません。 Lync Server 2013 に認定されているゲートウェイを展開し、Lync Server 2013 仲介サーバーに関連付ける必要があります。 Office Communications Server 2007 R2 展開を完全に使用停止にするには、この手順が必要です。

このセクションのトピックでは、Lync Server 2013 仲介サーバーの移行を完了した後に実行する必要がある構成タスクについて説明します。 併置された仲介サーバーからスタンドアロンの仲介サーバーへの移行は、オプションのタスクです。

  - [仲介サーバーの構成](configure-mediation-server.md)

  - [新しい Lync Server 2013 仲介サーバーを使用するように音声ルートを変更する](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [併置された仲介サーバーをスタンドアロンの仲介サーバーに移行する (オプション)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

