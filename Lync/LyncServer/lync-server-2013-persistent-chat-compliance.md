---
title: 'Lync Server 2013: 常設チャット コンプライアンス'
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
ms.openlocfilehash: bca8bec32c846d5d3c5defe87e4ebfe526dc5f63
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-compliance-in-lync-server-2013"></a><span data-ttu-id="93bfb-102">Lync Server 2013 の常設チャット コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="93bfb-102">Persistent Chat compliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93bfb-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="93bfb-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="93bfb-104">新しい常設チャットのコンプライアンス構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="93bfb-104">To create a new Persistent Chat compliance configuration</span></span>

    New-CsPersistentChatComplianceConfiguration -Identity <XdsIdentity> [-AdapterName <String>] [-AdapterOutputDirectory <String>] [-AdapterType <String>] [-AddChatRoomDetails <$true | $false>] [-AddUserDetails <$true | $false>] [-Confirm [<Switch Parameter>]] [-CreateFileAttachmentsManifest <$true | $false>] [-CustomConfiguration <String>] [-Force <Switch Parameter>] [-InMemory <Switch Parameter>] [-OneChatRoomPerOutputFile <$true | $false>] [-RunInterval <TimeSpan>] [-WhatIf [<Switch Parameter>]]

<span data-ttu-id="93bfb-105">常設チャットのコンプライアンス構成を取得するには</span><span class="sxs-lookup"><span data-stu-id="93bfb-105">To get Persistent Chat compliance configuration</span></span>

    Get-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] [-LocalStore <Switch Parameter>]

<span data-ttu-id="93bfb-106">常設チャットのコンプライアンス構成を設定するには</span><span class="sxs-lookup"><span data-stu-id="93bfb-106">To set Persistent Chat compliance configuration</span></span>

    Set-CsPersistentChatComplianceConfiguration -Identity <XdsIdentity> [-AdapterName <String>] [-AdapterOutputDirectory <String>] [-AdapterType <String>] [-AddChatRoomDetails <$true | $false>] [-AddUserDetails <$true | $false>] [-Confirm [<Switch Parameter>]] [-CreateFileAttachmentsManifest <$true | $false>] [-CustomConfiguration <String>] [-Force <Switch Parameter>] [-InMemory <Switch Parameter>] [-OneChatRoomPerOutputFile <$true | $false>] [-RunInterval <TimeSpan>] [-WhatIf [<Switch Parameter>]]

<span data-ttu-id="93bfb-107">常設チャットのコンプライアンス構成を削除するには</span><span class="sxs-lookup"><span data-stu-id="93bfb-107">To remove Persistent Chat compliance configuration</span></span>

    Remove-CsPersistentChatComplianceConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

</div>

<span> </span>

</div>

</div>

</div>

