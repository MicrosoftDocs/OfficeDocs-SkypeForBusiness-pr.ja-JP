---
title: 'Lync Server 2013: コマンドレットのアーカイブと監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Archiving and Monitoring cmdlets
ms:assetid: 04e1d0f6-d00e-4d8f-b969-daf092b2cdb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415629(v=OCS.15)
ms:contentKeyID: 48183281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f7242ee62bb7f9796b1f8445d49dc5efd32c06
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="archiving-and-monitoring-cmdlets-in-lync-server-2013"></a>Lync Server 2013 のアーカイブと監視コマンドレット

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-04_

アーカイブと監視のコマンドレットを使用して、管理者がインスタントメッセージと会議セッションのアーカイブを管理できるようにします。通話の詳細情報を記録するにはまた、Microsoft Lync Server 2013 で質の高いエクスペリエンス (QoE) を使って監視することができます。


> [!NOTE]
> コマンドレットの詳細については、「&nbsp;Lync Server Windows PowerShell <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>のブログ」を参照してください。 各ブログの内容と URL は、将来予告なしに変更されることがあります。



<div>

## <a name="archiving-and-monitoring-cmdlets"></a>コマンドレットのアーカイブと監視

アーカイブと監視の管理に直接関連するコマンドレットの一覧を次に示します。

**アーカイブと監視**

  - <span></span>  
    [Get-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg399012(v=OCS.15))

  - <span></span>  
    [New-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398471(v=OCS.15))

  - <span></span>  
    [Remove-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398951(v=OCS.15))

  - <span></span>  
    [Set-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg413030(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [エクスポート-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/en-us/library/JJ204627(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425731(v=OCS.15))

  - <span></span>  
    [Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398475(v=OCS.15))

  - <span></span>  
    [New-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg399032(v=OCS.15))

  - <span></span>  
    [Remove-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425924(v=OCS.15))

  - <span></span>  
    [Set-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398294(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsArchivingServer](https://technet.microsoft.com/en-us/library/Gg398923(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398298(v=OCS.15))

  - <span></span>  
    [新規-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg399018(v=OCS.15))

  - <span></span>  
    [Remove-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398451(v=OCS.15))

  - <span></span>  
    [Set-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398774(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsMonitoringServer](https://technet.microsoft.com/en-us/library/Gg425776(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得-CsQoEConfiguration しくみ](https://technet.microsoft.com/en-us/library/Gg399004(v=OCS.15))

  - <span></span>  
    [新しい-CsQoEConfiguration 「」](https://technet.microsoft.com/en-us/library/Gg398325(v=OCS.15))

  - <span></span>  
    [CsQoEConfiguration 削除](https://technet.microsoft.com/en-us/library/Gg425879(v=OCS.15))

  - <span></span>  
    [Set-CsQoEConfiguration 設定](https://technet.microsoft.com/en-us/library/Gg398245(v=OCS.15))

[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205113(v=OCS.15))

  - <span></span>  
    [エクスポート-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [呼び出し-CsQoEDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205247(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205356(v=OCS.15))

  - <span></span>  
    [新規の CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204787(v=OCS.15))

  - <span></span>  
    [CsReportingConfiguration の削除](https://technet.microsoft.com/en-us/library/JJ204711(v=OCS.15))

  - <span></span>  
    [設定-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205075(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204759(v=OCS.15))

  - <span></span>  
    [Remove-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204870(v=OCS.15))

  - <span></span>  
    [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204739(v=OCS.15))

  - <span></span>  
    [New-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ205254(v=OCS.15))

  - <span></span>  
    [Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204926(v=OCS.15))

  - <span></span>  
    [Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204620(v=OCS.15))

  - <span></span>  
    [テスト-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204652(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新規-Csex・・のテスト](https://technet.microsoft.com/en-us/library/JJ205275(v=OCS.15))

</div>

</div>

<span> </span>

</div>

</div>

</div>

