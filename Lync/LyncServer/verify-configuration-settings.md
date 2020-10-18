---
title: 構成の設定を確認する
description: 構成設定を確認します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7bb1135e95dafe51e906768fe0f4f0d57bf2d6c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573113"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="4989c-103">構成の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="4989c-103">Verify configuration settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4989c-104">_**トピックの最終更新日:** 2012-09-06_</span><span class="sxs-lookup"><span data-stu-id="4989c-104">_**Topic Last Modified:** 2012-09-06_</span></span>

<span data-ttu-id="4989c-105">中央管理ストアが配置されている内部コンピューターで、または Lync Server 2013 コアコンポーネント (OcsCore.msi) がインストールされているドメインに参加しているコンピューターで、Lync **server 2013 コマンド** レットを実行することで、構成情報のレプリケーションを検証できます。</span><span class="sxs-lookup"><span data-stu-id="4989c-105">You can validate the replication of configuration information to the Edge server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span>

<span data-ttu-id="4989c-106">最初の結果では、レプリケーションに関する状態が "True" ではなく "False" と示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="4989c-106">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="4989c-107">その場合、**Invoke-CsManagementStoreReplication** コマンドレットを実行し、時間をおいて、レプリケーションが完了してから再び **Get-CsManagementStoreReplicationStatus** コマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="4989c-107">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

