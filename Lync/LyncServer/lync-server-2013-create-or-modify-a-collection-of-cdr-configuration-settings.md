---
title: 'Lync Server 2013: CDR 構成設定のコレクションを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 828c02e11d9e5adfe7028dd8d224c10df14c2247
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 での CDR 構成設定のコレクションの作成または変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

通話詳細記録 (CDR) では、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。

Microsoft Lync Server 2013 をインストールすると、1つのグローバルな CDR 構成設定のグローバルコレクションが作成されます。 管理者は、サイト スコープでカスタム設定を作成することもできます。 これらのサイト スコープの設定が使用されるときは常に、グローバル設定よりも優先されます。 たとえば、レドモンド サイトにサイト スコープの設定を作成する場合、レドモンドでの CDR の管理には (グローバル設定ではなく) それらの設定が使用されます。

CDR 構成設定は、Lync Server コントロールパネルまたは[set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration)コマンドレットのいずれかを使用して作成できます。 Lync Server コントロールパネルまたは[set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration)コマンドレットを使用して、既存の設定を変更できます。 Lync Server コントロールパネルを使用して設定を作成または変更する場合は、次のオプションを使用できます。


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


<div>


> [!NOTE]  
> Set-cscdrconfiguration および Set-cscdrconfiguration コマンドレットには、Lync Server コントロールパネルでは使用できない追加オプションが含まれています。 詳細については、 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">set-cscdrconfiguration</A>および<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">set-cscdrconfiguration</A>ヘルプトピックを参照してください。



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して CDR 構成設定を作成するには

1.  Lync Server コントロールパネルで **、[監視とアーカイブ**] をクリックします。

2.  [**通話詳細記録**] タブで、[**新規**] をクリックします。

3.  [**サイトの選択**] ダイアログ ボックスで、新しい構成設定を作成するサイトを選択します。ダイアログ ボックスに何も表示されない場合は、すべてのサイトが CDR 構成設定のコレクションに割り当て済みであることを意味します。各サイトに対してこのようなコレクション 1 つに制限されています。その場合、設定を削除してから再作成するか、単純に既存の設定を変更することができます。

4.  [**新しい通話詳細記録 (CDR) 設定を作成する**] ダイアログで、任意に選択を行ってから [**コミット**] をクリックします。

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して既存の CDR 構成設定を変更するには

1.  Lync Server コントロールパネルで **、[監視とアーカイブ**] をクリックします。

2.  変更する設定のコレクションをダブルクリックするか、コレクションを選択して [**編集**] をクリックし、さらに [**詳細の表示**] をクリックします。 一度に変更できるのは 1 つのコレクションだけであることに注意してください。 複数のコレクションに同じ変更を加えるには、代わりに Lync Server 管理シェルを使用します。

3.  [**編集 通話詳細記録 (CDR) 設定**] ダイアログで、任意の選択を行ってから [**コミット**] をクリックします。

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して CDR 構成設定を作成する

CDR 構成設定は、Windows PowerShell および**set-cscdrconfiguration**コマンドレットを使用して作成することもできます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>新しい CDR 構成設定のコレクションを作成するには

  - このコマンドを実行すると、レドモンド サイトに適用される新しい CDR 構成設定のコレクションが作成されます。
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>通話詳細記録を無効にする CDR 構成設定のコレクションを作成するには

  - 前述のコマンドでは、必須の Identity パラメーター以外のパラメーターは指定されていないため、新しい構成設定のコレクションではすべてのプロパティで既定値が使用されます。異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を指定します。たとえば、既定では通話詳細記録の無効化を許可する通話詳細の構成設定のコレクションを作成するには、次のようなコマンドを使用します。
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>新しい CDR 構成設定のコレクションの作成時に複数のプロパティ値を指定するには

  - 複数のパラメーターを含めることで、複数のプロパティ値を変更できます。たとえば、このコマンドを実行すると、通話詳細記録を 30 日間保持し、エラー レポートを 90 日間保持するための新しい設定が構成されます。
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

詳細については、 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

