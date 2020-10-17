---
title: 通話詳細記録と qoe (Quality of Experience) 設定の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6f39bf16a9d0ecf57a5617774395af477a67c2d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502134"
---
# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a>Lync Server 2013 での通話詳細記録と qoe (Quality of Experience) 設定の構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-17_

監視ストアをフロントエンドプールに関連付けた後、監視ストアを設定してから、SQL Server Reporting Services と監視レポートをインストールおよび構成すると、通話詳細記録 (CDR) および QoE (Quality of Experience) の監視を Lync Server 管理シェルを使用して管理できます。 Lync Server 管理シェルコマンドレットを使用すると、特定のサイトまたは Lync Server の展開全体に対して、CDR または QoE 監視を有効または無効にすることができます。これは、次のように簡単にコマンドで実行できます。

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

Microsoft Lync Server 2013 をインストールすると、CDR と QoE の両方に対してグローバル構成設定の定義済みコレクションもインストールされます。 以下の表に、通話詳細記録で比較的よく使用される一部の設定の既定値を示します。


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
<td><p>正</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>CDR レコードをデータベースから定期的に削除するかどうかを示します。True の場合、KeepCallDetailForDays プロパティ (CDR レコードの場合) および KeepErrorReportForDays プロパティ (CDR エラーの場合) で指定されている期間を過ぎると、レコードが削除されます。False の場合、CDR レコードは無期限に保持されます。</p></td>
<td><p>正</p></td>
</tr>
<tr class="odd">
<td><p>KeepCallDetailForDays</p></td>
<td><p>CDR レコードをデータベース内に保持する日数を指定します。指定した日数を超えて存在する古いレコードはすべて自動的に削除されます。ただし、この処理は削除が有効になっている場合にのみ実行されます。</p>
<p>KeepCallDetailForDays には、1 ～ 2,562 (約 7 年間の日数に相当) の範囲の任意の整数値を設定できます。</p></td>
<td><p>60 (日)</p></td>
</tr>
<tr class="even">
<td><p>KeepErrorReportForDays</p></td>
<td><p>CDR エラー報告を保持する日数を示します。指定した日数より古いレポートは自動的に削除されます。 CDR エラーレポートは、Microsoft Lync 2013 などのクライアントアプリケーションによってアップロードされた診断レポートです。</p>
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
<td><p>正</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>QoE レコードをデータベースから定期的に削除するかどうかを示します。True の場合、KeepQoEDataForDays プロパティで指定されている期間を過ぎると、レコードが削除されます。False の場合、QoE レコードは無期限に保持されます。</p></td>
<td><p>正</p></td>
</tr>
<tr class="odd">
<td><p>KeepQoEDataForDays</p></td>
<td><p>QoE レコードをデータベース内に保持する日数を指定します。指定した日数を超えて存在する古いレコードはすべて自動的に削除されます。ただし、この処理は削除が有効になっている場合にのみ実行されます。</p>
<p>KeepCallDetailForDays は、1 ～ 2562 (日) の範囲の任意の整数値に設定できます。</p></td>
<td><p>60 日</p></td>
</tr>
</tbody>
</table>


これらのグローバル設定を変更する必要がある場合は、Set-CsCdrConfiguration コマンドレットや Set-CsQoEConfiguration コマンドレットを使用して、そうした変更を行うことができます。たとえば、(Lync Server 管理シェルから実行される) 次のコマンドは、CDR 監視をグローバル スコープで無効にします。この処理は、EnableCDR プロパティを False ($False) に設定することで行われます。

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

監視を無効にしても、監視ストアとフロントエンド プールとの関連付けは解除されず、バックエンド監視データベースがアンインストールされたり、その他の影響がこのデータベースに及んだりすることもありません。 Lync Server 管理シェルを使用して CDR または QoE 監視を無効にすると、実際には、Lync Server が監視データの収集とアーカイブを停止することはありません。 この場合、次のように EnableCDR プロパティの設定を True ($True) に戻すだけで、CDR データの収集とアーカイブを再開できます。

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

同様に、次のコマンドは、QoE レコードの削除をグローバル スコープで無効にします。

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

CDR と QoE の構成設定は、グローバル設定だけでなく、サイト スコープに割り当てることもできます。これにより、監視についての管理の柔軟性が向上します。たとえば、管理者は Redmond サイトで CDR 監視を有効にする一方で Dublin サイトでは CDR 監視を無効にできます。新しい CDR 構成設定をサイト スコープで作成するには、次のようなコマンドを使用します。

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

サイト スコープで構成されたこの設定は、グローバル スコープで構成された設定よりも優先されることに注意してください。たとえば、CDR 監視がグローバル スコープで有効になっていても、サイト スコープ (Redmond サイト) では無効になっているとします。この場合、Redmond サイト内のユーザーについては通話詳細記録の情報がアーカイブされません。ただし、その他のサイト内のユーザー (つまり、Redmond サイトの設定ではなくグローバル設定によって管理されているユーザー) の通話詳細記録の情報はアーカイブされます。

新しい QoE 構成設定をサイト スコープで作成するには、次のようなコマンドを使用します。

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

詳細については、Lync Server 管理シェルで次のコマンドを入力します。

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

