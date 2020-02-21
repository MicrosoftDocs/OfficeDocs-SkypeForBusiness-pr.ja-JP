---
title: 'Lync Server 2013: プッシュ通知の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad1967bea18e0a03ac3a34bf187c1248ec5a1ab2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>Lync Server 2013 でのプッシュ通知の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-12_

プッシュ通知は、バッジ、アイコン、または通知の形式で、モバイルアプリケーションが非アクティブな場合でもモバイルデバイスに送信できます。 プッシュ通知は、ユーザーに、新規または不在着信の IM 招待状、ボイス メールなどのイベントを通知します。 Lync Server 2013 Mobility Service は、クラウドベースの Lync Server プッシュ通知サービスに通知を送信します。これにより、Apple プッシュ通知サービス (APNS) (Lync 2010 モバイルクライアントを実行している Apple デバイスの場合) に通知が送信されます。Microsoft プッシュ通知サービス (MPNS) (Lync 2010 Mobile または Lync 2013 モバイルクライアントを実行している Windows Phone デバイス用)。

<div>


> [!IMPORTANT]  
> Lync 2010 mobile または Lync 2013 Mobile クライアントで Windows Phone を使用する場合、プッシュ通知は重要な考慮事項です。<BR>Apple デバイスで Lync 2010 Mobile を使用する場合、プッシュ通知は重要な考慮事項です。<BR>Apple デバイスで Lync 2013 Mobile を使用する場合、プッシュ通知は不要になります。



</div>

プッシュ通知をサポートするようにトポロジを構成するには、次の手順を実行します。

  - 使用している環境に Lync Server 2010 または Lync Server 2013 エッジサーバーがある場合は、新しいホスティングプロバイダーである Microsoft Lync Online を追加して、組織と Lync Online の間のホスティングプロバイダーフェデレーションを設定する必要があります。

  - ご使用の環境に Office Communications Server 2007 R2 エッジサーバーがある場合は、push.lync.com との直接 SIP フェデレーションを設定する必要があります。
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com は、プッシュ通知サービス用の Microsoft Office 365 ドメインです。

    
    </div>

  - プッシュ通知を有効にするには、 **Set-Cspの設定**コマンドレットを実行する必要があります。 既定では、プッシュ通知はオフになっています。

  - フェデレーション構成とプッシュ通知をテストします。

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>Lync server 2013 または Lync Server 2010 エッジサーバーでプッシュ通知を構成するには

1.  Lync Server 管理シェルと Ocscore がインストールされているコンピューターに、RtcUniversalServerAdmins グループのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  Lync Server online ホスティングプロバイダーを追加します。 コマンドラインで、次のように入力します。
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    次に例を示します。
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > 1つのホスティングプロバイダーとの間に複数のフェデレーション関係を設定することはできません。 つまり、sipfed.online.lync.com とのフェデレーション関係を持つホスティングプロバイダーを既にセットアップしている場合は、ホスティングプロバイダーの id が Nm-lynconline-w15-long 以外のものであっても、別のホスティングプロバイダーを追加しないでください。

    
    </div>

4.  組織と、Lync Online のプッシュ通知サービスとの間のホスティングプロバイダーフェデレーションを設定します。 コマンドラインで、次のように入力します。
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>Office Communications Server 2007 R2 エッジサーバーでプッシュ通知を構成するには

1.  RtcUniversalServerAdmins グループのメンバーとしてエッジサーバーにログオンします。

2.  [**スタート**]、[**すべてのプログラム**]、[**管理ツール**]、[**コンピューターの管理**] の順にクリックします。

3.  コンソールツリーで、[**サービスとアプリケーション**] を展開し、[ **Microsoft Office Communications Server 2007 R2**] を右クリックし、[**プロパティ**] をクリックします。

4.  [**許可**] タブで、[**追加**] をクリックします。

5.  [**フェデレーションパートナーの追加**] ダイアログボックスで、次の操作を行います。
    
      - [**フェデレーションパートナーのドメイン名**] に、「 **push.lync.com**」と入力します。
    
      - [**フェデレーションパートナーのアクセスエッジサーバー**] で、「 **sipfed.online.lync.com**」と入力します。
    
      - **[OK]** をクリックします。

</div>

<div>

## <a name="to-enable-push-notifications"></a>プッシュ通知を有効にするには

1.  Lync Server 管理シェルと Ocscore がインストールされているコンピューターに CsAdministrator の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  プッシュ通知を有効にします。 コマンドラインで、次のように入力します。
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  フェデレーションを有効にします。 コマンドラインで、次のように入力します。
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>フェデレーションとプッシュ通知をテストするには

1.  Lync Server 管理シェルと Ocscore がインストールされているコンピューターに CsAdministrator の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  フェデレーション構成をテストします。 コマンドラインで、次のように入力します。
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    次に例を示します。
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  プッシュ通知をテストします。 コマンドラインで、次のように入力します。
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    次に例を示します。
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a>関連項目


[Test-csfederatedpartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[テスト-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

