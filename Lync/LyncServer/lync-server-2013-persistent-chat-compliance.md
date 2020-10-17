---
title: 'Lync Server 2013: 常設チャットのコンプライアンス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat compliance
ms:assetid: 508933b6-bf17-4fb7-9147-f06ff6bc886f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204882(v=OCS.15)
ms:contentKeyID: 48184099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8255d4d2600366d63142d5c7cff2f74edff1399a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524274"
---
# <a name="persistent-chat-compliance-in-lync-server-2013"></a><span data-ttu-id="5de0d-102">Lync Server 2013 の常設チャットコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="5de0d-102">Persistent Chat compliance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5de0d-103">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="5de0d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="5de0d-104">新しい常設チャットのコンプライアンス構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="5de0d-104">To create a new Persistent Chat compliance configuration</span></span>

    New-CsPersistentChatComplianceConfiguration -Identity <XdsIdentity> [-AdapterName <String>] [-AdapterOutputDirectory <String>] [-AdapterType <String>] [-AddChatRoomDetails <$true | $false>] [-AddUserDetails <$true | $false>] [-Confirm [<Switch Parameter>]] [-CreateFileAttachmentsManifest <$true | $false>] [-CustomConfiguration <String>] [-Force <Switch Parameter>] [-InMemory <Switch Parameter>] [-OneChatRoomPerOutputFile <$true | $false>] [-RunInterval <TimeSpan>] [-WhatIf [<Switch Parameter>]]

<span data-ttu-id="5de0d-105">常設チャットのコンプライアンス構成を取得するには</span><span class="sxs-lookup"><span data-stu-id="5de0d-105">To get Persistent Chat compliance configuration</span></span>

    Get-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] [-LocalStore <Switch Parameter>]

<span data-ttu-id="5de0d-106">常設チャットのコンプライアンス構成を設定するには</span><span class="sxs-lookup"><span data-stu-id="5de0d-106">To set Persistent Chat compliance configuration</span></span>

    Set-CsPersistentChatComplianceConfiguration -Identity <XdsIdentity> [-AdapterName <String>] [-AdapterOutputDirectory <String>] [-AdapterType <String>] [-AddChatRoomDetails <$true | $false>] [-AddUserDetails <$true | $false>] [-Confirm [<Switch Parameter>]] [-CreateFileAttachmentsManifest <$true | $false>] [-CustomConfiguration <String>] [-Force <Switch Parameter>] [-InMemory <Switch Parameter>] [-OneChatRoomPerOutputFile <$true | $false>] [-RunInterval <TimeSpan>] [-WhatIf [<Switch Parameter>]]

<span data-ttu-id="5de0d-107">常設チャットのコンプライアンス構成を削除するには</span><span class="sxs-lookup"><span data-stu-id="5de0d-107">To remove Persistent Chat compliance configuration</span></span>

    Remove-CsPersistentChatComplianceConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

</div>

<span> </span>

</div>

</div>

</div>

