---
title: 'Lync Server 2013: サーバーの役割およびサービスのコマンドレット'
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
ms.openlocfilehash: a7b44cb01ed5ff967f47d46bffa833fe5007ff6f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-and-services-cmdlets-in-lync-server-2013"></a>Lync Server 2013 のサーバーの役割およびサービスのコマンドレット

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-29_

Microsoft Lync Server 2013 の多くのコンポーネントは、サーバーの役割またはサービスとして実行されます。 Lync Server 2013 には、これらのサーバーの役割とサービスを管理するための多数のコマンドレットが付属しています。

<div>

## <a name="server-roles-and-services-cmdlets"></a>サーバーの役割およびサービスのコマンドレット

サーバーおよびサービスの役割に適用する管理タスクの多く (ただしすべてではありません) は、Lync Server コントロールパネルから実行できます。 たとえば、Lync Server コントロールパネルを使用して、アドレス帳のサーバー設定ではなく、アーカイブサーバーの設定を管理できます。 ただし、これらのタスクはすべて、Lync Server 管理シェルまたはスクリプト内からコマンドレットを使用して実行できます。スクリプトを使用すると、特定のタスクを自動化できます。 以下は、サーバーの役割およびサービスの管理に直接関連するコマンドレットの一覧です。

**[Lync Server 2013 のアドレス帳サーバーのコマンドレット](lync-server-2013-address-book-server-cmdlets.md)**

  - <span></span>  
    [-CsAddressBookConfiguration の取得](https://technet.microsoft.com/library/Gg398132(v=OCS.15))

  - <span></span>  
    [新しい-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))

  - <span></span>  
    [-CsAddressBookConfiguration の削除](https://technet.microsoft.com/library/Gg398934(v=OCS.15))

  - <span></span>  
    [設定-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Update-csaddressbook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [デバッグ-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))

**[Lync Server 2013 でのアーカイブと監視のコマンドレット](lync-server-2013-archiving-and-monitoring-cmdlets.md)**

  - <span></span>  
    [Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))

  - <span></span>  
    [Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))

  - <span></span>  
    [Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))

  - <span></span>  
    [Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-csarchivingdatabasepurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))

  - <span></span>  
    [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))

  - <span></span>  
    [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))

  - <span></span>  
    [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))

  - <span></span>  
    [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))

  - <span></span>  
    [Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))

  - <span></span>  
    [Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))

  - <span></span>  
    [Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [設定-CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得-CsQoEConfiguration 場合](https://technet.microsoft.com/library/Gg399004(v=OCS.15))

  - <span></span>  
    [新しい-CsQoEConfiguration の場合](https://technet.microsoft.com/library/Gg398325(v=OCS.15))

  - <span></span>  
    [Remove-CsQoEConfiguration の場合](https://technet.microsoft.com/library/Gg425879(v=OCS.15))

  - <span></span>  
    [Set-CsQoEConfiguration 設定](https://technet.microsoft.com/library/Gg398245(v=OCS.15))

[Invoke-cscdrdatabasepurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))

  - <span></span>  
    [Export-csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [-CsReportingConfiguration の取得](https://technet.microsoft.com/library/JJ205356(v=OCS.15))

  - <span></span>  
    [新しい-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))

  - <span></span>  
    [-CsReportingConfiguration の削除](https://technet.microsoft.com/library/JJ204711(v=OCS.15))

  - <span></span>  
    [設定-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-cstestusercredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))

  - <span></span>  
    [Set-cstestusercredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))

  - <span></span>  
    [Set-cstestusercredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))

  - <span></span>  
    [Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))

  - <span></span>  
    [Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))

  - <span></span>  
    [Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))

  - <span></span>  
    [Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-Csex"Dedtest"](https://technet.microsoft.com/library/JJ205275(v=OCS.15))

**[Lync Server 2013 のデータベースおよび管理サーバーのコマンドレット](lync-server-2013-database-and-management-server-cmdlets.md)**

  - <span></span>  
    [Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))

  - <span></span>  
    [Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))

  - <span></span>  
    [Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [-CsDatabase をインストールする](https://technet.microsoft.com/library/Gg399044(v=OCS.15))

  - <span></span>  
    [テスト-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))

  - <span></span>  
    [アンインストール-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))

<!-- end list -->

  - [Invoke-CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))

<!-- end list -->

  - [Get-csdatabasemirrorstate 戻し](https://technet.microsoft.com/library/JJ204845(v=OCS.15))

<!-- end list -->

  - [Install-csmirrordatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))

  - [アンインストール-Install-csmirrordatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))

  - <span></span>  
    [設定-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [-CsUserDatabase を更新する](https://technet.microsoft.com/library/Gg398682(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Move-csmanagementserver](https://technet.microsoft.com/library/Gg412921(v=OCS.15))

  - <span></span>  
    [Move-csmanagementserver](https://technet.microsoft.com/library/Gg398465(v=OCS.15))

<!-- end list -->

  - [呼び出し-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))

**[Lync Server 2013 のエッジサーバーのコマンドレット](lync-server-2013-edge-server-cmdlets.md)**

  - <span></span>  
    [Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))

  - <span></span>  
    [Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))

  - <span></span>  
    [Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))

  - <span></span>  
    [Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))

  - <span></span>  
    [Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csavedgeconnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))

**[Lync Server 2013 のその他のサーバーの役割のコマンドレット](lync-server-2013-other-server-role-cmdlets.md)**

  - <span></span>  
    [CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [設定-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))

**[Lync Server 2013 のレジストラーおよびディレクターのコマンドレット](lync-server-2013-registrar-and-director-cmdlets.md)**

  - <span></span>  
    [設定-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Reset-cspoolregistrarstate](https://technet.microsoft.com/library/JJ619172(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [設定-CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))

  - <span></span>  
    [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))

  - <span></span>  
    [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))

  - <span></span>  
    [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [テスト-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))

**[Lync Server 2013 でのサービスのコマンドレット](lync-server-2013-services-cmdlets.md)**

  - <span></span>  
    [取得-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))

  - <span></span>  
    [Start-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))

  - <span></span>  
    [Stop-CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))

**[Lync Server 2013 のサーバーの役割およびサービスのコマンドレットのトラブルシューティング](lync-server-2013-troubleshooting-server-roles-and-services-cmdlets.md)**

  - <span></span>  
    [Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))

  - <span></span>  
    [Set-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))

  - <span></span>  
    [Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))

  - <span></span>  
    [Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))

  - <span></span>  
    [Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))

  - <span></span>  
    [Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))

  - <span></span>  
    [Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))

  - <span></span>  
    [Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-csdiagnosticsfilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))

  - <span></span>  
    [Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))

  - <span></span>  
    [Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))

  - <span></span>  
    [Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))

**[Lync Server 2013 の Web サーバーおよびサービスのコマンドレット](lync-server-2013-web-server-and-services-cmdlets.md)**

  - <span></span>  
    [新しい-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))

  - <span></span>  
    [新規-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))

  - <span></span>  
    [削除-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))

  - <span></span>  
    [設定-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新しい-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [設定-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))

  - <span></span>  
    [Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))

  - <span></span>  
    [Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))

  - <span></span>  
    [Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cswebtrustedcacertificate は](https://technet.microsoft.com/library/Gg412746(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-Csker' Osaccount '](https://technet.microsoft.com/library/Gg398485(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-Csker' Osaccountpassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))

<!-- end list -->

  - [テスト-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))

  - [Test-cswebappanonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))

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

