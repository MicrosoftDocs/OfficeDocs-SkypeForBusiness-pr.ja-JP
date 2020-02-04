---
title: System Center discovery に参加するためのウォッチャーノードの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ca3724f9b5bc8200e2ca006d9fa7445d7368ab7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a>Lync Server 2013 で監視ノードを構成して System Center discovery に参加する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

Watcher ノードが System Center Operations Manager の検出プロセスに参加していることを確認するには、System Center Operations Manager コンソールがインストールされているコンピューターで、次の手順を実行する必要があります。

1.  [**管理**] タブで、[**エージェントで管理**します] をクリックします。

2.  ウォッチャーノードのコンピューターの名前を右クリックし、[**プロパティ**] をクリックします。 [**プロパティ**] ダイアログボックスの [**セキュリティ**] タブで、[**このエージェントがプロキシとして機能することを許可し、他のコンピューター上の管理オブジェクトを検出**します] をクリックし、[ **OK]** をクリックします。

プロキシとして動作するようにウォッチャーノードを構成したら、ウォッチャーノードのコンピューターを再起動します。 コンピューターが再起動したら、そのコンピューターの Operations Manager イベントログにエラーイベントが記録されていないことを確認します。 コンピューターが15分以上実行されている場合は、Operations Manager コンソールを使用して、lync Server コンピューターが**lync**カテゴリの下に表示されていることを確認します。

</div>

<span> </span>

</div>

</div>

</div>

