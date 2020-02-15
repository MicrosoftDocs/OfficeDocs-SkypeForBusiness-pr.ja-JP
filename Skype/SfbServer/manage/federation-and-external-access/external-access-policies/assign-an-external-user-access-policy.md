---
title: 外部ユーザーアクセスポリシーの割り当て
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
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
description: ユーザーが Skype for business Server に対して有効になっている場合は、特定のユーザーに適切なポリシーを適用することで、Skype for Business Server コントロールパネルで SIP フェデレーション、リモートユーザーアクセス、およびパブリックインスタントメッセージング (IM) 接続を構成できます。
ms.openlocfilehash: c03eb957679877ec512b042e0db624adbb3e6f52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043679"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Skype for Business が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て

ユーザーが Skype for business Server に対して有効になっている場合は、特定のユーザーに適切なポリシーを適用することで、Skype for Business Server コントロールパネルで SIP フェデレーション、リモートユーザーアクセス、およびパブリックインスタントメッセージング (IM) 接続を構成できます。 たとえば、リモートユーザーアクセスをサポートするポリシーを作成した場合、ユーザーがリモートの場所から Skype for Business Server に接続して、リモートの場所から内部ユーザーと共同作業できるようにするには、そのポリシーをユーザーに適用する必要があります。


> [!NOTE]  
> 外部ユーザー アクセスをサポートするには、サポートする各種類の外部ユーザー アクセスのサポートを有効にし、適切なポリシーとその他の使用制御オプションを構成する必要があります。 詳細については、「 [Skype For Business Server へのフェデレーションと外部アクセスの管理](../managing-federation-and-external-access.md)」を参照してください。


このトピックの手順を使用して、あらかじめ作成した外部ユーザー アクセス ポリシーを、1 つまたは複数のユーザー アカウントに適用します。


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>外部ユーザー ポリシーをユーザー アカウントに適用するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [**外部アクセスポリシー**] の [ **Skype For business Server ユーザーの編集**] で、適用するユーザーポリシーを選択します。
     
> [!NOTE]  
> [ ** \<自動>** ] 設定では、既定のサーバーまたはグローバルポリシーの設定が適用されます。


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したユーザー単位の外部アクセスポリシーの割り当て

ユーザー単位の外部アクセスポリシーは、Windows PowerShell と Get-csexternalaccesspolicy コマンドレットを使用して割り当てることができます。 このコマンドレットは、Skype for Business Server 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行できます。 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>ユーザーごとの外部アクセスポリシーを単一のユーザーに割り当てるには

  - 次のコマンドは、ユーザーごとの外部アクセス ポリシー RedmondExternalAccessPolicy をユーザー Ken Myer に割り当てます。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>ユーザーごとの外部アクセスポリシーを複数のユーザーに割り当てるには

  - 次のコマンドは、ユーザーごとの外部アクセス ポリシー USAExternalAccessPolicy を、Active Directory の UnitedStates OU にアカウントを持っているすべてのユーザーに割り当てます。 このコマンドで使用されている OU パラメーターの詳細については、「 [Get-help user](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)コマンドレットのドキュメント」を参照してください。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>ユーザーごとの外部アクセスポリシーの割り当てを解除するには

  - 次のコマンドは、以前に Ken Myer に割り当てたユーザーごとの外部アクセス ポリシーのすべての割り当てを解除します。ユーザーごとのポリシーの割り当てを解除された後の Ken Myer は、グローバル ポリシーまたは存在する場合はローカル サイト ポリシーを使用して、自動的に管理されます。サイト ポリシーの方がグローバル ポリシーより優先されます。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



詳細については、 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。


