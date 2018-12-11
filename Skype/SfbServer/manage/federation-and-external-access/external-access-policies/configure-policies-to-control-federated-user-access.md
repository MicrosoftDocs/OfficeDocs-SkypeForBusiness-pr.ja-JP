---
title: フェデレーション ユーザー アクセスを制御するポリシーの構成
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'フェデレーション パートナーとの通信をサポートするためにポリシーを構成する場合は、フェデレーション ドメインのユーザーに、ポリシーが適用されます。 '
ms.openlocfilehash: fcb4b0651c81316e06ab659430c3b0e9e5664e64
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222990"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>ビジネス サーバーの Skype でフェデレーション ユーザー アクセスを制御するポリシーを構成します。

フェデレーション パートナーとの通信をサポートするためにポリシーを構成する場合は、フェデレーション ドメインのユーザーに、ポリシーが適用されます。 フェデレーション ドメインのユーザーがビジネス サーバーのユーザーは、Skype で共同作業を行うかどうかは、コントロールに 1 つまたは複数の外部ユーザー アクセス ポリシーを構成できます。 フェデレーション ユーザー アクセスを制御するには、グローバル ポリシー、サイト、およびユーザー レベルを構成できます。 Skype ビジネスのサーバーのポリシー設定が 1 つのポリシー レベルで適用されるは、別のポリシー レベルで適用される設定をオーバーライドできます。 ビジネス サーバー ポリシーの優先順位の Skype が: ユーザー ポリシー (ほとんどの影響) がサイト ポリシーを上書きし、[サイト ポリシーはグローバル ポリシー (最低限の影響) をよりも優先されます。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。


> [!NOTE]  
> 組織のフェデレーションが有効にしない場合でも、フェデレーション ユーザー アクセスを制御するポリシーを構成できます。 ただし、構成したポリシーは、フェデレーションの組織に対して有効である場合にのみ有効です。 フェデレーションを有効にする方法の詳細[を有効にするかリモート ユーザー アクセスを無効にする](../access-edge/enable-or-disable-remote-user-access.md)を参照してください。  さらに、フェデレーション ユーザー アクセスを制御するユーザー ポリシーを指定する場合は、Skype のビジネス サーバー有効になって、ポリシーを使用するように構成されているユーザーにのみ、ポリシーが適用されます。


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>フェデレーション ドメインのユーザーによるアクセスをサポートするためにポリシーを構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。

3.  左側のナビゲーション ・ バーでは、**外部ユーザー アクセス**をクリックし、**外部アクセス ポリシー**] をクリックします。

4.  [**外部アクセス ポリシー** ] ページで、次のいずれかの操作を行います。
    
      - フェデレーション ユーザー アクセスをサポートするグローバル ポリシーを構成するには、グローバル ポリシーをクリックして**編集**を**の詳細を表示**] をクリックします。
    
      - 新しいサイト ポリシーを作成、[**新規**作成] をクリックし、[**サイト ポリシー**] をクリックします。 ] で**サイトを選択して**、リストから適切なサイトをし、[ **OK**] をクリックします。
    
      - 新しいユーザー ポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザー ポリシー**] をクリックします。 **新しい外部アクセス ポリシー**では、どのユーザー ポリシーは (たとえば、フェデレーション ドメインのユーザーの通信を有効にするユーザー ポリシーの**EnableFederatedUsers** ) を示す [**名**] フィールドに一意の名前を作成します。
    
      - 既存のポリシーを変更するには、表に記載されている適切なポリシー] をクリック**を編集**するには、**の詳細を表示**] をクリックします。

5.  (省略可能)追加または説明を編集する場合は、 **[説明**] にポリシーの情報を指定します。

6.  次のいずれかの操作を行います。
    
      - ポリシーのフェデレーション ユーザー アクセスを有効にするには、**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスを選択します。
    
      - ポリシーのフェデレーション ユーザー アクセスを無効にするには、**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオフにします。

7.  [**確定**] をクリックします。

フェデレーション ユーザー アクセスを有効にするには、また組織でフェデレーションのサポートを有効にする必要があります。 詳細については、[有効にするかフェデレーションとパブリック IM 接続を無効にする](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)を参照してください。

ユーザー ポリシーの場合は、フェデレーション ユーザーと共同作業を行うことができるようにするユーザーにポリシーを適用する必要がありますもします。 詳細については、[外部ユーザー アクセス ポリシーを割り当てる](assign-an-external-user-access-policy.md)を参照してください。

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Windows PowerShell を使用して、フェデレーション ドメインのユーザーによるアクセスをサポートする既存のポリシーを構成するのには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ビジネス用サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、 **Skype**ビジネス サーバーをクリック**ビジネス サーバー管理シェルの Skype**です。

3.  ビジネス サーバー管理シェルには、Skype で次を入力します。
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > "EnablePublicCloudAudioVideoAccess"のパラメーターが対応する選択、Skype のビジネス サーバーのコントロール パネルの


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Windows PowerShell を使用して、フェデレーション ドメインのユーザーによるアクセスをサポートする新しいポリシーを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネスのサーバーの Microsoft の Skype**をクリック**ビジネス サーバー管理シェルの Skype**です。

3.  ビジネス サーバー管理シェルには、Skype で次を入力します。
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    新しいサイト ポリシーを作成する例です。
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>削除するか、フェデレーション ドメインのユーザーによるアクセスをサポートするために Windows PowerShell を使用してポリシーをリセットするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ビジネス サーバー管理シェルには、Skype で以下を入力します。
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    (グローバル ポリシーだけが削除の設定グローバル ポリシーをリセットする際の例します。 ポリシーは削除できません)。
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    サイト ポリシーを削除するには、次のように入力します。
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    レドモンド サイトのポリシーを削除します。 UserEAPPolicy をという名前のユーザー ポリシーを削除するのには次のように入力します。
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>関連項目


[フェデレーションおよびパブリック IM 接続の有効化または無効化](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[外部ユーザー アクセス ポリシーを割り当てる](assign-an-external-user-access-policy.md)

[組織の SIP フェデレーション ドメインの管理](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[組織の SIP フェデレーション プロバイダーの管理](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[新しい-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[許可 CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

