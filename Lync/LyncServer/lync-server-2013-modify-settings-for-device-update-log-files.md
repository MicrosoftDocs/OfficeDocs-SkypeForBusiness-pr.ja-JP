---
title: 'Lync Server 2013: デバイス更新ログファイルの設定を変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37002e1043f990ae1e726301b9c720af35556201
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>Lync Server 2013 でデバイス更新ログファイルの設定を変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、デバイスの更新情報が組織でどのように記録されるかに関する設定を変更することができます。 次の表では、どの設定が変更可能で、どのツールを使用して設定を変更するかを示しています。

ログ設定は、グローバルに、またはサイトごとに変更したり、適用したりすることができます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>変更方法</th>
<th>使用法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ログファイルの最大サイズ (バイト単位)</p></td>
<td><p>Lync Server コントロール パネル</p>
<p>/</p>
<p>Lync Server 管理シェル</p></td>
</tr>
<tr class="even">
<td><p>キャッシュ内に保持できる情報の最大量 (バイト単位)</p></td>
<td><p>Lync Server コントロール パネル</p>
<p>/</p>
<p>Lync Server 管理シェル</p></td>
</tr>
<tr class="odd">
<td><p>キャッシュされた情報をログファイルに書き込む頻度 (分)</p></td>
<td><p>Lync Server コントロール パネル</p>
<p>/</p>
<p>Lync Server 管理シェル</p></td>
</tr>
<tr class="even">
<td><p>ログファイルを保持する期間 (日数)</p></td>
<td><p>Lync Server コントロール パネル</p>
<p>/</p>
<p>Lync Server 管理シェル</p></td>
</tr>
<tr class="odd">
<td><p>削除する必要がある有効期限が切れたファイルをチェックするタイミング (時刻)</p></td>
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

1.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

2.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイスログの構成**] をクリックします。

3.  [**デバイスログの構成**] ページで、変更する構成をダブルクリックします。

4.  [**ログ設定の編集**] ダイアログボックスで、次のいずれかの設定を変更します。
    
      - **[ファイルの最大サイズ (バイト)**   ] は、ログファイルが削除されるまでの最大サイズを指定します。 既定値は1024000バイト (1 MB) です。
    
      - **[最大キャッシュサイズ (バイト)**   ] は、キャッシュを消去する前にログファイルキャッシュに保持できる情報の最大量 (バイト単位) を指定します。データはログファイルに書き込まれます。 既定値は512000バイト (0.5 MB) です。
    
      - **キャッシュをフラッシュする分数 (1-60)**   ログファイルキャッシュに保存されている情報が実際のログファイルに書き込まれる頻度を示します。 データをログに記録すると、キャッシュが消去されます。 既定値は5分です。
    
      - **ログファイルを保持する日数 (1-365)**   ログファイルが削除されるまで保持される日数を指定します。 既定値は10日です。

5.  [**コミット**] をクリックします。

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したログ設定の変更

デバイス更新ログファイル設定は、Windows PowerShell と**Set-CsDeviceUpdateConfiguration**コマンドレットを使用して変更できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。



</div>

次の例は、 **Set-CsDeviceUpdateConfiguration**を使って設定を変更するいくつかの方法を示しています。

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>ログファイルの最大サイズとログのクリーンアップ間隔を変更するには

  - 次のコマンドは、Redmond サイトに適用されるデバイス更新ログの設定を変更します。 この例では、ログファイルの最大サイズは204800バイトに、ログのクリーンアップ間隔は14日間に設定されています。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>ログのクリーンアップ時間を変更するには

  - このコマンドは、Redmond サイトのログクリーンアップ時間を 3:00 AM に設定します。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

詳細については、「 [Set-CsDeviceUpdateConfiguration 設定](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration)」コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

