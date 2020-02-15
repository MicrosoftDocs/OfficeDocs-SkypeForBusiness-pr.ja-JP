---
title: 'Lync Server 2013: デバイス更新ログファイルの設定の変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 770682cfed17d9b029688275469351c1cfdf9f4d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>Lync Server 2013 のデバイス更新ログファイルの設定を変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、組織内でのデバイス更新情報のログ記録方法の設定を変更できます。 次の表に、変更可能な設定と、設定の変更に使用するツールを示します。

ログ設定は、グローバルに、またはサイトごとに変更することができます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>を変更する</th>
<th>使用法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ログファイルの最大サイズ (バイト単位)</p></td>
<td><p>Lync Server コントロール パネル</p>
<p>または</p>
<p>Lync Server 管理シェル</p></td>
</tr>
<tr class="even">
<td><p>キャッシュに保持できる情報の最大量 (バイト単位)</p></td>
<td><p>Lync Server コントロール パネル</p>
<p>または</p>
<p>Lync Server 管理シェル</p></td>
</tr>
<tr class="odd">
<td><p>キャッシュされた情報をログファイルに書き込む頻度 (分単位)</p></td>
<td><p>Lync Server コントロール パネル</p>
<p>または</p>
<p>Lync Server 管理シェル</p></td>
</tr>
<tr class="even">
<td><p>ログファイルを保持する時間 (日数)</p></td>
<td><p>Lync Server コントロール パネル</p>
<p>または</p>
<p>Lync Server 管理シェル</p></td>
</tr>
<tr class="odd">
<td><p>削除する必要のある期限切れファイルがあるかどうかをチェックする時間 (日)</p></td>
<td><p>Lync Server 管理シェル</p></td>
</tr>
<tr class="even">
<td><p>許可するログファイル拡張子</p></td>
<td><p>Lync Server 管理シェル</p></td>
</tr>
<tr class="odd">
<td><p>保持するログファイルの種類</p></td>
<td><p>Lync Server 管理シェル</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してログ設定を変更するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで **[クライアント]** をクリックし、**[デバイス ログ構成]** をクリックします。

3.  **[デバイス ログ構成]** ページで、変更する構成をダブルクリックします。

4.  [**ログ設定の編集**] ダイアログボックスで、次のいずれかの設定を変更します。
    
      - **[最大ファイルサイズ (バイト)**   ] ログファイルが削除されるまでの最大サイズを指定します。 既定値は1024000バイト (1 MB) です。
    
      - **[最大キャッシュサイズ (バイト)**   ] は、キャッシュがクリアされてデータがログファイルに書き込まれる前に、ログファイルキャッシュに保持できる最大情報量 (バイト単位) を指定します。 既定値は512000バイト (0.5 MB) です。
    
      - **キャッシュをフラッシュする時間 (分) (1-60)**   は、ログファイルキャッシュに格納されている情報が実際のログファイルに書き込まれる頻度を示します。 データがログに記録されると、キャッシュはクリアされます。 既定値は5分です。
    
      - **ログファイルを保持する日数 (1-365)**   削除されるまでにログファイルを保持する日数を指定します。 既定値は10日です。

5.  **[確定]** をクリックします。

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してログ設定を変更する

デバイス更新のログファイルの設定を変更するには、Windows PowerShell と、 **-CsDeviceUpdateConfiguration 設定**コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

次の例は、設定を変更するために、 **Set-CsDeviceUpdateConfiguration**を使用するいくつかの方法を示しています。

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>ログファイルの最大サイズとログのクリーンアップ間隔を変更するには

  - 次のコマンドは、Redmond サイトに適用されているデバイス更新ログ設定を変更します。 この例では、ログファイルの最大サイズを204800バイトに設定し、ログのクリーンアップ間隔を14日に設定します。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>ログのクリーンアップ時間 (日) を変更するには

  - このコマンドは、Redmond サイトのログのクリーンアップ時間を 3:00 AM に設定します。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

詳細につい[ては、このコマンドレット](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration)のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

