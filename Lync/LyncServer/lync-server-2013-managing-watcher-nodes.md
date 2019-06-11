---
title: 'Lync Server 2013: ウォッチャーノードの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7edddd1a1bb67dc4bf3df5b7809aa76b2397e56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a>Lync Server 2013 でのウォッチャーノードの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-20_

ウォッチャーノードで実行される代理トランザクションの変更に加えて、管理者は、 **CsWatcherNodeConfiguration**コマンドレットを使用して、他の2つの重要なタスク (ウォッチャーノードの有効化と無効化) を実行することもできます。テストを実行するときに、内部 Url または外部 Url のいずれかを使用するようにウォッチャーノードを構成します。

既定では、監視ノードは、すべての有効な代理トランザクションを定期的に実行するように設計されています。 ただし、場合によっては、それらのトランザクションを中断する必要があります。 たとえば、監視ノードを一時的にネットワークから切り離す場合は、代理トランザクションを実行する理由がありません。 ネットワーク接続されていない場合、これらのトランザクションは確実に失敗します。 ウォッチャーノードを一時的に無効にする場合は、次のようなコマンドを Lync Server 管理シェルから実行します。

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

このコマンドは、watcher ノードの001.litwareinc.com での代理トランザクションの実行を無効にします。 代理トランザクションの実行を再開するには、Enabled プロパティを True ($True) に戻します。

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> Enabled プロパティを使用して監視ノードをオンまたはオフにできます。監視ノードを完全に削除する場合は、<STRONG>Remove-CsWatcherNodeConfiguration</STRONG> コマンドレットを使用します。<BR>Remove-CsWatcherNodeConfiguration – Identity "atl-watcher-001.litwareinc.com"<BR>このコマンドは、指定されたコンピューターからすべてのウォッチャーノードの構成設定を削除します。これにより、コンピューターで代理トランザクションが自動的に実行されることはなくなります。 ただし、このコマンドを実行しても、System Center agent ファイルまたは Lync Server 2013 のシステムファイルはアンインストールされません。



</div>

既定では、ウォッチャーノードでは、テストを実施するときに、組織の外部 Url が使用されます。 ただし、組織の内部 Url を使用するようにウォッチャーノードを構成することもできます。 これにより、管理者は、境界ネットワーク内に配置されたユーザーの URL アクセスを検証できます。 外部 Url の代わりに内部 Url を使用するようにウォッチャーノードを構成するには、UseInternalWebUrls プロパティを True ($True) に設定します。

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

このプロパティを既定値の False ($False) にリセットすると、ウォッチャーは外部 Url を使用します。

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

