---
title: 構成設定のレプリケーションを検証する
description: 構成設定のレプリケーションを検証します。
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
ms.openlocfilehash: 26d8e9326da8b865f4e2ca3181975fb899300636
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552603"
---
# <a name="validate-replication-of-configuration-settings"></a><span data-ttu-id="ba9eb-103">構成設定のレプリケーションを検証する</span><span class="sxs-lookup"><span data-stu-id="ba9eb-103">Validate replication of configuration settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba9eb-104">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ba9eb-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ba9eb-105">中央管理ストアが配置されている内部コンピューターまたは Lync Server 2013 コアコンポーネントがインストールされているドメインに参加しているコンピューターで、 **get-csmanagementstorereplicationstatus** コマンドレットを2013実行することで、構成情報のエッジサーバーへのレプリケーションを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="ba9eb-105">You can validate the replication of configuration information to the Edge Server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located or any domain joined computer on which Lync Server 2013 Core Components is installed.</span></span>

<span data-ttu-id="ba9eb-106">最初の結果では、レプリケーションに関する状態が "True" ではなく "False" と示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ba9eb-106">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="ba9eb-107">その場合は、**Invoke-CsManagementStoreReplication** コマンドレットを実行し、レプリケーションが完了するのを待ってから、もう一度 **Get-CsManagementStoreReplicationStatus** コマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="ba9eb-107">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** cmdlet again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

