---
title: 'Lync Server 2013: デバイス更新構成設定の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Device Update configuration settings
ms:assetid: aa6a70a9-bd77-4606-b797-ea6a3bab9cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994059(v=OCS.15)
ms:contentKeyID: 51803970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4c334e44212116418a953b2bbf84ece75063f8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-device-update-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 でのデバイス更新構成設定の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-20_

Lync Server 管理シェルと、Windows のリモートセッションから2013実行できる、 **CsDeviceUpdateConfiguration**コマンドレットを使用して、デバイス更新サービスの構成設定を表示できます (複数可)。PowerShell

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。



</div>

<div>


<div>


  - すべての音声ルートに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsDeviceUpdateConfiguration
    
    このコマンドは、次のような情報を返します。
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

</div>

このコマンドレットの詳細については、「 [CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateConfiguration)概要」のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

