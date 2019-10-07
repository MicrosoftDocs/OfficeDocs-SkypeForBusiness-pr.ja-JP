---
title: 'Lync Server 2013: デバイス更新の構成設定のコレクションの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a collection of Device Update configuration settings
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994019(v=OCS.15)
ms:contentKeyID: 51803928
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6de7e3e6ecef8338a3a5514cf3a84180e05ca276
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 でのデバイス更新の構成設定のコレクションの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

デバイス更新の構成設定は、Windows PowerShell と **Remove-CsdeviceUpdateConfiguration** コマンドレットを使用しても削除できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a>デバイス更新の構成設定の特定のコレクションを削除するには

  - 次のコマンドは、Redmond サイトに適用されたデバイス更新の構成設定を削除します。
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a>サイト スコープに適用されたデバイス更新の構成設定をすべて削除するには

  - 次のコマンドは、サイト スコープに適用されたデバイス更新の構成設定をすべて削除します。
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a>LogCleanUpInterval プロパティの値に基づいてデバイス更新の構成設定を削除するには

  - 次のコマンドは、ログのクリーンアップ間隔が 10 日 (10.00:00:00) を超えている場合にデバイス更新の構成設定をすべて削除します。
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

詳細については、[Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) コマンドレットに関するヘルプ トピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

