---
title: Online Connector を使用してユーザー アカウントを管理する
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
description: 組織の skype for Business Online Get-CsOnlineUserに関する情報をWindows PowerShell、このコマンドレットを使用します。
ms.openlocfilehash: bdf1d445fa7c0a9ac4f874e0983b8ab7e8cb19e1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113173"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>Online Connector を使用してユーザー アカウントを管理する

## <a name="manage-user-accounts"></a>ユーザー アカウントを管理する

このトピックには次のセクションが含まれます。

- [すべての Lync Online ユーザーに関する情報を返す](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [Skype for Business Online で特定のユーザーの情報を返す](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [Skype for Business Online で特定のユーザーに関する特定の情報を返す](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [Skype for Business Online でフィルター処理されたユーザーのリストを返す](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> **Set-CsUser コマンドレット** は、Skype for Business Online 管理者が使用できる一連のコマンドレットにも含まれています。 ただし、 **現在、Set-CsUser** は _AudioVideoDisabled_ パラメーターを設定する以外は、Skype for Business Online の管理に使用できません。 他のパラメーターでコマンドレットを実行しようとすると、"SipAddress" を設定できません。 このパラメーターは、リモート テナント PowerShell 内で制限されます。

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>すべての Lync Online ユーザーに関する情報を返す
<a name="BKAllUsers"> </a>

Skype for Business Online が有効になっているすべてのユーザーに関する情報を返す場合は、追加のパラメーターなしで [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) コマンドレットを呼び出します。

```PowerShell
Get-CsOnlineUser
```

ランダムに選択された 1 人のユーザーの情報を返す場合 (たとえば、このアカウントをテスト目的で使用する場合 **)、Get-CsOnlineUser** コマンドレットを呼び出し _、ResultSize_ パラメーターを 1 に設定します。

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

この場合、組織内のユーザー数に関係なく **、Get-CsOnlineUser** コマンドレットは 1 人のユーザーの情報を返します。 5 人のユーザーの情報を返す場合は _、ResultSize パラメーターの値_ を 5 に設定します。

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Skype for Business Online で特定のユーザーの情報を返す
<a name="BKSpecificUser"> </a>

[Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)コマンドレットを呼び出す場合、特定のユーザー アカウントを参照する方法は複数あります。 ユーザーの Active Directory ドメイン サービス (AD DS) の表示名を使用できます。

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

ユーザーの SIP アドレスを使用できます。

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

ユーザーのユーザー プリンシパル名 (UPN) を使用できます。

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Skype for Business Online で特定のユーザーに関する特定の情報を返す
<a name="BKSpecificUsers"> </a>

既定では [、Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) コマンドレットは、Skype for Business Online ユーザー アカウントごとに大量の情報を返します。 その情報のサブセットのみを使用する場合は、返されたデータを **Select-Object コマンドレットにパイプします** 。 たとえば、このコマンドはユーザー Ken Myer のすべてのデータを返し **、Select-Object** コマンドレットを使用して、画面に表示される情報を Ken の AD DS の表示名とダイヤル プランに制限します。

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

次のコマンドは、すべてのユーザーの表示名とダイヤル プランを返します。

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Skype for Business Online ユーザー アカウントのプロパティを見つけるには、次のコマンドを使用します。

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Skype for Business Online でフィルター処理されたユーザーのリストを返す
<a name="BKListofUsers"> </a>

[Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)コマンドレットと _LdapFilter_ または _Filter_ パラメーターを使用すると、対象ユーザーのセットに関する情報を簡単に返すことができます。 たとえば、このコマンドは財務部門で働くすべてのユーザーを返します。

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>関連項目
[Skype for Business Online 管理用にコンピューターをセットアップするには、次のWindows PowerShell](set-up-your-computer-for-windows-powershell.md)