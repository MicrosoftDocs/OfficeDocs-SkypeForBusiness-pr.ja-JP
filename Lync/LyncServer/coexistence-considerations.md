---
title: 共存の考慮事項
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7052042afbc3927e1047a9c2fbb30a71168f317
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>共存の考慮事項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-06_

移行後、Lync Server 2013、常設チャットサーバープールのみが存在し、従来の展開を使用停止にすることができます。

移行が完了する前、および現在のグループチャットサーバーの展開を完全に使用停止にする前に、次のいずれかの展開を行うことができます。

  - Lync server 2013、常設チャットサーバープール。 Lync Server 2013 プールに所属している必要があります。

  - Lync server 2010、グループチャットプール。 Lync Server 2010 プールに所属している必要があります。

  - Office Communications Server 2007 R2 グループチャットプール。これは、Office Communications Server 2007 R2 プールに所属している必要があります。

These deployments can exist side by side. However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.

手動構成を使用すると、従来のクライアント (グループチャットクライアント) は、Office Communications Server 2007 R2、Lync Server 2010、グループチャット、または Lync Server 2013 に対して、一度に1つのプールに接続できます。

Lync 2013 (クライアント) は、従来のグループチャットサーバープールではなく、Lync Server 2013、常設チャットサーバープールとのみ対話できます。 Lync 2013 (クライアント) で常設チャットを使用するには、ユーザーが Lync 2013 に所属し、ポリシーによって有効になっている必要があります。

</div>

<span> </span>

</div>

</div>

</div>

