---
title: 'Lync Server 2013: 常設チャット サーバーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Persistent Chat Server
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205054(v=OCS.15)
ms:contentKeyID: 48184709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8ff9c59efeb2eb8106a3fe823c8256c86474f51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="bad57-102">Lync Server 2013 での常設チャット サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="bad57-102">Configure Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bad57-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="bad57-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="bad57-104">新しい常設チャット構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="bad57-104">To create a new Persistent Chat configuration</span></span>

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="bad57-105">常設チャットの設定を取得するには</span><span class="sxs-lookup"><span data-stu-id="bad57-105">To get Persistent Chat configuration</span></span>

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

<span data-ttu-id="bad57-106">常設チャットの構成を削除するには</span><span class="sxs-lookup"><span data-stu-id="bad57-106">To remove Persistent Chat configuration</span></span>

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

<span data-ttu-id="bad57-107">常設チャットの構成を設定するには</span><span class="sxs-lookup"><span data-stu-id="bad57-107">To set Persistent Chat configuration</span></span>

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="bad57-108">Lync Server 2013 の場合、すべての web サービストラフィックは、Lync Server 2013、フロントエンドサーバーでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bad57-108">For Lync Server 2013, all web service traffic is supported on the Lync Server 2013, Front End Servers.</span></span> <span data-ttu-id="bad57-109">したがって、常設チャットサーバーの gcweb01 アドレスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bad57-109">Therefore, the gcweb01 address on Persistent Chat Server is not necessary.</span></span> <span data-ttu-id="bad57-110">内部 web サービスへのアクセスは引き続きサポートされるため、*内部*web サイト (リモートユーザー向けの*外部*web サイトではなく) にファイルアップロードとダウンロード web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="bad57-110">We still support internal web service access because we provide the File Upload/Download Web service to the *internal* website only (not to the *external* website for remote users).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

