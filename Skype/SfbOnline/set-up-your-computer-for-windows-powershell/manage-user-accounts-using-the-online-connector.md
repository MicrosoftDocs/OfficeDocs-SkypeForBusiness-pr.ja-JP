---
title: オンラインコネクタを使用してユーザーアカウントを管理する
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
ms.openlocfilehash: 5be51ac39f4a5bd07788a3341114d72a8556cc1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284682"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>オンラインコネクタを使用してユーザーアカウントを管理する

## <a name="manage-user-accounts"></a>ユーザー アカウントを管理する

このトピックには次のセクションが含まれます。

- [すべての Lync Online ユーザーに関する情報を返す](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [Skype for Business Online の特定のユーザーに関する情報を返す](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [Skype for Business Online の特定のユーザーに固有の情報を返す](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [Skype for Business Online でフィルター処理されたユーザーのリストを返す](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> **Set-CsUser**コマンドレットは、Skype For business Online の管理者が利用できるコマンドレットのセットにも含まれています。 ただし、 _Audiovideodisabled_パラメーターを設定する場合を除き、現在 Skype For business Online の管理には、 **Set-csuser**は使用できません。 他のパラメーターでコマンドレットを実行しようとすると、次のようなエラーメッセージが表示されて失敗します。 "SipAddress" を設定できません。 このパラメーターは、リモートテナント PowerShell で制限されています。

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>すべての Lync Online ユーザーに関する情報を返す
<a name="BKAllUsers"> </a>

Skype for Business Online が有効になっているすべてのユーザーに関する情報を取得するには、追加のパラメーターを指定せずに、 [Csonline ユーザー](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットを呼び出します。

```
Get-CsOnlineUser
```

ランダムに選択された1人のユーザーに関する情報を返すには (たとえば、テスト目的でこのアカウントを使用する場合など)、" **Csonline ユーザー** " コマンドレットを呼び出し、 _resultsize_パラメーターを1に設定します。

```
Get-CsOnlineUser -ResultSize 1
```

これにより**** 、組織内のユーザー数に関係なく、1人のユーザーの情報が返されます。 5人のユーザーの情報を返すには、 _Resultsize_パラメーターの値を5に設定します。

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Skype for Business Online の特定のユーザーに関する情報を返す
<a name="BKSpecificUser"> </a>

[Csonline ユーザー](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットを呼び出すと、複数の方法で特定のユーザーアカウントを参照できます。 ユーザーの Active Directory ドメインサービス (AD DS) の表示名を使用できます。

```
Get-CsOnlineUser -Identity "Ken Myer"
```

ユーザーの SIP アドレスを使用できます。

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

ユーザーのユーザープリンシパル名 (UPN) を使うことができます。

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Skype for Business Online の特定のユーザーに固有の情報を返す
<a name="BKSpecificUsers"> </a>

既定では、[ユーザーの取得](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx)コマンドレットによって、Skype For business Online のユーザーアカウントごとに膨大な量の情報が返されます。 その情報の一部のみを対象としている場合は、返されるデータを**オブジェクトの選択**コマンドレットにパイプします。 たとえば、このコマンドは、ユーザー Ken Myer のすべてのデータを返し、次に、**オブジェクトの選択**コマンドレットを使用して、表示される情報を KEN の AD DS 表示名とダイヤルプランに制限します。

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

次のコマンドは、すべてのユーザーの表示名とダイヤルプランを返します。

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Skype for Business Online のユーザーアカウントのプロパティを確認するには、次のコマンドを使用します。

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Skype for Business Online でフィルター処理されたユーザーのリストを返す
<a name="BKListofUsers"> </a>

[ユーザーのアクセス](https://go.microsoft.com/fwlink/p/?linkid=849603)コマンドレットと_Ldapfilter_または_filter_パラメーターを使用することで、対象となるユーザーのセットに関する情報を簡単に返すことができます。 たとえば、このコマンドは、財務部門で仕事をしているすべてのユーザーを返します。

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>関連トピック
[Windows PowerShell を使用して skype for business online 管理用にコンピューターをセットアップする](set-up-your-computer-for-windows-powershell.md)


