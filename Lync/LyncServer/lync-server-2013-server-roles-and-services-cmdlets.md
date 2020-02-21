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
ms.openlocfilehash: 47c01108bbdf7f9619f8318de36d1d35d49e8ac1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-roles-and-services-cmdlets-in-lync-server-2013"></a><span data-ttu-id="8536a-102">Lync Server 2013 のサーバーの役割およびサービスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="8536a-102">Server roles and services cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8536a-103">_**トピックの最終更新日:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="8536a-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="8536a-104">Microsoft Lync Server 2013 の多くのコンポーネントは、サーバーの役割またはサービスとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="8536a-104">Many Microsoft Lync Server 2013 components run as server roles or as services.</span></span> <span data-ttu-id="8536a-105">Lync Server 2013 には、これらのサーバーの役割とサービスを管理するための多数のコマンドレットが付属しています。</span><span class="sxs-lookup"><span data-stu-id="8536a-105">Lync Server 2013 ships with a number of cmdlets that enable you to manage these server roles and services.</span></span>

<div>

## <a name="server-roles-and-services-cmdlets"></a><span data-ttu-id="8536a-106">サーバーの役割およびサービスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="8536a-106">Server Roles and Services Cmdlets</span></span>

<span data-ttu-id="8536a-107">サーバーおよびサービスの役割に適用する管理タスクの多く (ただしすべてではありません) は、Lync Server コントロールパネルから実行できます。</span><span class="sxs-lookup"><span data-stu-id="8536a-107">Many (but not all) of the management tasks that apply to servers and service roles can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="8536a-108">たとえば、Lync Server コントロールパネルを使用して、アドレス帳のサーバー設定ではなく、アーカイブサーバーの設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="8536a-108">For example, you can manage Archiving Server settings but not Address Book Server settings by using Lync Server Control Panel.</span></span> <span data-ttu-id="8536a-109">ただし、これらのタスクはすべて、Lync Server 管理シェルまたはスクリプト内からコマンドレットを使用して実行できます。スクリプトを使用すると、特定のタスクを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="8536a-109">However, all these tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="8536a-110">以下は、サーバーの役割およびサービスの管理に直接関連するコマンドレットの一覧です。</span><span class="sxs-lookup"><span data-stu-id="8536a-110">The following is a list of cmdlets that relate directly to managing server roles and services:</span></span>

