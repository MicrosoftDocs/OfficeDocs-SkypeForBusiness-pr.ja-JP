---
title: 'Lync Server 2013: リモート通話コントロールの静的ルートを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41e871e3023449123af76530659397e1faa6b51d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013 でリモート通話コントロールの静的ルートを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-22_

リモート通話コントロールを使用するには、すべての Lync Server プールが、そのプールから、構内交換 (PBX) に接続する SIP/CSTA ゲートウェイへのパスで構成されている必要があります。 このパスでは、各プールに、PBX への通話に関連付けられた SIP 通話制御メッセージをプロキシする、各ゲートウェイに対して1つの静的ルートが必要です。 リモート通話コントロールのグローバル静的ルートを構成する場合、プールレベルで静的ルートを使用して構成されていない各プールは、グローバル静的ルートを使用します。

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>リモート通話コントロール用の静的ルートを構成するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバー、または、**新しい-CsStaticRoute**コマンドレットを割り当てた役割ベースのアクセス制御 (RBAC) の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  静的ルートを作成して $TLSRoute または $TCPRoute 変数に挿入するには、次のいずれかの操作を行います。
    
    <div class="">
    

    > [!TIP]  
    > ドメインの子ドメインを照合するために、MatchUri パラメーターでワイルドカード値を指定できます。 たとえば、<STRONG>*.contoso.net</STRONG> と入力すると、 末尾が <STRONG>contoso.net</STRONG> のドメインが照合されます。

    
    </div>
    
      - トランスポート層セキュリティ (TLS) 接続の場合、コマンド プロンプトで次のように入力します。
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        次にその例を示します。
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        UseDefaultCertificate を False に設定する場合、TLSCertIssuer および TLSCertSerialNumber パラメーターを指定する必要があります。 これらのパラメーターは、それぞれ、静的ルートで使用される証明書を発行した証明機関 (CA) の名前とその TLS 証明書のシリアル番号を指定します。 これらのパラメーターの詳細については、コマンドプロンプトで次のように入力して、「Lync Server Management Shell Help」を参照してください。
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - 伝送制御プロトコル (TCP) 接続の場合、コマンド プロンプトで次のように入力します。
        
        <div class="">
        

        > [!NOTE]  
        > 完全修飾ドメイン名 (FQDN) を指定する場合は、まず、ドメイン ネーム システム (DNS) A レコードを構成する必要があります。

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        次にその例を示します。
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        以下では、静的ルートのオプション パラメーターの既定値を示します。
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        これらの既定値は変更しないことを強くお勧めします。 ただし、これらのパラメーターのいずれかを変更する必要がある場合は、コマンドプロンプトで次のように入力して、「Lync Server Management Shell Help」を参照してください。
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  中央管理ストアで新しく作成された静的ルートを保持するには、必要に応じて次のいずれかを実行します。
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのリモート通話コントロールの信頼済みアプリケーションエントリを構成する](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Lync Server 2013 での SIP/CSTA ゲートウェイの IP アドレスの定義](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

