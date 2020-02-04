---
title: 'Lync Server 2013: デバイス更新ログファイルを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c684978445f727dc155fade59654ff6e2866f084
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a>Lync Server 2013 でデバイス更新ログファイルを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

デバイス更新 Web サービスは、ログファイルの広範なコレクションを保持します。 このコレクションには、サービス自体によって実行された監査ログとクライアントデバイスからアップロードされたログファイルの両方が含まれます。 サーバーがデバイス更新 Web サービスログでいっぱいにならないようにするには、一定の期間、使用されていたログファイルを消去する必要があります。 この日数は、更新アクティビティと組織内のクライアントデバイスの数に基づいて、および Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して設定します。

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してデバイス更新ログを消去するには

1.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

2.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイスログの構成**] をクリックします。

3.  [**デバイスログの構成**] ページで、変更する構成をダブルクリックします。

4.  [**ログ設定の編集**] ダイアログボックスで、[**ログファイルを保持する日数 (1-365)**] に日数を指定します。

5.  [**コミット**] をクリックします。 指定した日数を超えてサーバー上に存在するすべてのファイルが削除されます。 この設定は、変更するまでこの構成に適用されます。

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してデバイスの更新ログを消去する

デバイス更新ログは、Windows PowerShell と、ユーザーの**クリアな Deviceupdatelog**コマンドレットを使用してクリアできます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a>1台のサーバーでデバイス更新ログを消去するには

  - 次のコマンドは、Web サーバー atl-cs-001.litwareinc.com のデバイス更新ログをクリアします。 10日以上経過しているすべてのログエントリ (DaysBack パラメーターで指定された値) はログから削除されます。
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a>すべてのデバイス更新ログを消去するには

  - このコマンドを実行すると、組織で現在使用されているすべてのデバイス更新ログから古いエントリ (この例では、10日以上経過したエントリ) が削除されます。
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

詳細については、「 [CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog)コマンドレット」のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

