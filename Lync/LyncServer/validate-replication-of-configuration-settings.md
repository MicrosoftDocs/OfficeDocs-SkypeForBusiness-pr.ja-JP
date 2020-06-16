---
title: 構成設定のレプリケーションを検証する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf08d920983ef4463f9e8236f6c9e458f120074b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a><span data-ttu-id="49d70-102">構成設定のレプリケーションを検証する</span><span class="sxs-lookup"><span data-stu-id="49d70-102">Validate replication of configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49d70-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="49d70-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="49d70-104">中央管理ストアが配置されている内部コンピューターまたは Lync Server 2013 コアコンポーネントがインストールされているドメインに参加しているコンピューターで、 **get-csmanagementstorereplicationstatus**コマンドレットを2013実行することで、構成情報のエッジサーバーへのレプリケーションを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="49d70-104">You can validate the replication of configuration information to the Edge Server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located or any domain joined computer on which Lync Server 2013 Core Components is installed.</span></span>

<span data-ttu-id="49d70-105">最初の結果では、レプリケーションに関する状態が "True" ではなく "False" と示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="49d70-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="49d70-106">その場合は、**Invoke-CsManagementStoreReplication** コマンドレットを実行し、レプリケーションが完了するのを待ってから、もう一度 **Get-CsManagementStoreReplicationStatus** コマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="49d70-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** cmdlet again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

