---
title: 標準移行シナリオ - 概要
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68ff7110cc7e14ccc76ab7d0c0125e723477934a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a>標準移行シナリオ - 概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-30_

Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットを Lync Server 2013、常設チャットサーバーに移行する場合は、次の項目を出発点として使用します。 標準の Lync Server 2013 の移行パスは、次のようになります。

  - 組織が以前に Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットを展開しており、Lync Server 2013、常設チャットサーバーを展開している。

  - Lync Server 2013 を展開して、常設チャットサーバープールを展開します。

  - 常設チャットルームの移行を準備および計画し、移行のためにシステムをシャットダウンする適切な時間を決定します。

  - 移行用の Windows PowerShell コマンドレット (**エクスポート-CsPersistentChatData**と**インポート-CsPersistentChatData**) を実行して、コンテンツを永続的なチャットサーバーに移動します。

  - 移行が正常に完了したことを確認します。

  - 従来の展開を廃止します。

  - レガシクライアントが Lync Server 2013 の常設チャットサーバーに接続できるように、常設チャットサーバーを構成します。 これが必要なのは、新しいクライアントを展開するのに時間がかかるためです。また、従来のクライアントを使用する既存のユーザーができるだけ早くチャットルームにアクセスできるようにしたいと考えています。

  - 新しいクライアントを展開しながら、従来のグループチャット (クライアント) のワーカが自分のチャットルームにアクセスできることを確認します。

</div>

<span> </span>

</div>

</div>

</div>

