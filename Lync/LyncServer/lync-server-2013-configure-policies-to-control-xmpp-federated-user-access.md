---
title: 'Lync Server 2013: XMPP フェデレーションユーザーアクセスを制御するポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98c1cce84068681640d0b19ad0f604e9a0e518c9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Lync Server 2013 での XMPP フェデレーションユーザーアクセスを制御するポリシーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

このドキュメントは暫定版であり、変更される可能性があります。 空白のトピックがプレースホルダーとして含まれています。

XMPP (eXtensible Messaging and Presence Protocol) フェデレーション パートナーをサポートするポリシーを構成すると、そのポリシーは XMPP フェデレーション ドメインのユーザーには適用されますが、SIP (セッション開始プロトコル) インスタント メッセージング (IM) サービス プロバイダー (Windows Live など) のユーザーや、SIP フェデレーション ドメインのユーザーには適用されません。 ユーザーが連絡先を追加して通信できるようにする XMPP フェデレーションドメインごとに**Xmpp フェデレーションパートナー**を構成します。 XMPP フェデレーションパートナーポリシーは単一のスコープでのみ使用できますが、グローバルポリシーとして定義されていませんが、グローバルポリシーとして機能します。 XMPP フェデレーションパートナーのグローバル、サイト、またはユーザーポリシーを定義するには、まず、必要なスコープの外部アクセスポリシーを作成して構成することによって、ポリシースコープを構成します。 外部アクセスおよびフェデレーションに対して構成できるポリシーの種類の詳細については、「操作」のドキュメントの「[管理フェデレーション」および「Lync Server 2013 への外部アクセス」を](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)参照してください。

<div>


> [!NOTE]  
> <STRONG>フェデレーションおよび外部アクセス</STRONG> ポリシーは、インバンド プロビジョニングを通じて適用されます。 ユーザーに適用されるポリシー、サイトに所属するポリシー、またはスコープ内のグローバル ポリシーは、ログイン時にクライアントとの間でやり取りされます。 組織で XMPP フェデレーションを有効にしていない場合でも、XMPP フェデレーション パートナーのアクセスを制御するポリシーを構成できます。 ただし、これらのポリシーが有効になるのは、組織に XMPP パートナー フェデレーションが展開、有効化、および構成されている場合に限られます。 XMPP パートナーフェデレーションの展開と構成の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリックインスタントメッセージングの構成</A>」を参照してください。 また、外部アクセスポリシーで XMPP フェデレーションパートナーを制御するユーザーポリシーを指定した場合、このポリシーは Lync Server 2013 が有効になっていて、そのポリシーを使用するように構成されているユーザーにのみ適用されます。



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>XMPP フェデレーション パートナーのグローバル ポリシーを編集するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。

4.  [**外部アクセス ポリシー**] ページで、グローバル ポリシーに対して、次の操作を行います。

5.  グローバル ポリシーをクリックし、[**編集**] をクリックして、[詳細の表示] をクリックします。

6.  グローバル ポリシーの説明を指定します (オプション)。

7.  [**フェデレーション ユーザーとの通信を有効にする**] を選択します。

8.  [**XMPP フェデレーション ユーザーとの通信を有効にする**] を選択します。

9.  [**コミット**] をクリックして、グローバル ポリシーに加えた変更を保存します。

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>XMPP フェデレーション パートナーのサイト ポリシーまたはユーザー ポリシーを作成するには

1.  [**新規**] をクリックし、[**サイト ポリシー**] または [**ユーザー ポリシー**] をクリックします。[**サイトの選択**] で、一覧から適切なサイトをクリックし、[**OK**] をクリックします。

2.  サイト ポリシーの説明を指定します (オプション)。

3.  サイト ポリシーまたはユーザー ポリシーで、[**フェデレーション ユーザーとの通信を有効にする**] を選択します。

4.  [**XMPP フェデレーション ユーザーとの通信を有効にする**] をオンにします。

5.  [**コミット**] をクリックして、サイト ポリシーまたはユーザー ポリシーに加えた変更を保存します。

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>XMPP フェデレーション パートナーの既存のポリシーを編集するには

1.  既存のポリシーを変更するには、一覧から該当するポリシーを選択し、[**編集**]、[**詳細の表示**] の順にクリックします。

2.  ポリシーの説明を変更または更新します (オプション)。

3.  [**フェデレーション ユーザーとの通信を有効にする**] を選択または選択解除します。

4.  [**XMPP フェデレーション ユーザーとの通信を有効にする**] を選択または選択解除します。

5.  [**コミット**] をクリックして、ポリシーに加えた変更を保存します。

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Windows PowerShell を使用して XMPP フェデレーションパートナーの既存のポリシーを編集するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  Lync Server 管理シェルで、次のように入力します。
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    フェデレーションユーザーアクセスのグローバルポリシーを True (有効) に、XMPP ドメインアクセスを True (有効) に設定するコマンドの例を次に示します。
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>Windows PowerShell を使用して XMPP フェデレーションパートナーのサイトポリシーまたはユーザーポリシーを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  Lync Server 管理シェルで、次のように入力します。
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    このサンプル コマンドは、フェデレーション ユーザーのアクセスと XMPP ドメインのアクセスに対して、サイト ポリシー (Redmond サイト用) をそれぞれ有効に設定します。
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Windows PowerShell を使用して XMPP フェデレーションパートナーの既存のポリシーを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  Lync Server 管理シェルで、次のように入力します。
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    次のサンプル コマンドは、ユーザー ポリシーを削除します。
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  次のサンプル コマンドは、グローバル ポリシーを既定値にリセットします。
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Lync が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Lync Server 2013 での XMPP フェデレーションパートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

