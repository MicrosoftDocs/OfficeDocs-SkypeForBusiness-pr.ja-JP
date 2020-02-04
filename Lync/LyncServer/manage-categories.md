---
title: カテゴリを管理する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage categories
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204719(v=OCS.15)
ms:contentKeyID: 48183543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bac2433702a90624e3ee4fb865bfb70b6d07d16
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-categories"></a><span data-ttu-id="5f33e-102">Manage categories</span><span class="sxs-lookup"><span data-stu-id="5f33e-102">Manage categories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f33e-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="5f33e-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="5f33e-104">新しい常設チャットサーバーカテゴリを作成するには</span><span class="sxs-lookup"><span data-stu-id="5f33e-104">To create a new Persistent Chat Server Category</span></span>

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5f33e-105">PersistentChatPoolFqdn は、常設チャットサーバープールが複数ある場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="5f33e-105">PersistentChatPoolFqdn is needed only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="5f33e-106">既存の常設チャットサーバーカテゴリを変更するには</span><span class="sxs-lookup"><span data-stu-id="5f33e-106">To make changes to existing Persistent Chat Server Category</span></span>

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

<span data-ttu-id="5f33e-107">Windows PowerShell: AllowedMembers、DeniedMembers、およびクリエーターは、同時に設定できます。</span><span class="sxs-lookup"><span data-stu-id="5f33e-107">Windows PowerShell: AllowedMembers, DeniedMembers, and Creators can be set simultaneously.</span></span> <span data-ttu-id="5f33e-108">作成者は、AllowedMembers-DeniedMembers のサブセットにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f33e-108">Creators should be the subset of AllowedMembers minus DeniedMembers.</span></span> <span data-ttu-id="5f33e-109">カテゴリのプロパティは、メンバーとクリエーターと同時に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f33e-109">You can also set the properties of a category at the same time as the members and creators.</span></span>

<div>

## <a name="create-get-set-or-remove-a-category"></a><span data-ttu-id="5f33e-110">分類を作成、取得、設定、または削除する</span><span class="sxs-lookup"><span data-stu-id="5f33e-110">Create, Get, Set, or Remove a Category</span></span>

<span data-ttu-id="5f33e-111">新しいカテゴリを作成するには</span><span class="sxs-lookup"><span data-stu-id="5f33e-111">To create a new Category</span></span>

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

<span data-ttu-id="5f33e-112">カテゴリを取得するには</span><span class="sxs-lookup"><span data-stu-id="5f33e-112">To get a Category</span></span>

    Get-CsPersistentChatCategory -Identity <String>

<span data-ttu-id="5f33e-113">または</span><span class="sxs-lookup"><span data-stu-id="5f33e-113">or</span></span>

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

<span data-ttu-id="5f33e-114">分類項目を設定するには</span><span class="sxs-lookup"><span data-stu-id="5f33e-114">To set a Category</span></span>

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="5f33e-115">または</span><span class="sxs-lookup"><span data-stu-id="5f33e-115">or</span></span>

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="5f33e-116">分類項目を削除するには</span><span class="sxs-lookup"><span data-stu-id="5f33e-116">To remove a Category</span></span>

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="5f33e-117">または</span><span class="sxs-lookup"><span data-stu-id="5f33e-117">or</span></span>

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

