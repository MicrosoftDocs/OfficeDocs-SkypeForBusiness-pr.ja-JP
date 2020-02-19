---
title: 'Lync Server 2013: コマンドレットのインデックス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets index
ms:assetid: cd37aba7-3d27-4db9-b69f-3a6da1fb4b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398867(v=OCS.15)
ms:contentKeyID: 48185661
ms.date: 04/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb713c1f328258bcb80173e0ff7e61ddd8304075
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-index"></a>Lync Server 2013 コマンドレットのインデックス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-04-12_

Microsoft Lync Server 2013 には、管理者が Lync Server 2013 をコマンドラインから管理できるようにするコマンドレットを700超えるコマンドレットが付属しています。 Lync Server コマンドレットは、通常、Lync Server 管理シェルで使用されます。 Lync server 管理シェルを使用する方法の1つは、Lync Server サービスまたはサーバーの役割を実行しているコンピューターにログオンする方法です。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。 管理シェルを開いた後、以下のようにコマンドを入力すると、コマンドレットに関するヘルプをコマンド ラインから直接取得できます。

    Get-Help New-CsVoicePolicy -Full

前述のコマンドは、**New-CsVoicePolicy** コマンドレットで使用できるすべてのヘルプを取得します。 別のコマンドレットのヘルプを表示するには、**New-CsVoicePolicy** を、ヘルプを取得したいコマンドレットの名前に置き換えます。

Lync Server の管理に使用できるコマンドレットの完全なリストを取得するには、Lync Server 管理シェルコマンドプロンプトで次のように入力します。

    Get-Command * -Module Lync -CommandType cmdlet

Lync Server 管理シェルの使用の詳細については、「Lync Server Windows PowerShell [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)のブログ」を参照してください。

<div>

## <a name="lync-server-2013-cmdlets"></a>Lync Server 2013 コマンドレット

