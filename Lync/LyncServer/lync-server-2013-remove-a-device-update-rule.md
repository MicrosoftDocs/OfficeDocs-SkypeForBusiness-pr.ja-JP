---
title: 'Lync Server 2013: デバイス更新ルールを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28b02da5927b6a33cabefd005a8f026ca65f99b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>Lync Server 2013 のデバイス更新ルールを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

デバイス更新ルールを削除すると、デバイス更新キューから完全に取得されます。

ルールを削除することと、展開内のデバイスから、またはテストデバイスから更新プログラムをアンインストールすることは異なります。 承認済みの更新プログラムを展開からアンインストールするには、デバイス更新ルールを*復元*します。 詳細については、「 [Lync Server 2013 でのデバイス更新ルールの復元](lync-server-2013-restore-a-device-update-rule.md)」を参照してください。 テストデバイスからまだ承認されていない更新プログラムをアンインストールするには、それを*リセット*します。 詳細については、「 [Lync Server 2013 のデバイス更新ルールをリセットする](lync-server-2013-reset-a-device-update-rule.md)」を参照してください。

デバイス更新ルールを削除するには、Lync Server コントロールパネルまたは Windows PowerShell を使用します。

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してデバイス更新ルールを削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーションバーで [**クライアント**] をクリックし、[**デバイスの更新**] ナビゲーションボタンをクリックします。

4.  [**デバイスの更新**] ページで、次のいずれかの操作を行います。
    
      - 1つのルールを削除するには、削除するルールを選択します。
    
      - すべてのルールを削除するには、[**編集**] メニューをクリックし、[**すべて選択**] をクリックします。

5.  [**編集**] をクリックして、[**削除**] をクリックします。

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してデバイス更新ルールを削除する

デバイス更新ルールは、Windows PowerShell と**get-csdeviceupdaterule**コマンドレットを使用して削除することもできます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>サーバーから1つのデバイス更新ルールを削除するには

  - 次のコマンドは、atl-cs-001.litwareinc.com の Web サーバーから 2588-420a-82ac-dc2d9b1222ff9-82ac-82ac-dc2d9b1222ff9 のデバイス更新ルール d5ce3c10 を削除します。
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>サーバーからすべてのデバイス更新ルールを削除するには

  - このコマンドは、atl-cs-001.litwareinc.com 上の web サーバーからすべてのデバイス更新ルールを削除します。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

詳細については、 [get-csdeviceupdaterule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのデバイス更新ルールの承認](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

