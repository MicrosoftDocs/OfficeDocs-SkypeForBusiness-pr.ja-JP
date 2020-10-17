---
title: 'Lync Server 2013: 中央管理ストアのレプリケーションの状態'
description: 'Lync Server 2013: 中央管理ストアのレプリケーションの状態。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f1f9008a966040cf34ac0499c023f9dbe53a541
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544363"
---
# <a name="central-management-store-replication-status-in-lync-server-2013"></a>Lync Server 2013 の中央管理ストアのレプリケーションの状態

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-01-26_

管理者が Lync Server に何らかの種類を変更した場合 (たとえば、管理者が新しい音声ポリシーを作成するか、アドレス帳サーバーの構成設定を変更した場合)、変更は中央管理ストアに記録されます。 その後、Lync Server サービスまたはサーバーの役割を実行しているすべてのコンピューターに変更をレプリケートする必要があります。

データをレプリケートするために、マスターレプリケーター (中央管理サーバー上で実行されている) は、変更された構成データのスナップショットを作成します。 次に、このスナップショットのコピーが、Lync Server サービスまたはサーバーの役割を実行している各コンピューターに送信されます。 これらのコンピューターでは、レプリケーションエージェントがスナップショットを受信し、変更されたデータをアップロードします。 エージェントは、マスターレプリケーターを送信して、最新のレプリケーションの状態を報告するメッセージを送信します。

Get-CsManagementStoreReplicationStatus コマンドレットを使用すると、組織内の Lync Server コンピューターのレプリケーションの状態を確認できます。

このコマンドレットを実行できるユーザー 既定では、次のグループのメンバーが、Get-CsManagementStoreReplicationStatus コマンドレットをローカルで実行することを承認されています。 RTCUniversalUserAdmins、RTCUniversalServerAdmins。

このコマンドレットが割り当てられているすべての RBAC の役割の一覧 (自分で作成したカスタムの RBAC の役割を含む) を取得するには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a>関連項目


[Get-csmanagementstorereplicationstatus](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

