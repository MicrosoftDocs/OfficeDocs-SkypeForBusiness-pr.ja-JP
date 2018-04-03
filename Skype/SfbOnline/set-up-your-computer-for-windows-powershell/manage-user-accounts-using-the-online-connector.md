---
title: オンラインのコネクタを使用してユーザー アカウントを管理します。
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
description: オンライン ビジネスのユーザーに対して、組織の Skype に関する情報を取得するのには Windows PowerShell の Get CsOnlineUser コマンドレットを使用します。
ms.openlocfilehash: 1583e808cc489bb19f51acd6f52c900772138efe
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="manage-user-accounts-using-the-online-connector"></a>オンラインのコネクタを使用してユーザー アカウントを管理します。

## <a name="manage-user-accounts"></a>ユーザー アカウントを管理します。

このトピックには次のセクションが含まれます。
  
- [オンライン ビジネスのユーザーに、すべての Skype に関する情報を返す](manage-user-accounts-using-the-online-connector.md#BKAllUsers)
    
- [Skype でオンライン ビジネスの特定のユーザーに関する情報を返す](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)
    
- [Skype でオンライン ビジネスの特定のユーザーに固有の情報を返す](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)
    
- [Skype でオンライン ビジネスのユーザーのフィルター処理された一覧を返す](manage-user-accounts-using-the-online-connector.md#BKListofUsers)
    
> [!NOTE]
> **セット CsUser**コマンドレットは、管理者のオンライン ビジネスの Skype を利用可能なコマンドレットのセットにも含まれます。 ただし、 **csuser からのセット**は、 _AudioVideoDisabled_パラメーターを設定する以外のビジネス オンラインでは、Skype を管理するために現在使用できません。 次のようなエラー メッセージで失敗、他のパラメーターを持つコマンドレットを実行しようとした場合:"SipAddress"を設定できません。 このパラメーターは、リモートのテナント PowerShell 内で制限されています。
  
### <a name="return-information-about-all-your-skype-for-business-online-users"></a>すべての Lync Online ユーザーに関する情報を返す
<a name="BKAllUsers"> </a>

Skype のオンライン ビジネスに有効になっているすべてのユーザーに関する情報を返すには、追加パラメーターを指定せず[取得 CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットを呼び出します。
  
```
Get-CsOnlineUser
```

(たとえば、テスト目的でこのアカウントを使用する場合など)、1 つのランダムに選択したユーザーの情報を取得するには、 **Get CsOnlineUser**コマンドレットを呼び出すし、 _ResultSize_パラメーターを 1 に設定します。
  
```
Get-CsOnlineUser -ResultSize 1
```

組織内にあるユーザーの数に関係なく、1 つのユーザーの情報を取得する**Get CsOnlineUser**コマンドレットの原因となります。 5 人のユーザーの情報を返すには、 _ResultSize_パラメーターの値を 5 に設定します。
  
```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Skype でオンライン ビジネスの特定のユーザーに関する情報を返す
<a name="BKSpecificUser"> </a>

[Get CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットを呼び出すときに特定のユーザー アカウントを参照する複数の方法があります。 ユーザーの Active Directory ドメイン サービス (AD DS) の表示名を使用することができます。
  
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

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Skype でオンライン ビジネスの特定のユーザーに固有の情報を返す
<a name="BKSpecificUsers"> </a>

既定では、 [Get CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx)コマンドレットは、膨大なオンライン ビジネスのユーザー アカウントの各 Skype の情報を返します。 情報のサブセットのみに関心がある場合は、返されたデータを**Select-object**コマンドレットをパイプします。 たとえば、このコマンドを返します Ken Myer のユーザーとし、情報を制限する**Select-object**コマンドレットが表示される使用のすべてのデータ画面に表示される Ken の AD DS の表示名] と [ダイヤル プランにします。
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

次のコマンドでは、[表示名] と [ダイヤルの計画のすべてのユーザーを返します。
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

オンライン ビジネスのユーザー アカウントの Skype のプロパティを検索するには、次のコマンドを使用します。
  
```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Skype でオンライン ビジネスのユーザーのフィルター処理された一覧を返す
<a name="BKListofUsers"> </a>

[Get CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットと、 _LdapFilter_パラメーターまたは_フィルター_パラメーターを使用すると、対象となる一連のユーザーに関する情報を簡単に戻ることができます。 たとえば、このコマンドは、財務部門で働くすべてのユーザーを返します。
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。
[Windows PowerShell を使用してビジネスのオンライン管理のための skype には、コンピューターを設定します](set-up-your-computer-for-windows-powershell.md)

  
 