<span data-ttu-id="8536a-111">**[Lync Server 2013 のアドレス帳サーバーのコマンドレット](lync-server-2013-address-book-server-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="8536a-111">**[Address Book Server cmdlets in Lync Server 2013](lync-server-2013-address-book-server-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-112">[-CsAddressBookConfiguration の取得](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-112">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-113">[新しい-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-113">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-114">[-CsAddressBookConfiguration の削除](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-114">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-115">[設定-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-115">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-116">[Update-csaddressbook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-116">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-117">[デバッグ-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-117">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-118">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-118">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-119">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-119">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

<span data-ttu-id="8536a-120">**[Lync Server 2013 でのアーカイブと監視のコマンドレット](lync-server-2013-archiving-and-monitoring-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="8536a-120">**[Archiving and Monitoring cmdlets in Lync Server 2013](lync-server-2013-archiving-and-monitoring-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-121">[Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-121">[Get-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-122">[Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-122">[New-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-123">[Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-123">[Remove-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-124">[Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-124">[Set-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-125">[Export-csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-125">[Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-126">[Invoke-csarchivingdatabasepurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-126">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-127">[Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-127">[Get-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-128">[Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-128">[Grant-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-129">[Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-129">[New-CsArchivingPolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-130">[Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-130">[Remove-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-131">[Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-131">[Set-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-132">[CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-132">[Set-CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-133">[Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-133">[Get-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-134">[Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-134">[New-CsCdrConfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-135">[Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-135">[Remove-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-136">[Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-136">[Set-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-137">[設定-CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-137">[Set-CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-138">[取得-CsQoEConfiguration 場合](https://technet.microsoft.com/library/Gg399004(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-138">[Get-CsQoEConfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-139">[新しい-CsQoEConfiguration の場合](https://technet.microsoft.com/library/Gg398325(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-139">[New-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-140">[Remove-CsQoEConfiguration の場合](https://technet.microsoft.com/library/Gg425879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-140">[Remove-CsQoEConfiguration](https://technet.microsoft.com/library/Gg425879(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-141">[Set-CsQoEConfiguration 設定](https://technet.microsoft.com/library/Gg398245(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-141">[Set-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))</span></span>

<span data-ttu-id="8536a-142">[Invoke-cscdrdatabasepurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-142">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-143">[Export-csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-143">[Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-144">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-144">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-145">[-CsReportingConfiguration の取得](https://technet.microsoft.com/library/JJ205356(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-145">[Get-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-146">[新しい-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-146">[New-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-147">[-CsReportingConfiguration の削除](https://technet.microsoft.com/library/JJ204711(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-147">[Remove-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204711(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-148">[設定-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-148">[Set-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-149">[Set-cstestusercredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-149">[Get-CsTestUserCredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-150">[Set-cstestusercredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-150">[Remove-CsTestUserCredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-151">[Set-cstestusercredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-151">[Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-152">[Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-152">[Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-153">[Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-153">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-154">[Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-154">[Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-155">[Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-155">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-156">[Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-156">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-157">[New-Csex"Dedtest"](https://technet.microsoft.com/library/JJ205275(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-157">[New-CsExtendedTest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))</span></span>

<span data-ttu-id="8536a-158">**[Lync Server 2013 のデータベースおよび管理サーバーのコマンドレット](lync-server-2013-database-and-management-server-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="8536a-158">**[Database and Management Server cmdlets in Lync Server 2013](lync-server-2013-database-and-management-server-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-159">[Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-159">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-160">[Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-160">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-161">[Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-161">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-162">[-CsDatabase をインストールする](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-162">[Install-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-163">[テスト-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-163">[Test-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-164">[アンインストール-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-164">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="8536a-165">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-165">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="8536a-166">[Get-csdatabasemirrorstate 戻し](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-166">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="8536a-167">[Install-csmirrordatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-167">[Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="8536a-168">[アンインストール-Install-csmirrordatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-168">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-169">[取得-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-169">[Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-170">[設定-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-170">[Set-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-171">[-CsUserDatabase を更新する](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-171">[Update-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-172">[Move-csmanagementserver](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-172">[Move-CsManagementServer](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-173">[Move-csmanagementserver](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-173">[Set-CsManagementServer](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="8536a-174">[呼び出し-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-174">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span></span>

<span data-ttu-id="8536a-175">**[Lync Server 2013 のエッジサーバーのコマンドレット](lync-server-2013-edge-server-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="8536a-175">**[Edge Server cmdlets in Lync Server 2013](lync-server-2013-edge-server-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-176">[Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-176">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-177">[Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-177">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-178">[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-178">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-179">[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-179">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-180">[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-180">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-181">[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-181">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-182">[Test-csavedgeconnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-182">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-183">[CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-183">[Set-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span></span>

<span data-ttu-id="8536a-184">**[Lync Server 2013 のその他のサーバーの役割のコマンドレット](lync-server-2013-other-server-role-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="8536a-184">**[Other server role cmdlets in Lync Server 2013](lync-server-2013-other-server-role-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-185">[CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-185">[Set-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-186">[設定-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-186">[Set-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span></span>

<span data-ttu-id="8536a-187">**[Lync Server 2013 のレジストラーおよびディレクターのコマンドレット](lync-server-2013-registrar-and-director-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="8536a-187">**[Registrar and Director cmdlets in Lync Server 2013](lync-server-2013-registrar-and-director-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-188">[設定-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-188">[Set-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-189">[Reset-cspoolregistrarstate](https://technet.microsoft.com/library/JJ619172(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-189">[Reset-CsPoolRegistrarState](https://technet.microsoft.com/library/JJ619172(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-190">[設定-CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-190">[Set-CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-191">[Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-191">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-192">[Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-192">[New-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-193">[Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-193">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-194">[Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-194">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-195">[テスト-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-195">[Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))</span></span>

<span data-ttu-id="8536a-196">**[Lync Server 2013 でのサービスのコマンドレット](lync-server-2013-services-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="8536a-196">**[Services cmdlets in Lync Server 2013](lync-server-2013-services-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-197">[取得-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-197">[Get-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-198">[取得-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-198">[Get-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-199">[Start-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-199">[Start-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-200">[Stop-CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-200">[Stop-CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))</span></span>

<span data-ttu-id="8536a-201">**[Lync Server 2013 のサーバーの役割およびサービスのコマンドレットのトラブルシューティング](lync-server-2013-troubleshooting-server-roles-and-services-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="8536a-201">**[Troubleshooting server roles and services cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-server-roles-and-services-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-202">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-202">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-203">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-203">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-204">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-204">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-205">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-205">[New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-206">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-206">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-207">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-207">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-208">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-208">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-209">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-209">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-210">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-210">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-211">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-211">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-212">[New-csdiagnosticsfilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-212">[New-CsDiagnosticsFilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-213">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-213">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-214">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-214">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-215">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-215">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-216">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-216">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))</span></span>

<span data-ttu-id="8536a-217">**[Lync Server 2013 の Web サーバーおよびサービスのコマンドレット](lync-server-2013-web-server-and-services-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="8536a-217">**[Web server and services cmdlets in Lync Server 2013](lync-server-2013-web-server-and-services-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-218">[新しい-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-218">[New-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-219">[取得-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-219">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-220">[新規-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-220">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-221">[削除-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-221">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-222">[設定-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-222">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-223">[新しい-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-223">[New-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-224">[設定-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-224">[Set-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-225">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-225">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-226">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-226">[New-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-227">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-227">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-228">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-228">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-229">[New-cswebtrustedcacertificate は](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-229">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-230">[New-Csker' Osaccount '](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-230">[New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-231">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-231">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-232">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-232">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-233">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-233">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-234">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-234">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8536a-235">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-235">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8536a-236">[Set-Csker' Osaccountpassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-236">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="8536a-237">[テスト-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-237">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span></span>

  - <span data-ttu-id="8536a-238">[Test-cswebappanonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8536a-238">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8536a-239">関連項目</span><span class="sxs-lookup"><span data-stu-id="8536a-239">See Also</span></span>


[<span data-ttu-id="8536a-240">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="8536a-240">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

