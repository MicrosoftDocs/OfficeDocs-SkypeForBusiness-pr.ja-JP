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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ユーザーが有効になって Skype のビジネス サーバー、SIP フェデレーション、リモート ユーザー アクセス、およびパブリック インスタント ビジネス サーバーのコントロール パネルの特定のユーザーに適切なポリシーを適用することにより、Skype での (IM) 接続をメッセージングを構成できます。
ms.openlocfilehash: 7a2563900ae72bf57b26b5eff9997f3d1c65a71e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920676"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>外部ユーザー アクセス ポリシーを有効になっているビジネス ユーザーに、Skype を割り当てる

ユーザーが有効になって Skype のビジネス サーバー、SIP フェデレーション、リモート ユーザー アクセス、およびパブリック インスタント ビジネス サーバーのコントロール パネルの特定のユーザーに適切なポリシーを適用することにより、Skype での (IM) 接続をメッセージングを構成できます。 などのリモート ユーザー アクセスをサポートするポリシーを作成した場合必要がありますに適用するユーザー、ユーザーはリモートの場所から、ビジネス サーバーの Skype に接続でき、リモートの場所から内部のユーザーと共同作業を行う前にします。


> [!NOTE]  
> 外部ユーザー アクセスをサポートするためには、サポートする外部ユーザー アクセスの種類ごとにサポートを有効にして、適切なポリシーとその使用を制御するその他のオプションを構成する必要があります。 詳細については、[管理するフェデレーションと Skype のビジネス サーバーへの外部アクセス](../managing-federation-and-external-access.md)を参照してください。


このトピックで以前に作成した外部ユーザー アクセス ポリシーを 1 つまたは複数のユーザー アカウントに適用するのに手順を使用します。


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>ユーザー アカウントに、外部のユーザー ポリシーを適用するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  **外部アクセス ポリシー**] の下の**サーバー ユーザーのビジネスの Skype を編集**、適用するユーザー ポリシーを選択します。
     
> [!NOTE]  
> ** \<Automatic>** の設定は、既定のサーバーまたはグローバル ポリシーの設定を適用します。


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、ユーザーごとの外部アクセス ポリシーを割り当てる

Windows PowerShell と与える CsExternalAccessPolicy コマンドレットを使用して、ユーザーごとの外部アクセス ポリシーを指定できます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>1 人のユーザーにユーザーごとの外部アクセス ポリシーを設定するのには

  - このコマンドでは、Ken Myer のユーザーに、ユーザーごとの外部アクセス ポリシー RedmondExternalAccessPolicy が割り当てられます。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>複数のユーザーにユーザーごとの外部アクセス ポリシーを設定するのには

  - このコマンドは、アメリカ合衆国の組織単位に Active Directory のアカウントを持つすべてのユーザーに、ユーザーごとの外部アクセス ポリシー USAExternalAccessPolicy を割り当てます。 このコマンドで使用されている OU パラメーターの詳細については、 [Get CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser)コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>ユーザーごとの外部アクセス ポリシーの割り当てを解除するには

  - このコマンド Ken Myer に割り当てられていたすべてのユーザーごとの外部アクセス ポリシー割り当てが解除されます。 ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。 サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



詳細については、[補助金 CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)コマンドレットのヘルプ トピックを参照してください。


