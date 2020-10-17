---
title: 'Lync Server 2013: 代理トランザクションの実行'
description: 'Lync Server 2013: 代理トランザクションの実行。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b0c26024f361dac196319eaf849c1847033cc9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569353"
---
# <a name="running-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013 で代理トランザクションを実行する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-08-18_

代理トランザクションは、通常、2つの方法で実施されます。 Get-cshealthmonitoringconfiguration コマンドレットを使用して、各レジストラープールのテストユーザーをセットアップできます。 これらのテストユーザーは、代理トランザクションで使用するために事前に構成されたユーザーのペアです。 (通常、これらはテストアカウントであり、実際のユーザーに属するアカウントではありません)。テストユーザーがプールに対して構成されている場合は、テストに関与するユーザーアカウントの id を指定せずに (および資格情報を指定して)、そのプールに対して代理トランザクションを実行することができます。

または、実際のユーザーアカウントを使用して代理トランザクションを実行することもできます。 たとえば、2人のユーザーがインスタントメッセージを交換できない場合は、2つのユーザーアカウントを使用して代理トランザクションを実行して (テストアカウントのペアではなく)、問題の診断と解決を試みることができます。 実際のユーザーアカウントを使用して代理トランザクションを実行する場合は、各ユーザーのログオン名とパスワードを指定する必要があります。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で監視ノードのテストユーザーと構成設定を構成する](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Lync Server 2013 での代理トランザクションの特別なセットアップ手順](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

