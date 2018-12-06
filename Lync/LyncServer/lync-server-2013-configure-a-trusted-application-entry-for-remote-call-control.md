---
title: 'Lync Server 2013: リモート通話コントロールの信頼済みアプリケーション エントリを構成する'
TOCTitle: リモート通話コントロールの信頼済みアプリケーション エントリを構成する
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48271768
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でリモート通話コントロールの信頼済みアプリケーション エントリを構成する

 

_**トピックの最終更新日:** 2015-11-02_

Lync Server で静的ルートを適用して通話をゲートウェイにルーティングする目的で、信頼されたアプリケーションとして SIP/CSTA ゲートウェイを構成する必要があります。


> [!IMPORTANT]
> Lync Server の前のバージョンの展開からユーザーを移行する場合、このトピックの手順を実行する前に、SIP/CSTA ゲートウェイ用に作成した既存の信頼されたアプリケーション エントリ (以前は承認済みホスト エントリと呼ばれていました) がすべて削除されていることを確認します。詳細については、「<A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Lync Server 2013 での従来の承認済みホストの削除 (オプション)</A>」を参照してください。



## SIP/CSTA ゲートウェイの信頼されたアプリケーション エントリを構成するには

1.  Lync Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバー、または **New-CsTrustedApplicationPool** コマンドレットを割り当てた役割ベースのアクセス制御 (RBAC) の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  信頼されたアプリケーション エントリを作成するには、次のどちらかの操作を行います。
    
      - トランスポート層セキュリティ (TLS) 接続の場合、コマンド プロンプトで次のように入力します。
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        次に例を示します。
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - 伝送制御プロトコル (TCP) 接続の場合、コマンド プロンプトで次のように入力します。
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        次に例を示します。
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  信頼されたアプリケーションをプールに追加するには、次のどちらかの操作を行います。
    
      - TLS 接続の場合、コマンド プロンプトで次のように入力します。
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        次に例を示します。
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - TCP 接続の場合、コマンド プロンプトで次のように入力します。
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        次に例を示します。
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  トポロジに対して行った公開された変更を実装するには、コマンド プロンプトで次のように入力します。
    
        Enable-CsTopology

## 関連項目

#### タスク

[Lync Server 2013 でのリモート通話コントロールの静的ルートの構成](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Lync Server 2013 での SIP/CSTA ゲートウェイの IP アドレスの定義](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)

