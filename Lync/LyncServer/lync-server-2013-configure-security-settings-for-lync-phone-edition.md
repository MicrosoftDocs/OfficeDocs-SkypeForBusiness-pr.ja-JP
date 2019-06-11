---
title: 'Lync Server 2013: Lync Phone Edition のセキュリティ設定を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7bd44b5d3f466728ac1dbe928c08b1f4786f8fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>Lync Server 2013 で Lync Phone Edition のセキュリティ設定を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

SIP セキュリティ設定と電話ロック設定を使用して、Lync Phone Edition を実行しているデバイスのセキュリティを向上させます。

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>Lync Phone Edition のセキュリティ設定を構成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイスの構成**] をクリックします。

4.  [**デバイスの構成**] ページのデバイス構成の一覧で、セキュリティ設定を変更する構成をダブルクリックします。

5.  [**デバイス構成の編集**] の [ **sip セキュリティ**] で、sip セキュリティレベルを指定します。 既定のレベルは**High**で、これを使用することをお勧めします。

6.  [**デバイス構成の編集**] の [**電話のロック**] で、[デバイスの**ロックを強制**する] チェックボックスをオンまたはオフにします (既定で選択されています)。 PIN の最小の長さ (既定では6文字) とタイムアウト期間 (既定では10分) を指定します。 既定の設定を使用するか、PIN の長さを大きくするか、またはタイムアウト期間を短くすることをお勧めします。
    
    <div>
    

    > [!NOTE]  
    > 詳細については、「 <A href="lync-server-2013-enforce-phone-locking.md">Lync Server 2013 で電話のロックを適用</A>する」を参照してください。

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、Lync Phone Edition Phone のセキュリティ設定を構成する

セキュリティ設定を管理するには、Lync Server 管理シェルと**CsUCPhoneConfiguration**コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-modify-the-sip-security-mode"></a>SIP セキュリティモードを変更するには

  - このコマンドは、UC 電話設定のグローバルコレクションの SIPSecurityMode を Medium に設定します。 SIP セキュリティは、低または高 (既定値) に設定することもできます。
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>PIN の最小文字数を変更するには

  - この例では、すべての UC 携帯電話の設定が変更され、PIN の長さを7桁以上にする必要があります。
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

詳細については、「 [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 認証の管理](lync-server-2013-managing-lync-server-authentication.md)  


[Lync Server 2013 でのデバイス、電話、クライアント アプリケーションの管理](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

