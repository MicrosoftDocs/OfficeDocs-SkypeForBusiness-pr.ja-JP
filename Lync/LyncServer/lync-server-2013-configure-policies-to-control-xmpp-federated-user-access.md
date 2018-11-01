---
title: 'Lync Server 2013: XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成'
TOCTitle: XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ552446(v=OCS.15)
ms:contentKeyID: 49115200
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成

 

_**トピックの最終更新日:** 2012-11-01_

このドキュメントは暫定版であり、変更される可能性があります。空白のトピックがプレースホルダーとして含まれています。

Extensible Messaging and Presence Protocol (XMPP) フェデレーション パートナーをサポートするためのポリシーを構成すると、それらのポリシーは XMPP フェデレーション ドメインのユーザーに適用されますが、セッション開始プロトコル (SIP) インスタント メッセージング (IM) サービス プロバイダー (たとえば、Windows Live) または SIP フェデレーション ドメインのユーザーには適用されません。**XMPP フェデレーション パートナー**は、ユーザーに対して連絡先の追加と通信を許可する XMPP フェデレーション ドメインごとに構成します。XMPP フェデレーション パートナー ポリシーは、単一のスコープ内でのみ使用できます。また、XMPP フェデレーション パートナー ポリシーは、グローバル ポリシーとしては定義されませんが、グローバル ポリシーとして機能します。XMPP フェデレーション パートナーを対象としたグローバル ポリシー、サイト ポリシー、またはユーザー ポリシーを定義するには、ポリシーのスコープを構成します。そのためには、まず、外部アクセス ポリシーを作成し、必要なスコープに合わせてそのポリシーを構成します。外部アクセスとフェデレーション用に構成できるポリシーの種類の詳細については、「操作」のドキュメントの「[Lync Server 2013 へのフェデレーションおよび外部アクセスの管理](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)」を参照してください。

> [!NOTE]
> <strong>フェデレーションおよび外部アクセス</strong> ポリシーは、インバンド プロビジョニングを通じて適用されます。ユーザーに適用されるポリシー、サイトに所属するポリシー、またはスコープ内のグローバル ポリシーは、ログイン時にクライアントとの間でやり取りされます。組織で XMPP フェデレーションを有効にしていない場合でも、XMPP フェデレーション パートナーのアクセスを制御するポリシーを構成できます。ただし、これらのポリシーが有効になるのは、組織に XMPP パートナー フェデレーションが展開、有効化、および構成されている場合に限られます。XMPP パートナー フェデレーションの展開および構成の詳細については、「展開」のドキュメントの「<a href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリック インスタント メッセージングの構成</a>」を参照してください。また、外部アクセス ポリシーのユーザー ポリシーを指定して XMPP フェデレーション パートナーを制御する場合、そのポリシーは、Lync Server 2013 に対して有効で、かつそのポリシーを使用するように構成されているユーザーに対してのみ適用されます。


## XMPP フェデレーション パートナーのグローバル ポリシーを編集するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**外部ユーザー アクセス**\] をクリックし、\[**外部アクセス ポリシー**\] をクリックします。

4.  \[**外部アクセス ポリシー**\] ページで、グローバル ポリシーに対して、次の操作を行います。

5.  グローバル ポリシーをクリックし、\[**編集**\] をクリックして、\[詳細の表示\] をクリックします。

6.  グローバル ポリシーの説明を指定します (オプション)。

7.  \[**フェデレーション ユーザーとの通信を有効にする**\] を選択します。

8.  \[**XMPP フェデレーション ユーザーとの通信を有効にする**\] を選択します。

9.  \[**コミット**\] をクリックして、グローバル ポリシーに加えた変更を保存します。

## XMPP フェデレーション パートナーのサイト ポリシーまたはユーザー ポリシーを作成するには

1.  \[**新規**\] をクリックし、\[**サイト ポリシー**\] または \[**ユーザー ポリシー**\] をクリックします。\[**サイトの選択**\] で、一覧から適切なサイトをクリックし、\[**OK**\] をクリックします。

2.  サイト ポリシーの説明を指定します (オプション)。

3.  サイト ポリシーまたはユーザー ポリシーで、\[**フェデレーション ユーザーとの通信を有効にする**\] を選択します。

4.  \[**XMPP フェデレーション ユーザーとの通信を有効にする**\] を選択します。

5.  \[ **確定** \] をクリックして、サイトまたはユーザー ポリシーへの変更を保存します。

## XMPP フェデレーション パートナーの既存のポリシーを編集するには

1.  既存のポリシーを変更するには、一覧から該当するポリシーを選択し、\[**編集**\]、\[**詳細の表示**\] の順にクリックします。

2.  ポリシーの説明を変更または更新します (オプション)。

3.  \[**フェデレーション ユーザーとの通信を有効にする**\] を選択または選択解除します。

4.  \[**XMPP フェデレーション ユーザーとの通信を有効にする**\] を選択または選択解除します。

5.  \[**コミット**\] をクリックして、ポリシーに加えた変更を保存します。

## Windows PowerShell を使用して XMPP フェデレーション パートナーの既存のポリシーを編集するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  Lync Server 管理シェルで次のコマンドを入力します。
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    次のサンプル コマンドは、フェデレーション ユーザーのアクセスと XMPP ドメインのアクセスに対して、グローバル ポリシーをそれぞれ True (有効) に設定します。
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

## Windows PowerShell を使用して XMPP フェデレーション パートナー用のサイト ポリシーまたはユーザー ポリシーを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  Lync Server 管理シェルで次のコマンドを入力します。
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    このサンプル コマンドは、フェデレーション ユーザーのアクセスと XMPP ドメインのアクセスに対して、サイト ポリシー (Redmond サイト用) をそれぞれ有効に設定します。
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

## Windows PowerShell を使用して XMPP フェデレーション パートナーの既存のポリシーを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  Lync Server 管理シェルで次のコマンドを入力します。
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    次のサンプル コマンドは、ユーザー ポリシーを削除します。
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  次のサンプル コマンドは、グローバル ポリシーを既定値にリセットします。
    
        Remove-CsExternalAccessPolicy -Identity global

## 関連項目

#### タスク

[Lync Server 2013 での Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  

#### その他のリソース

[Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

