---
title: 'Lync Server 2013: サーバーの役割とサービスのコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles and services cmdlets
ms:assetid: ff3561de-043e-4071-88f7-8de3cded52f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415683(v=OCS.15)
ms:contentKeyID: 48185971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f59ff1b76b2381c611f07f09bbdaabcdc5e4a69b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-and-services-cmdlets-in-lync-server-2013"></a>Lync Server 2013 のサーバーの役割とサービスコマンドレット

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-07-29_

多くの Microsoft Lync Server 2013 コンポーネントは、サーバーの役割またはサービスとして実行されます。 Lync Server 2013 には、これらのサーバーの役割とサービスを管理できる多数のコマンドレットが付属しています。

<div>

## <a name="server-roles-and-services-cmdlets"></a>サーバーの役割とサービスのコマンドレット

サーバーおよびサービスロールに適用される管理タスクの多くは、Lync Server コントロールパネルから実行できます。 たとえば、アーカイブサーバーの設定を管理することはできますが、Lync Server コントロールパネルを使用して、アドレス帳のサーバー設定を管理することはできません。 ただし、これらのすべてのタスクは、Lync Server 管理シェルのコマンドレットまたはスクリプト内から実行できます。スクリプトを使用すると、特定のタスクを自動化できます。 次に示すのは、サーバーの役割とサービスを管理するために直接関連するコマンドレットの一覧です。

**[Lync Server 2013 のアドレス帳サーバーコマンドレット](lync-server-2013-address-book-server-cmdlets.md)**

  - <span></span>  
    [CsAddressBookConfiguration の入手](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))

  - <span></span>  
    [New-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))

  - <span></span>  
    [CsAddressBookConfiguration の削除](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))

  - <span></span>  
    [Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [更新-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))

**[Lync Server 2013 のアーカイブと監視コマンドレット](lync-server-2013-archiving-and-monitoring-cmdlets.md)**

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

**[Lync Server 2013 のデータベースと管理サーバーのコマンドレット](lync-server-2013-database-and-management-server-cmdlets.md)**

  - <span></span>  
    [Get-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg412814(v=OCS.15))

  - <span></span>  
    [Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398214(v=OCS.15))

  - <span></span>  
    [Set-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398258(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Install-CsDatabase](https://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))

  - <span></span>  
    [Test-CsDatabase](https://technet.microsoft.com/en-us/library/JJ204839(v=OCS.15))

  - <span></span>  
    [Uninstall-CsDatabase](unhttps://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))

<!-- end list -->

  - [Invoke-CsDatabaseFailover](https://technet.microsoft.com/en-us/library/JJ204744(v=OCS.15))

<!-- end list -->

  - [Get-CsDatabaseMirrorState](https://technet.microsoft.com/en-us/library/JJ204845(v=OCS.15))

<!-- end list -->

  - [Install-CsMirrorDatabase](https://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))

  - [Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg398831(v=OCS.15))

  - <span></span>  
    [設定-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg412973(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsUserDatabase の更新](https://technet.microsoft.com/en-us/library/Gg398682(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsManagementServer の移動](https://technet.microsoft.com/en-us/library/Gg412921(v=OCS.15))

  - <span></span>  
    [Set-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg398465(v=OCS.15))

<!-- end list -->

  - [Invoke-CsManagementServerFailover](https://technet.microsoft.com/en-us/library/JJ204647(v=OCS.15))

**[Lync Server 2013 のエッジサーバーコマンドレット](lync-server-2013-edge-server-cmdlets.md)**

  - <span></span>  
    [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))

  - <span></span>  
    [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))

  - <span></span>  
    [新規-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))

  - <span></span>  
    [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))

  - <span></span>  
    [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))

**[Lync Server 2013 のその他のサーバーの役割コマンドレット](lync-server-2013-other-server-role-cmdlets.md)**

  - <span></span>  
    [Set-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))

**[Lync Server 2013 のレジストラーとディレクターのコマンドレット](lync-server-2013-registrar-and-director-cmdlets.md)**

  - <span></span>  
    [Set-CsDirector](https://technet.microsoft.com/en-us/library/Gg398565(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Reset-CsPoolRegistrarState](https://technet.microsoft.com/en-us/library/JJ619172(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [設定-CsRegistrar](https://technet.microsoft.com/en-us/library/Gg398993(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398483(v=OCS.15))

  - <span></span>  
    [新規-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg425893(v=OCS.15))

  - <span></span>  
    [Remove-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398482(v=OCS.15))

  - <span></span>  
    [Set-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398764(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15))

**[Lync Server 2013 のサービスコマンドレット](lync-server-2013-services-cmdlets.md)**

  - <span></span>  
    [CsService の入手](https://technet.microsoft.com/en-us/library/Gg413038(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsWindowsService の入手](https://technet.microsoft.com/en-us/library/Gg398803(v=OCS.15))

  - <span></span>  
    [CsWindowsService の開始](https://technet.microsoft.com/en-us/library/Gg398561(v=OCS.15))

  - <span></span>  
    [CsWindowsService の停止](https://technet.microsoft.com/en-us/library/Gg398426(v=OCS.15))

**[Lync Server 2013 のサーバーの役割とサービスコマンドレットのトラブルシューティング](lync-server-2013-troubleshooting-server-roles-and-services-cmdlets.md)**

  - <span></span>  
    [Get-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))

  - <span></span>  
    [Set-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))

  - <span></span>  
    [新規-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))

  - <span></span>  
    [Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))

  - <span></span>  
    [Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))

  - <span></span>  
    [新規-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))

  - <span></span>  
    [Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))

  - <span></span>  
    [Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新規-CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))

  - <span></span>  
    [New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))

  - <span></span>  
    [Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))

  - <span></span>  
    [Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))

**[Lync Server 2013 の Web サーバーとサービスのコマンドレット](lync-server-2013-web-server-and-services-cmdlets.md)**

  - <span></span>  
    [New-CsSimpleUrl](https://technet.microsoft.com/en-us/library/Gg398180(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsSimpleUrlConfiguration の入手](https://technet.microsoft.com/en-us/library/Gg398392(v=OCS.15))

  - <span></span>  
    [New-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg425813(v=OCS.15))

  - <span></span>  
    [Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398515(v=OCS.15))

  - <span></span>  
    [Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg412991(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSimpleUrlEntry](https://technet.microsoft.com/en-us/library/Gg425902(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsWebServer](https://technet.microsoft.com/en-us/library/Gg398759(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg425751(v=OCS.15))

  - <span></span>  
    [New-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398440(v=OCS.15))

  - <span></span>  
    [Remove-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398266(v=OCS.15))

  - <span></span>  
    [Set-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398396(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新規-CsWebTrustedCACertificate](https://technet.microsoft.com/en-us/library/Gg412746(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新しい-Csker"@ @" アカウント](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))

  - <span></span>  
    [New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))

  - <span></span>  
    [Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))

  - <span></span>  
    [Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))

  - <span></span>  
    [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-Csker\ "Osaccountpassword"](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))

<!-- end list -->

  - [Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))

  - [Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server PowerShell ブログ](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

