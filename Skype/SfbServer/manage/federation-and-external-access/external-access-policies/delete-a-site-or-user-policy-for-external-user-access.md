---
title: 外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除
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
localization_priority: Normal
description: '[外部アクセスポリシー] ページの [Skype for Business Server] コントロールパネルに表示されているサイトまたはユーザーポリシーは、削除することができます。'
ms.openlocfilehash: 615df309088a329e07f5417dce16e98366a371c7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280125"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除

使用しない外部ユーザーアクセスポリシーを作成または構成している場合は、次の操作を行うことができます。

  - 作成したサイトまたはユーザーのポリシーを削除します。

  - グローバルポリシーを既定の設定にリセットします。 既定のグローバルポリシー設定では、外部ユーザーのアクセスを拒否します。 グローバルポリシーは削除できません。


[**外部アクセスポリシー** ] ページの [Skype For Business Server] コントロールパネルに表示されているサイトまたはユーザーポリシーは、削除することができます。 グローバルポリシーを削除しても、実際に削除されるわけではありませんが、外部ユーザーアクセスオプションのサポートは含まれていない既定の設定にリセットされるだけです。 グローバルポリシーのリセットの詳細については、「[外部ユーザーアクセスのグローバルポリシーをリセット](reset-the-global-policy-for-external-user-access.md)する」を参照してください。


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>外部ユーザーアクセスのサイトまたはユーザーポリシーを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  [**外部ユーザーアクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。

4.  [**外部アクセスポリシー** ] タブで、削除するサイトまたはユーザーのポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。

5.  削除を確認するメッセージが表示されたら、[ **OK**] をクリックします。


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して PIN ポリシーを削除する

外部アクセスポリシーは、Windows PowerShell と CsExternalAccessPolicy コマンドレットを使用して削除できます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 


## <a name="to-remove-a-specific-external-access-policy"></a>特定の外部アクセスポリシーを削除するには

  - このコマンドは、Redmond サイトに適用されている外部アクセスポリシーを削除します。
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>ユーザーごとのスコープに適用されたすべての外部アクセスポリシーを削除するには

  - このコマンドは、ユーザーごとのスコープで構成されたすべての外部アクセスポリシーを削除します。
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>外部ユーザーアクセスが無効になっている外部アクセスポリシーをすべて削除するには

  - このコマンドは、外部ユーザーアクセスが無効になっている外部アクセスポリシーをすべて削除します。
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


詳細については、 [CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。
