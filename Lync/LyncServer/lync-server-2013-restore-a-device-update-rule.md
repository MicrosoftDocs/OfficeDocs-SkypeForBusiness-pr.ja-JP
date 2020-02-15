---
title: 'Lync Server 2013: デバイス更新ルールを復元する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 728adc1384738d93fc7ac4506a55621830c7de39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a>Lync Server 2013 でのデバイス更新ルールの復元

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

展開内のデバイスからデバイス更新ルールをアンインストールするには、それを復元します。 デバイス更新ルールを復元すると、どちらも更新プログラムがアンインストールされ、そのルールの以前のバージョンが再インストールされます。

デバイス更新ルールを復元するには、Lync Server コントロールパネルまたは Windows PowerShell を使用します。

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してデバイス更新ルールを復元するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーションバーで [**クライアント**] をクリックし、[**デバイスの更新**] ナビゲーションボタンをクリックします。

4.  [**デバイスの更新**] ページで、次のいずれかの操作を行います。
    
      - 1つのルールを復元するには、そのルールを選択します。
    
      - すべてのルールを復元するには、[**編集**] をクリックし、[**すべて選択**] をクリックします。

5.  [**アクション**] メニューをクリックし、[**復元**] をクリックします。

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してデバイス更新ルールを復元する

デバイス更新ルールは、Windows PowerShell と**get-csdeviceupdaterule**コマンドレットを使用して復元することもできます。. このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a>単一のデバイス更新ルールをサーバーに復元するには

  - 次のコマンドは、d5ce3c10-2588-420a-82ac-dc2d9b1222ff9-82ac-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com のデバイス更新ルールを復元します。
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a>サーバー上のすべてのデバイス更新ルールを復元するには

  - このコマンドは、web サーバー atl-cs-001.litwareinc.com 上のすべてのデバイス更新ルールを復元します。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

詳細については、 [get-csdeviceupdaterule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

