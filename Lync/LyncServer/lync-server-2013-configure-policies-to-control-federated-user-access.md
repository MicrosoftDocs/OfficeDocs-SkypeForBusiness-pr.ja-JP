---
title: 'Lync Server 2013: フェデレーション ユーザー アクセスを制御するポリシーの構成'
TOCTitle: フェデレーション ユーザー アクセスを制御するポリシーの構成
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48272107
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成

 

_**トピックの最終更新日:** 2014-02-05_

フェデレーション パートナーとの通信をサポートするためのポリシーを構成すると、そのポリシーはフェデレーション ドメインのユーザーに適用されます。1 つ以上の外部ユーザー アクセス ポリシーを構成して、フェデレーション ドメインのユーザーが Lync Server 2013 ユーザーと共同作業できるかどうかを制御できます。フェデレーション ユーザー アクセスを制御するために、グローバル レベル、サイト レベル、およびユーザー レベルでポリシーを構成できます。あるポリシー レベルで適用されている Lync Server ポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。Lync Server ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。

> [!NOTE]
> 組織でフェデレーションを有効にしていなくても、フェデレーション ユーザー アクセスを制御するポリシーを構成できます。ただし、構成したポリシーは、組織でフェデレーションを有効にした場合にのみ有効となります。フェデレーションの有効化の詳細については、「展開」または「操作」のドキュメントの「<a href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモート ユーザー アクセスの有効化または無効化</a>」を参照してください。また、フェデレーション ユーザー アクセスを制御するユーザー ポリシーを指定した場合、そのポリシーは Lync Server 2013 で有効であり、そのポリシーを使用するよう構成されているユーザーにのみ適用されます。


## フェデレーション ドメインのユーザーによるアクセスをサポートするためのポリシーを構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**外部ユーザー アクセス**\] をクリックし、\[**外部アクセス ポリシー**\] をクリックします。

4.  \[**外部アクセス ポリシー**\] ページで、次のいずれかの操作を行います。
    
      - フェデレーション ユーザー アクセスをサポートするようにグローバル ポリシーを構成するには、グローバル ポリシーをクリックし、\[**編集**\] に続いて \[**詳細の表示**\] をクリックします。
    
      - 新しいサイト ポリシーを作成するには、\[**新規作成**\] をクリックし、\[**サイト ポリシー**\] をクリックします。 \[**サイトの選択**\] で一覧から適切なサイトをクリックし、\[**OK**\] をクリックします。
    
      - 新しいユーザー ポリシーを作成するには、\[**新規作成**\] をクリックし、\[**ユーザー ポリシー**\] をクリックします。 \[**新しい外部アクセス ポリシー**\] の \[**名前**\] フィールドで、ユーザー ポリシーの適用範囲を示す一意の名前を作成します (たとえば、フェデレーション ドメイン ユーザーの通信を有効にするユーザー ポリシーの場合、**EnableFederatedUsers** という名前を作成します)。
    
      - 既存のポリシーを変更するには、表に表示されている適切なポリシーをクリックし、\[**編集**\] に続いて \[**詳細の表示**\] をクリックします。

5.  (オプション) 説明を追加または編集する場合は、\[**説明**\] でポリシーの情報を指定します。

6.  次のいずれかの操作を行います。
    
      - ポリシーのフェデレーション ユーザー アクセスを有効にするには、\[**フェデレーション ユーザーとの通信を有効にする**\] チェック ボックスをオンにします。
    
      - ポリシーのフェデレーション ユーザー アクセスを無効にするには、\[**フェデレーション ユーザーとの通信を有効にする**\] チェック ボックスをオフにします。

7.  \[**確定**\] をクリックします。

フェデレーション ユーザー アクセスを有効にするには、組織でフェデレーションのサポートも有効にする必要があります。詳細については、「[Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)」を参照してください。

ユーザー ポリシーの場合、フェデレーション ユーザーと共同作業できるようにするユーザーにもポリシーを適用する必要があります。詳細については、「[Lync Server 2013 での Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)」を参照してください。

## フェデレーション ドメインのユーザーによるアクセスをサポートするために Windows PowerShellを使用して既存のポリシーを構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  Lync Server 管理シェルで次のコマンドを入力します。
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    
    フェデレーション ユーザー アクセス、XMPP ドメイン アクセス、リモート ユーザー アクセス、およびパブリック プロバイダー アクセスを有効にし、パブリック プロバイダーの音声とビデオを使用できるようにするグローバル ポリシーを設定するコマンドの例を次に示します。
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    

    > [!TIP]
    > Lync Server コントロール パネルには、"EnablePublicCloudAudioVideoAccess" パラメーターに対応する選択項目はありません。



## フェデレーション ドメインのユーザーによるアクセスをサポートするために Windows PowerShellを使用して新しいポリシーを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  Lync Server 管理シェルで次のコマンドを入力します。
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    新しいサイト ポリシーを作成する例を次に示します。
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

## フェデレーション ドメインのユーザーによるアクセスをサポートするために Windows PowerShellを使用してポリシーを削除またはリセットするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルで次のコマンドを入力します。
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    グローバル ポリシーをリセットする例を次に示します (グローバル ポリシーは設定のみを削除できます。ポリシー自体を削除することはできません)。
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    サイト ポリシーを削除するには、次のコマンドを入力します。
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    Redmond というサイト ポリシーを削除します。UserEAPPolicy というユーザー ポリシーを削除するには、次のコマンドを入力します。
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

## 関連項目

#### タスク

[Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[Lync Server 2013 での Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  

#### その他のリソース

[Lync Server 2013 での組織の SIP フェデレーション ドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Lync Server 2013 での組織の SIP フェデレーション プロバイダーの管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

