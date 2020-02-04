---
title: 'Lync Server 2013: 電話のロックを適用する'
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
ms.openlocfilehash: 9c781c09db1834d85a1df4532d1484e43d74ca48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a>Lync Server 2013 での電話のロックを適用する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

Lync Phone Edition のデバイスは、セキュリティのためにロックすることができます。 電話のロックを適用した場合、Lync Phone Edition を実行しているデバイスは、一定の時間が経過した後でロックされます。 電話がロックされている場合、ユーザーは電話をかけることはできますが、予定表や連絡先情報、ボイスメール、通話ログにアクセスしたり、検索を使用したりすることはできません。 電話のロックを解除するために、ユーザーは PIN を入力します。

電話のロックを適用するには、Lync Server コントロールパネルまたは Lync Server PowerShell コマンドレットを使用して、電話のロックを有効にして構成します。 電話のロックは、グローバルに適用することも、構成されているサイト内でのみ強制することもできます。

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>電話のロックを構成して強制するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  [**クライアント**] をクリックし、[**デバイスの構成**] をクリックします。

4.  [**デバイス構成**] タブのデバイス構成の一覧で、電話のロックの設定を変更する構成をダブルクリックします。

5.  [**デバイス構成の編集**] ダイアログボックスで、[**デバイスのロックを強制**する] チェックボックスがオンになっていることを確認します。

6.  **Pin の最小の長さ**には、ロック解除ピンに含まれている、または新しい値を指定する必要がある最小桁数の既定値をそのまま使用します。 PIN の長さの範囲は 4 ~ 15 桁で、既定値は6です。

7.  **電話ロックのタイムアウト**では、電話をロックするか、または新しい値を指定するまでの時間の長さに応じて、既定値をそのまま使用します。 タイムアウトの範囲は 0 ~ 60 分で、既定値は10です。 値は、HH:MM:SS の形式で入力してください。

8.  [**コミット**] をクリックします。

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して電話のロックを適用する

電話のロックを適用するには、CsUCPhoneConfiguration コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-enable-phone-locking"></a>電話のロックを有効にするには

  - 次のコマンドは、Redmond サイトの電話のロックを有効にします。 電話のロックを無効にするには、EnforcePhoneLock プロパティを False ($False) に設定します。
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>電話のロックを有効にし、電話のロックタイムアウトを変更するには

  - このコマンドにより、電話のロックが有効になり、電話のロックタイムアウトも30分に設定されます。
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>組織全体で電話のロックを有効にするには

  - この例では、組織で使用されているすべての UC 電話構成設定で電話のロックが有効になっています。
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

詳細については、 [CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration)コマンドレットのヘルプトピックを参照してください。

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

