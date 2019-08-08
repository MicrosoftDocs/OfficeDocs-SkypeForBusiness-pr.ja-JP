---
title: 共存の考慮事項
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc2889a11f6cc0afaecd7adf35bc16075011fef9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>共存の考慮事項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-06_

移行後、Lync Server 2013、常設チャットサーバープールのみが存在し、従来の展開を廃止することができます。

移行が完了する前に、現在のグループチャットサーバーの展開を完全に解除する前に、次のいずれかの展開を使用している可能性があります。

  - Lync server 2013 の常設チャットサーバープール。 Lync Server 2013 プールに所属している必要があります。

  - Lync server 2010、グループチャットプール (Lync Server 2010 プールに所属している必要があります)。

  - Office Communications Server 2007 R2 グループチャットプール。これは、Office Communications Server 2007 R2 プールに所属している必要があります。

これらの展開は、並行して行うことができます。 ただし、1つの展開に含まれているカテゴリ、ルーム、アドインは、関連付けられている展開では操作できません。

手動構成を使用すると、レガシクライアント (グループチャットクライアント) は、Office Communications Server 2007 R2、Lync Server 2010、グループチャット、または Lync Server 2013 で、一度に1つのプールに接続できます。

Lync 2013 (クライアント) は、従来のグループチャットサーバープールではなく、Lync Server 2013、常設チャットサーバープールのみで操作できます。 Lync 2013 (クライアント) で常設チャットを使用するには、ユーザーが Lync 2013 を使っていて、ポリシーによって有効になっている必要があります。

</div>

<span> </span>

</div>

</div>

</div>

