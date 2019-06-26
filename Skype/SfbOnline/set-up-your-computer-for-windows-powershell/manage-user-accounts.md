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
f1keywords: None
ms.custom:
- PowerShell
description: Windows PowerShell で、組織の Skype for Business Online ユーザーに関する情報を取得するには、Windows PowerShell でユーザーの取得コマンドレットを使用します。
ms.openlocfilehash: 973529682224231e997e3900664fb5163156dfc3
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221765"
---
# <a name="manage-user-accounts"></a><span data-ttu-id="6e4c8-103">ユーザー アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="6e4c8-103">Manage user accounts</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="6e4c8-104">ユーザー アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="6e4c8-104">Manage user accounts</span></span>

<span data-ttu-id="6e4c8-105">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="6e4c8-106">すべての Lync Online ユーザーに関する情報を返す</span><span class="sxs-lookup"><span data-stu-id="6e4c8-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [<span data-ttu-id="6e4c8-107">Skype for Business Online の特定のユーザーに関する情報を返す</span><span class="sxs-lookup"><span data-stu-id="6e4c8-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [<span data-ttu-id="6e4c8-108">Skype for Business Online の特定のユーザーに固有の情報を返す</span><span class="sxs-lookup"><span data-stu-id="6e4c8-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [<span data-ttu-id="6e4c8-109">Skype for Business Online でフィルター処理されたユーザーのリストを返す</span><span class="sxs-lookup"><span data-stu-id="6e4c8-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> <span data-ttu-id="6e4c8-110">**Set-CsUser**コマンドレットは、Skype For business Online の管理者が利用できるコマンドレットのセットにも含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="6e4c8-111">ただし、 _Audiovideodisabled_パラメーターを設定する場合を除き、現在 Skype For business Online の管理には、 **Set-csuser**は使用できません。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="6e4c8-112">他のパラメーターでコマンドレットを実行しようとすると、次のようなエラーメッセージが表示されて失敗します。 "SipAddress" を設定できません。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="6e4c8-113">このパラメーターは、リモートテナント PowerShell で制限されています。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="6e4c8-114">すべての Lync Online ユーザーに関する情報を返す</span><span class="sxs-lookup"><span data-stu-id="6e4c8-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="6e4c8-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="6e4c8-115"></span></span>

<span data-ttu-id="6e4c8-116">Skype for Business Online が有効になっているすべてのユーザーに関する情報を取得するには、追加のパラメーターを指定せずに、 [Csonline ユーザー](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```
Get-CsOnlineUser
```

<span data-ttu-id="6e4c8-117">ランダムに選択された1人のユーザーに関する情報を返すには (たとえば、テスト目的でこのアカウントを使用する場合など)、" **Csonline ユーザー** " コマンドレットを呼び出し、 _resultsize_パラメーターを1に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="6e4c8-118">これにより\*\*\*\* 、組織内のユーザー数に関係なく、1人のユーザーの情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="6e4c8-119">5人のユーザーの情報を返すには、 _Resultsize_パラメーターの値を5に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="6e4c8-120">Skype for Business Online の特定のユーザーに関する情報を返す</span><span class="sxs-lookup"><span data-stu-id="6e4c8-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="6e4c8-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="6e4c8-121"></span></span>

<span data-ttu-id="6e4c8-122">[Csonline ユーザー](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットを呼び出すと、複数の方法で特定のユーザーアカウントを参照できます。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="6e4c8-123">ユーザーの Active Directory ドメインサービス (AD DS) の表示名を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="6e4c8-124">ユーザーの SIP アドレスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-124">You can use the user's SIP address.</span></span>

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="6e4c8-125">ユーザーのユーザープリンシパル名 (UPN) を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-125">You can use the user's user principal name (UPN).</span></span>

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="6e4c8-126">Skype for Business Online の特定のユーザーに固有の情報を返す</span><span class="sxs-lookup"><span data-stu-id="6e4c8-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="6e4c8-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="6e4c8-127"></span></span>

<span data-ttu-id="6e4c8-128">既定では、[ユーザーの取得](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx)コマンドレットによって、Skype For business Online のユーザーアカウントごとに膨大な量の情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-128">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="6e4c8-129">その情報の一部のみを対象としている場合は、返されるデータを**オブジェクトの選択**コマンドレットにパイプします。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="6e4c8-130">たとえば、このコマンドは、ユーザー Ken Myer のすべてのデータを返し、次に、**オブジェクトの選択**コマンドレットを使用して、表示される情報を KEN の AD DS 表示名とダイヤルプランに制限します。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="6e4c8-131">次のコマンドは、すべてのユーザーの表示名とダイヤルプランを返します。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-131">The following command returns the display name and dial plan for all your users.</span></span>

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="6e4c8-132">Skype for Business Online のユーザーアカウントのプロパティを確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="6e4c8-133">Skype for Business Online でフィルター処理されたユーザーのリストを返す</span><span class="sxs-lookup"><span data-stu-id="6e4c8-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="6e4c8-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="6e4c8-134"></span></span>

<span data-ttu-id="6e4c8-135">[ユーザーのアクセス](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットと_Ldapfilter_または_filter_パラメーターを使用することで、対象となるユーザーのセットに関する情報を簡単に返すことができます。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="6e4c8-136">たとえば、このコマンドは、財務部門で仕事をしているすべてのユーザーを返します。</span><span class="sxs-lookup"><span data-stu-id="6e4c8-136">For example, this command returns all the users who work in the Finance department.</span></span>

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="6e4c8-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6e4c8-137">Related topics</span></span>
[<span data-ttu-id="6e4c8-138">Windows PowerShell を使用して skype for business online 管理用にコンピューターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="6e4c8-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


