---
title: フェデレーション ユーザー アクセスを制御するポリシーの構成
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
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
description: 'フェデレーションパートナーとの通信をサポートするようにポリシーを構成すると、フェデレーションドメインのユーザーにポリシーが適用されます。 '
ms.openlocfilehash: 2e9385436427fd73f90e308d7747cf304bf37501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818318"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Skype for Business Server でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する

フェデレーションパートナーとの通信をサポートするようにポリシーを構成すると、フェデレーションドメインのユーザーにポリシーが適用されます。 フェデレーションドメインのユーザーが Skype for Business Server ユーザーと共同作業できるかどうかを制御するために、1つ以上の外部ユーザーアクセスポリシーを構成することができます。 フェデレーションされたユーザーアクセスを制御するには、グローバル、サイト、ユーザーレベルでポリシーを構成できます。 1つのポリシーレベルで適用される Skype for Business Server のポリシー設定は、別のポリシーレベルで適用されている設定を上書きすることができます。 Skype for Business Server のポリシーの優先順位: ユーザーポリシー (ほとんどの影響) でサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。


> [!NOTE]  
> 組織でフェデレーションを有効にしていない場合でも、フェデレーションされたユーザーアクセスを制御するためのポリシーを構成できます。 ただし、構成したポリシーは、組織でフェデレーションが有効になっている場合にのみ有効になります。 フェデレーションを有効にする方法について詳しくは、「[リモートユーザーアクセスを有効または無効](../access-edge/enable-or-disable-remote-user-access.md)にする」をご覧ください。  また、フェデレーションされたユーザーアクセスを制御するユーザーポリシーを指定した場合、このポリシーは、Skype for Business Server が有効になっていて、ポリシーを使用するように構成されているユーザーにのみ適用されます。


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>フェデレーションドメインのユーザーによるアクセスをサポートするようにポリシーを構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。

4.  [**外部アクセスポリシー** ] ページで、次のいずれかの操作を行います。
    
      - フェデレーションされたユーザーアクセスをサポートするようにグローバルポリシーを構成するには、グローバルポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。
    
      - 新しいサイトポリシーを作成するには、[**新規**作成] をクリックし、[**サイトポリシー**] をクリックします。 [**サイトの選択**] で、一覧から該当するサイトをクリックし、[ **OK]** をクリックします。
    
      - 新しいユーザーポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザーポリシー**] をクリックします。 [**新しい外部アクセスポリシー**] で、[**名前**] フィールドに、ユーザーポリシーがどのようなものであるかを示す一意の名前を作成します (たとえば、フェデレーションされたドメインユーザーの通信を有効にするユーザーポリシーの**EnableFederatedUsers** )。
    
      - 既存のポリシーを変更するには、表に記載されている適切なポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  省略説明を追加または編集する場合は、ポリシーの情報を [**説明**] で指定します。

6.  次のいずれかを実行します。
    
      - ポリシーのフェデレーションされたユーザーアクセスを有効にするには、[**フェデレーションユーザーとの通信を有効**にする] チェックボックスをオンにします。
    
      - ポリシーのフェデレーションされたユーザーアクセスを無効にするには、[フェデレーションされ**たユーザーとの通信を有効**にする] チェックボックスをオフにします。

7.  [**コミット**] をクリックします。

フェデレーションされたユーザーアクセスを有効にするには、組織のフェデレーションのサポートも有効にする必要があります。 詳細について[は、「フェデレーションとパブリック IM 接続を有効または無効](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)にする」を参照してください。

ユーザーポリシーの場合は、フェデレーションされたユーザーと共同作業できるようにするユーザーにもポリシーを適用する必要があります。 詳細については、「[外部ユーザーアクセスポリシーを割り当てる](assign-an-external-user-access-policy.md)」を参照してください。

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Windows PowerShell を使用して既存のポリシーを構成し、フェデレーションドメインのユーザーによるアクセスをサポートするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Skype for Busines Server Management Shell を起動します。 [**スタート**]、[**すべてのプログラム**] の順にクリックし、[ **skype for business server**] をクリックして、[ **skype for business server 管理シェル**] をクリックします。

3.  Skype for Business Server 管理シェルで次のように入力します。
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > Skype for Business Server コントロールパネルで、"EnablePublicCloudAudioVideoAccess" のパラメーターに対応する項目が選択されていません


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>フェデレーションドメインのユーザーによるアクセスをサポートするために、Windows PowerShell を使用して新しいポリシーを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Skype for Business Server 管理シェルを開始します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft skype for Business server**]、[ **skype for business server 管理シェル**] の順にクリックします。

3.  Skype for Business Server 管理シェルで次のように入力します。
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    新しいサイトポリシーを作成する例:
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>フェデレーションドメインのユーザーによるアクセスをサポートするために Windows PowerShell を使用してポリシーを削除またはリセットするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Skype for Business Server 管理シェルで次のように入力します。
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    グローバルポリシーをリセットする例です (グローバルポリシーではその設定のみを削除できます)。 ポリシーは削除できません):
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    サイトポリシーを削除するには、次のように入力します。
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    サイトポリシーレドモンドを削除します。 UserEAPPolicy という名前のユーザーポリシーを削除するには、次のように入力します。
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>関連項目


[フェデレーションおよびパブリック IM 接続の有効化または無効化](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[外部ユーザー アクセス ポリシーの割り当て](assign-an-external-user-access-policy.md)

[組織の SIP フェデレーション ドメインの管理](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[組織の SIP フェデレーション プロバイダーの管理](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

