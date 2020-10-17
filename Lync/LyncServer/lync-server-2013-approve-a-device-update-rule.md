---
title: 'Lync Server 2013: デバイス更新ルールの承認'
description: 'Lync Server 2013: デバイス更新ルールを承認します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 127d16dad6329e952b9033db07ac2f4a4fe9112c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550723"
---
# <a name="approve-a-device-update-rule-in-lync-server-2013"></a>Lync Server 2013 でのデバイス更新ルールの承認

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

デバイス更新ルールをインポートした後、それはテストデバイスにインストールされます。 テストが成功し、更新プログラムを組織に展開する場合は、Lync Server コントロールパネルまたは Windows PowerShell を使用して承認する必要があります。

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してデバイス更新ルールを承認するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  [ **デバイスの更新** ] ページで、次のいずれかの操作を行います。
    
      - 1つのルールを承認するには、そのルールを選択します。
    
      - すべてのルールを承認するには、[ **編集**] をクリックし、[ **すべて選択**] をクリックします。

4.  [ **アクション**] をクリックし、[ **承認**] をクリックします。

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してデバイス更新ルールを承認する

デバイス更新ルールは、Windows PowerShell と **get-csdeviceupdaterule** コマンドレットを使用して承認することもできます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a>単一のデバイス更新ルールを承認するには

  - 次のコマンドは、d5ce3c10-2588-420a-82ac-dc2d9b1222ff9-82ac-82ac-dc2d9b1222ff9 が Web サーバー atl-cs-001.litwareinc.com で検出されたデバイス更新ルールを承認します。
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a>複数のデバイス更新ルールを承認するには

  - このコマンドは、Microsoft ブランドデバイスのすべてのデバイス更新ルールを承認します。
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

詳細については、 [get-csdeviceupdaterule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのデバイス更新ルールのインポート](lync-server-2013-import-device-update-rules.md)  
[Lync Server 2013 でのデバイス更新ルールの復元](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

