---
title: 'Lync Server 2013: 電話ロックの適用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61042ebd21786513c482f1286cd9120711d1cfb9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a>Lync Server 2013 での電話ロックの適用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

Lync Phone Edition デバイスは、セキュリティを確保する目的でロックできます。 電話ロックを強制すると、構成した時間が経過した後、Lync Phone Edition を実行しているデバイスがロックされます。 電話がロックされている場合、ユーザーは電話をかけることはできますが、予定表および連絡先情報、ボイスメール、または通話ログにアクセスすることはできません。また、検索を使用することもできません 電話のロックを解除するために、ユーザーは PIN を入力します。

電話ロックを強制するには、Lync Server コントロールパネルまたは Lync Server PowerShell コマンドレットを使用して、電話ロックを有効にし、構成します。 電話のロックは、グローバルに、または構成されているサイト内でのみ強制できます。

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>電話ロックを構成および強制するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  [**クライアント**] をクリックして、[**デバイス構成**] をクリックします。

4.  [**デバイス構成**] タブのデバイス構成のリストで、電話ロックの設定値を変更する構成をダブルクリックします。

5.  [**デバイス構成の編集**] ダイアログ ボックスで、[**デバイス ロックを適用する**] チェック ボックスがオンになっていることを確認します。

6.  [ **Pin の最小の長さ**] で、ロックを解除する pin に含める必要がある最小桁数または新しい値を指定する既定値をそのまま使用します。 PIN の長さの範囲は 4 ~ 15 桁で、既定値は6です。

7.  [**電話のロック**タイムアウト] で、電話が自分にロックされるまでの最短時間の既定値をそのまま使用するか、または新しい値を指定します。 タイムアウトの範囲は 0 ~ 60 分で、既定値は10です。 値は、HH:MM:SS の形式で入力してください。

8.  [**確定**] をクリックします。

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して電話ロックを強制する

電話のロックは、Get-csucphoneconfiguration コマンドレットを使用して適用できます。 このコマンドレットは、Lync Server 2013 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-enable-phone-locking"></a>電話ロックを有効にするには

  - 次のコマンドは、Redmond サイトの電話ロックを有効にします。 電話ロックを無効にするには、EnforcePhoneLock プロパティを False ($False) に設定します。
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>電話のロックを有効にし、電話ロックのタイムアウトを変更するには

  - 次のコマンドは、電話ロックを有効にして、電話ロックのタイムアウトを 30 分に設定します。
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>組織全体での電話ロックを有効にするには

  - 次の例では、組織で使用されているすべての UC 電話構成設定で、電話ロックが有効になります。
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

詳細については、 [get-csucphoneconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration)コマンドレットのヘルプトピックを参照してください。

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

