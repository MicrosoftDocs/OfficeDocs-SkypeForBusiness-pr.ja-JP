---
title: 標準移行シナリオ-高レベル
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0acdf50ac515810b2813a98e9dc1f289e327eba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a>標準移行シナリオ-高レベル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-30_

Lync Server 2010、グループチャットまたは Office Communications Server 2007 R2 グループチャットから Lync Server 2013、常設チャットサーバーへの移行時には、次の項目を開始点として使用します。 Lync Server 2013 の標準の移行パスは次のとおりです。

  - 組織が以前に Lync Server 2010、グループチャットまたは Office Communications Server 2007 R2 グループチャットを展開していて、Lync Server 2013、常設チャットサーバーを展開している。

  - Lync Server 2013 を展開し、次に常設チャットサーバープールを展開します。

  - 常設チャットルームの移行の準備と計画を行い、移行のためにシステムをシャットダウンするための適切な時間を決定します。

  - 移行用の Windows PowerShell コマンドレット (**export-cspersistentchatdata**および**export-cspersistentchatdata**) を実行して、コンテンツを常設チャットサーバーに移動します。

  - 移行が成功したことを確認します。

  - 従来の展開を使用停止にします。

  - 従来のクライアントが Lync Server 2013 の常設チャットサーバーに接続できるように常設チャットサーバーを構成します。 新しいクライアントの展開には時間がかかるので、従来のクライアントのユーザーがチャット ルームに可能な限り早急にアクセスできるようにするには、この操作が必要になります。

  - 新しいクライアントを展開する一方で、従来のグループチャット (クライアント) を使用しているワーカーが自分のチャットルームにアクセスできるようにします。

</div>

<span> </span>

</div>

</div>

</div>

