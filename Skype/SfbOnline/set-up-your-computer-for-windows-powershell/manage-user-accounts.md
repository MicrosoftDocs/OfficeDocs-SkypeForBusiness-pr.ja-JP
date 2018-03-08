---
title: "ユーザー アカウントを管理します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: "Windows PowerShell で情報を取得する組織の Skype for Business Online ユーザー Get CsOnlineUser コマンドレットを使用します。"
ms.openlocfilehash: f51f2c1f723a26bfa3a815bfe7641b68c5d23b26
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="manage-user-accounts"></a><span data-ttu-id="b5232-103">ユーザー アカウントを管理します。</span><span class="sxs-lookup"><span data-stu-id="b5232-103">Manage user accounts</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="b5232-104">ユーザー アカウントを管理します。</span><span class="sxs-lookup"><span data-stu-id="b5232-104">Manage user accounts</span></span>

<span data-ttu-id="b5232-105">このトピックには、次のセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b5232-105">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="b5232-106">すべて Skype for Business Online ユーザーに関する情報を返す</span><span class="sxs-lookup"><span data-stu-id="b5232-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)
    
- [<span data-ttu-id="b5232-107">Skype for Business Online の特定のユーザーに関する情報を返す</span><span class="sxs-lookup"><span data-stu-id="b5232-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)
    
- [<span data-ttu-id="b5232-108">Skype for Business Online の特定のユーザーの特定の情報を返す</span><span class="sxs-lookup"><span data-stu-id="b5232-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)
    
- [<span data-ttu-id="b5232-109">Skype for Business Online ユーザーのフィルターが適用されたリストを返します</span><span class="sxs-lookup"><span data-stu-id="b5232-109">Return a filtered list of users in Skype for Business Online </span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)
    
> [!NOTE]
> <span data-ttu-id="b5232-p101">**セット CsUser**コマンドレットは Skype for Business Online の管理者できるコマンドレットのセットにも含まれます。ただし、**セット CsUser**は for Business Online では、Skype を管理する_AudioVideoDisabled_パラメーターを設定する以外に現在使用できません。その他のすべてのパラメーターを使用して、コマンドレットを実行しようとする場合は、次のようなエラー メッセージが失敗:"SipAddress"を設定できません。このパラメーターは、テナントのリモート PowerShell 内で制限されています。</span><span class="sxs-lookup"><span data-stu-id="b5232-p101">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins. However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter. If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress". This parameter is restricted within Remote Tenant PowerShell.</span></span>
  
### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="b5232-114">すべて Skype for Business Online ユーザーに関する情報を返す</span><span class="sxs-lookup"><span data-stu-id="b5232-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="b5232-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="b5232-115"></span></span>

<span data-ttu-id="b5232-116">Skype for Business Online 有効になっているすべてのユーザーに関する情報を取得するには、パラメーターを追加せずに[取得 CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b5232-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>
  
```
Get-CsOnlineUser
```

<span data-ttu-id="b5232-117">1 つ、ランダムに選択したユーザー (たとえば、テスト用の現在のアカウントを使用する場合など) の情報を取得するにはするには、 **Get CsOnlineUser**コマンドレットを_ResultSize_パラメーターが 1 に設定します。</span><span class="sxs-lookup"><span data-stu-id="b5232-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>
  
```
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="b5232-p102">ある、組織のユーザーの数に関係なく、1 つのユーザーの情報を取得する**Get CsOnlineUser**コマンドレットの原因となります。5 人のユーザーの情報を返すには、5 _ResultSize_パラメーターの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="b5232-p102">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization. To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>
  
```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="b5232-120">Skype for Business Online の特定のユーザーに関する情報を返す</span><span class="sxs-lookup"><span data-stu-id="b5232-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="b5232-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="b5232-121"></span></span>

<span data-ttu-id="b5232-p103">[Get CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットの通話する際に、特定のユーザー アカウントを参照する複数の方法があります。ユーザーの Active Directory ドメイン サービス (AD DS) の表示名を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b5232-p103">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet. You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="b5232-124">ユーザーの SIP アドレスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b5232-124">You can use the user's SIP address.</span></span>
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="b5232-125">ユーザーのユーザー プリンシパル名 (UPN) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b5232-125">You can use the user's user principal name (UPN).</span></span>
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="b5232-126">Skype for Business Online の特定のユーザーの特定の情報を返す</span><span class="sxs-lookup"><span data-stu-id="b5232-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="b5232-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="b5232-127"></span></span>

<span data-ttu-id="b5232-p104">既定では、 [Get CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx)コマンドレットは、大量の各の Skype for Business Online のユーザー アカウントの情報を返します。関心の情報の一部のみの場合は、パイプの返されるデータ**のコマンドレット**を実行します。たとえば、このコマンドすべてのデータを返します青木 Myer の場合は、[ユーザーと関数を使用して**、コマンドレットの情報を制限するのに**は表示し、画面に表示される青木の AD DS の表示名とダイヤル プランにします。</span><span class="sxs-lookup"><span data-stu-id="b5232-p104">By default, the [Get-CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account. If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet. For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="b5232-131">次のコマンドは、すべてのユーザーの表示名とダイヤルの計画を返します。</span><span class="sxs-lookup"><span data-stu-id="b5232-131">The following command returns the display name and dial plan for all your users.</span></span>
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="b5232-132">Business Online のユーザー アカウントの Skype のプロパティを検索するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5232-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>
  
```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="b5232-133">Skype for Business Online ユーザーのフィルターが適用されたリストを返します</span><span class="sxs-lookup"><span data-stu-id="b5232-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="b5232-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="b5232-134"></span></span>

<span data-ttu-id="b5232-p105">[Get CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットとパラメーター _LdapFilter_または_フィルター_を使用すると、ユーザーの対象となるセットに関する情報を簡単に戻ることができます。たとえば、このコマンドは、財務部で作業しているすべてのユーザーを返します。</span><span class="sxs-lookup"><span data-stu-id="b5232-p105">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users. For example, this command returns all the users who work in the Finance department.</span></span>
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="b5232-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b5232-137">Related topics</span></span>
[<span data-ttu-id="b5232-138">Skype for business online 管理の Windows PowerShell を使用して、コンピューターを設定します。</span><span class="sxs-lookup"><span data-stu-id="b5232-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
