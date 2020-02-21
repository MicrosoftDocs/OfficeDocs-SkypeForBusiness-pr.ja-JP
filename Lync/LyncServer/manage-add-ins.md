---
title: アドインの管理
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage add-ins
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205193(v=OCS.15)
ms:contentKeyID: 48185204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 465f71a8221ce273574c5cf602146272b34f0cf7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-add-ins"></a><span data-ttu-id="3d0d7-102">アドインの管理</span><span class="sxs-lookup"><span data-stu-id="3d0d7-102">Manage add-ins</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d0d7-103">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="3d0d7-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="3d0d7-104">新しい常設チャットサーバーアドインを作成するには</span><span class="sxs-lookup"><span data-stu-id="3d0d7-104">To create a new Persistent Chat Server Add-in</span></span>

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

<div>

## <a name="create-get-set-or-remove-an-add-in"></a><span data-ttu-id="3d0d7-105">アドインの作成、取得、設定、削除</span><span class="sxs-lookup"><span data-stu-id="3d0d7-105">Create, Get, Set, or Remove an Add-in</span></span>

<span data-ttu-id="3d0d7-106">新しいアドインを作成するには</span><span class="sxs-lookup"><span data-stu-id="3d0d7-106">To create a new Add-in</span></span>

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3d0d7-107">PersistentChatPoolFqdn &lt;文字列&gt;は、複数の常設チャットサーバープールが存在する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="3d0d7-107">PersistentChatPoolFqdn &lt;String&gt; is required only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="3d0d7-108">アドインを取得するには</span><span class="sxs-lookup"><span data-stu-id="3d0d7-108">To get an Add-in</span></span>

    Get-CsPersistentChatAddin -Identity <String>]

<span data-ttu-id="3d0d7-109">または</span><span class="sxs-lookup"><span data-stu-id="3d0d7-109">or</span></span>

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

<span data-ttu-id="3d0d7-110">アドインを設定するには</span><span class="sxs-lookup"><span data-stu-id="3d0d7-110">To set an Add-in</span></span>

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="3d0d7-111">または</span><span class="sxs-lookup"><span data-stu-id="3d0d7-111">or</span></span>

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="3d0d7-112">アドインを削除するには</span><span class="sxs-lookup"><span data-stu-id="3d0d7-112">To remove an Add-in</span></span>

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="3d0d7-113">または</span><span class="sxs-lookup"><span data-stu-id="3d0d7-113">or</span></span>

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

