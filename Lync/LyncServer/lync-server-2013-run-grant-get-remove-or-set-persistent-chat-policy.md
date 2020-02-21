---
title: 'Lync Server 2013: 常設チャットポリシーを実行、付与、取得、削除、または設定します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run, grant, get, remove, or set Persistent Chat Policy
ms:assetid: 39ccdbe8-fb3d-47bc-96e2-9486b6d317e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204810(v=OCS.15)
ms:contentKeyID: 48183857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 875e9e48bd371735c5e69b16239351e0a062d17f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-grant-get-remove-or-set-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="aaf0a-102">Lync Server 2013 での常設チャットポリシーの実行、付与、取得、削除、または設定</span><span class="sxs-lookup"><span data-stu-id="aaf0a-102">Run, grant, get, remove, or set Persistent Chat Policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aaf0a-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="aaf0a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="aaf0a-104">新しい常設チャットポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="aaf0a-104">To create a new Persistent Chat policy</span></span>

    New-CsPersistentChatPolicy -Identity <XdsIdentity> [-Enable <Switch Parameter>] [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>] [-InMemory <Switch Parameter>]

<span data-ttu-id="aaf0a-105">常設チャットポリシーを付与するには</span><span class="sxs-lookup"><span data-stu-id="aaf0a-105">To grant Persistent Chat policy</span></span>

    Grant-CsPersistentChatPolicy -Identity <UserIdParameter> -PolicyName <String> [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="aaf0a-106">常設チャットポリシーを取得するには</span><span class="sxs-lookup"><span data-stu-id="aaf0a-106">To get Persistent Chat policy</span></span>

    Get-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Filter <String>] [-LocalStore <Switch Parameter>]

<span data-ttu-id="aaf0a-107">常設チャットポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="aaf0a-107">To remove Persistent Chat policy</span></span>

    Remove-CsPersistentChatPolicy -Identity <XdsIdentity> [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="aaf0a-108">常設チャットポリシーを設定するには</span><span class="sxs-lookup"><span data-stu-id="aaf0a-108">To set Persistent Chat policy</span></span>

    Set-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Instance < PSObject>]

</div>

<span> </span>

</div>

</div>

</div>

