---
title: カテゴリを管理する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Manage categories
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204719(v=OCS.15)
ms:contentKeyID: 48183543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6942346156b3dcd8999c4a2c3ada02328c68dccf
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-categories"></a><span data-ttu-id="82fc6-102">カテゴリを管理する</span><span class="sxs-lookup"><span data-stu-id="82fc6-102">Manage categories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82fc6-103">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="82fc6-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="82fc6-104">新しい常設チャットサーバーカテゴリを作成するには</span><span class="sxs-lookup"><span data-stu-id="82fc6-104">To create a new Persistent Chat Server Category</span></span>

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="82fc6-105">PersistentChatPoolFqdn は、複数の常設チャットサーバープールがある場合にのみ必要になります。</span><span class="sxs-lookup"><span data-stu-id="82fc6-105">PersistentChatPoolFqdn is needed only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="82fc6-106">既存の常設チャットサーバーカテゴリに変更を加えるには</span><span class="sxs-lookup"><span data-stu-id="82fc6-106">To make changes to existing Persistent Chat Server Category</span></span>

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

<span data-ttu-id="82fc6-107">Windows PowerShell: AllowedMembers、DeniedMembers、およびクリエーターを同時に設定できます。</span><span class="sxs-lookup"><span data-stu-id="82fc6-107">Windows PowerShell: AllowedMembers, DeniedMembers, and Creators can be set simultaneously.</span></span> <span data-ttu-id="82fc6-108">Creators は、AllowedMembers から DeniedMembers を引いたもののサブセットである必要があります。</span><span class="sxs-lookup"><span data-stu-id="82fc6-108">Creators should be the subset of AllowedMembers minus DeniedMembers.</span></span> <span data-ttu-id="82fc6-109">メンバーおよび作成者と同時にカテゴリのプロパティも設定できます。</span><span class="sxs-lookup"><span data-stu-id="82fc6-109">You can also set the properties of a category at the same time as the members and creators.</span></span>

<div>

## <a name="create-get-set-or-remove-a-category"></a><span data-ttu-id="82fc6-110">カテゴリの作成、取得、設定、または削除</span><span class="sxs-lookup"><span data-stu-id="82fc6-110">Create, Get, Set, or Remove a Category</span></span>

<span data-ttu-id="82fc6-111">新しいカテゴリを作成するには</span><span class="sxs-lookup"><span data-stu-id="82fc6-111">To create a new Category</span></span>

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

<span data-ttu-id="82fc6-112">カテゴリを取得するには</span><span class="sxs-lookup"><span data-stu-id="82fc6-112">To get a Category</span></span>

    Get-CsPersistentChatCategory -Identity <String>

<span data-ttu-id="82fc6-113">または</span><span class="sxs-lookup"><span data-stu-id="82fc6-113">or</span></span>

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

<span data-ttu-id="82fc6-114">カテゴリを設定するには</span><span class="sxs-lookup"><span data-stu-id="82fc6-114">To set a Category</span></span>

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="82fc6-115">または</span><span class="sxs-lookup"><span data-stu-id="82fc6-115">or</span></span>

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="82fc6-116">カテゴリを削除するには</span><span class="sxs-lookup"><span data-stu-id="82fc6-116">To remove a Category</span></span>

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="82fc6-117">または</span><span class="sxs-lookup"><span data-stu-id="82fc6-117">or</span></span>

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

