---
title: 外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 記載されている、Skype ビジネス サーバーのコントロール パネルの [外部アクセス ポリシー] ページで、サイトまたはユーザーのポリシーを削除することができます。
ms.openlocfilehash: 24d26e8668d04f1c11a3039b4b524d25e209e619
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197745"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除

作成または、外部ユーザー アクセス ポリシーを使用する必要がなくなったように構成した場合は、次の操作を行うことができます。

  - 作成したサイトまたはユーザーのポリシーを削除します。

  - グローバル ポリシーを既定の設定にリセットします。 既定のグローバル ポリシー設定は、すべての外部ユーザー アクセスを拒否します。 グローバル ポリシーは削除できません。


記載されている、Skype ビジネス サーバーのコントロール パネルの [**外部アクセス ポリシー** ] ページで、サイトまたはユーザーのポリシーを削除することができます。 グローバル ポリシーを削除すると、実際には削除されず、ですが、のみが、外部ユーザー アクセス オプションのサポートが含まれていない既定の設定にリセットします。 グローバル ポリシーのリセットの詳細については、[外部ユーザー アクセス用のグローバル ポリシーのリセット](reset-the-global-policy-for-external-user-access.md)を参照してください。


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>外部ユーザー アクセスのサイトまたはユーザーのポリシーを削除するのには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  **外部ユーザー アクセス**] をクリックして、[**外部アクセス ポリシー**] をクリックします。

4.  [**外部アクセス ポリシー** ] タブで、削除、**編集**] をクリックし、[**削除**] をクリックするサイトまたはユーザーのポリシーをクリックします。

5.  削除の確認メッセージが表示されたら、[ **OK**を] をクリックします。


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、暗証番号 (pin) ポリシーを削除します。

外部アクセス ポリシーは、Windows PowerShell と削除 CsExternalAccessPolicy コマンドレットを使用して削除できます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 


## <a name="to-remove-a-specific-external-access-policy"></a>特定の外部アクセス ポリシーを削除するには

  - このコマンドは、Redmond サイトに適用される外部アクセス ポリシーを削除します。
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>外部アクセス ユーザーごとのスコープに適用されるポリシーをすべて削除するには

  - このコマンドは、ユーザーごとのスコープで構成されているすべての外部アクセス ポリシーを削除します。
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>外部ユーザー アクセスが無効になっているすべての外部アクセス ポリシーを削除するのには

  - このコマンドは、外部ユーザー アクセスが無効になってすべての外部アクセス ポリシーを削除します。
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


詳細については、[削除 CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)コマンドレットのヘルプ トピックを参照してください。
