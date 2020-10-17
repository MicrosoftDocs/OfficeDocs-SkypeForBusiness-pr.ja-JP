---
title: 'Lync Server 2013: デバイス更新ログファイルの削除'
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
ms.openlocfilehash: 576daa823dfd5bb8e6e7eb8c6bedeaa689780dbe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514464"
---
# <a name="delete-device-update-log-files-in-lync-server-2013"></a>Lync Server 2013 でのデバイス更新ログファイルの削除

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

デバイス更新 Web サービスは、ログファイルの広範なコレクションを保持します。 このコレクションには、サービス自体によって実行された監査ログと、クライアントデバイスからアップロードされたログファイルが含まれます。 サーバーがデバイス更新 Web サービスのログにいっぱいにならないようにするには、特定の日数になっていたログファイルを消去することをお勧めします。 この日数は、更新アクティビティと、組織内のクライアントデバイス数、および Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して設定します。

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してデバイス更新ログをクリアするには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで **[クライアント]** をクリックし、**[デバイス ログ構成]** をクリックします。

3.  **[デバイス ログ構成]** ページで、変更する構成をダブルクリックします。

4.  [ **ログ設定の編集** ] ダイアログボックスの [ **ログファイルを保持する日数 (1-365)**] で、日数を指定します。

5.  [**確定**] をクリックします。 指定した日数を超えるまでサーバー上に存在していたすべてのファイルが削除されます。 この設定は、変更するまでこの構成に適用されます。

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してデバイス更新ログをクリアする

Windows PowerShell を使用してデバイス更新ログをクリアすることができます。また、 **CsDeviceUpdateLog** コマンドレットを使用することもできます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a>1台のサーバー上のデバイス更新ログをクリアするには

  - 次のコマンドを実行すると、Web サーバー atl-cs-001.litwareinc.com のデバイス更新ログがクリアされます。 10日以上経過したすべてのログエントリ (DaysBack パラメーターで指定された値) はログから削除されます。
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a>すべてのデバイス更新ログをクリアするには

  - このコマンドは、組織で現在使用されているすべてのデバイス更新ログから古いエントリ (この例では、10日以上経過したエントリ) を削除します。
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

詳細につい [ては、](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) 「」のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

