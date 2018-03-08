---
title: "オンラインのコネクタを使用してユーザー アカウントを管理します。"
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
ms.openlocfilehash: 6cd8f24638622b1581003c1b4f372923ca7c4939
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="manage-user-accounts-using-the-online-connector"></a>オンラインのコネクタを使用してユーザー アカウントを管理します。

## <a name="manage-user-accounts"></a>ユーザー アカウントを管理します。

このトピックには、次のセクションが含まれています。
  
- [すべて Skype for Business Online ユーザーに関する情報を返す](manage-user-accounts-using-the-online-connector.md#BKAllUsers)
    
- [Skype for Business Online の特定のユーザーに関する情報を返す](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)
    
- [Skype for Business Online の特定のユーザーの特定の情報を返す](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)
    
- [Skype for Business Online ユーザーのフィルターが適用されたリストを返します](manage-user-accounts-using-the-online-connector.md#BKListofUsers)
    
> [!NOTE]
> **セット CsUser**コマンドレットは Skype for Business Online の管理者できるコマンドレットのセットにも含まれます。ただし、**セット CsUser**は for Business Online では、Skype を管理する_AudioVideoDisabled_パラメーターを設定する以外に現在使用できません。その他のすべてのパラメーターを使用して、コマンドレットを実行しようとする場合は、次のようなエラー メッセージが失敗:"SipAddress"を設定できません。このパラメーターは、テナントのリモート PowerShell 内で制限されています。
  
### <a name="return-information-about-all-your-skype-for-business-online-users"></a>すべて Skype for Business Online ユーザーに関する情報を返す
<a name="BKAllUsers"> </a>

Skype for Business Online 有効になっているすべてのユーザーに関する情報を取得するには、パラメーターを追加せずに[取得 CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットを呼び出します。
  
```
Get-CsOnlineUser
```

1 つ、ランダムに選択したユーザー (たとえば、テスト用の現在のアカウントを使用する場合など) の情報を取得するにはするには、 **Get CsOnlineUser**コマンドレットを_ResultSize_パラメーターが 1 に設定します。
  
```
Get-CsOnlineUser -ResultSize 1
```

ある、組織のユーザーの数に関係なく、1 つのユーザーの情報を取得する**Get CsOnlineUser**コマンドレットの原因となります。5 人のユーザーの情報を返すには、5 _ResultSize_パラメーターの値を設定します。
  
```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Skype for Business Online の特定のユーザーに関する情報を返す
<a name="BKSpecificUser"> </a>

[Get CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットの通話する際に、特定のユーザー アカウントを参照する複数の方法があります。ユーザーの Active Directory ドメイン サービス (AD DS) の表示名を使用することができます。
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

ユーザーの SIP アドレスを使用することができます。
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

ユーザーのユーザー プリンシパル名 (UPN) を使用することができます。
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Skype for Business Online の特定のユーザーの特定の情報を返す
<a name="BKSpecificUsers"> </a>

既定では、 [Get CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx)コマンドレットは、大量の各の Skype for Business Online のユーザー アカウントの情報を返します。関心の情報の一部のみの場合は、パイプの返されるデータ**のコマンドレット**を実行します。たとえば、このコマンドすべてのデータを返します青木 Myer の場合は、[ユーザーと関数を使用して**、コマンドレットの情報を制限するのに**は表示し、画面に表示される青木の AD DS の表示名とダイヤル プランにします。
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

次のコマンドは、すべてのユーザーの表示名とダイヤルの計画を返します。
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Business Online のユーザー アカウントの Skype のプロパティを検索するには、次のコマンドを使用します。
  
```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Skype for Business Online ユーザーのフィルターが適用されたリストを返します
<a name="BKListofUsers"> </a>

[Get CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットとパラメーター _LdapFilter_または_フィルター_を使用すると、ユーザーの対象となるセットに関する情報を簡単に戻ることができます。たとえば、このコマンドは、財務部で作業しているすべてのユーザーを返します。
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>関連トピック
[Skype for business online 管理の Windows PowerShell を使用して、コンピューターを設定します。](set-up-your-computer-for-windows-powershell.md)
