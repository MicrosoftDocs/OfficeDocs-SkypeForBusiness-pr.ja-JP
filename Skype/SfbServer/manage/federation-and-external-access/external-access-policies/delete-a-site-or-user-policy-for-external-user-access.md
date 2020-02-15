---
title: 外部ユーザーアクセスのサイトポリシーまたはユーザーポリシーを削除する
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '[外部アクセスポリシー] ページで、Skype for Business Server コントロールパネルに表示されているサイトポリシーまたはユーザーポリシーを削除することができます。'
ms.openlocfilehash: ae0a0499e7497c4d62884860a2730960e5070ac8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041236"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>外部ユーザーアクセスのサイトポリシーまたはユーザーポリシーを削除する

使用しなくなった外部ユーザー アクセス ポリシーを作成または構成済みの場合は、次の操作を実行できます。

  - 作成したサイトやユーザー ポリシーを削除します。

  - グローバル ポリシーを既定の設定にリセットします。 既定のグローバル ポリシー設定では、外部ユーザー アクセスが許可されません。 グローバル ポリシーは削除できません。


[**外部アクセスポリシー** ] ページで、Skype For Business Server コントロールパネルに表示されているサイトポリシーまたはユーザーポリシーを削除することができます。 グローバル ポリシーを削除すると、実際には削除されず、外部ユーザー アクセス オプションのサポートが含まれていない既定の設定にリセットされるだけです。 グローバルポリシーのリセットの詳細については、「 [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md)」を参照してください。


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>外部ユーザー アクセスのサイト ポリシーまたはユーザー ポリシーを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。 

3.  [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。

4.  [**外部アクセス ポリシー**] タブで、削除するサイト ポリシーまたはユーザー ポリシーをクリックして [**編集**] をクリックし、[**削除**] をクリックします。

5.  削除について確認するメッセージが表示されたら、[**OK**] をクリックします。


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して PIN ポリシーを削除する

外部アクセスポリシーは、Windows PowerShell と Get-csexternalaccesspolicy コマンドレットを使用して削除できます。 このコマンドレットは、Skype for Business Server 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行できます。 


## <a name="to-remove-a-specific-external-access-policy"></a>特定の外部アクセスポリシーを削除するには

  - 次のコマンドでは、Redmond サイトに適用されている外部アクセス ポリシーを削除します。
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>ユーザーごとのスコープに適用されているすべての外部アクセスポリシーを削除するには

  - 次のコマンドでは、ユーザーごとのスコープで構成されているすべての外部アクセス ポリシーを削除します。
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>外部ユーザーアクセスが無効になっているすべての外部アクセスポリシーを削除するには

  - 次のコマンドでは、外部ユーザー アクセス ポリシーが無効になっているすべての外部アクセス ポリシーを削除します。
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


詳細については、 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。
