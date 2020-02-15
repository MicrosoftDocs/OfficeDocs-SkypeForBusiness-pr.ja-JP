---
title: ユーザー id を使用する Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8310d5e25b5fc3dd3ada43fcf3c8f899f60e5a7e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001262"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>ユーザー id を使用する Skype for Business Online のコマンドレット

 


Skype for Business Online では、個別のユーザー Id を参照するさまざまな方法があります。

  - ユーザーの Active Directory ドメインサービスの表示名を使用します。 例:
    
        -Identity "Ken Myer"

  - ユーザーの SIP アドレスを使用します。 例:
    
        -Identity "sip:kenmyer@litwareinc.com"

  - ユーザーの UPN を使用します。 例:
    
        -Identity " kenmyer@litwareinc.com"

  - ユーザーの Active Directory ドメインサービスの識別名を使用します。 例:
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

次のコマンドレットは、ユーザー Id を受け入れます。

  - [無効化-Csの会議室](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))

  - [Enable-Csの会議室](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))

  - [取得-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))

  - [取得-Cs会議室](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))

  - [取得-Csonline ユーザー](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))

  - [取得-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))

  - [新規-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))

  - [削除-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))

  - [削除-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))

  - [Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))

  - [セットアップ-Csの会議室](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))

  - [設定-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))

なお、この**Get Cs**コマンドレットのいずれかを呼び出す場合は、ユーザー id を指定する必要はありません。 この例では、コマンドレットは指定されたアイテムのすべてのインスタンスを返します。 たとえば、次のコマンドを実行すると、Skype for Business Online が有効になっているすべてのユーザーに関する情報が戻されます。

    Get-CsOnlineUser

Identity パラメーターは、特定のユーザーについての情報を取得する場合にのみ必要です。

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a>関連項目


[Skype for Business Online の id、スコープ、およびテナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype for Business Online のコマンドレット](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

