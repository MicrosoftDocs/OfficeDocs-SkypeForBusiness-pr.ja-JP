---
title: 'Lync Server 2013: デバイス更新ルールを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3776fe2b80e301e02c099f3c6154afc1c382d0d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>Lync Server 2013 でデバイス更新ルールを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

デバイス更新ルールを削除すると、デバイス更新キューから完全に削除されます。

ルールの削除は、展開内のデバイスやテストデバイスからの更新プログラムのアンインストールとは異なります。 展開から承認済みの更新プログラムをアンインストールするには、デバイス更新ルールを*復元*します。 詳細については、「 [Lync Server 2013 でデバイス更新ルールを復元する](lync-server-2013-restore-a-device-update-rule.md)」を参照してください。 テストデバイスから承認されていない更新プログラムをアンインストールするには、それを*リセット*します。 詳細については、「 [Lync Server 2013 でデバイス更新ルールをリセットする](lync-server-2013-reset-a-device-update-rule.md)」を参照してください。

Lync Server コントロールパネルまたは Windows PowerShell を使用して、デバイス更新ルールを削除することができます。

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してデバイス更新ルールを削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイスの更新**] ナビゲーションボタンをクリックします。

4.  [**デバイス更新**] ページで、次のいずれかの操作を行います。
    
      - 1つのルールを削除するには、削除するルールを選びます。
    
      - すべてのルールを削除するには、[**編集**] メニューをクリックし、[**すべて選択**] をクリックします。

5.  [**編集**] をクリックして、[**削除**] をクリックします。

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してデバイス更新ルールを削除する

デバイス更新ルールは、Windows PowerShell と**CsDeviceUpdateRule**コマンドレットを使用して削除することもできます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>サーバーから1つのデバイス更新ルールを削除するには

  - 次のコマンドは、atl-cs-001.litwareinc.com 上の Web サーバーから、デバイス更新ルール d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 を削除します。
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>サーバーからすべてのデバイス更新ルールを削除するには

  - このコマンドを実行すると、atl-cs-001.litwareinc.com 上の web サーバーからすべてのデバイス更新ルールが削除されます。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

詳細については、 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でデバイス更新ルールを承認する](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

