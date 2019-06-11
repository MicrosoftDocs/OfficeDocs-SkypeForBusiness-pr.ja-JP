---
title: 'Lync Server 2013: CDR 構成設定の既存のコレクションを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d15f224d7e3aa4b43b20925a4efd4007a0c6c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 で既存の CDR 構成設定のコレクションを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。

Microsoft Lync Server 2013 をインストールすると、1つのグローバルな CDR 構成設定が作成されます。 また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。 設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。 サイト スコープ設定を削除した場合、CDR はそのサイトでグローバル設定を使用して管理されます。

なお、"削除" はグローバル設定に対しても実行できます。ただし、グローバル設定は実際には削除されません。代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。たとえば、既定では CDR 構成設定のコレクションで削除が有効になります。削除が無効になるようにグローバル コレクションを変更すると想定します。後でグローバル設定を削除した場合、すべてのプロパティが既定値にリセットされます。この場合、削除が再び有効になります。

[Lync Server] コントロールパネルまたは[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration)コマンドレットを使用して、CDR 構成設定を削除することができます。

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a>Lync Server コントロールパネルで CDR の設定を削除するには

1.  Lync Server コントロールパネルで、[**監視とアーカイブ**] をクリックします。

2.  [**通話詳細記録**] タブで、削除する CDR 設定のコレクションを 1 つまたは複数選択します。複数のコレクションを選択するには、最初のコレクションをクリックし、Ctrl キーを押しながら他のコレクションをクリックします。

3.  [**編集**] をクリックして、[**削除**] をクリックします。

4.  [Lync Server コントロールパネル] ダイアログボックスで、[ **OK**] をクリックします。

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して CDR 構成設定を削除する

Windows PowerShell と CsCdrConfiguration コマンドレットを使用して、通話の詳細**な**レコーディング設定を削除できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>指定された CDR 構成設定のコレクションを削除するには

  - このコマンドでは、Redmond サイトに適用されていた CDR 構成設定が削除されます。
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>サイト スコープに適用されていた CDR 構成設定をすべて削除するには

  - このコマンドでは、サイト スコープに適用されていたすべての CDR 構成設定が削除されます。
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>通話詳細記録を無効にする CDR 構成設定をすべて削除するには

  - このコマンドでは、通話詳細記録が無効になっているすべての CDR 構成設定が削除されます。
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

詳細については、 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

