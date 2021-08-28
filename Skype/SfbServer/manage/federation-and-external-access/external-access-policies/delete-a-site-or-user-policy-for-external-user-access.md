---
title: 外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: '[外部アクセス ポリシー] ページの [コントロール パネル] の [Skype for Business Server] に表示されているサイトまたはユーザー ポリシーを削除できます。'
ms.openlocfilehash: dc8ebdd0fc37d638f4d129dd995ebd2f179b0026
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582761"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除

使用する必要がなくなった外部ユーザー アクセス ポリシーを作成または構成している場合は、次の方法を実行できます。

  - 作成したサイトやユーザー ポリシーを削除します。

  - グローバル ポリシーを既定の設定にリセットします。 既定のグローバル ポリシー設定では、外部ユーザー アクセスが許可されません。 グローバル ポリシーは削除できません。


[外部アクセス ポリシー] ページの [コントロール パネル] の [Skype for Business Server] に表示されているサイトポリシーまたはユーザー ポリシー **を削除** できます。 グローバル ポリシーを削除しても、実際には削除されませんが、外部ユーザー アクセス オプションのサポートが含まれる既定の設定にのみリセットされます。 グローバル ポリシーのリセットの詳細については、「外部ユーザー アクセスのグローバル ポリシーを [リセットする」を参照してください](reset-the-global-policy-for-external-user-access.md)。


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>外部ユーザー アクセスのサイト ポリシーまたはユーザー ポリシーを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 

3.  [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。

4.  [**外部アクセス ポリシー**] タブで、削除するサイト ポリシーまたはユーザー ポリシーをクリックして [**編集**] をクリックし、[**削除**] をクリックします。

5.  削除について確認するメッセージが表示されたら、[**OK**] をクリックします。


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用した PIN ポリシー Windows PowerShell削除する

外部アクセス ポリシーは、外部アクセス ポリシーと Windows PowerShellコマンドレットをRemove-CsExternalAccessPolicyできます。 このコマンドレットは、管理シェルから、またはSkype for Business Serverのリモート セッションから実行Windows PowerShell。 


## <a name="to-remove-a-specific-external-access-policy"></a>特定の外部アクセス ポリシーを削除するには

  - 次のコマンドでは、Redmond サイトに適用されている外部アクセス ポリシーを削除します。<br/><br/>Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>ユーザーごとのスコープに適用されている外部アクセス ポリシーをすべて削除するには

  - 次のコマンドでは、ユーザーごとのスコープで構成されているすべての外部アクセス ポリシーを削除します。<br/><br/>Get-CsExternalAccessPolicy -Filter "tag:*" |Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>外部ユーザー アクセスが無効になっているすべての外部アクセス ポリシーを削除するには

  - 次のコマンドでは、外部ユーザー アクセス ポリシーが無効になっているすべての外部アクセス ポリシーを削除します。<br/><br/>Get-CsExternalAccessPolicy |Where-Object {$_.EnableOutsideAccess -eq $False} |Remove-CsExternalAccessPolicy


詳細については [、Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) コマンドレットのヘルプ トピックを参照してください。
