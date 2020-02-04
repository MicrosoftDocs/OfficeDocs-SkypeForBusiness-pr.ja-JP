---
title: 'Lync Server 2013: 常設チャット サーバーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205054(v=OCS.15)
ms:contentKeyID: 48184709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3762679b8926370b85e03d0ffac2981c5c7d13a3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="2b7b6-102">Lync Server 2013 での常設チャット サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="2b7b6-102">Configure Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b7b6-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="2b7b6-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="2b7b6-104">新しい常設チャット構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="2b7b6-104">To create a new Persistent Chat configuration</span></span>

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="2b7b6-105">常設チャットの設定を取得するには</span><span class="sxs-lookup"><span data-stu-id="2b7b6-105">To get Persistent Chat configuration</span></span>

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

<span data-ttu-id="2b7b6-106">常設チャットの構成を削除するには</span><span class="sxs-lookup"><span data-stu-id="2b7b6-106">To remove Persistent Chat configuration</span></span>

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

<span data-ttu-id="2b7b6-107">常設チャットの構成を設定するには</span><span class="sxs-lookup"><span data-stu-id="2b7b6-107">To set Persistent Chat configuration</span></span>

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="2b7b6-108">Lync Server 2013 の場合、すべての web サービストラフィックは、Lync Server 2013、フロントエンドサーバーでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2b7b6-108">For Lync Server 2013, all web service traffic is supported on the Lync Server 2013, Front End Servers.</span></span> <span data-ttu-id="2b7b6-109">したがって、常設チャットサーバーの gcweb01 アドレスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2b7b6-109">Therefore, the gcweb01 address on Persistent Chat Server is not necessary.</span></span> <span data-ttu-id="2b7b6-110">内部 web サービスへのアクセスは引き続きサポートされるため、*内部*web サイト (リモートユーザー向けの*外部*web サイトではなく) にファイルアップロードとダウンロード web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="2b7b6-110">We still support internal web service access because we provide the File Upload/Download Web service to the *internal* website only (not to the *external* website for remote users).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

