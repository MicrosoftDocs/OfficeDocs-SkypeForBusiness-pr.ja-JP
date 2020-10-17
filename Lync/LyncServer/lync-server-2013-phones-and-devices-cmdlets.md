---
title: 'Lync Server 2013: 電話およびデバイスのコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones and devices cmdlets
ms:assetid: 6ebeba4b-43ce-4a31-9060-50d249b7564c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415657(v=OCS.15)
ms:contentKeyID: 48184467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d997b8a6c6dfc82943134d797ab2d98eb93d888
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524204"
---
# <a name="phones-and-devices-cmdlets-in-lync-server-2013"></a><span data-ttu-id="285e0-102">Lync Server 2013 の電話およびデバイスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="285e0-102">Phones and devices cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="285e0-103">_**トピックの最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="285e0-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="285e0-104">Microsoft Lync Server 2013 には、電話機やその他のハードウェアデバイスを管理するための多数のコマンドレットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="285e0-104">Microsoft Lync Server 2013 provides a number of cmdlets that enable you to manage telephones and other hardware devices.</span></span> <span data-ttu-id="285e0-105">これには、ボイスオーバー IP (VoIP) 電話などが含まれます。共通領域電話 (建物のロビー、カフェテリア、その他の公共の場所などの電話)。さらに、携帯電話の場合でも、Lync Phone Edition を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="285e0-105">This includes such things as Voice over IP (VoIP) phones; common area phones (for example, a phone in a building lobby, cafeteria, or other public location); and even analog phones, phones that are not capable of running Lync Phone Edition.</span></span>

<div>

## <a name="phones-and-devices-cmdlets"></a><span data-ttu-id="285e0-106">電話およびデバイスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="285e0-106">Phones and Devices Cmdlets</span></span>

<span data-ttu-id="285e0-107">**Csdeviceupdate**コマンドレットは、管理者がファームウェアの更新を電話機および Lync Phone Edition を実行している他のデバイスに配布できるようにする lync Server コンポーネントであるデバイス更新 Web サービスを管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="285e0-107">The **CsDeviceUpdate** cmdlets are used to manage the Device Update Web service, a Lync Server component that enables administrators to distribute firmware updates to telephones and other devices running Lync Phone Edition.</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-108">[CsAnalogDevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-108">[Get-CsAnalogDevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-109">[CsAnalogDevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-109">[Move-CsAnalogDevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-110">[CsAnalogDevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-110">[New-CsAnalogDevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-111">[CsAnalogDevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-111">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-112">[CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-112">[Set-CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="285e0-113">[Move-cscommonareaphone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-113">[Get-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-114">[Move-cscommonareaphone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-114">[Move-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-115">[Move-cscommonareaphone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-115">[New-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-116">[Move-cscommonareaphone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-116">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-117">[Move-cscommonareaphone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-117">[Set-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="285e0-118">[Get-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-118">[Get-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-119">[Get-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-119">[New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-120">[Get-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-120">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-121">[Get-csucphoneconfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-121">[Set-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="285e0-122">[インポート-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-122">[Import-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="285e0-123">[-CsDeviceUpdateConfiguration の取得](https://technet.microsoft.com/library/Gg399030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-123">[Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-124">[新規-CsDeviceUpdateConfiguration 変更](https://technet.microsoft.com/library/Gg425761(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-124">[New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-125">[-CsDeviceUpdateConfiguration 削除](https://technet.microsoft.com/library/Gg425933(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-125">[Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425933(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-126">[-CsDeviceUpdateConfiguration 設定](https://technet.microsoft.com/library/Gg398320(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-126">[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="285e0-127">[削除-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-127">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-128">[クリア-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-128">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="285e0-129">[承認-Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-129">[Approve-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-130">[Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-130">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-131">[Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-131">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-132">[Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-132">[Reset-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-133">[Restore-Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-133">[Restore-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="285e0-134">[テスト-CsPhoneBootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-134">[Test-CsPhoneBootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="285e0-135">[New-cstestdevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-135">[Get-CsTestDevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-136">[New-cstestdevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-136">[New-CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-137">[New-cstestdevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-137">[Remove-CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="285e0-138">[New-cstestdevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="285e0-138">[Set-CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="285e0-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="285e0-139">See Also</span></span>


[<span data-ttu-id="285e0-140">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="285e0-140">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

