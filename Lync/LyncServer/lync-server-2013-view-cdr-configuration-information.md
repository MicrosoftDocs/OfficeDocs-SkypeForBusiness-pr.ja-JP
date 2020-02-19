---
title: 'Lync Server 2013: CDR 構成情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccf5658b49118f4053f0bd76b18273fb77f90237
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-cdr-configuration-information-in-lync-server-2013"></a>Lync Server 2013 での CDR 構成情報の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。

Microsoft Lync Server 2013 をインストールすると、CDR 構成設定のグローバルコレクションが1つ作成されます。 また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。 Lync Server コントロールパネルまたは[set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)コマンドレットを使用して、組織で使用されている CDR 構成設定を表示できます。

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して CDR 構成情報を表示するには

1.  Lync Server コントロールパネルで **、[監視とアーカイブ**] をクリックします。

2.  すべての CDR 構成設定の一覧が、[**通話詳細記録**] タブに表示されます。設定の各コレクションについて、コレクションの [**名前**]、CDR が有効になっているかどうか ([**CDR**] プロパティ)、削除が有効になっているかどうか ([**CDR の削除**] プロパティ) が表示されます。コレクションの詳細情報を表示するには、コレクションをダブルクリックするか、適切なコレクションを選択して [**編集**] をクリックし、続いて [**詳細の表示**] をクリックします。詳細情報を表示できる CDR 構成設定のコレクションは一度に 1 つだけであることに注意してください。

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用した CDR 構成情報の表示

CDR 構成設定は、Windows PowerShell と Set-cscdrconfiguration コマンドレットを使用して表示できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-view-cdr-configuration-information"></a>CDR の構成情報を表示するには

  - すべての CDR 構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。
    
        Get-CsCdrConfiguration
    
    次のような情報が表示されます。
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

詳細については、 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

