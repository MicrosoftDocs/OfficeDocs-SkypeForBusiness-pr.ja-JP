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
ms.openlocfilehash: 8165781f9604b84f5b846ebda8679f9110262b88
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a><span data-ttu-id="82b8a-102">Lync Server 2013 の内部サーバーとエッジサーバーの間の接続を確認する</span><span class="sxs-lookup"><span data-stu-id="82b8a-102">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82b8a-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="82b8a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="82b8a-104">Lync Server 2013 では、エッジサーバーと内部サーバー間の接続を検証するために別の検証ウィザードを使用できました。</span><span class="sxs-lookup"><span data-stu-id="82b8a-104">In Lync Server 2013, a separate validation wizard was available to help validate connectivity between Edge Servers and internal servers.</span></span> <span data-ttu-id="82b8a-105">Lync Server 2013 接続の検証は、エッジサーバーをインストールすると自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="82b8a-105">In Lync Server 2013 validation of connectivity is done automatically when you install your Edge Servers.</span></span>

<span data-ttu-id="82b8a-106">中央管理ストアが配置されている内部コンピューターで Windows PowerShell **get-csmanagementstorereplicationstatus**コマンドレットを実行することによって、構成情報のエッジへのレプリケーションを検証できます (または、Lync Server 2013 コアコンポーネント (ocscore) がインストールされているドメインに参加しているコンピューター)。</span><span class="sxs-lookup"><span data-stu-id="82b8a-106">You can validate the replication of configuration information to the edge by running the Windows PowerShell **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located (or any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span> <span data-ttu-id="82b8a-107">最初の結果では、レプリケーションに関する状態が "True" ではなく "False" と示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="82b8a-107">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="82b8a-108">その場合は、**Invoke-CsManagementStoreReplication** コマンドレットを実行し、レプリケーションが完了するまでしばらく時間を置いてから、再び **Get-CsManagementStoreReplicationStatus** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="82b8a-108">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

<span data-ttu-id="82b8a-109">リモート ユーザー接続の確認のための Office Communications Server リモート接続アナライザーの利用も含め、外部ユーザー接続を別々に確認することができます。</span><span class="sxs-lookup"><span data-stu-id="82b8a-109">You can verify external user connectivity separately, including using the Office Communications Server Remote Connectivity Analyzer to verify remote user connectivity.</span></span> <span data-ttu-id="82b8a-110">詳細については、「 [Lync Server 2013 で外部ユーザーの接続を確認する](lync-server-2013-verify-connectivity-for-external-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82b8a-110">For details, see [Verify connectivity for external users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

