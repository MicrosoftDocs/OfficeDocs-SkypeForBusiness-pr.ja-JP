---
title: 内部サーバーとエッジ サーバーの間の接続の検証
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e3868462036312be97484e41c69b51ae022b57c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a>Lync Server 2013 での内部サーバーとエッジ サーバーの間の接続の検証

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-08_

Lync Server 2013 では、エッジサーバーと内部サーバーの間の接続を検証するために、個別の検証ウィザードを利用できました。 Lync Server 2013 では、エッジサーバーをインストールすると、接続の検証が自動的に行われます。

中央管理ストアが配置されている内部コンピューター (または任意のドメインに参加しているコンピューター) で Windows PowerShell **CsManagementStoreReplicationStatus**コマンドレットを実行することで、構成情報のエッジへのレプリケーションを検証できます。Lync Server 2013 コアコンポーネント (OcsCore) がインストールされているコンピューター。 初期結果では、レプリケーションに "True" ではなく "False" と表示されることがあります。 その場合は、 **CsManagementStoreReplication**コマンドレットを実行して、 **CsManagementStoreReplicationStatus**をもう一度実行する前に複製処理が完了するまで待ちます。

Office Communications Server リモート接続アナライザーを使用してリモートユーザー接続を確認するなど、外部ユーザー接続を個別に確認することができます。 詳細については、「 [Lync Server 2013 で外部ユーザーへの接続を確認](lync-server-2013-verify-connectivity-for-external-users.md)する」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

