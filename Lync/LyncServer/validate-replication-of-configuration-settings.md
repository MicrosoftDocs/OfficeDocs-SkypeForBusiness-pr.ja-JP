---
title: 構成設定のレプリケーションを検証する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cde1f3a96f249e98bc4e48c2e6d9c40adaad526
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a>構成設定のレプリケーションを検証する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

中央管理ストアが配置されている内部コンピューターまたは任意のドメインで Lync Server 2013 **CsManagementStoreReplicationStatus**コマンドレットを実行して、構成情報のレプリケーションをエッジサーバーに対して検証することができます。Lync Server 2013 コアコンポーネントがインストールされている参加しているコンピューター。

初期結果では、レプリケーションに "True" ではなく "False" と表示されることがあります。 その場合は、 **CsManagementStoreReplication**コマンドレットを実行して、 **CsManagementStoreReplicationStatus**コマンドレットをもう一度実行する前に、レプリケーションが完了するまで待ちます。

</div>

<span> </span>

</div>

</div>

</div>

