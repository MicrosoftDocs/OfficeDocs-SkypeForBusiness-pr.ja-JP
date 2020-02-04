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
ms.openlocfilehash: d0416092c7021d599ec7e516d72c19e8baa3c598
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a>Lync Server 2013 でデバイス更新ルールを復元する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

展開したデバイスからデバイス更新ルールをアンインストールするには、デバイスを復元します。 デバイス更新ルールを復元すると、更新プログラムがアンインストールされ、そのルールの以前のバージョンが再インストールされます。

Lync Server コントロールパネルまたは Windows PowerShell を使用して、デバイス更新ルールを復元することができます。

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してデバイス更新ルールを復元するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイスの更新**] ナビゲーションボタンをクリックします。

4.  [**デバイス更新**] ページで、次のいずれかの操作を行います。
    
      - 1つのルールを復元するには、そのルールを選びます。
    
      - すべてのルールを復元するには、[**編集**] をクリックし、[**すべて選択**] をクリックします。

5.  [**操作**] メニューをクリックし、[**復元**] をクリックします。

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してデバイス更新ルールを復元する

デバイス更新ルールは、Windows PowerShell と**CsDeviceUpdateRule**コマンドレットを使用して復元することもできます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a>サーバー上の1つのデバイス更新ルールを復元するには

  - 次のコマンドは、デバイス更新ルール d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 を Web サーバー atl-cs-001.litwareinc.com に復元します。
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a>サーバー上のすべてのデバイス更新ルールを復元するには

  - このコマンドは、web サーバー atl-cs-001.litwareinc.com 上のすべてのデバイス更新ルールを復元します。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

詳細については、「 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule)コマンドレットのヘルプ」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

