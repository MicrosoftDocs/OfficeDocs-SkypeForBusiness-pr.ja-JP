---
title: デバイス更新プログラム ログ ファイルの設定を変更する
TOCTitle: デバイス更新プログラム ログ ファイルの設定を変更する
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48273006
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# デバイス更新プログラム ログ ファイルの設定を変更する

 

_**トピックの最終更新日:** 2015-03-09_

Lync Server コントロール パネルまたは Lync Server 管理シェルを使用して、デバイス更新情報が組織でログに記録される方法の設定を変更できます。以下の表は、どの設定が編集可能か、そして、設定を変更するには、どのツールを使用するかを示します。

ログ設定は、グローバルまたはサイトごとに変更して適用できます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>変更対象</th>
<th>使用項目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ログ ファイルの最大サイズ (バイト単位)</p></td>
<td><p>Lync Server コントロール パネル</p>
<p>- または -</p>
<p>Lync Server 管理シェル</p></td>
</tr>
<tr class="even">
<td><p>キャッシュに保持できる情報の最大サイズ (バイト単位)</p></td>
<td><p>Lync Server コントロール パネル</p>
<p>- または -</p>
<p>Lync Server 管理シェル</p></td>
</tr>
<tr class="odd">
<td><p>キャッシュした情報をログ ファイルに書き込む間隔 (分単位)</p></td>
<td><p>Lync Server コントロール パネル</p>
<p>- または -</p>
<p>Lync Server 管理シェル</p></td>
</tr>
<tr class="even">
<td><p>ログ ファイルを保持する期間 (日単位)</p></td>
<td><p>Lync Server コントロール パネル</p>
<p>- または -</p>
<p>Lync Server 管理シェル</p></td>
</tr>
<tr class="odd">
<td><p>期限切れのファイルを削除する必要があるか確認する時間 (時刻)</p></td>
<td><p>Lync Server 管理シェル</p></td>
</tr>
<tr class="even">
<td><p>どのログ ファイル拡張子を認めるか</p></td>
<td><p>Lync Server 管理シェル</p></td>
</tr>
<tr class="odd">
<td><p>どのログ ファイルの種類を保持するか</p></td>
<td><p>Lync Server 管理シェル</p></td>
</tr>
</tbody>
</table>


## Lync Server コントロール パネルを使用してログ設定を変更するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで **\[クライアント\]** をクリックし、**\[デバイス ログ構成\]** をクリックします。

3.  **\[デバイス ログ構成\]** ページで、変更する構成をダブルクリックします。

4.  **\[ログ設定の編集\]** ダイアログ ボックスで、次の設定のいずれかを変更します。
    
      - **\[最大ファイル サイズ (バイト)\]**   削除されるまでに許容されるログ ファイルの最大サイズを指定します。 既定値は 1,024,000 バイト (1 MB) です。
    
      - **\[最大キャッシュ サイズ (バイト)\]**   キャッシュのクリアが必要でデータがログ ファイルに書き込まれるまでに、ログ ファイルのキャッシュに保持できる情報の最大サイズ (バイト単位) を指定します。 既定値は 512,000 バイト (0.5 MB) です。
    
      - **\[キャッシュをフラッシュする分数 (1 ～ 60)\]**   ログ ファイルのキャッシュに格納された情報が、実際のログ ファイルに書き込まれる頻度を示します。 データがログに書き込まれた後、キャッシュはクリアされます。 既定値は 5 分です。
    
      - **\[ログ ファイルを保持する日数 (1 ～ 365)\]**   ログ ファイルが削除されるまで保持される日数を指定します。 既定値は 10 日です。

5.  **\[確定\]** をクリックします。

## Windows PowerShell コマンドレットを使用してログ記録設定を変更する

デバイス更新ログ ファイル設定は、Windows PowerShell と **Set-CsDeviceUpdateConfiguration** コマンドレットを使用して変更できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。

> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 (<a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>) を参照してください。


以下の例は設定を、変更する **Set-CsDeviceUpdateConfiguration** を使用する 2 つの方法を示します。

## 最大ログ ファイル サイズおよびログ クリーンアップ間隔を変更するには

  - 以下のコマンドは、Redmond サイトに適用されるデバイス更新ログ設定を変更します。この例では、最大ログ ファイル サイズは 204800 バイトに、ログ クリーンアップ間隔は 14 日間に設定されます。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

## ログ クリーンアップ時刻を変更するには

  - このコマンドは、Redmond サイトのログ クリーンアップ時刻を午前 3 時 00 分に設定します。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

詳細については、[Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsDeviceUpdateConfiguration) コマンドレットに関するヘルプ トピックを参照してください。

