---
title: 'Lync Server 2013: Lync Phone Edition のセキュリティ設定を構成する'
description: 'Lync Server 2013: Lync Phone Edition のセキュリティ設定を構成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82e6a6488db66a8497930ee6b2d1aec6fc8b0b2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564353"
---
# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>Lync Server 2013 で Lync Phone Edition のセキュリティ設定を構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

SIP セキュリティ設定および電話ロック設定を使用して、Lync Phone Edition を実行しているデバイスのセキュリティを強化する方法について説明します。

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>Lync Phone Edition のセキュリティ設定を構成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**クライアント**] をクリックし、[**デバイス構成**] をクリックします。

4.  [**デバイス構成**] ページのデバイス構成の一覧で、セキュリティ設定を変更する構成をダブルクリックします。

5.  [**デバイス構成の編集**] の [**SIP セキュリティ**] で、SIP セキュリティ レベルを指定します。既定のレベルは [**高**] (推奨される設定) です。

6.  [**デバイス構成の編集**] の [**電話のロック**] で、[**デバイス ロックの適用**] チェック ボックス (既定ではオン) をオンまたはオフにして、PIN の最小桁数 (既定では 6 桁) とタイムアウト期間 (既定では 10 分) を指定します。これらの既定値を使用するか、または PIN の桁数を大きくするかタイムアウト期間を小さくする (あるいはその両方を行う) ことをお勧めします。
    
    <div>
    

    > [!NOTE]  
    > 詳細については、「 <A href="lync-server-2013-enforce-phone-locking.md">Lync Server 2013 での電話ロックの強制</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して Lync Phone Edition 電話のセキュリティ設定を構成する

セキュリティ設定は、Lync Server 管理シェルと **get-csucphoneconfiguration** コマンドレットを使用して管理できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-modify-the-sip-security-mode"></a>SIP セキュリティ モードを変更するには

  - 次のコマンドでは、UC 電話設定のグローバル コレクションの SIPSecurityMode を Medium に設定します。SIP セキュリティは、Low または High (既定値) に設定することもできます。
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>PIN の最小桁数を変更するには

  - 次の例では、すべての UC 電話設定で必要とされる PIN の最小桁数を 7 桁に変更します。
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

詳細については、「 [get-csucphoneconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 認証の管理](lync-server-2013-managing-lync-server-authentication.md)  


[Lync Server 2013 でのデバイス、電話、クライアントアプリケーションの管理](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