以下に、Lync Server 2013 に同梱されているコマンドレットの一覧を示します。

  - [CsSlaDelegates](https://technet.microsoft.com/library/Mt703199(v=OCS.15))

  - [承認-Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))

  - [バックアップ-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))

  - [削除-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))

  - [クリア-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))

  - [Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))

  - [Convert-CsUserData](https://technet.microsoft.com/library/JJ205337(v=OCS.15))

  - [デバッグ-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))

  - [デバッグ-Csintrアポストロフィ Olreplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))

  - [Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))

  - [無効-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))

  - [無効-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))

  - [-CsComputer を無効にする](https://technet.microsoft.com/library/Gg399023(v=OCS.15))

  - [Disable-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))

  - [無効化-Csの会議室](https://technet.microsoft.com/library/JJ204723(v=OCS.15))

  - [Enable-cspublicprovider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))

  - [無効-CsUser](https://technet.microsoft.com/library/Gg398747(v=OCS.15))

  - [Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))

  - [Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))

  - [を有効にする-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))

  - [Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))

  - [Enable-Csの会議室](https://technet.microsoft.com/library/JJ205062(v=OCS.15))

  - [Enable-cspublicprovider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))

  - [を有効にする-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))

  - [Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))

  - [を有効にする-CsUser](https://technet.microsoft.com/library/Gg398711(v=OCS.15))

  - [Export-csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))

  - [エクスポート-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))

  - [Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))

  - [Export-cspersistentchatdata](https://technet.microsoft.com/library/JJ205378(v=OCS.15))

  - [Export-CsRgsConfiguration](https://technet.microsoft.com/library/JJ205011(v=OCS.15))

  - [エクスポート-CsUserData](https://technet.microsoft.com/library/JJ204897(v=OCS.15))

  - [Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))

  - [取得-CsAdContact](https://technet.microsoft.com/library/Gg412776(v=OCS.15))

  - [取得-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))

  - [-CsAddressBookConfiguration の取得](https://technet.microsoft.com/library/Gg398132(v=OCS.15))

  - [取得-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))

  - [-CsAdminRole の取得](https://technet.microsoft.com/library/Gg399050(v=OCS.15))

  - [-CsAdminRoleAssignment の取得](https://technet.microsoft.com/library/Gg398434(v=OCS.15))

  - [取得-CsAdPrincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))

  - [取得-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))

  - [取得-CsAdUser](https://technet.microsoft.com/library/Gg398592(v=OCS.15))

  - [Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))

  - [CsAnalogDevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))

  - [-CsAnnouncement を入手する](https://technet.microsoft.com/library/Gg398937(v=OCS.15))

  - [Get-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398655(v=OCS.15))

  - [Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))

  - [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))

  - [Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))

  - [Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690014(v=OCS.15))

  - [Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))

  - [Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))

  - [Get-csbackupservicestatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))

  - [CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))

  - [Get-csblockeddomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))

  - [Get-cscallparkorbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))

  - [Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))

  - [-CsCertificate の取得](https://technet.microsoft.com/library/Gg398227(v=OCS.15))

  - [-CsClientAccessLicense を取得する](https://technet.microsoft.com/library/JJ204853(v=OCS.15))

  - [Revoke-csclientcertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))

  - [-CsClientPinInfo を取得する](https://technet.microsoft.com/library/Gg425947(v=OCS.15))

  - [Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))

  - [-CsClientVersionConfiguration の取得](https://technet.microsoft.com/library/Gg399072(v=OCS.15))

  - [-CsClientVersionPolicy の取得](https://technet.microsoft.com/library/Gg398957(v=OCS.15))

  - [-CsClientVersionPolicyRule の取得](https://technet.microsoft.com/library/Gg413048(v=OCS.15))

  - [取得-CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))

  - [取得-CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))

  - [取得-CsClsScenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))

  - [New-csclssecuritygroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))

  - [Move-cscommonareaphone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))

  - [-CsComputer の取得](https://technet.microsoft.com/library/Gg425959(v=OCS.15))

  - [Get-csconferencedirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))

  - [Get-csconferencedisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))

  - [Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))

  - [Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))

  - [New-cscpsconfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))

  - [Get-csdatabasemirrorstate 戻し](https://technet.microsoft.com/library/JJ204845(v=OCS.15))

  - [-CsDeviceUpdateConfiguration の取得](https://technet.microsoft.com/library/Gg399030(v=OCS.15))

  - [Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))

  - [Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))

  - [Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))

  - [Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))

  - [Set-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))

  - [Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))

  - [Get-csdialinconferencinglanguagelist](https://technet.microsoft.com/library/Gg425869(v=OCS.15))

  - [Get-CsDialPlan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))

  - [CsEffectivePolicy](https://technet.microsoft.com/library/JJ204636(v=OCS.15))

  - [CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))

  - [Get-CsExUmContact](https://technet.microsoft.com/library/Gg412725(v=OCS.15))

  - [-CsFileTransferFilterConfiguration の取得](https://technet.microsoft.com/library/Gg398527(v=OCS.15))

  - [-CsFIPSConfiguration の取得](https://technet.microsoft.com/library/JJ204904(v=OCS.15))

  - [Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398348(v=OCS.15))

  - [取得-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))

  - [Get-Cシム Filterconfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))

  - [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))

  - [Test-csliscivicaddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))

  - [Get-cslislocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))

  - [CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))

  - [CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))

  - [CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))

  - [CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))

  - [CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))

  - [-CsLocationPolicy の取得](https://technet.microsoft.com/library/Gg398911(v=OCS.15))

  - [-CsManagementConnection の取得](https://technet.microsoft.com/library/Gg412849(v=OCS.15))

  - [Get-csmanagementstorereplicationstatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))

  - [Get-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690031(v=OCS.15))

  - [Get-csmediaconfiguration](https://technet.microsoft.com/library/Gg398128(v=OCS.15))

  - [-Cs会議構成の取得](https://technet.microsoft.com/library/Gg425875(v=OCS.15))

  - [取得-Cs会議室](https://technet.microsoft.com/library/JJ205277(v=OCS.15))

  - [Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690017(v=OCS.15))

  - [Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))

  - [Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))

  - [Get-csnetworkinterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))

  - [Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))

  - [Get-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))

  - [取得-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))

  - [Get-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))

  - [-CsNetworkSite の取得](https://technet.microsoft.com/library/Gg398766(v=OCS.15))

  - [-CsNetworkSubnet の取得](https://technet.microsoft.com/library/Gg412825(v=OCS.15))

  - [取得-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))

  - [取得-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))

  - [New-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))

  - [New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))

  - [Get-cspersistentchataddin 戻し](https://technet.microsoft.com/library/JJ204670(v=OCS.15))

  - [New-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))

  - [New-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ204625(v=OCS.15))

  - [Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205140(v=OCS.15))

  - [Get-cspersistentchateligibleprincipal](https://technet.microsoft.com/library/JJ204891(v=OCS.15))

  - [New-cspersistentchatendpoint](https://technet.microsoft.com/library/JJ204764(v=OCS.15))

  - [Get-cspersistentchatpolicy 戻し](https://technet.microsoft.com/library/JJ204673(v=OCS.15))

  - [Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))

  - [Set-cspersistentchatstate](https://technet.microsoft.com/library/JJ204915(v=OCS.15))

  - [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))

  - [取得-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))

  - [Get-cspoolbackuprelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))

  - [Get-cspoolupgradereadinessstate 戻し](https://technet.microsoft.com/library/JJ204689(v=OCS.15))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))

  - [Get-CsPresenceProvider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))

  - [Get-csprivacyconfiguration 戻し](https://technet.microsoft.com/library/Gg413002(v=OCS.15))

  - [-CsProxyConfiguration の取得](https://technet.microsoft.com/library/Gg399011(v=OCS.15))

  - [Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))

  - [Enable-cspublicprovider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))

  - [Get-Cspの、構成](https://technet.microsoft.com/library/Hh690049(v=OCS.15))

  - [取得-CsQoEConfiguration 場合](https://technet.microsoft.com/library/Gg399004(v=OCS.15))

  - [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))

  - [-CsReportingConfiguration の取得](https://technet.microsoft.com/library/JJ205356(v=OCS.15))

  - [Get-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg425793(v=OCS.15))

  - [Get-CsRgsConfiguration](https://technet.microsoft.com/library/Gg412762(v=OCS.15))

  - [Get-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg412983(v=OCS.15))

  - [Get-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398284(v=OCS.15))

  - [Get-CsRgsQueue](https://technet.microsoft.com/library/Gg412759(v=OCS.15))

  - [Get-CsRgsWorkflow](https://technet.microsoft.com/library/Gg425766(v=OCS.15))

  - [-CsRoutingConfiguration の取得](https://technet.microsoft.com/library/Gg425851(v=OCS.15))

  - [-CsServerApplication の取得](https://technet.microsoft.com/library/Gg425948(v=OCS.15))

  - [Get-csserverversion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))

  - [取得-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))

  - [取得-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))

  - [New-cssipdomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))

  - [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))

  - [Set-csslaconfiguration](https://technet.microsoft.com/library/Mt703200(v=OCS.15))

  - [取得-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))

  - [-CsStaticRoutingConfiguration の取得](https://technet.microsoft.com/library/Gg398754(v=OCS.15))

  - [New-cstestdevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))

  - [Set-cstestusercredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))

  - [取得-CsTopology テクノロジー](https://technet.microsoft.com/library/Gg412824(v=OCS.15))

  - [取得-CsTrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))

  - [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))

  - [「New-cstrustedapplication](https://technet.microsoft.com/library/Gg399025(v=OCS.15))

  - [CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg425843(v=OCS.15))

  - [CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg413035(v=OCS.15))

  - [「New-cstrustedapplicationpool](https://technet.microsoft.com/library/Gg413055(v=OCS.15))

  - [Get-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))

  - [Get-csuiculture](https://technet.microsoft.com/library/Gg412900(v=OCS.15))

  - [Remove-csunassignednumber](https://technet.microsoft.com/library/Gg412792(v=OCS.15))

  - [取得-CsUser](https://technet.microsoft.com/library/Gg398125(v=OCS.15))

  - [取得-CsUserAcp](https://technet.microsoft.com/library/Gg398978(v=OCS.15))

  - [取得-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))

  - [取得-CsUserPoolInfo](https://technet.microsoft.com/library/Gg398615(v=OCS.15))

  - [-CsUserReplicatorConfiguration の取得](https://technet.microsoft.com/library/Gg398548(v=OCS.15))

  - [-Csuserサービス構成を取得する](https://technet.microsoft.com/library/Gg398133(v=OCS.15))

  - [-Csuserサービスポリシーを取得する](https://technet.microsoft.com/library/JJ204838(v=OCS.15))

  - [CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))

  - [Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg425732(v=OCS.15))

  - [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))

  - [Get-csvoiceroute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))

  - [Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))

  - [Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))

  - [Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))

  - [Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))

  - [取得-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))

  - [Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))

  - [-CsXmppGatewayConfiguration の取得](https://technet.microsoft.com/library/JJ204869(v=OCS.15))

  - [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))

  - [Grant-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))

  - [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))

  - [Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))

  - [Get-csdialplan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))

  - [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))

  - [Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412829(v=OCS.15))

  - [Grant-CsLocationPolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))

  - [Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690038(v=OCS.15))

  - [付与-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))

  - [Get-cspersistentchatpolicy 戻し](https://technet.microsoft.com/library/JJ204907(v=OCS.15))

  - [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))

  - [Grant-CsPresencePolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))

  - [Grant-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))

  - [Grant-Csuserサービスポリシー](https://technet.microsoft.com/library/JJ205388(v=OCS.15))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))

  - [Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))

  - [インポート-Csアナウンス Ementfile](https://technet.microsoft.com/library/Gg398472(v=OCS.15))

  - [インポート-CsCertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))

  - [インポート-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))

  - [インポート-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))

  - [Import-cslegacyconferencedirectory](https://technet.microsoft.com/library/Gg398418(v=OCS.15))

  - [Import-cslegacyconfiguration](https://technet.microsoft.com/library/Gg412923(v=OCS.15))

  - [Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))

  - [Export-cspersistentchatdata](https://technet.microsoft.com/library/JJ204709(v=OCS.15))

  - [Import-CsRgsAudioFile](https://technet.microsoft.com/library/Gg412830(v=OCS.15))

  - [Import-CsRgsConfiguration](https://technet.microsoft.com/library/JJ205245(v=OCS.15))

  - [インポート-CsUserData](https://technet.microsoft.com/library/JJ205373(v=OCS.15))

  - [Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))

  - [-CsDatabase をインストールする](https://technet.microsoft.com/library/Gg399044(v=OCS.15))

  - [Install-csmirrordatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))

  - [Invoke-csarchivingdatabasepurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))

  - [Invoke-csbackupservicesync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))

  - [Invoke-cscdrdatabasepurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))

  - [Invoke-CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))

  - [呼び出し-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))

  - [Invoke-csmanagementstorereplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))

  - [Invoke-cspoolfailback](https://technet.microsoft.com/library/JJ204873(v=OCS.15))

  - [Initialize-cspoolfailover](https://technet.microsoft.com/library/JJ205189(v=OCS.15))

  - [Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))

  - [Invoke-csucsrollback](https://technet.microsoft.com/library/JJ204661(v=OCS.15))

  - [ロック-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - [Merge-cslegacytopology](https://technet.microsoft.com/library/Gg425870(v=OCS.15))

  - [CsAnalogDevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - [Move-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398188(v=OCS.15))

  - [Move-cscommonareaphone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - [Get-csconferencedirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))

  - [Move-CsExUmContact](https://technet.microsoft.com/library/Gg425842(v=OCS.15))

  - [Move-cslegacyuser](https://technet.microsoft.com/library/Gg413025(v=OCS.15))

  - [Move-csmanagementserver](https://technet.microsoft.com/library/Gg412921(v=OCS.15))

  - [移行-Csの会議室](https://technet.microsoft.com/library/JJ204889(v=OCS.15))

  - [Move-CsRgsConfiguration](https://technet.microsoft.com/library/Gg398782(v=OCS.15))

  - [Move-CsUser](https://technet.microsoft.com/library/Gg398528(v=OCS.15))

  - [新しい-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))

  - [新しい-CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))

  - [新しい-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))

  - [CsAnalogDevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))

  - [新しい-CsAnnouncement](https://technet.microsoft.com/library/Gg398522(v=OCS.15))

  - [Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))

  - [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))

  - [Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690022(v=OCS.15))

  - [Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))

  - [CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))

  - [Get-csblockeddomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))

  - [Get-cscallparkorbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))

  - [Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))

  - [新しい-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))

  - [新しい-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))

  - [新しい-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))

  - [新しい-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))

  - [新しい-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))

  - [新しい-CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))

  - [新しい-CsClsScenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))

  - [New-csclssecuritygroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))

  - [Move-cscommonareaphone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))

  - [Get-csconferencedirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))

  - [Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))

  - [Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))

  - [New-cscpsconfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))

  - [新規-CsDeviceUpdateConfiguration 変更](https://technet.microsoft.com/library/Gg425761(v=OCS.15))

  - [Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))

  - [Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))

  - [New-csdiagnosticsfilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))

  - [Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))

  - [Set-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))

  - [Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))

  - [Get-csdialplan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))

  - [New-Csex"Dedtest"](https://technet.microsoft.com/library/JJ205275(v=OCS.15))

  - [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))

  - [New-CsExUmContact](https://technet.microsoft.com/library/Gg398139(v=OCS.15))

  - [新しい-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))

  - [新しい-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))

  - [Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))

  - [New-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398653(v=OCS.15))

  - [新規-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

  - [New-Cシム Filterconfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))

  - [New-csissuedcertid](https://technet.microsoft.com/library/Gg425814(v=OCS.15))

  - [New-Csker' Osaccount '](https://technet.microsoft.com/library/Gg398485(v=OCS.15))

  - [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))

  - [新しい-CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))

  - [新しい-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690035(v=OCS.15))

  - [Get-csmediaconfiguration](https://technet.microsoft.com/library/Gg425881(v=OCS.15))

  - [新しい-Cs会議の構成](https://technet.microsoft.com/library/Gg398065(v=OCS.15))

  - [Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh689987(v=OCS.15))

  - [Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))

  - [新しい-CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))

  - [新しい-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))

  - [新しい-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))

  - [Get-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))

  - [新しい-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/library/Gg425718(v=OCS.15))

  - [新しい-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))

  - [新しい-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))

  - [新しい-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))

  - [新しい-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))

  - [新しい-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))

  - [New-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))

  - [New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))

  - [Get-cspersistentchataddin 戻し](https://technet.microsoft.com/library/JJ204641(v=OCS.15))

  - [New-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))

  - [New-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ205163(v=OCS.15))

  - [Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205330(v=OCS.15))

  - [New-cspersistentchatendpoint](https://technet.microsoft.com/library/JJ204811(v=OCS.15))

  - [Get-cspersistentchatpolicy 戻し](https://technet.microsoft.com/library/JJ205396(v=OCS.15))

  - [Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))

  - [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))

  - [新しい-CsPresencePolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))

  - [新しい-CsPresenceProvider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))

  - [Get-csprivacyconfiguration 戻し](https://technet.microsoft.com/library/Gg398807(v=OCS.15))

  - [新しい-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))

  - [Enable-cspublicprovider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))

  - [新しい-Cspの、構成](https://technet.microsoft.com/library/Hh690027(v=OCS.15))

  - [新しい-CsQoEConfiguration の場合](https://technet.microsoft.com/library/Gg398325(v=OCS.15))

  - [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))

  - [新しい-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))

  - [New-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg413065(v=OCS.15))

  - [New-CsRgsAnswer](https://technet.microsoft.com/library/Gg412812(v=OCS.15))

  - [New-CsRgsCallAction](https://technet.microsoft.com/library/Gg398136(v=OCS.15))

  - [New-CsRgsHoliday](https://technet.microsoft.com/library/Gg398075(v=OCS.15))

  - [New-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398403(v=OCS.15))

  - [New-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398291(v=OCS.15))

  - [New-CsRgsPrompt](https://technet.microsoft.com/library/Gg398486(v=OCS.15))

  - [New-CsRgsQuestion](https://technet.microsoft.com/library/Gg398186(v=OCS.15))

  - [New-CsRgsQueue](https://technet.microsoft.com/library/Gg398989(v=OCS.15))

  - [New-CsRgsTimeRange](https://technet.microsoft.com/library/Gg399040(v=OCS.15))

  - [New-CsRgsWorkflow](https://technet.microsoft.com/library/Gg398246(v=OCS.15))

  - [新しい-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))

  - [新しい-CsServerApplication](https://technet.microsoft.com/library/Gg398096(v=OCS.15))

  - [新しい-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))

  - [新規-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))

  - [新しい-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))

  - [New-cssipdomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))

  - [New-cssipproxycustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))

  - [New-cssipproxyrealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))

  - [New-cssipproxytcp](https://technet.microsoft.com/library/Gg425745(v=OCS.15))

  - [New-cssipproxytls](https://technet.microsoft.com/library/Gg398629(v=OCS.15))

  - [New-cssipproxytransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))

  - [New-cssipproxyusedefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))

  - [New-cssipproxyusedefaultcert は](https://technet.microsoft.com/library/Gg425858(v=OCS.15))

  - [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))

  - [新しい-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))

  - [新しい-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))

  - [New-cstestdevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))

  - [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))

  - [「New-cstrustedapplication](https://technet.microsoft.com/library/Gg398259(v=OCS.15))

  - [CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398405(v=OCS.15))

  - [CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398594(v=OCS.15))

  - [「New-cstrustedapplicationpool](https://technet.microsoft.com/library/Gg425804(v=OCS.15))

  - [Get-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))

  - [Remove-csunassignednumber](https://technet.microsoft.com/library/Gg398651(v=OCS.15))

  - [新しい-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))

  - [新しい-Csuserサービスの構成](https://technet.microsoft.com/library/Gg412926(v=OCS.15))

  - [新しい-Csuserサービスポリシー](https://technet.microsoft.com/library/JJ205072(v=OCS.15))

  - [New-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg425849(v=OCS.15))

  - [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398240(v=OCS.15))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))

  - [CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))

  - [Get-csvoiceroute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))

  - [Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))

  - [Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))

  - [Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))

  - [新しい-CsWebLink](https://technet.microsoft.com/library/Hh690053(v=OCS.15))

  - [Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))

  - [New-cswebtrustedcacertificate は](https://technet.microsoft.com/library/Gg412746(v=OCS.15))

  - [新しい-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))

  - [Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))

  - [発行-CsTopology テクノロジー](https://technet.microsoft.com/library/Gg398953(v=OCS.15))

  - [-CsAddressBookConfiguration の削除](https://technet.microsoft.com/library/Gg398934(v=OCS.15))

  - [-CsAdminRole の削除](https://technet.microsoft.com/library/Gg413036(v=OCS.15))

  - [-CsAllowedDomain の削除](https://technet.microsoft.com/library/Gg398913(v=OCS.15))

  - [CsAnalogDevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - [削除-CsAnnouncement](https://technet.microsoft.com/library/Gg412766(v=OCS.15))

  - [Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))

  - [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))

  - [Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690054(v=OCS.15))

  - [Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))

  - [Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))

  - [CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))

  - [Get-csblockeddomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))

  - [Get-cscallparkorbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))

  - [Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))

  - [削除-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))

  - [-CsClientPolicy を削除する](https://technet.microsoft.com/library/Gg425772(v=OCS.15))

  - [-CsClientVersionConfiguration の削除](https://technet.microsoft.com/library/Gg425925(v=OCS.15))

  - [-CsClientVersionPolicy の削除](https://technet.microsoft.com/library/Gg425801(v=OCS.15))

  - [-CsClientVersionPolicyRule の削除](https://technet.microsoft.com/library/Gg398541(v=OCS.15))

  - [削除-CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))

  - [削除-CsClsScenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))

  - [New-csclssecuritygroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))

  - [Move-cscommonareaphone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - [Get-csconferencedirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))

  - [Get-csconferencedisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))

  - [Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))

  - [Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))

  - [Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))

  - [New-cscpsconfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))

  - [-CsDeviceUpdateConfiguration 削除](https://technet.microsoft.com/library/Gg425933(v=OCS.15))

  - [Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))

  - [Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))

  - [Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))

  - [Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))

  - [Set-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))

  - [Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))

  - [Get-csdialplan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))

  - [CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg425810(v=OCS.15))

  - [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))

  - [Remove-CsExUmContact](rehttps://technet.microsoft.com/library/Gg425842(v=OCS.15))

  - [削除-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))

  - [削除-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))

  - [Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))

  - [Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398211(v=OCS.15))

  - [Remove-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))

  - [Remove-Cシム Filterconfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))

  - [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))

  - [Get-cslislocation](https://technet.microsoft.com/library/Gg425722(v=OCS.15))

  - [CsLisPort](https://technet.microsoft.com/library/Gg412899(v=OCS.15))

  - [CsLisServiceProvider](https://technet.microsoft.com/library/Gg398904(v=OCS.15))

  - [CsLisSubnet](https://technet.microsoft.com/library/Gg413053(v=OCS.15))

  - [CsLisSwitch](https://technet.microsoft.com/library/Gg398352(v=OCS.15))

  - [CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398461(v=OCS.15))

  - [削除-CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))

  - [-CsManagementConnection を削除する](https://technet.microsoft.com/library/Gg425803(v=OCS.15))

  - [Remove-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690026(v=OCS.15))

  - [Get-csmediaconfiguration](https://technet.microsoft.com/library/Gg398705(v=OCS.15))

  - [削除-Cs会議の構成](https://technet.microsoft.com/library/Gg412775(v=OCS.15))

  - [Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690048(v=OCS.15))

  - [Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))

  - [Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))

  - [-CsNetworkInterRegionRoute の削除](https://technet.microsoft.com/library/Gg398743(v=OCS.15))

  - [Get-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))

  - [-CsNetworkRegion の削除](https://technet.microsoft.com/library/Gg398466(v=OCS.15))

  - [-CsNetworkRegionLink の削除](https://technet.microsoft.com/library/Gg413012(v=OCS.15))

  - [-CsNetworkSite の削除](https://technet.microsoft.com/library/Gg398135(v=OCS.15))

  - [-CsNetworkSubnet の削除](https://technet.microsoft.com/library/Gg425726(v=OCS.15))

  - [Remove-CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))

  - [New-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))

  - [New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))

  - [Get-cspersistentchataddin 戻し](https://technet.microsoft.com/library/JJ205350(v=OCS.15))

  - [New-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204660(v=OCS.15))

  - [New-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ204767(v=OCS.15))

  - [Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ204927(v=OCS.15))

  - [New-cspersistentchatendpoint](https://technet.microsoft.com/library/JJ204626(v=OCS.15))

  - [Test-cspersistentchatmessage](https://technet.microsoft.com/library/JJ204668(v=OCS.15))

  - [Get-cspersistentchatpolicy 戻し](https://technet.microsoft.com/library/JJ205301(v=OCS.15))

  - [Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ204639(v=OCS.15))

  - [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))

  - [Remove-CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))

  - [Remove-CsPresenceProvider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))

  - [Get-csprivacyconfiguration 戻し](https://technet.microsoft.com/library/Gg425821(v=OCS.15))

  - [-CsProxyConfiguration を削除する](https://technet.microsoft.com/library/Gg398553(v=OCS.15))

  - [Enable-cspublicprovider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))

  - [削除-Cspの "構成"](https://technet.microsoft.com/library/Hh690028(v=OCS.15))

  - [Remove-CsQoEConfiguration の場合](https://technet.microsoft.com/library/Gg425879(v=OCS.15))

  - [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))

  - [-CsReportingConfiguration の削除](https://technet.microsoft.com/library/JJ204711(v=OCS.15))

  - [Remove-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg398969(v=OCS.15))

  - [Remove-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398521(v=OCS.15))

  - [Remove-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398568(v=OCS.15))

  - [Remove-CsRgsQueue](https://technet.microsoft.com/library/Gg398576(v=OCS.15))

  - [Remove-CsRgsWorkflow](https://technet.microsoft.com/library/Gg398765(v=OCS.15))

  - [-CsRoutingConfiguration の削除](https://technet.microsoft.com/library/Gg398643(v=OCS.15))

  - [-CsServerApplication の削除](https://technet.microsoft.com/library/Gg398366(v=OCS.15))

  - [削除-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))

  - [New-cssipdomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))

  - [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))

  - [Set-csslaconfiguration](https://technet.microsoft.com/library/Mt703201(v=OCS.15))

  - [CsSlaDelegates](https://technet.microsoft.com/library/Mt703203(v=OCS.15))

  - [-CsStaticRoutingConfiguration の削除](https://technet.microsoft.com/library/Gg398668(v=OCS.15))

  - [New-cstestdevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))

  - [Set-cstestusercredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))

  - [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))

  - [「New-cstrustedapplication](https://technet.microsoft.com/library/Gg398176(v=OCS.15))

  - [CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398838(v=OCS.15))

  - [CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398837(v=OCS.15))

  - [「New-cstrustedapplicationpool](https://technet.microsoft.com/library/Gg398750(v=OCS.15))

  - [Get-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))

  - [Remove-csunassignednumber](https://technet.microsoft.com/library/Gg398209(v=OCS.15))

  - [削除-CsUserAcp](https://technet.microsoft.com/library/Gg398982(v=OCS.15))

  - [-CsUserReplicatorConfiguration の削除](https://technet.microsoft.com/library/Gg425738(v=OCS.15))

  - [-Csuserサービス構成を削除する](https://technet.microsoft.com/library/Gg398722(v=OCS.15))

  - [削除-Csuserサービスポリシー](https://technet.microsoft.com/library/JJ204629(v=OCS.15))

  - [-CsUserStoreBackupData を削除する](https://technet.microsoft.com/library/JJ205003(v=OCS.15))

  - [CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))

  - [Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg398573(v=OCS.15))

  - [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398501(v=OCS.15))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))

  - [Get-csvoiceroute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))

  - [Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ204799(v=OCS.15))

  - [Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))

  - [Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))

  - [Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))

  - [削除-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))

  - [要求-CsCertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))

  - [Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))

  - [Restore-Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))

  - [Revoke-csclientcertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))

  - [Revoke-CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))

  - [失効-CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))

  - [Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

  - [設定-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))

  - [設定-CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))

  - [設定-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))

  - [CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))

  - [設定-CsAnnouncement](https://technet.microsoft.com/library/Gg425752(v=OCS.15))

  - [CsApplicationServer](https://technet.microsoft.com/library/Gg398562(v=OCS.15))

  - [Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))

  - [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))

  - [CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))

  - [Set-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))

  - [Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh689980(v=OCS.15))

  - [Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))

  - [Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))

  - [CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))

  - [Get-csblockeddomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))

  - [Get-cscallparkorbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))

  - [Set-cscallparkservicemusiconholdfile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))

  - [Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))

  - [設定-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))

  - [-CsClientPin の設定](https://technet.microsoft.com/library/Gg398929(v=OCS.15))

  - [設定-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))

  - [-CsClientVersionConfiguration の設定](https://technet.microsoft.com/library/Gg398623(v=OCS.15))

  - [-CsClientVersionPolicy の設定](https://technet.microsoft.com/library/Gg398876(v=OCS.15))

  - [Set-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))

  - [設定-CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))

  - [Set-CsClsScenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))

  - [Set-CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))

  - [New-csclssecuritygroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))

  - [Move-cscommonareaphone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))

  - [Get-csconferencedisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))

  - [CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))

  - [Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))

  - [Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))

  - [Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))

  - [New-cscpsconfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))

  - [-CsDeviceUpdateConfiguration 設定](https://technet.microsoft.com/library/Gg398320(v=OCS.15))

  - [Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))

  - [Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))

  - [Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))

  - [Set-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))

  - [Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))

  - [Get-csdialplan](https://technet.microsoft.com/library/Gg398644(v=OCS.15))Get-csdialplan

  - [設定-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))

  - [CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))

  - [CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg398620(v=OCS.15))

  - [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))

  - [Set-CsExUmContact](https://technet.microsoft.com/library/Gg412944(v=OCS.15))

  - [Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))

  - [設定-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))

  - [Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))

  - [Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412722(v=OCS.15))

  - [Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))

  - [Set-Cシム Filterconfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))

  - [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))

  - [Set-Csker' Osaccountpassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))

  - [Get-cslislocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))

  - [CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))

  - [CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))

  - [CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))

  - [CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))

  - [CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))

  - [設定-CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))

  - [-CsManagementConnection の設定](https://technet.microsoft.com/library/Gg413045(v=OCS.15))

  - [Set-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690050(v=OCS.15))

  - [Move-csmanagementserver](https://technet.microsoft.com/library/Gg398465(v=OCS.15))

  - [Get-csmediaconfiguration](https://technet.microsoft.com/library/Gg398580(v=OCS.15))

  - [Set-CsMediationServer](https://technet.microsoft.com/library/Gg398213(v=OCS.15))

  - [設定-Cs会議構成](https://technet.microsoft.com/library/Gg398648(v=OCS.15))

  - [セットアップ-Csの会議室](https://technet.microsoft.com/library/JJ204831(v=OCS.15))

  - [Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690021(v=OCS.15))

  - [設定-CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))

  - [Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))

  - [Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))

  - [設定-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))

  - [Get-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))

  - [設定-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))

  - [設定-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))

  - [設定-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))

  - [設定-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))

  - [Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))

  - [Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))

  - [New-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))

  - [New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))

  - [Set-cspersistentchatactiveserver](https://technet.microsoft.com/library/JJ205065(v=OCS.15))

  - [Get-cspersistentchataddin 戻し](https://technet.microsoft.com/library/JJ204721(v=OCS.15))

  - [New-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))

  - [New-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ204949(v=OCS.15))

  - [Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205122(v=OCS.15))

  - [Get-cspersistentchatpolicy 戻し](https://technet.microsoft.com/library/JJ205192(v=OCS.15))

  - [Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))

  - [Set-cspersistentchatstate](https://technet.microsoft.com/library/JJ205109(v=OCS.15))

  - [Get-cspinpolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))

  - [Set-CsPresencePolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))

  - [Set-CsPresenceProvider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))

  - [Get-csprivacyconfiguration 戻し](https://technet.microsoft.com/library/Gg398484(v=OCS.15))

  - [設定-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))

  - [Set-CsPstnGateway](https://technet.microsoft.com/library/Gg398408(v=OCS.15))

  - [Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))

  - [Enable-cspublicprovider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))

  - [Set-Cspの通知構成](https://technet.microsoft.com/library/Hh690013(v=OCS.15))

  - [Set-CsQoEConfiguration 設定](https://technet.microsoft.com/library/Gg398245(v=OCS.15))

  - [設定-CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))

  - [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))

  - [設定-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))

  - [Set-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg425955(v=OCS.15))

  - [Set-CsRgsConfiguration](https://technet.microsoft.com/library/Gg425728(v=OCS.15))

  - [Set-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398736(v=OCS.15))

  - [Set-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg412929(v=OCS.15))

  - [Set-CsRgsQueue](https://technet.microsoft.com/library/Gg412947(v=OCS.15))

  - [Set-CsRgsWorkflow](https://technet.microsoft.com/library/Gg425845(v=OCS.15))

  - [-CsRoutingConfiguration の設定](https://technet.microsoft.com/library/Gg412811(v=OCS.15))

  - [設定-CsServerApplication](https://technet.microsoft.com/library/Gg412850(v=OCS.15))

  - [設定-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))

  - [New-cssipdomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))

  - [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))

  - [設定-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))

  - [Set-csslaconfiguration](https://technet.microsoft.com/library/Mt703202(v=OCS.15))

  - [-CsStaticRoutingConfiguration の設定](https://technet.microsoft.com/library/Gg398724(v=OCS.15))

  - [New-cstestdevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))

  - [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))

  - [「New-cstrustedapplication](https://technet.microsoft.com/library/Gg425840(v=OCS.15))

  - [CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398509(v=OCS.15))

  - [「New-cstrustedapplicationpool](https://technet.microsoft.com/library/Gg398187(v=OCS.15))

  - [Get-csucphoneconfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))

  - [Get-csuiculture](https://technet.microsoft.com/library/Gg398354(v=OCS.15))

  - [Remove-csunassignednumber](https://technet.microsoft.com/library/Gg399033(v=OCS.15))

  - [設定-CsUser](https://technet.microsoft.com/library/Gg398510(v=OCS.15))

  - [設定-CsUserAcp](https://technet.microsoft.com/library/Gg413018(v=OCS.15))

  - [設定-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))

  - [設定-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))

  - [設定-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))

  - [-Csuserサービス構成の設定](https://technet.microsoft.com/library/Gg398340(v=OCS.15))

  - [設定-Csuserサービスポリシー](https://technet.microsoft.com/library/JJ205414(v=OCS.15))

  - [CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))

  - [Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg412948(v=OCS.15))

  - [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))

  - [Get-csvoiceroute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))

  - [Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))

  - [Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))

  - [Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))

  - [設定-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))

  - [Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))

  - [Set-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))

  - [-CsXmppGatewayConfiguration の設定](https://technet.microsoft.com/library/JJ204769(v=OCS.15))

  - [Start-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))

  - [Stop-CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))

  - [同期-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))

  - [Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))

  - [Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))

  - [テスト-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))

  - [Test-csaudioconferencingprovider](https://technet.microsoft.com/library/JJ205117(v=OCS.15))

  - [テスト-CsAVConference 会議](https://technet.microsoft.com/library/Gg412749(v=OCS.15))

  - [Test-csavedgeconnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))

  - [Test-Cs/Test](https://technet.microsoft.com/library/Gg398647(v=OCS.15))

  - [テスト-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))

  - [テスト-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))

  - [Test-csdataconference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))

  - [テスト-Csダイヤルイン会議](https://technet.microsoft.com/library/Gg399013(v=OCS.15))

  - [Get-csdialplan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))

  - [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))

  - [Test-CsExStorageNotification](https://technet.microsoft.com/library/JJ205331(v=OCS.15))

  - [Test-CsExUMConnectivity](https://technet.microsoft.com/library/JJ204784(v=OCS.15))

  - [Test-CsExUMVoiceMail](https://technet.microsoft.com/library/JJ205058(v=OCS.15))

  - [Test-csfederatedpartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))

  - [テスト-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))

  - [テスト-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))

  - [テスト-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))

  - [Test-csintertrunkrouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))

  - [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))

  - [Test-csliscivicaddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))

  - [Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))

  - [テスト-CsLocationPolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))

  - [テスト-CsMcxConference 会議](https://technet.microsoft.com/library/Hh690045(v=OCS.15))

  - [Test-csmcxp2pim](https://technet.microsoft.com/library/Hh690020(v=OCS.15))

  - [テスト-CsMcxPushNotification](https://technet.microsoft.com/library/Hh690043(v=OCS.15))

  - [テスト-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))

  - [Test-csp2pav](https://technet.microsoft.com/library/Gg412821(v=OCS.15))

  - [Test-cspersistentchatmessage](https://technet.microsoft.com/library/JJ204656(v=OCS.15))

  - [テスト-CsPhoneBootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))

  - [テスト-CsPresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))

  - [テスト-CsPstnOutboundCall](https://technet.microsoft.com/library/Gg398207(v=OCS.15))

  - [テスト-CsPstnPeerToPeerCall](https://technet.microsoft.com/library/Gg398662(v=OCS.15))

  - [テスト-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))

  - [テスト-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))

  - [テスト-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))

  - [テスト-CsTopology テクノロジー](https://technet.microsoft.com/library/Gg398127(v=OCS.15))

  - [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))

  - [Test-csunifiedcontactstore](https://technet.microsoft.com/library/JJ204662(v=OCS.15))

  - [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))

  - [Get-csvoiceroute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

  - [Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))

  - [CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))

  - [Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))

  - [テスト-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))

  - [Test-cswebappanonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))

  - [テスト-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))

  - [テスト-CsXmppIM](https://technet.microsoft.com/library/JJ205423(v=OCS.15))

  - [アンインストール-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))

  - [アンインストール-Install-csmirrordatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))

  - [ロック解除-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - [未発行-Export-cslisconfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))

  - [Update-csaddressbook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))

  - [-CsAdminRole の更新](https://technet.microsoft.com/library/JJ204851(v=OCS.15))

  - [CsTenantMeetingUrl](https://technet.microsoft.com/library/Dn424754(v=OCS.15))

  - [更新プログラム-CsUserData](https://technet.microsoft.com/library/JJ205358(v=OCS.15))

  - [-CsUserDatabase を更新する](https://technet.microsoft.com/library/Gg398682(v=OCS.15))

</div>

</div>

<span> </span>

</div>

</div>

</div>

