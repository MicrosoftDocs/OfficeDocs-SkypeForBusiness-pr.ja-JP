---
title: ユーザー id を使用する Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce46e700a65f00625aeebad1032c54a5affeaa19
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233114"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>ユーザー id を使用する Skype for Business Online のコマンドレット

 


Skype for Business Online には、個々のユーザー Id を参照するさまざまな方法があります。

  - ユーザーの Active Directory ドメインサービスの表示名を使用します。 次に例を示します。
    
        -Identity "Ken Myer"

  - ユーザーの SIP アドレスを使用します。 次に例を示します。
    
        -Identity "sip:kenmyer@litwareinc.com"

  - ユーザーの UPN を使用します。 次に例を示します。
    
        -Identity " kenmyer@litwareinc.com"

  - ユーザーの Active Directory ドメインサービスの識別名を使用します。 次に例を示します。
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

次のコマンドレットは、ユーザー Id を受け取ります。

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))

  - [Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))

  - [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))

  - [Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))

  - [New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))

  - [Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))

  - [CsUserAcp の削除](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))

  - [Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))

  - [Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))

**Get Cs**コマンドレットのいずれかを呼び出す場合は、ユーザー id を指定する必要はないことに注意してください。 この場合、コマンドレットは指定された項目のすべてのインスタンスを返します。 たとえば、次のコマンドは、Skype for Business Online が有効になっているすべてのユーザーに関する情報を返します。

    Get-CsOnlineUser

Identity パラメーターが必要になるのは、特定のユーザーに関する情報を返す場合のみです。

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a>関連項目


[Skype for Business Online の id、スコープ、テナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online のコマンドレット](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

