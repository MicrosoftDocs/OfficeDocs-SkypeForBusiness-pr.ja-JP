---
title: 'Lync Server 2013: リモート通話コントロールの静的ルートの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e6a388c602d30e6f60eac0c575d7640f63993f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013 でのリモート通話コントロールの静的ルートの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-22_

リモート通話コントロールでは、すべての Lync Server プールが、そのプールからプライベートブランチ exchange (PBX) に接続する SIP/CSTA ゲートウェイへのパスを使用するように構成されている必要があります。 このパスを使用するには、各プールに1つずつの静的ルートが必要です。各ゲートウェイは、PBX への通話に関連付けられた SIP コールコントロールメッセージをプロキシします。 リモート通話コントロール用にグローバル静的ルートを構成する場合、プールレベルで静的ルートを使用して構成されていない各プールは、グローバル静的ルートを使用します。

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>リモート通話コントロールの静的ルートを構成するには

1.  Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューター、または**新しい CsStaticRoute**コマンドレットを割り当てたロールベースのアクセス制御 (RBAC) ロールとしてログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  静的ルートを作成して、変数 $TLSRoute または $TCPRoute に配置するには、次のいずれかの操作を行います。
    
    <div class="">
    

    > [!TIP]  
    > ドメインの子ドメインと一致させるには、MatchUri パラメーターでワイルドカード値を指定します。 たとえば、 <STRONG>contoso.net</STRONG>のようになります。 この値は、サフィックス<STRONG>contoso.net</STRONG>で終わるドメインと一致します。

    
    </div>
    
      - トランスポート層セキュリティ (TLS) 接続の場合は、コマンドプロンプトで次を入力します。
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        
        次に例を示します。
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        
        UseDefaultCertificate が False に設定されている場合は、TLSCertIssuer パラメーターと TLSCertSerialNumber パラメーターを指定する必要があります。 これらのパラメーターは、静的ルートで使用された証明書を発行した証明機関 (CA) の名前と、その TLS 証明書のシリアル番号を示します。 これらのパラメーターの詳細については、コマンドプロンプトで次を入力して、「Lync Server 管理シェルのヘルプ」を参照してください。
        
            Get-Help New-CsStaticRoute -Full
    
      - 伝送制御プロトコル (TCP) 接続の場合は、コマンドプロンプトで次を入力します。
        
        <div class="">
        

        > [!NOTE]  
        > 完全修飾ドメイン名 (FQDN) を指定した場合は、ドメインネームシステム (DNS) で最初にレコードを設定する必要があります。

        
        </div>
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        
        次に例を示します。
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        
        静的ルートのオプションパラメーターには、次の既定値があります。
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        これらの既定値は変更しないことを強くお勧めします。 ただし、これらのパラメーターを変更する必要がある場合は、コマンドプロンプトで次を入力して、「Lync Server 管理シェルのヘルプ」を参照してください。
        
            Get-Help New-CsStaticRoute -Full

4.  新しく作成された静的ルートを中央管理ストアで保持するには、必要に応じて次のいずれかを実行します。
    
       ```
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でリモート通話コントロールの信頼済みアプリケーション エントリを構成する](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Lync Server 2013 での SIP/CSTA ゲートウェイの IP アドレスの定義](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

