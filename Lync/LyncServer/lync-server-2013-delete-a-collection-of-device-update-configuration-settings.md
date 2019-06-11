---
title: 'Lync Server 2013: デバイス更新プログラムの構成設定のコレクションを削除する'
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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 でデバイス更新設定のコレクションを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-20_

デバイス更新プログラムの設定は、Windows PowerShell と、 **CsdeviceUpdateConfiguration**コマンドレットを使用して削除することもできます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a>デバイスの更新設定の特定のコレクションを削除するには

  - このコマンドは、Redmond サイトに適用されているデバイスの更新設定を削除します。
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a>サイトの範囲に適用されているすべてのデバイス更新設定を削除するには

  - このコマンドは、サイトスコープに適用されているすべてのデバイス更新構成設定を削除します。
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a>LogCleanUpInterval プロパティの値に基づいてデバイス更新の構成設定を削除するには

  - 次のコマンドは、ログのクリーンアップ間隔が10日 (10.00:00:00) よりも大きいデバイスの更新設定をすべて削除します。
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

詳細については、「 [CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration)オプションの削除」コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

