---
title: 'Lync Server 2013: XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成'
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
ms.openlocfilehash: cc79a915d0735f87c0852dff0ba4228b1e391fd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Lync Server 2013 での XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

このドキュメントは暫定版であり、変更される可能性があります。 空白のトピックがプレースホルダーとして含まれています。

拡張メッセージングとプレゼンスプロトコル (XMPP) フェデレーションパートナーをサポートするためにポリシーを構成すると、そのポリシーは XMPP フェデレーションドメインのユーザーに適用されますが、セッション開始プロトコル (SIP) のインスタントメッセージング (IM) サービスプロバイダーのユーザーには適用されません。(たとえば、Windows Live など)、または SIP フェデレーションドメイン。 ユーザーが連絡先を追加して通信できるようにする、各 XMPP フェデレーションドメインに対して**Xmpp フェデレーションパートナー**を構成します。 XMPP フェデレーションパートナーのポリシーは1つのスコープでのみ使用できますが、グローバルポリシーとして定義されていませんが、グローバルポリシーとして機能します。 XMPP フェデレーションパートナー用のグローバル、サイト、またはユーザーのポリシーを定義するには、まず、必要なスコープの外部アクセスポリシーを作成して構成することによって、ポリシーのスコープを構成します。 外部アクセスとフェデレーションに対して構成できるポリシーの種類の詳細については、操作のドキュメントで「 [Lync Server 2013 へのフェデレーションと外部アクセスを管理する](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)」を参照してください。

<div>


> [!NOTE]  
> すべての<STRONG>フェデレーションと外部アクセス</STRONG>ポリシーは、インバンドプロビジョニングによって適用されます。 ユーザーに適用されるポリシー、サイトに属しているポリシー、またはスコープ内のグローバルのポリシーは、ログイン時にクライアントに伝達されます。 組織に対して XMPP フェデレーションを有効にしていない場合でも、ポリシーを構成して XMPP フェデレーションパートナーアクセスを制御することができます。 ただし、構成したポリシーは、XMPP パートナーフェデレーションが展開されていて、有効になっており、組織で構成されている場合にのみ有効になります。 XMPP パートナーフェデレーションの展開と構成の詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013 で SIP フェデレーション、XMPP フェデレーションおよびパブリックインスタントメッセージングを構成する</A>」を参照してください。 さらに、外部アクセスポリシーのユーザーポリシーを指定して XMPP フェデレーションパートナーを制御している場合、ポリシーは Lync Server 2013 で有効になっていて、ポリシーを使用するように構成されているユーザーにのみ適用されます。



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>XMPP フェデレーションパートナーのグローバルポリシーを編集するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。

4.  [**外部アクセスポリシー** ] ページで、グローバルポリシーに対して次の操作を行います。

5.  グローバルポリシーをクリックし、[**編集**] をクリックして、[詳細の表示] をクリックします。

6.  グローバルポリシーの説明を入力します (省略可能)。

7.  [**フェデレーションユーザーとの通信を有効にする**] を選択します。

8.  [ **XMPP フェデレーションユーザーとの通信を有効にする**] を選択します。

9.  [**コミット**] をクリックして、変更内容をグローバルポリシーに保存します。

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>XMPP フェデレーションパートナーのサイトまたはユーザーポリシーを作成するには

1.  [**新規作成**] をクリックし、[**サイトポリシー** ] または [**ユーザーポリシー**] をクリックします。 [**サイトの選択**] で、一覧から該当するサイトをクリックし、[ **OK]** をクリックします。

2.  サイトポリシーの説明を入力します (省略可能)。

3.  サイトまたはユーザーポリシーで、[**フェデレーションされたユーザーとの通信を有効にする**] を選択します。

4.  [ **XMPP フェデレーションユーザーとの通信を有効にする**] を選択します。

5.  [**コミット**] をクリックして、サイトまたはユーザーポリシーの変更を保存します。

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>XMPP フェデレーションパートナーの既存のポリシーを編集するには

1.  既存のポリシーを変更するには、一覧で適切なポリシーを選択し、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

2.  ポリシーの説明を変更または更新します (省略可能)。

3.  [**フェデレーションユーザーとの通信を有効にする**] をオンまたはオフにします。

4.  [ **XMPP フェデレーションユーザーとの通信を有効にする**] をオンまたはオフにします。

5.  [**コミット**] をクリックして、変更内容をポリシーに保存します。

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Windows PowerShell を使用して XMPP フェデレーションパートナーの既存のポリシーを編集するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  Lync Server 管理シェルで、次のように入力します。
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    フェデレーションされたユーザーアクセスのグローバルポリシーを True (有効) と XMPP ドメインアクセスの True (有効) に設定するコマンドの例です。
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>Windows PowerShell を使用して XMPP フェデレーションパートナー用のサイトまたはユーザーポリシーを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  Lync Server 管理シェルで、次のように入力します。
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    フェデレーションされたユーザーアクセスを有効にして、XMPP ドメインアクセスを有効にするために Redmond サイトのサイトポリシーを設定するコマンドの例を次に示します。
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Windows PowerShell を使用して XMPP フェデレーションパートナーの既存のポリシーを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  Lync Server 管理シェルで、次のように入力します。
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    ユーザーポリシーを削除するコマンドの例を次に示します。
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  グローバルポリシーを既定値にリセットするコマンドの例を次に示します。
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
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

