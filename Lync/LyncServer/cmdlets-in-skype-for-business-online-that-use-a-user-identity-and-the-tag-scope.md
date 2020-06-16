---
title: ユーザー id とタグスコープを使用する Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 9adf86a6ec6d2bd859411005dcc67b0dcbe09c7f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755119"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>ユーザー id とタグスコープを使用する Skype for Business Online のコマンドレット

 


**Grant-Cs**コマンドレット (ユーザーにポリシーを割り当てるために使用される) には、ユーザー Id (identity パラメーター) とユーザーごとのポリシーの Id (PolicyName パラメーター) という2つの識別子が必要です。 たとえば、音声ポリシー RedmondVoicePolicy をユーザー Ken Myer に割り当てるには、次のコマンドを使用します。

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

ポリシーをユーザーに割り当てる際には、次の2つの点に注意する必要があります。 最初に、ユーザーごとのポリシーのみを割り当てることができます。 グローバルポリシーをユーザーに割り当てることはできません。 たとえば、次のコマンドは失敗します。

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

グローバルポリシーを割り当てる必要がないため、このコマンドは失敗します。 グローバルポリシーを使用してユーザーを管理する場合は、そのユーザーにユーザーごとのポリシーを割り当てないでください。 ユーザーごとのポリシーがユーザーに割り当てられていない場合、そのユーザーはグローバルポリシーを使用して自動的に管理されます。


> [!NOTE]  
> ユーザーが以前ユーザーごとのポリシーを割り当てていて、そのポリシーの割り当てを解除して、代わりにグローバルポリシーでユーザーを管理する場合は、どうなりますか。 その場合は、まず、次の構文を使用します。これは、ユーザーごとのポリシーを割り当てないようにするために、そのユーザーに null ポリシーを付与します。<BR>Set-csvoicepolicy – Identity "Ken Myer" – PolicyName $Null



2番目に、ユーザーごとのポリシーがタグスコープで作成されることに注意してください。 ただし、ポリシー名を指定するときは、タグ**プレフィックス**を省略できます。 これらの2つのコマンドは同じです。

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

すべてのユーザーごとのポリシー (または、少なくとも、音声ポリシーなど、指定された種類のすべてのユーザーごとのポリシー) の id を返す場合は、次のようなコマンドを使用します。

    Get-CsVoicePolicy -Filter "tag:*"

次のコマンドレットでは、ユーザー Id とタグスコープの両方を使用します。

  - [Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))

  - [Get-csconferencingpolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))

  - [Get-csdialplan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))

  - [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))

  - [Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>関連項目


[Skype for Business Online の id、スコープ、およびテナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype for Business Online のコマンドレット](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

