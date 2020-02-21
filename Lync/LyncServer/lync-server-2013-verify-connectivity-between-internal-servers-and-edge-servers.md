---
title: 内部サーバーとエッジサーバーの間の接続を確認する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bd749aea86f610cee2671648e4e2ce1486cfba5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a>Lync Server 2013 の内部サーバーとエッジサーバーの間の接続を確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

Lync Server 2013 では、エッジサーバーと内部サーバー間の接続を検証するために別の検証ウィザードを使用できました。 Lync Server 2013 接続の検証は、エッジサーバーをインストールすると自動的に行われます。

中央管理ストアが配置されている内部コンピューターで Windows PowerShell **get-csmanagementstorereplicationstatus**コマンドレットを実行することによって、構成情報のエッジへのレプリケーションを検証できます (または、Lync Server 2013 コアコンポーネント (ocscore) がインストールされているドメインに参加しているコンピューター)。 最初の結果では、レプリケーションに関する状態が "True" ではなく "False" と示される場合があります。 その場合は、**Invoke-CsManagementStoreReplication** コマンドレットを実行し、レプリケーションが完了するまでしばらく時間を置いてから、再び **Get-CsManagementStoreReplicationStatus** コマンドレットを実行します。

リモート ユーザー接続の確認のための Office Communications Server リモート接続アナライザーの利用も含め、外部ユーザー接続を別々に確認することができます。 詳細については、「 [Lync Server 2013 で外部ユーザーの接続を確認する](lync-server-2013-verify-connectivity-for-external-users.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

