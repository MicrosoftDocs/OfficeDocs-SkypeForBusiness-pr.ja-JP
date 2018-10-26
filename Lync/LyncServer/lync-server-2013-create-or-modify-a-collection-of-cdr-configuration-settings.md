---
title: CDR 構成設定のコレクションの作成または変更
TOCTitle: CDR 構成設定のコレクションの作成または変更
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49887141
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# CDR 構成設定のコレクションの作成または変更

 

_**トピックの最終更新日:** 2015-03-09_

通話詳細記録 (CDR) では、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。

Microsoft Lync Server 2013 をインストールすると、CDR 構成設定のグローバル コレクションが 1 つ作成されます。管理者は、サイト スコープでカスタム設定を作成することもできます。これらのサイト スコープの設定が使用されるときは常に、グローバル設定よりも優先されます。たとえば、レドモンド サイトにサイト スコープの設定を作成する場合、レドモンドでの CDR の管理には (グローバル設定ではなく) それらの設定が使用されます。

CDR 構成設定は、Lync Server コントロール パネルまたは [New-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration) コマンドレットを使用して作成できます。既存の設定を変更するには、Lync Server コントロール パネル または [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration) コマンドレットを使用します。Lync Server コントロール パネル を使用して設定を作成または変更する場合、次のオプションを使用できます。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI 設定</th>
<th>PowerShell パラメーター</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名前</p></td>
<td><p>ID</p></td>
<td><p>作成する CDR 構成設定に対する一意の識別子。これらの設定はサイト スコープでのみ作成できます。</p></td>
</tr>
<tr class="even">
<td><p>CDR の監視を有効にする</p></td>
<td><p>EnableCDR</p></td>
<td><p>CDR を有効にするかどうかを示します。</p></td>
</tr>
<tr class="odd">
<td><p>CDR の削除を有効にする</p></td>
<td><p>EnablePurging</p></td>
<td><p>CDR の記録を CDR データベースから定期的に削除するかどうかを示します。</p></td>
</tr>
<tr class="even">
<td><p>Keep CDRs for maximum duration (days) (CDR の最大保持期間 (日))</p></td>
<td><p>KeepCallDetailForDays</p></td>
<td><p>CDR データベースに CDR レコードを保持する日数を示します。指定された日数より古いレコードは、自動的に削除されます (削除が実行されるのは、削除が有効になっている場合のみです)。</p></td>
</tr>
<tr class="odd">
<td><p>エラー報告データを保持する最大期間 (日数)</p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>CDR エラー報告を保持する日数を指定します。指定した日数を超えて保持されている報告は、自動的に削除されます。CDR エラー報告は、クライアント アプリケーションによってアップロードされる診断レポートです。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> New-CsCdrConfiguration および Set-CsCdrConfiguration のコマンドレットには、Lync Server コントロール パネルでは使用できない追加のオプションが含まれます。詳細については、「<a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</a>」と「<a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</a>」のヘルプ トピックを参照してください。


## Lync Server コントロール パネルを使用して CDR 構成設定を作成するには

1.  Lync Server コントロール パネルで、\[**監視およびアーカイブ**\] をクリックします。

2.  \[**通話詳細記録**\] タブで、\[**新規**\] をクリックします。

3.  \[**サイトの選択**\] ダイアログ ボックスで、新しい構成設定を作成するサイトを選択します。ダイアログ ボックスに何も表示されない場合は、すべてのサイトが CDR 構成設定のコレクションに割り当て済みであることを意味します。各サイトに対してこのようなコレクション 1 つに制限されています。その場合、設定を削除してから再作成するか、単純に既存の設定を変更することができます。

4.  \[**新しい通話詳細記録 (CDR) 設定を作成する**\] ダイアログで、任意に選択を行ってから \[**コミット**\] をクリックします。

## Lync Server コントロール パネル を使用して既存の CDR 構成設定を変更するには

1.  Lync Server コントロール パネルで、\[**監視およびアーカイブ**\] をクリックします。

2.  変更する設定のコレクションをダブルクリックするか、コレクションを選択して \[**編集**\] をクリックし、さらに \[**詳細の表示**\] をクリックします。一度に変更できるのは 1 つのコレクションだけであることに注意してください。複数のコレクションに同じ変更を加えるには、Lync Server 管理シェルを使用します。

3.  \[**編集 通話詳細記録 (CDR) 設定**\] ダイアログで、任意の選択を行ってから \[**コミット**\] をクリックします。

## Lync Server 管理シェル コマンドレットを使用して CDR 構成設定を作成するには

CDR 構成設定は、Windows PowerShell と **New-CsCdrConfiguration** コマンドレットを使用して作成することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、またはWindows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 新しい CDR 構成設定のコレクションを作成するには

  - このコマンドを実行すると、レドモンド サイトに適用される新しい CDR 構成設定のコレクションが作成されます。
    
        New-CsCdrConfiguration -Identity "site:Redmond"

## 通話詳細記録を無効にする CDR 構成設定のコレクションを作成するには

  - 前述のコマンドでは、必須の Identity パラメーター以外のパラメーターは指定されていないため、新しい構成設定のコレクションではすべてのプロパティで既定値が使用されます。異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を指定します。たとえば、既定では通話詳細記録の無効化を許可する通話詳細の構成設定のコレクションを作成するには、次のようなコマンドを使用します。
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

## 新しい CDR 構成設定のコレクションの作成時に複数のプロパティ値を指定するには

  - 複数のパラメーターを含めることで、複数のプロパティ値を変更できます。たとえば、このコマンドを実行すると、通話詳細記録を 30 日間保持し、エラー レポートを 90 日間保持するための新しい設定が構成されます。
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

詳細については、[New-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration) コマンドレットのヘルプ トピックを参照してください。

