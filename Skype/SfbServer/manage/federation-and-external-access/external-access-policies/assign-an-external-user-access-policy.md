---
title: 外部ユーザー アクセス ポリシーの割り当て
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
localization_priority: Normal
description: ユーザーが Skype for business Server 用に有効になっている場合は、特定のユーザーに適切なポリシーを適用することにより、Skype for Business Server コントロールパネルで SIP フェデレーション、リモートユーザーアクセス、およびパブリックインスタントメッセージング (IM) 接続を構成できます。
ms.openlocfilehash: ae8bea38a01f9211fc3338faf3e97f737c99e1a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280174"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>外部ユーザーアクセスポリシーを Skype for Business が有効なユーザーに割り当てる

ユーザーが Skype for business Server 用に有効になっている場合は、特定のユーザーに適切なポリシーを適用することにより、Skype for Business Server コントロールパネルで SIP フェデレーション、リモートユーザーアクセス、およびパブリックインスタントメッセージング (IM) 接続を構成できます。 たとえば、リモートユーザーアクセスをサポートするためのポリシーを作成した場合、ユーザーがリモートの場所から Skype for Business Server に接続して、リモートの場所から内部ユーザーと共同作業できるようにするには、ユーザーにそのポリシーを適用する必要があります。


> [!NOTE]  
> 外部ユーザーのアクセスをサポートするには、サポートする外部ユーザーアクセスの種類ごとにサポートを有効にし、その使用を制御するために適切なポリシーとその他のオプションを構成する必要があります。 詳細については、「 [Skype For Business Server へのフェデレーションと外部アクセスの管理](../managing-federation-and-external-access.md)」を参照してください。


このトピックの手順を使用して、以前に作成した外部ユーザーアクセスポリシーを1つ以上のユーザーアカウントに適用します。


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>ユーザーアカウントに外部ユーザーポリシーを適用するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [**外部アクセスポリシー**] の [ **Skype For business Server ユーザーの編集**] で、適用するユーザーポリシーを選択します。
     
> [!NOTE]  
> ** \<Automatic>** の設定では、既定のサーバーまたはグローバルポリシーの設定が適用されます。


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、ユーザーごとの外部アクセスポリシーを割り当てる

ユーザーごとの外部アクセスポリシーは、Windows PowerShell と Grant-CsExternalAccessPolicy コマンドレットを使用して割り当てることができます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>ユーザーごとの外部アクセスポリシーを1人のユーザーに割り当てるには

  - このコマンドを実行すると、ユーザーごとの外部アクセスポリシー RedmondExternalAccessPolicy が Ken Myer に割り当てられます。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>ユーザーごとの外部アクセスポリシーを複数のユーザーに割り当てるには

  - このコマンドによって、Active Directory の米国 OU にアカウントを持つすべてのユーザーに、ユーザーごとの外部アクセスポリシー USAExternalAccessPolicy が割り当てられます。 このコマンドで使用される OU パラメーターの詳細については、「[ユーザーの取得](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser)」コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>ユーザーごとの外部アクセスポリシーを割り当て解除するには

  - このコマンドは、前に Ken Myer に割り当てられているユーザーごとの外部アクセスポリシーを割り当て解除します。 ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。 サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



詳細については、「 [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。


