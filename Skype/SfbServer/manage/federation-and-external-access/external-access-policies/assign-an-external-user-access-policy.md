---
title: 外部ユーザー アクセス ポリシーの割り当て
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ユーザーが Skype for Business Server で有効になっている場合は、特定のユーザーに適切なポリシーを適用して、Skype for Business Server コントロール パネルで SIP フェデレーション、リモート ユーザー アクセス、およびパブリック インスタント メッセージング (IM) 接続を構成できます。
ms.openlocfilehash: 45e22a0d7951bfe4d58d90a1e5190aa242f7b29a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099053"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Skype for Business が有効なユーザーに外部ユーザー アクセス ポリシーを割り当てる

ユーザーが Skype for Business Server で有効になっている場合は、特定のユーザーに適切なポリシーを適用して、Skype for Business Server コントロール パネルで SIP フェデレーション、リモート ユーザー アクセス、およびパブリック インスタント メッセージング (IM) 接続を構成できます。 たとえば、リモート ユーザー アクセスをサポートするポリシーを作成した場合、ユーザーがリモートの場所から Skype for Business Server に接続し、リモートの場所から内部ユーザーと共同作業を行う前に、ユーザーに適用する必要があります。


> [!NOTE]  
> 外部ユーザー アクセスをサポートするには、サポートする各種類の外部ユーザー アクセスのサポートを有効にし、適切なポリシーとその他の使用制御オプションを構成する必要があります。 詳細については [、「Skype for Business Server へのフェデレーションと外部アクセスの管理」を参照してください](../managing-federation-and-external-access.md)。


このトピックの手順を使用して、あらかじめ作成した外部ユーザー アクセス ポリシーを、1 つまたは複数のユーザー アカウントに適用します。


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>外部ユーザー ポリシーをユーザー アカウントに適用するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [**外部アクセス ポリシー] の [Skype for Business Server ユーザー** の編集] で、適用するユーザー ポリシーを選択します。 
     
> [!NOTE]  
> この **\<Automatic>** 設定は、既定のサーバーまたはグローバル ポリシー設定を適用します。


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>コマンドレットをPer-Userして外部アクセス ポリシーを割り当Windows PowerShellする

ユーザーごとの外部アクセス ポリシーを割り当てるには、Windows PowerShellコマンドレットをGrant-CsExternalAccessPolicyします。 このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>ユーザーごとの外部アクセス ポリシーを 1 人のユーザーに割り当てるには

  - 次のコマンドは、ユーザーごとの外部アクセス ポリシー RedmondExternalAccessPolicy をユーザー Ken Myer に割り当てます。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>ユーザーごとの外部アクセス ポリシーを複数のユーザーに割り当てるには

  - 次のコマンドは、ユーザーごとの外部アクセス ポリシー USAExternalAccessPolicy を、Active Directory の UnitedStates OU にアカウントを持っているすべてのユーザーに割り当てます。 このコマンドで使用される OU パラメーターの詳細については [、Get-CsUser](/powershell/module/skype/Get-CsUser) コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>ユーザーごとの外部アクセス ポリシーの割り当てを解除するには

  - 次のコマンドは、以前に Ken Myer に割り当てたユーザーごとの外部アクセス ポリシーのすべての割り当てを解除します。ユーザーごとのポリシーの割り当てを解除された後の Ken Myer は、グローバル ポリシーまたは存在する場合はローカル サイト ポリシーを使用して、自動的に管理されます。サイト ポリシーの方がグローバル ポリシーより優先されます。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



詳細については [、Grant-CsExternalAccessPolicy](/powershell/module/skype/Grant-CsExternalAccessPolicy) コマンドレットのヘルプ トピックを参照してください。