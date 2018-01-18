---
title: "オンラインのコネクタを使用してユーザー アカウントを管理します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: PowerShell
description: "オンライン ビジネスのユーザーに対して、組織の Skype に関する情報を取得するのには Windows PowerShell の Get CsOnlineUser コマンドレットを使用します。"
ms.openlocfilehash: 299731f811163f57f54e7e2a6c8f263f6d68de5e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="manage-user-accounts-using-the-online-connector"></a><span data-ttu-id="93d41-103">オンラインのコネクタを使用してユーザー アカウントを管理します。</span><span class="sxs-lookup"><span data-stu-id="93d41-103">Manage user accounts using the Online Connector</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="93d41-104">ユーザー アカウントを管理します。</span><span class="sxs-lookup"><span data-stu-id="93d41-104">Manage user accounts</span></span>

<span data-ttu-id="93d41-105">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="93d41-105">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="93d41-106">オンライン ビジネスのユーザーに、すべての Skype に関する情報を返す</span><span class="sxs-lookup"><span data-stu-id="93d41-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts-using-the-online-connector.md#BKAllUsers)
    
- [<span data-ttu-id="93d41-107">Skype でオンライン ビジネスの特定のユーザーに関する情報を返す</span><span class="sxs-lookup"><span data-stu-id="93d41-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)
    
- [<span data-ttu-id="93d41-108">Skype でオンライン ビジネスの特定のユーザーに固有の情報を返す</span><span class="sxs-lookup"><span data-stu-id="93d41-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)
    
- [<span data-ttu-id="93d41-109">Skype でオンライン ビジネスのユーザーのフィルター処理された一覧を返す</span><span class="sxs-lookup"><span data-stu-id="93d41-109">Return a filtered list of users in Skype for Business Online </span></span>](manage-user-accounts-using-the-online-connector.md#BKListofUsers)
    
> [!NOTE]
> <span data-ttu-id="93d41-110">**セット CsUser**コマンドレットは、管理者のオンライン ビジネスの Skype を利用可能なコマンドレットのセットにも含まれます。</span><span class="sxs-lookup"><span data-stu-id="93d41-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="93d41-111">ただし、 **csuser からのセット**は、 _AudioVideoDisabled_パラメーターを設定する以外のビジネス オンラインでは、Skype を管理するために現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="93d41-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="93d41-112">次のようなエラー メッセージで失敗、他のパラメーターを持つコマンドレットを実行しようとした場合:"SipAddress"を設定できません。</span><span class="sxs-lookup"><span data-stu-id="93d41-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="93d41-113">このパラメーターは、リモートのテナント PowerShell 内で制限されています。</span><span class="sxs-lookup"><span data-stu-id="93d41-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>
  
### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="93d41-114">すべての Lync Online ユーザーに関する情報を返す</span><span class="sxs-lookup"><span data-stu-id="93d41-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="93d41-115"><a name="BKAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="93d41-115"></span></span>

<span data-ttu-id="93d41-116">Skype のオンライン ビジネスに有効になっているすべてのユーザーに関する情報を返すには、追加パラメーターを指定せず[取得 CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="93d41-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>
  
```
Get-CsOnlineUser
```

<span data-ttu-id="93d41-117">(たとえば、テスト目的でこのアカウントを使用する場合など)、1 つのランダムに選択したユーザーの情報を取得するには、 **Get CsOnlineUser**コマンドレットを呼び出すし、 _ResultSize_パラメーターを 1 に設定します。</span><span class="sxs-lookup"><span data-stu-id="93d41-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>
  
```
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="93d41-118">組織内にあるユーザーの数に関係なく、1 つのユーザーの情報を取得する**Get CsOnlineUser**コマンドレットの原因となります。</span><span class="sxs-lookup"><span data-stu-id="93d41-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="93d41-119">5 人のユーザーの情報を返すには、 _ResultSize_パラメーターの値を 5 に設定します。</span><span class="sxs-lookup"><span data-stu-id="93d41-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>
  
```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="93d41-120">Skype でオンライン ビジネスの特定のユーザーに関する情報を返す</span><span class="sxs-lookup"><span data-stu-id="93d41-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="93d41-121"><a name="BKSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="93d41-121"></span></span>

<span data-ttu-id="93d41-122">[Get CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットを呼び出すときに特定のユーザー アカウントを参照する複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="93d41-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="93d41-123">ユーザーの Active Directory ドメイン サービス (AD DS) の表示名を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="93d41-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="93d41-124">ユーザーの SIP アドレスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="93d41-124">You can use the user's SIP address.</span></span>
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="93d41-125">ユーザーのユーザー プリンシパル名 (UPN) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="93d41-125">You can use the user's user principal name (UPN).</span></span>
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="93d41-126">Skype でオンライン ビジネスの特定のユーザーに固有の情報を返す</span><span class="sxs-lookup"><span data-stu-id="93d41-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="93d41-127"><a name="BKSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="93d41-127"></span></span>

<span data-ttu-id="93d41-128">既定では、 [Get CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx)コマンドレットは、膨大なオンライン ビジネスのユーザー アカウントの各 Skype の情報を返します。</span><span class="sxs-lookup"><span data-stu-id="93d41-128">By default, the [Get-CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="93d41-129">情報のサブセットのみに関心がある場合は、返されたデータを**Select-object**コマンドレットをパイプします。</span><span class="sxs-lookup"><span data-stu-id="93d41-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="93d41-130">たとえば、このコマンドを返します Ken Myer のユーザーとし、情報を制限する**Select-object**コマンドレットが表示される使用のすべてのデータ画面に表示される Ken の AD DS の表示名] と [ダイヤル プランにします。</span><span class="sxs-lookup"><span data-stu-id="93d41-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="93d41-131">次のコマンドでは、[表示名] と [ダイヤルの計画のすべてのユーザーを返します。</span><span class="sxs-lookup"><span data-stu-id="93d41-131">The following command returns the display name and dial plan for all your users.</span></span>
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="93d41-132">オンライン ビジネスのユーザー アカウントの Skype のプロパティを検索するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="93d41-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>
  
```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="93d41-133">Skype でオンライン ビジネスのユーザーのフィルター処理された一覧を返す</span><span class="sxs-lookup"><span data-stu-id="93d41-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="93d41-134"><a name="BKListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="93d41-134"></span></span>

<span data-ttu-id="93d41-135">[Get CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットと、 _LdapFilter_パラメーターまたは_フィルター_パラメーターを使用すると、対象となる一連のユーザーに関する情報を簡単に戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="93d41-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="93d41-136">たとえば、このコマンドは、財務部門で働くすべてのユーザーを返します。</span><span class="sxs-lookup"><span data-stu-id="93d41-136">For example, this command returns all the users who work in the Finance department.</span></span>
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="93d41-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="93d41-137">Related topics</span></span>
[<span data-ttu-id="93d41-138">Windows PowerShell を使用してビジネスのオンライン管理のための skype には、コンピューターを設定します</span><span class="sxs-lookup"><span data-stu-id="93d41-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
