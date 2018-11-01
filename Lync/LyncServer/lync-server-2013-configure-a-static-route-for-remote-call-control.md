---
title: 'Lync Server 2013: リモート通話コントロールの静的ルートの構成'
TOCTitle: リモート通話コントロールの静的ルートの構成
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48274158
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのリモート通話コントロールの静的ルートの構成

 

_**トピックの最終更新日:** 2012-09-22_

リモート通話コントロールでは、構内交換機 (PBX) に接続される SIP/CSTA ゲートウェイへの Lync Server プールからのパスを使用してすべての Lync Server プールをそれぞれ構成する必要があります。 このパスでは、各プールからそれぞれのゲートウェイへの静的ルートが 1 つ必要です。プールは、このゲートウェイに対して、PBX への通話に関連付けられた SIP 通話コントロール メッセージをプロキシします。 リモート通話コントロール用にグローバル静的ルートを構成すると、プール レベルでの静的ルートを使用した構成が行われていない各プールは、グローバル静的ルートを使用します。

## リモート通話コントロール用の静的ルートを構成するには

1.  RTCUniversalServerAdmins グループまたは、**New-CsStaticRoute** コマンドレットを割り当てた役割ベースのアクセス制御 (RBAC) の役割のメンバーとして、Lync Server 管理シェルがインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  静的ルートを作成して $TLSRoute または $TCPRoute 変数に挿入するには、次のいずれかの操作を行います。
    

    > [!TIP]
    > ドメインの子ドメインを照合するために、MatchUri パラメーターでワイルドカード値を指定できます。 たとえば、<STRONG>*.contoso.net</STRONG> と入力すると、 末尾が <STRONG>contoso.net</STRONG> のドメインが照合されます。

    
      - トランスポート層セキュリティ (TLS) 接続の場合、コマンド プロンプトで次のように入力します。
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        
        次に例を示します。
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        
        UseDefaultCertificate を False に設定する場合、TLSCertIssuer および TLSCertSerialNumber パラメーターを指定する必要があります。 これらのパラメーターは、それぞれ、静的ルートで使用される証明書を発行した証明機関 (CA) の名前とその TLS 証明書のシリアル番号を指定します。 これらのパラメーターの詳細については、コマンド プロンプトで次のように入力して Lync Server 管理シェルのヘルプを参照してください。
        
            Get-Help New-CsStaticRoute -Full
    
      - 伝送制御プロトコル (TCP) 接続の場合、コマンド プロンプトで次のように入力します。
        
        > [!NOTE]  
        > 完全修飾ドメイン名 (FQDN) を指定する場合は、まず、ドメイン ネーム システム (DNS) A レコードを構成する必要があります。
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        
        次に例を示します。
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        
        以下では、静的ルートのオプション パラメーターの既定値を示します。
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        これらの既定値は変更しないことを強くお勧めします。 ただし、これらのパラメーターのいずれかを変更しなければならない場合は、コマンド プロンプトで次のように入力して、Lync Server 管理シェルのヘルプを参照してください。
        
            Get-Help New-CsStaticRoute -Full

4.  新しく作成した静的ルートを 中央管理ストアで引き続き保存するには、必要に応じて、次のいずれかを実行します。
    
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}

     &nbsp;
    
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}

## 関連項目

#### タスク

[Lync Server 2013 でリモート通話コントロールの信頼済みアプリケーション エントリを構成する](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Lync Server 2013 での SIP/CSTA ゲートウェイの IP アドレスの定義](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)

