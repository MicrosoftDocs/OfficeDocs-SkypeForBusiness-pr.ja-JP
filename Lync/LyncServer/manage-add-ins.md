---
title: アドインの管理
description: アドインを管理します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Manage add-ins
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205193(v=OCS.15)
ms:contentKeyID: 48185204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2f381e73d8da33e1347ccc81e7b0d98270827d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545943"
---
# <a name="manage-add-ins"></a><span data-ttu-id="096a7-103">アドインの管理</span><span class="sxs-lookup"><span data-stu-id="096a7-103">Manage add-ins</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="096a7-104">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="096a7-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="096a7-105">新しい常設チャットサーバーアドインを作成するには</span><span class="sxs-lookup"><span data-stu-id="096a7-105">To create a new Persistent Chat Server Add-in</span></span>

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

<div>

## <a name="create-get-set-or-remove-an-add-in"></a><span data-ttu-id="096a7-106">アドインの作成、取得、設定、削除</span><span class="sxs-lookup"><span data-stu-id="096a7-106">Create, Get, Set, or Remove an Add-in</span></span>

<span data-ttu-id="096a7-107">新しいアドインを作成するには</span><span class="sxs-lookup"><span data-stu-id="096a7-107">To create a new Add-in</span></span>

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="096a7-108">PersistentChatPoolFqdn &lt; 文字列 &gt; は、複数の常設チャットサーバープールが存在する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="096a7-108">PersistentChatPoolFqdn &lt;String&gt; is required only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="096a7-109">アドインを取得するには</span><span class="sxs-lookup"><span data-stu-id="096a7-109">To get an Add-in</span></span>

    Get-CsPersistentChatAddin -Identity <String>]

<span data-ttu-id="096a7-110">または</span><span class="sxs-lookup"><span data-stu-id="096a7-110">or</span></span>

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

<span data-ttu-id="096a7-111">アドインを設定するには</span><span class="sxs-lookup"><span data-stu-id="096a7-111">To set an Add-in</span></span>

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="096a7-112">または</span><span class="sxs-lookup"><span data-stu-id="096a7-112">or</span></span>

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="096a7-113">アドインを削除するには</span><span class="sxs-lookup"><span data-stu-id="096a7-113">To remove an Add-in</span></span>

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="096a7-114">または</span><span class="sxs-lookup"><span data-stu-id="096a7-114">or</span></span>

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

