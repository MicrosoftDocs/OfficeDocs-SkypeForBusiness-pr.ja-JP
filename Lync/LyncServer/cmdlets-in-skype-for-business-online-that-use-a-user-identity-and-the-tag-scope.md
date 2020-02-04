---
title: ユーザー id とタグのスコープを使う Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24c197934705a86d91e0492949aa2a9e6484f903
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727567"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>ユーザー id とタグのスコープを使う Skype for Business Online のコマンドレット

 


ユーザーにポリシーを割り当てるために使用される**Grant-Cs**コマンドレットは、ユーザー Id (identity パラメーター) とユーザーごとのポリシーの Id (PolicyName パラメーター) の2つの識別子を必要とします。 たとえば、ユーザー Ken Myer にボイスポリシー RedmondVoicePolicy を割り当てるには、次のコマンドを使用します。

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

ユーザーにポリシーを割り当てるときは、次の2つの点に注意する必要があります。 最初に、ユーザーごとのポリシーのみを割り当てることができます。 グローバルポリシーをユーザーに割り当てることはできません。 たとえば、次のコマンドは失敗します。

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

グローバルポリシーを割り当てる必要がないため、このコマンドは失敗します。 グローバルポリシーを使用してユーザーを管理する場合は、そのユーザーにユーザーごとのポリシーを割り当てないでください。 ユーザーごとのポリシーが割り当てられていない場合、そのユーザーはグローバルポリシーを使用して自動的に管理されます。


> [!NOTE]  
> ユーザーに以前にユーザーポリシーが割り当てられていて、そのポリシーを割り当て解除して、代わりにグローバルポリシーでユーザーを管理する場合は、どうすればよいですか。 その場合は、最初に次の構文を使用します。この構文は、ユーザーに対して、null ポリシーを付与することにより、ユーザーごとのポリシーを割り当て解除します。<BR>Grant-CsVoicePolicy – Identity "Ken Myer" – PolicyName $Null



次に、ユーザーごとのポリシーはタグのスコープで作成されることに注意してください。 ただし、ポリシー名を指定するときは、タグ**プレフィックス**を省略できます。 次の2つのコマンドは同じです。

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

すべてのユーザーごとのポリシー (音声ポリシーなど、指定した種類のすべてのユーザーごとのポリシー) の id を返す場合は、次のようなコマンドを使用します。

    Get-CsVoicePolicy -Filter "tag:*"

次のコマンドレットでは、ユーザー Id とタグスコープの両方を使用します。

  - [権限の付与: CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))

  - [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))

  - [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))

  - [Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))

  - [Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))

  - [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>関連項目


[Skype for Business Online の id、スコープ、テナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online のコマンドレット](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

