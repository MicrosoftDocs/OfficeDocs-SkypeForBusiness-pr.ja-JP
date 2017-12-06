---
title: "ビジネス Online コネクタの Skype を使用してユーザー アカウントを管理します。"
ms.author: tonysmit
author: tonysmit
ms.date: 5/23/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
description: "Use the Get-CsOnlineUser cmdlet in Windows PowerShell to get information about your organization's Skype for Business Online users."
---

# ビジネス Online コネクタの Skype を使用してユーザー アカウントを管理します。

> [!IMPORTANT]
> この記事は機械翻訳されています。機械翻訳についての「[免責事項](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#MT_Footer)」をお読みください。この記事の英語版を参照するには、[ここ](https://support.office.com/en-us/article/a226b0d4-6359-42b8-808d-4b8ab3736d3b)をクリックしてください。 
  
## ユーザー アカウントを管理する

このトピックは、次のセクションで構成されています。
  
- [すべての Skype for Business Online ユーザーに関する情報を返す](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoAboutAllUsers)
    
- [Skype for Business Online の特定のユーザー (1 人) に関する情報を返す](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoSpecificUser)
    
- [Skype for Business Online の特定のユーザー (複数) に関する情報を返す](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturninfoSpecificUsers)
    
- [Skype for Business Online のユーザーをフィルタリング処理したリストを返す ](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnFilteredListofUsers)
    
> [!NOTE]
> **Set-CsUser** コマンドレットは、Skype for Business Online の管理者に用意された一連のコマンドレットにも含まれています。ただし、 **Set-CsUser** は現在、 _AudioVideoDisabled_ パラメーターを設定する場合を除いて、Skype for Business Online を管理する目的では使用できません。その他のパラメーターを使用してこのコマンドを実行しようとすると、次のようなエラー メッセージにより失敗します。「SipAddress」を設定できません。このパラメーターは Remote Tenant PowerShell 内での使用に制限されています。
  
### すべての Skype for Business Online ユーザーに関する情報を返す
<a name="BKMK_ReturnInfoAboutAllUsers"> </a>

Skype for Business Online が有効化されているすべてのユーザーの情報を返すには、追加のパラメーターを使用せずに [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) コマンドレットを呼び出します。
  
```
Get-CsOnlineUser
```

単一の不特定ユーザーに関する情報を返すには (たとえば、テスト目的でこのアカウントを使用する場合)、 **Get-CsOnlineUser** コマンドレットを呼び出して、 _ResultSize_ パラメーターを 1 に設定します。
  
```
Get-CsOnlineUser -ResultSize 1
```

この操作により、 **Get-CsOnlineUser** コマンドレットは、組織におけるユーザーの数に関わらず、1 人のユーザーに関する情報のみを返します。5 人のユーザーに関する情報を返すには、 _ResultSize_ パラメーターの値を 5 に設定します。
  
```
Get-CsOnlineUser -ResultSize 5
```

### Skype for Business Online の特定のユーザー (1 人) に関する情報を返す
<a name="BKMK_ReturnInfoSpecificUser"> </a>

[Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) コマンドレットを呼び出すときに特定のユーザー アカウントを参照するには、次の方法があります。ユーザーの Active Directory ドメイン サービス (AD DS) 表示名を使用する。
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

ユーザーの SIP アドレスを使用する。
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

ユーザーのユーザー プリンシパル名 (UPN) を使用する。
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### Skype for Business Online の特定のユーザー (複数) に関する情報を返す
<a name="BKMK_ReturninfoSpecificUsers"> </a>

既定では、[Get-CsOnlineUser](https://support.office.com/article/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) コマンドレットは、各 Skype for Business Online ユーザー アカウントについて膨大な量の情報を返します。その情報の一部のみを取得したい場合は、返されたデータを **Select-Object** コマンドレットにパイプ処理します。たとえば、このコマンドを使用すると、Ken Myer というユーザーに関するすべてのデータが返されますが、 **Select-Object** コマンドレットを使用することで、画面に表示される情報を Ken の AD DS 表示名とダイヤル プランに制限できます。
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

次のコマンドは、すべてのユーザーの表示名とダイアル プランを返します。
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Skype for Business Online ユーザー アカウントのプロパティを確認するには、次のコマンドを使用します。
  
```
Get-CsOnlineUser | Get-Member
```

### Skype for Business Online のユーザーをフィルタリング処理したリストを返す
<a name="BKMK_ReturnFilteredListofUsers"> </a>

[Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) コマンドレットと _LdapFilter_ または _Filter_ パラメーターを使用することで、対象グループのユーザーに関する情報を簡単に取得することができます。たとえば、このコマンドは、財務部門に所属するすべてのユーザーを返します。
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **機械翻訳についての免責事項**: この記事の翻訳はコンピューター システムによって行われており、人間の手は加えられていません。マイクロソフトでは、英語を話さないユーザーがマイクロソフトの製品、サービス、テクノロジに関するコンテンツを理解するのに役立てるため、こうした機械翻訳を提供しています。記事は機械翻訳されているため、用語、構文、文法などに誤りがある場合があります。 
  

