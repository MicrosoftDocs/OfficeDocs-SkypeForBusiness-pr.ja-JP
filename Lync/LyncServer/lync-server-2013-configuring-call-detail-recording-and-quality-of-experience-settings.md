---
title: 通話詳細記録と QoE (Quality of Experience) 設定の構成
TOCTitle: 通話詳細記録と QoE (Quality of Experience) 設定の構成
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48271056
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 通話詳細記録と QoE (Quality of Experience) 設定の構成

 

_**トピックの最終更新日:** 2015-03-09_

監視ストアとフロントエンド プールの関連付け、監視ストアのセットアップ、SQL Server Reporting Services と監視レポートのインストールおよび構成が完了すると、Lync Server 管理シェルを使用して通話詳細記録 (CDR) や QoE (Quality of Experience) 監視を管理できます。Lync Server 管理シェル コマンドレットを使用すると、特定のサイトまたは Lync Server 展開の全体で CDR や QoE 監視を有効または無効にできます。こうした操作は、次のような簡単なコマンドで実行できます。

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

Microsoft Lync Server 2013 をインストールすると、CDR と QoE の両方に対するグローバル構成設定の定義済みコレクションもインストールされます。以下の表に、通話詳細記録で比較的よく使用される一部の設定の既定値を示します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>プロパティ</th>
<th>説明</th>
<th>既定値</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableCDR</p></td>
<td><p>CDR が有効かどうかを示します。True の場合、すべての CDR レコードが収集され、監視データベースに書き込まれます。</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>CDR レコードをデータベースから定期的に削除するかどうかを示します。True の場合、KeepCallDetailForDays プロパティ (CDR レコードの場合) および KeepErrorReportForDays プロパティ (CDR エラーの場合) で指定されている期間を過ぎると、レコードが削除されます。False の場合、CDR レコードは無期限に保持されます。</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepCallDetailForDays</p></td>
<td><p>CDR レコードをデータベース内に保持する日数を指定します。指定した日数を超えて存在する古いレコードはすべて自動的に削除されます。ただし、この処理は削除が有効になっている場合にのみ実行されます。</p>
<p>KeepCallDetailForDays には、1 ～ 2,562 (約 7 年間の日数に相当) の範囲の任意の整数値を設定できます。</p></td>
<td><p>60 (日)</p></td>
</tr>
<tr class="even">
<td><p>KeepErrorReportForDays</p></td>
<td><p>CDR エラー報告を保持する日数を指定します。指定した日数を超えて保持されている報告は、自動的に削除されます。CDR エラー報告は、Microsoft Lync 2013 のようなクライアント アプリケーションによってアップロードされる診断レポートです。</p>
<p>このプロパティには、1 ～ 2,562 (日) の範囲の任意の整数値に指定できます。</p></td>
<td><p>60 (日)</p></td>
</tr>
</tbody>
</table>


同様に、一部の QoE 設定の既定値を以下の表に示します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>プロパティ</th>
<th>説明</th>
<th>既定値</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableQoE</p></td>
<td><p>QoE 監視が有効かどうかを示します。True の場合、すべての QoE レコードが収集され、監視データベースに書き込まれます。</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>QoE レコードをデータベースから定期的に削除するかどうかを示します。True の場合、KeepQoEDataForDays プロパティで指定されている期間を過ぎると、レコードが削除されます。False の場合、QoE レコードは無期限に保持されます。</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepQoEDataForDays</p></td>
<td><p>QoE レコードをデータベース内に保持する日数を指定します。指定した日数を超えて存在する古いレコードはすべて自動的に削除されます。ただし、この処理は削除が有効になっている場合にのみ実行されます。</p>
<p>KeepCallDetailForDays は、1 ～ 2562 (日) の範囲の任意の整数値に設定できます。</p></td>
<td><p>60 (日)</p></td>
</tr>
</tbody>
</table>


これらのグローバル設定を変更する必要がある場合は、Set-CsCdrConfiguration コマンドレットや Set-CsQoEConfiguration コマンドレットを使用して、そうした変更を行うことができます。たとえば、(Lync Server 管理シェルから実行される) 次のコマンドは、CDR 監視をグローバル スコープで無効にします。この処理は、EnableCDR プロパティを False ($False) に設定することで行われます。

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

監視を無効にしても、監視ストアとフロントエンド プールとの関連付けは解除されず、バックエンド監視データベースがアンインストールされたり、その他の影響がこのデータベースに及んだりすることもありません。Lync Server 管理シェルを使用して CDR または QoE 監視を無効にする場合、実際に行われるのは Lync Server による監視データの収集およびアーカイブの停止のみです。この場合、次のように EnableCDR プロパティの設定を True ($True) に戻すだけで、CDR データの収集とアーカイブを再開できます。

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

同様に、次のコマンドは、QoE レコードの削除をグローバル スコープで無効にします。

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

CDR と QoE の構成設定は、グローバル設定だけでなく、サイト スコープに割り当てることもできます。これにより、監視についての管理の柔軟性が向上します。たとえば、管理者は Redmond サイトで CDR 監視を有効にする一方で Dublin サイトでは CDR 監視を無効にできます。新しい CDR 構成設定をサイト スコープで作成するには、次のようなコマンドを使用します。

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

サイト スコープで構成されたこの設定は、グローバル スコープで構成された設定よりも優先されることに注意してください。たとえば、CDR 監視がグローバル スコープで有効になっていても、サイト スコープ (Redmond サイト) では無効になっているとします。この場合、Redmond サイト内のユーザーについては通話詳細記録の情報がアーカイブされません。ただし、その他のサイト内のユーザー (つまり、Redmond サイトの設定ではなくグローバル設定によって管理されているユーザー) の通話詳細記録の情報はアーカイブされます。

新しい QoE 構成設定をサイト スコープで作成するには、次のようなコマンドを使用します。

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

詳細については、Lync Server 管理シェルで次のコマンドを入力してください。

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

