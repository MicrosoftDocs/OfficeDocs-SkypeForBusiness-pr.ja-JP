---
title: 'Lync Server 2013: プッシュ通知を構成する'
TOCTitle: プッシュ通知を構成する
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48273710
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でプッシュ通知を構成する

 

_**トピックの最終更新日:** 2013-02-12_

プッシュ通知は、モバイル アプリケーションが非アクティブであっても、バッジ、アイコン、または警告の形式でモバイル デバイスに送信できます。プッシュ通知は、ユーザーに、新規または不在着信の IM 招待状、ボイス メールなどのイベントを通知します。 Lync Server 2013 Mobility Service では、通知がクラウドベースの Lync Server プッシュ通知サービスに送信されます。その通知は、次に Apple Push Notification Service (APNS) ( Lync 2010 Mobile クライアントを実行中の Apple デバイス向け) または Microsoft Push Notification Service (MPNS) ( Lync 2010 Mobile または Lync 2013 モバイル クライアントを実行中の Windows Phone デバイス向け) に送信されます。


> [!IMPORTANT]
> Lync 2010 Mobile または Lync 2013 モバイル クライアントと共に Windows Phone を使用する場合、プッシュ通知は重要な検討事項です。<BR>Apple デバイスで Lync 2010 Mobile を使用する場合、プッシュ通知は重要な検討事項です。<BR>Apple デバイスで Lync 2013 モバイルを使用する場合、プッシュ通知は不要です。



プッシュ通知をサポートするようにトポロジを構成するには、以下を実行します。

  - 環境に Lync Server 2010 または Lync Server 2013エッジ サーバーがある場合は、新しいホスティング プロバイダーである Microsoft Lync Online を追加し、組織と Lync Online 間にホスティング プロバイダーのフェデレーションを設定する必要があります。

  - 環境に Office Communications Server 2007 R2エッジ サーバーがある場合は、push.lync.com との直接的な SIP フェデレーションを設定する必要があります。
    
    > [!NOTE]
    > Push.lync.com は、プッシュ通知サービス用の Microsoft Office 365 ドメインです。


  - プッシュ通知を有効にするには、 **Set-CsPushNotificationConfiguration** コマンドレットを実行する必要があります。既定では、プッシュ通知は無効になっています。

  - フェデレーション設定とプッシュ通知をテストします。

## Lync Server 2013 または Lync Server 2010エッジ サーバーでプッシュ通知を構成するには

1.  Lync Server 管理シェルと Ocscore が RtcUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  Lync Server オンライン ホスティング プロバイダーを追加します。コマンドラインで、次のように入力します。
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    次に例を示します。
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    > [!NOTE]
    > 単一のホスティング プロバイダーに対して複数のフェデレーション関係を持つことはできません。つまり、sipfed.online.lync.com とのフェデレーション関係を持つホスティング プロバイダーを既に設定している場合は、ホスティング プロバイダーの ID が LyncOnline 以外のものであっても、別のホスティング プロバイダーを追加しないでください。


4.  Lync Online で、組織とプッシュ通知サービス間にホスティング プロバイダー フェデレーションを設定します。コマンドラインで、次のように入力します。
    
        New-CsAllowedDomain -Identity "push.lync.com"

## Office Communications Server 2007 R2エッジ サーバーでプッシュ通知を構成するには

1.  RtcUniversalServerAdmins グループのメンバーとして エッジ サーバーにログオンします。

2.  \[**スタート**\] をクリックし、\[**すべてのプログラム**\]、\[**管理ツール**\] をクリックし、\[**コンピューターの管理**\] をクリックします。

3.  コンソール ツリーで、\[**サービスとアプリケーション**\] を展開し、\[**Microsoft Office Communications Server 2007 R2**\] を右クリックして、\[**プロパティ**\] をクリックします。

4.  \[**許可**\] タブをクリックし、\[**追加**\] をクリックします。

5.  \[**フェデレーション パートナーの追加**\] ダイアログ ボックスで、次の操作を行います。
    
      - \[**フェデレーション パートナーのドメイン名**\] に、「**push.lync.com** 」と入力します。
    
      - \[**フェデレーション パートナーのアクセス エッジ サーバー**\] に、「**sipfed.online.lync.com**」と入力します。
    
      - \[**OK**\] をクリックします。

## プッシュ通知を有効にするには

1.  Lync Server 管理シェルおよび Ocscore がインストールされているコンピューターに CsAdministrator の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  プッシュ通知を有効にします。コマンドラインで、次のように入力します。
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  フェデレーションを有効にします。コマンドラインで、次のように入力します。
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

## フェデレーションとプッシュ通知をテストするには

1.  Lync Server 管理シェルおよび Ocscore がインストールされているコンピューターに CsAdministrator の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  フェデレーションの設定をテストします。コマンドラインで、次のように入力します。
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    次に例を示します。
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  プッシュ通知をテストします。コマンドラインで、次のように入力します。
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    次に例を示します。
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

## 関連項目

#### その他のリソース

[Test-CsFederatedPartner](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxPushNotification)

