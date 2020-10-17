---
title: グローバルスコープとタグスコープを使用する Skype for Business Online のコマンドレット
description: グローバルスコープとタグスコープを使用する Skype for Business Online のコマンドレット。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba89ebe7322159027c5de765117afd366cb3dc23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545623"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>グローバルスコープとタグスコープを使用する Skype for Business Online のコマンドレット

 


Skype for Business Online では、ポリシーは、 *グローバルスコープ* または *タグの範囲* (または *ユーザーごとのスコープ*) のいずれかで構成できます。 **Get-Cs**コマンドレットを使用する場合、スコープまたは id を指定する必要はありません。 パラメーターを指定せずにこれらのコマンドレットのいずれかを呼び出すと、関連するすべての項目が返されます。 たとえば、次のコマンドを実行すると、すべての外部アクセスポリシーに関する情報が戻されます。

    Get-CsExternalAccessPolicy

返されるデータを制限する場合は、Identity パラメーターまたは Filter パラメーターのみを含める必要があります。 たとえば、グローバルポリシーのみを返すには、次のコマンドを使用します。

    Get-CsExternalAccessPolicy -Identity "global"

Id が "RedmondAccessPolicy" のユーザーごとのポリシーを返すには、次のコマンドを使用します。

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> ユーザーごとのポリシーを参照する場合、タグ <STRONG>プリフィックス</STRONG> はオプションです。 この構文は、プレフィックスを含むので、次のようにも有効です。<BR>Get-CsExternalAccessPolicy – Identity "tag: RedmondAccessPolicy"



グローバルポリシー (つまり、すべてのユーザーごとのポリシー) を除くすべてのポリシーを戻すには、次のコマンドを使用します。

    Get-CsExternalAccessPolicy -Filter "tag:*"

次のコマンドレットは、グローバルスコープとユーザーごと (タグ) スコープの両方に対して動作します。

  - [Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> 名前にかかわらず、ダイヤルプランは、機能的には、ポリシーになります。 以前のバージョンの Lync Server で使用されていた用語を保持するために、ダイヤルポリシーなどの代わりに、" <EM>ダイヤルプラン</EM> " という用語を使用します。



## <a name="see-also"></a>関連項目


[Skype for Business Online の id、スコープ、およびテナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype for Business Online のコマンドレット](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

