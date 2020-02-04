---
title: 'Lync Server 2013: デバイス更新ルールを承認する'
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
ms.openlocfilehash: 8bb464d0845f70012bdd8e70365c8a7993de6b4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a>Lync Server 2013 でデバイス更新ルールを承認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

デバイス更新ルールをインポートした後は、テストデバイスにインストールされます。 テストが成功し、組織に更新プログラムをロールアウトする場合は、Lync Server コントロールパネルまたは Windows PowerShell を使用して承認します。

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してデバイス更新ルールを承認するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  [**デバイス更新**] ページで、次のいずれかの操作を行います。
    
      - 1つのルールを承認するには、そのルールを選びます。
    
      - すべてのルールを承認するには、[**編集**] をクリックし、[**すべて選択**] をクリックします。

4.  [**アクション**] をクリックし、[**承認**] をクリックします。

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してデバイス更新ルールを承認する

デバイス更新ルールは、Windows PowerShell と**CsDeviceUpdateRule**コマンドレットを使用して承認することもできます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a>1つのデバイス更新ルールを承認するには

  - 次のコマンドは、Web サーバーの atl-cs-001.litwareinc.com で検出されたデバイス更新ルール d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 を承認します。
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a>複数のデバイス更新ルールを承認するには

  - このコマンドは、Microsoft 製デバイスのすべてのデバイス更新ルールを承認します。
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

詳細については、「[承認-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でデバイス更新ルールをインポートする](lync-server-2013-import-device-update-rules.md)  
[Lync Server 2013 でデバイス更新ルールを復元する](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

