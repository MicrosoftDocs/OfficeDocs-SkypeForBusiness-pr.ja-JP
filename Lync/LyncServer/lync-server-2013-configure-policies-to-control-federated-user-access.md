---
title: 'Lync Server 2013: フェデレーション ユーザー アクセスを制御するポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fb009561c36395ee31a49986f2db0103cbe096b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a>Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-05_

フェデレーションパートナーとの通信をサポートするようにポリシーを構成すると、フェデレーションドメインのユーザーにポリシーが適用されます。 フェデレーションドメインのユーザーが Lync Server 2013 ユーザーと共同作業できるかどうかを制御するために、1つ以上の外部ユーザーアクセスポリシーを構成することができます。 フェデレーションされたユーザーアクセスを制御するには、グローバル、サイト、ユーザーレベルでポリシーを構成できます。 1つのポリシーレベルで適用される Lync Server ポリシーの設定は、別のポリシーレベルで適用されている設定を上書きすることができます。 Lync Server ポリシーの優先順位: ユーザーポリシー (ほとんどの影響) によってサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。

<div>


> [!NOTE]  
> 組織でフェデレーションを有効にしていない場合でも、フェデレーションされたユーザーアクセスを制御するためのポリシーを構成できます。 ただし、構成したポリシーは、組織でフェデレーションが有効になっている場合にのみ有効になります。 フェデレーションを有効にする方法について詳しくは、展開ドキュメントまたは運用ドキュメントの「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスを有効または無効</A>にする」をご覧ください。 また、フェデレーションされたユーザーアクセスを制御するユーザーポリシーを指定した場合、このポリシーは、Lync Server 2013 で有効になっていて、ポリシーを使用するように構成されているユーザーにのみ適用されます。



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>フェデレーションドメインのユーザーによるアクセスをサポートするようにポリシーを構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。

4.  [**外部アクセスポリシー** ] ページで、次のいずれかの操作を行います。
    
      - フェデレーションされたユーザーアクセスをサポートするようにグローバルポリシーを構成するには、グローバルポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。
    
      - 新しいサイトポリシーを作成するには、[**新規**作成] をクリックし、[**サイトポリシー**] をクリックします。 [**サイトの選択**] で、一覧から該当するサイトをクリックし、[ **OK]** をクリックします。
    
      - 新しいユーザーポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザーポリシー**] をクリックします。 [**新しい外部アクセスポリシー**] で、[**名前**] フィールドに、ユーザーポリシーがどのようなものであるかを示す一意の名前を作成します (たとえば、フェデレーションされたドメインユーザーの通信を有効にするユーザーポリシーの**EnableFederatedUsers** )。
    
      - 既存のポリシーを変更するには、表に記載されている適切なポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  省略説明を追加または編集する場合は、ポリシーの情報を [**説明**] で指定します。

6.  次のいずれかの操作を行います。
    
      - ポリシーのフェデレーションされたユーザーアクセスを有効にするには、[**フェデレーションユーザーとの通信を有効**にする] チェックボックスをオンにします。
    
      - ポリシーのフェデレーションされたユーザーアクセスを無効にするには、[フェデレーションされ**たユーザーとの通信を有効**にする] チェックボックスをオフにします。

7.  [**コミット**] をクリックします。

フェデレーションされたユーザーアクセスを有効にするには、組織のフェデレーションのサポートも有効にする必要があります。 詳細については、「 [Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にする」を参照してください。

ユーザーポリシーの場合は、フェデレーションされたユーザーと共同作業できるようにするユーザーにもポリシーを適用する必要があります。 詳細については、「 [Lync Server 2013 で lync を有効にしたユーザーに外部ユーザーアクセスポリシーを割り当てる](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)」を参照してください。

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Windows PowerShell を使用して既存のポリシーを構成し、フェデレーションドメインのユーザーによるアクセスをサポートするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  Lync Server 管理シェルで、次のように入力します。
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    フェデレーションされたユーザーアクセスのグローバルポリシーを enabled に設定するコマンドの例。 XMPP ドメインへのアクセスは有効、リモートユーザーアクセスは有効、パブリックプロバイダーアクセスを有効にするには、次のようにします。
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > パラメーター "EnablePublicCloudAudioVideoAccess" には、Lync Server のコントロールパネルで対応する選択がありません。

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>フェデレーションドメインのユーザーによるアクセスをサポートするために、Windows PowerShell を使用して新しいポリシーを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  Lync Server 管理シェルで、次のように入力します。
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    新しいサイトポリシーを作成する例:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>フェデレーションドメインのユーザーによるアクセスをサポートするために Windows PowerShell を使用してポリシーを削除またはリセットするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルで次のように入力します。
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    グローバルポリシーをリセットする例です (グローバルポリシーではその設定のみを削除できます)。 ポリシーは削除できません):
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    サイトポリシーを削除するには、次のように入力します。
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    サイトポリシーレドモンドを削除します。 UserEAPPolicy という名前のユーザーポリシーを削除するには、次のように入力します。
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[Lync Server 2013 での Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[Lync Server 2013 での組織の SIP フェデレーション ドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Lync Server 2013 での組織の SIP フェデレーション プロバイダーの管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

