---
title: グローバルスコープとタグスコープを使う Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51327b98be69f92736c1c8523c97b4de6463273b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840094"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>グローバルスコープとタグスコープを使う Skype for Business Online のコマンドレット

 


Skype for Business Online では、ポリシーは*グローバルスコープ*または*タグのスコープ*(または*ユーザーごとのスコープ*) で構成できます。 **Get-Cs**コマンドレットを使う場合は、スコープまたは id を指定する必要はありません。 パラメーターを指定せずにこれらのコマンドレットのいずれかを呼び出すと、関連するすべての項目が返されます。 たとえば、次のコマンドは、すべての外部アクセスポリシーに関する情報を返します。

    Get-CsExternalAccessPolicy

返されるデータを制限する場合は、Identity パラメーターまたは Filter パラメーターのみを含める必要があります。 たとえば、グローバルポリシーのみを返すには、次のコマンドを使用します。

    Get-CsExternalAccessPolicy -Identity "global"

Id が "RedmondAccessPolicy" のユーザーごとのポリシーを返すには、次のコマンドを使用します。

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> ユーザーごとのポリシーを参照する場合、タグ<STRONG>プレフィックス</STRONG>は省略可能です。 プレフィックスを含むこの構文は、次の場合にも有効です。<BR>Get-CsExternalAccessPolicy – Identity "tag: RedmondAccessPolicy"



グローバルポリシー (つまり、ユーザーごとのポリシー) を除くすべてのポリシーを返すには、次のコマンドを使用します。

    Get-CsExternalAccessPolicy -Filter "tag:*"

次のコマンドレットは、グローバルスコープとユーザーごとの (タグ) スコープの両方に対して動作します。

  - [CsClientPolicy の入手](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> 名前にかかわらず、ダイヤルプランは、機能的に言うことができます。ポリシー。 以前のバージョンの Lync Server で使用されていた用語を保存するために、[ダイヤルポリシー] の代わりに、"<EM>ダイヤルプラン</EM>" という用語を使用します。



## <a name="see-also"></a>関連項目


[Skype for Business Online の id、スコープ、テナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online のコマンドレット](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

