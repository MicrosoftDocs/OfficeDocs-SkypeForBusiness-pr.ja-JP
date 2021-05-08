---
title: ユーザー アカウントを管理する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 組織の Get-CsOnlineUser Online Windows PowerShellに関する情報を取得するには、Skype for Business コマンドレットを使用します。
ms.openlocfilehash: aec79f589f6b1fb0c9d38fd4bc70421b30f66a56
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238723"
---
# <a name="manage-user-accounts"></a><span data-ttu-id="10ccb-103">ユーザー アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="10ccb-103">Manage user accounts</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="manage-user-accounts"></a><span data-ttu-id="10ccb-104">ユーザー アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="10ccb-104">Manage user accounts</span></span>

<span data-ttu-id="10ccb-105">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="10ccb-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="10ccb-106">すべての Lync Online ユーザーに関する情報を返す</span><span class="sxs-lookup"><span data-stu-id="10ccb-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [<span data-ttu-id="10ccb-107">Skype for Business Online で特定のユーザーの情報を返す</span><span class="sxs-lookup"><span data-stu-id="10ccb-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [<span data-ttu-id="10ccb-108">Skype for Business Online で特定のユーザーの特定の情報を返す</span><span class="sxs-lookup"><span data-stu-id="10ccb-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [<span data-ttu-id="10ccb-109">Skype for Business Online でフィルター処理されたユーザーの一覧を返す</span><span class="sxs-lookup"><span data-stu-id="10ccb-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> <span data-ttu-id="10ccb-110">**Set-CsUser コマンドレット** は、オンライン管理者が使用できる一連のコマンドレットSkype for Business含まれています。</span><span class="sxs-lookup"><span data-stu-id="10ccb-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="10ccb-111">ただし **、Set-CsUser** は現在 _、AudioVideoDisabled_ パラメーターを設定する場合を除き、Skype for Business Online の管理に使用できません。</span><span class="sxs-lookup"><span data-stu-id="10ccb-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="10ccb-112">他のパラメーターを指定してコマンドレットを実行しようとすると、"SipAddress" を設定できません。</span><span class="sxs-lookup"><span data-stu-id="10ccb-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="10ccb-113">このパラメーターは、リモート テナント PowerShell 内で制限されます。</span><span class="sxs-lookup"><span data-stu-id="10ccb-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="10ccb-114">すべての Lync Online ユーザーに関する情報を返す</span><span class="sxs-lookup"><span data-stu-id="10ccb-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="10ccb-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="10ccb-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span></span>

<span data-ttu-id="10ccb-116">Skype for Business Online を有効にしているすべてのユーザーに関する情報を返す場合は、追加のパラメーターを指定せずに[Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="10ccb-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="10ccb-117">ランダムに選択された 1 人のユーザー (たとえば、このアカウントをテスト目的で使用する場合) の情報を返す場合は **、Get-CsOnlineUser** コマンドレットを呼び出し _、ResultSize_ パラメーターを 1 に設定します。</span><span class="sxs-lookup"><span data-stu-id="10ccb-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="10ccb-118">このため **、Get-CsOnlineUser** コマンドレットは、組織内のユーザー数に関係なく、1 人のユーザーについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="10ccb-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="10ccb-119">5 人のユーザーの情報を返す場合は _、ResultSize パラメーターの値_ を 5 に設定します。</span><span class="sxs-lookup"><span data-stu-id="10ccb-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="10ccb-120">Skype for Business Online で特定のユーザーの情報を返す</span><span class="sxs-lookup"><span data-stu-id="10ccb-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="10ccb-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="10ccb-121"><a name="BKMKReturnInfoSpecificUser"> </a></span></span>

<span data-ttu-id="10ccb-122">[Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)コマンドレットを呼び出す場合、特定のユーザー アカウントを参照する方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="10ccb-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet.</span></span> <span data-ttu-id="10ccb-123">ユーザーの Active Directory Domain Services (AD DS) の表示名を使用できます。</span><span class="sxs-lookup"><span data-stu-id="10ccb-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="10ccb-124">ユーザーの SIP アドレスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="10ccb-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="10ccb-125">ユーザーのユーザー プリンシパル名 (UPN) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="10ccb-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="10ccb-126">Skype for Business Online で特定のユーザーの特定の情報を返す</span><span class="sxs-lookup"><span data-stu-id="10ccb-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="10ccb-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="10ccb-127"><a name="BKMKReturninfoSpecificUsers"> </a></span></span>

<span data-ttu-id="10ccb-128">既定では[、Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)コマンドレットは、オンライン ユーザー アカウントの各ユーザー Skype for Business情報を返します。</span><span class="sxs-lookup"><span data-stu-id="10ccb-128">By default, the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="10ccb-129">その情報のサブセットのみを使用する場合は、返されたデータを **Select-Object コマンドレットにパイプします** 。</span><span class="sxs-lookup"><span data-stu-id="10ccb-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="10ccb-130">たとえば、このコマンドはユーザー Ken Myer のすべてのデータを返し **、Select-Object** コマンドレットを使用して、Ken の AD DS 表示名とダイヤル プランに画面に表示される情報を制限します。</span><span class="sxs-lookup"><span data-stu-id="10ccb-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="10ccb-131">次のコマンドは、すべてのユーザーの表示名とダイヤル プランを返します。</span><span class="sxs-lookup"><span data-stu-id="10ccb-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="10ccb-132">Skype for Business Online ユーザー アカウントのプロパティを検索するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="10ccb-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="10ccb-133">Skype for Business Online でフィルター処理されたユーザーの一覧を返す</span><span class="sxs-lookup"><span data-stu-id="10ccb-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="10ccb-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="10ccb-134"><a name="BKMKReturnFilteredListofUsers"> </a></span></span>

<span data-ttu-id="10ccb-135">[Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)コマンドレットと _LdapFilter_ または _Filter_ パラメーターを使用すると、対象ユーザーのセットに関する情報を簡単に返すことができます。</span><span class="sxs-lookup"><span data-stu-id="10ccb-135">By using the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="10ccb-136">たとえば、このコマンドは財務部門で働くすべてのユーザーを返します。</span><span class="sxs-lookup"><span data-stu-id="10ccb-136">For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="10ccb-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="10ccb-137">Related topics</span></span>
[<span data-ttu-id="10ccb-138">Skype for Business Online 管理用にコンピューターをセットアップするには、Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="10ccb-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
