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
description: Windows PowerShell で、組織の Skype for Business Online ユーザーに関する情報を取得するには、Windows PowerShell でユーザーの取得コマンドレットを使用します。
ms.openlocfilehash: 97d717d3472ae96dc66ad58ee5699f3f646a0f3b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706242"
---
# <a name="manage-user-accounts"></a>ユーザー アカウントを管理する

## <a name="manage-user-accounts"></a>ユーザー アカウントを管理する

このトピックには次のセクションが含まれます。

- [すべての Lync Online ユーザーに関する情報を返す](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [Skype for Business Online の特定のユーザーに関する情報を返す](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [Skype for Business Online の特定のユーザーに固有の情報を返す](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [Skype for Business Online でフィルター処理されたユーザーのリストを返す](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> **Set-CsUser**コマンドレットは、Skype For business Online の管理者が利用できるコマンドレットのセットにも含まれています。 ただし、 _Audiovideodisabled_パラメーターを設定する場合を除き、現在 Skype For business Online の管理には、 **Set-csuser**は使用できません。 他のパラメーターでコマンドレットを実行しようとすると、次のようなエラーメッセージが表示されて失敗します。 "SipAddress" を設定できません。 このパラメーターは、リモートテナント PowerShell で制限されています。

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>すべての Lync Online ユーザーに関する情報を返す
<a name="BKMKReturnInfoAboutAllUsers"> </a>

Skype for Business Online が有効になっているすべてのユーザーに関する情報を取得するには、追加のパラメーターを指定せずに、 [Csonline ユーザー](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットを呼び出します。

```PowerShell
Get-CsOnlineUser
```

ランダムに選択された1人のユーザーに関する情報を返すには (たとえば、テスト目的でこのアカウントを使用する場合など)、" **Csonline ユーザー** " コマンドレットを呼び出し、 _resultsize_パラメーターを1に設定します。

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

これにより **、組織**内のユーザー数に関係なく、1人のユーザーの情報が返されます。 5人のユーザーの情報を返すには、 _Resultsize_パラメーターの値を5に設定します。

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Skype for Business Online の特定のユーザーに関する情報を返す
<a name="BKMKReturnInfoSpecificUser"> </a>

[Csonline ユーザー](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットを呼び出すと、複数の方法で特定のユーザーアカウントを参照できます。 ユーザーの Active Directory ドメインサービス (AD DS) の表示名を使用できます。

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

ユーザーの SIP アドレスを使用できます。

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

ユーザーのユーザープリンシパル名 (UPN) を使うことができます。

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Skype for Business Online の特定のユーザーに固有の情報を返す
<a name="BKMKReturninfoSpecificUsers"> </a>

既定では、[ユーザーの取得](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx)コマンドレットによって、Skype For business Online のユーザーアカウントごとに膨大な量の情報が返されます。 その情報の一部のみを対象としている場合は、返されるデータを**オブジェクトの選択**コマンドレットにパイプします。 たとえば、このコマンドは、ユーザー Ken Myer のすべてのデータを返し、次に、**オブジェクトの選択**コマンドレットを使用して、表示される情報を KEN の AD DS 表示名とダイヤルプランに制限します。

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

次のコマンドは、すべてのユーザーの表示名とダイヤルプランを返します。

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Skype for Business Online のユーザーアカウントのプロパティを確認するには、次のコマンドを使用します。

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Skype for Business Online でフィルター処理されたユーザーのリストを返す
<a name="BKMKReturnFilteredListofUsers"> </a>

[ユーザーのアクセス](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットと_Ldapfilter_または_filter_パラメーターを使用することで、対象となるユーザーのセットに関する情報を簡単に返すことができます。 たとえば、このコマンドは、財務部門で仕事をしているすべてのユーザーを返します。

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>関連トピック
[Windows PowerShell を使用して skype for business online 管理用にコンピューターをセットアップする](set-up-your-computer-for-windows-powershell.md)


