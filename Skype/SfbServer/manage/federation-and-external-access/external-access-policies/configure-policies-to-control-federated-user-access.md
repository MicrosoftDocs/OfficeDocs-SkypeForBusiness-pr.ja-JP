---
title: フェデレーションユーザーアクセスを制御するポリシーの構成
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
description: 'フェデレーション パートナーとの通信をサポートするためのポリシーを構成すると、そのポリシーはフェデレーション ドメインのユーザーに適用されます。 '
ms.openlocfilehash: 447aad751ce6fc91bf2d6b80c8a14e92f9d4da82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037407"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Skype for Business Server でフェデレーションユーザーアクセスを制御するポリシーの構成

フェデレーション パートナーとの通信をサポートするためのポリシーを構成すると、そのポリシーはフェデレーション ドメインのユーザーに適用されます。 1つ以上の外部ユーザーアクセスポリシーを構成して、フェデレーションドメインのユーザーが Skype for Business Server ユーザーと共同作業できるかどうかを制御できます。 フェデレーション ユーザー アクセスを制御するために、グローバル レベル、サイト レベル、およびユーザー レベルでポリシーを構成できます。 1つのポリシーレベルで適用されている Skype for Business Server のポリシー設定は、別のポリシーレベルで適用される設定を上書きすることができます。 Skype for Business Server のポリシーの優先順位は次のとおりです。ユーザーポリシー (最も影響を与える) はサイトポリシーを上書きし、サイトポリシーはグローバルポリシーよりも優先されます (影響が少なくなります)。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。


> [!NOTE]  
> 組織でフェデレーションを有効にしていなくても、フェデレーション ユーザー アクセスを制御するポリシーを構成できます。 ただし、構成したポリシーは、組織でフェデレーションを有効にした場合にのみ有効となります。 フェデレーションの有効化の詳細については、「 [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md)」を参照してください。  また、フェデレーションユーザーアクセスを制御するユーザーポリシーを指定した場合、このポリシーは Skype for Business Server が有効になっていて、そのポリシーを使用するように構成されているユーザーにのみ適用されます。


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>フェデレーション ドメインのユーザーによるアクセスをサポートするためのポリシーを構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。

4.  [**外部アクセス ポリシー**] ページで、次のいずれかの操作を行います。
    
      - フェデレーション ユーザー アクセスをサポートするようにグローバル ポリシーを構成するには、グローバル ポリシーをクリックし、[**編集**] に続いて [**詳細の表示**] をクリックします。
    
      - 新しいサイト ポリシーを作成するには、[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。 [**サイトの選択**] で一覧から適切なサイトをクリックし、[**OK**] をクリックします。
    
      - 新しいユーザー ポリシーを作成するには、[**新規作成**] をクリックし、[**ユーザー ポリシー**] をクリックします。 [**新しい外部アクセス ポリシー**] の [**名前**] フィールドで、ユーザー ポリシーの適用範囲を示す一意の名前を作成します (たとえば、フェデレーション ドメイン ユーザーの通信を有効にするユーザー ポリシーの場合、**EnableFederatedUsers** という名前を作成します)。
    
      - 既存のポリシーを変更するには、表に表示されている適切なポリシーをクリックし、[**編集**] に続いて [**詳細の表示**] をクリックします。

5.  (オプション) 説明を追加または編集する場合は、[**説明**] でポリシーの情報を指定します。

6.  次のどちらかの操作を行います。
    
      - ポリシーのフェデレーション ユーザー アクセスを有効にするには、[**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオンにします。
    
      - ポリシーのフェデレーション ユーザー アクセスを無効にするには、[**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオフにします。

7.  [**確定**] をクリックします。

フェデレーション ユーザー アクセスを有効にするには、組織でフェデレーションのサポートも有効にする必要があります。 詳細については、「 [Enable or disable federation and PUBLIC IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)」を参照してください。

ユーザー ポリシーの場合、フェデレーション ユーザーと共同作業できるようにするユーザーにもポリシーを適用する必要があります。 詳細については、「[外部ユーザーアクセスポリシーの割り当て](assign-an-external-user-access-policy.md)」を参照してください。

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Windows PowerShell を使用して既存のポリシーを構成し、フェデレーションドメインのユーザーによるアクセスをサポートするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Skype for Busines サーバー管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for Business server**]、[ **skype for business server 管理シェル**] の順にクリックします。

3.  Skype for Business Server 管理シェルで次のように入力します。
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > パラメーター "EnablePublicCloudAudioVideoAccess" には、Skype for Business Server コントロールパネルで対応する選択項目がありません


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Windows PowerShell を使用して、フェデレーションドメインのユーザーによるアクセスをサポートする新しいポリシーを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Skype for Business server**]、[ **skype for business server 管理シェル**] の順にクリックします。

3.  Skype for Business Server 管理シェルで次のように入力します。
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    新しいサイト ポリシーを作成する例を次に示します。
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Windows PowerShell を使用してポリシーを削除またはリセットして、フェデレーションドメインのユーザーによるアクセスをサポートするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Skype for Business Server 管理シェルで次のように入力します。
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    グローバル ポリシーをリセットする例を次に示します (グローバル ポリシーは設定のみを削除できます。ポリシー自体を削除することはできません)。
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    サイト ポリシーを削除するには、次のコマンドを入力します。
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Redmond というサイト ポリシーを削除します。 UserEAPPolicy というユーザー ポリシーを削除するには、次のコマンドを入力します。
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>関連項目


[フェデレーションとパブリック IM 接続を有効または無効にする](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[外部ユーザーアクセスポリシーの割り当て](assign-an-external-user-access-policy.md)

[組織の SIP フェデレーションドメインの管理](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[組織の SIP フェデレーションプロバイダーの管理](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

