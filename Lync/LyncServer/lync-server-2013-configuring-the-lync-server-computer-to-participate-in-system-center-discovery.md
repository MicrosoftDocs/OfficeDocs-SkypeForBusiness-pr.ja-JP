---
title: System Center discovery に参加するように Lync Server コンピューターを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cec18903f1621d5a616debbbdd16f3c834ac21c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>System Center discovery に参加するように Lync Server 2013 コンピューターを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-20_

新しい Lync Server エージェントが System Center Operations Manager の検出プロセスに参加するようにするには、System Center Operations Manager コンソールがインストールされている各コンピューターで、次の手順を実行する必要があります。

1.  [**管理**] タブで、[**エージェントで管理**します] をクリックします。

2.  コンピューターの名前を右クリックし、[**プロパティ**] をクリックします。 [**プロパティ**] ダイアログボックスの [**セキュリティ**] タブで、[**このエージェントがプロキシとして機能することを許可し、他のコンピューター上の管理オブジェクトを検出**します] をクリックし、[ **OK]** をクリックします。

手順2を完了したら、正常性エージェントサービスを再起動します。 (サービスを再起動すると、新しいコンピューターの検出が強制されます。 サービスを再起動しない場合は、新しいコンピューターが System Center Operations Manager によって検出されるまでに4時間かかることがあります。 サービスが再起動したら、そのコンピューターの Operations Manager イベントログにエラーイベントが記録されていないことを確認します。

</div>

<span> </span>

</div>

</div>

</div>

