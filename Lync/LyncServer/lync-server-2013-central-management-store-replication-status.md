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
# <a name="central-management-store-replication-status-in-lync-server-2013"></a><span data-ttu-id="df5a6-103">Lync Server 2013 の中央管理ストアのレプリケーションの状態</span><span class="sxs-lookup"><span data-stu-id="df5a6-103">Central management store replication status in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df5a6-104">_**トピックの最終更新日:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="df5a6-104">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="df5a6-105">管理者が Lync Server に何らかの種類を変更した場合 (たとえば、管理者が新しい音声ポリシーを作成するか、アドレス帳サーバーの構成設定を変更した場合)、変更は中央管理ストアに記録されます。</span><span class="sxs-lookup"><span data-stu-id="df5a6-105">When an administrator makes a change of some kind to Lync Server (for example, when an administrator creates a new voice policy or changes the Address Book Server configuration settings) that change is recorded in the Central Management store.</span></span> <span data-ttu-id="df5a6-106">その後、Lync Server サービスまたはサーバーの役割を実行しているすべてのコンピューターに変更をレプリケートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df5a6-106">In turn, the change must then be replicated to all the computers that are running Lync Server services or server roles.</span></span>

<span data-ttu-id="df5a6-107">データをレプリケートするために、マスターレプリケーター (中央管理サーバー上で実行されている) は、変更された構成データのスナップショットを作成します。</span><span class="sxs-lookup"><span data-stu-id="df5a6-107">To replicate data, the Master Replicator (running on the Central Management Server) creates a snapshot of the changed configuration data.</span></span> <span data-ttu-id="df5a6-108">次に、このスナップショットのコピーが、Lync Server サービスまたはサーバーの役割を実行している各コンピューターに送信されます。</span><span class="sxs-lookup"><span data-stu-id="df5a6-108">A copy of this snapshot is then sent to each computer that is running Lync Server services or server roles.</span></span> <span data-ttu-id="df5a6-109">これらのコンピューターでは、レプリケーションエージェントがスナップショットを受信し、変更されたデータをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="df5a6-109">On those computers, a replication agent receives the snapshot and uploads the changed data.</span></span> <span data-ttu-id="df5a6-110">エージェントは、マスターレプリケーターを送信して、最新のレプリケーションの状態を報告するメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="df5a6-110">The agent then sends the Master Replicator a message reporting the latest replication status.</span></span>

<span data-ttu-id="df5a6-111">Get-CsManagementStoreReplicationStatus コマンドレットを使用すると、組織内の Lync Server コンピューターのレプリケーションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="df5a6-111">The Get-CsManagementStoreReplicationStatus cmdlet enables you to verify the replication status for any (or all) of the Lync Server computers in your organization.</span></span>

<span data-ttu-id="df5a6-112">このコマンドレットを実行できるユーザー</span><span class="sxs-lookup"><span data-stu-id="df5a6-112">Who can run this cmdlet?</span></span> <span data-ttu-id="df5a6-113">既定では、次のグループのメンバーが、Get-CsManagementStoreReplicationStatus コマンドレットをローカルで実行することを承認されています。 RTCUniversalUserAdmins、RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="df5a6-113">By default, members of the following groups are authorized to run the Get-CsManagementStoreReplicationStatus cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span>

<span data-ttu-id="df5a6-114">このコマンドレットが割り当てられているすべての RBAC の役割の一覧 (自分で作成したカスタムの RBAC の役割を含む) を取得するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df5a6-114">To return a list of all RBAC roles this cmdlet was assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a><span data-ttu-id="df5a6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="df5a6-115">See Also</span></span>


[<span data-ttu-id="df5a6-116">Get-csmanagementstorereplicationstatus</span><span class="sxs-lookup"><span data-stu-id="df5a6-116">Get-CsManagementStoreReplicationStatus</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

