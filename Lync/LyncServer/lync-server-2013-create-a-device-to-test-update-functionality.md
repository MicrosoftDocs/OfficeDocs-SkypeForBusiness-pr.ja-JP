---
title: 'Lync Server 2013: 更新プログラムの機能をテストするデバイスを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 227ca68433cfcc41f966e220ffc826357b50d54b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a><span data-ttu-id="c663e-102">Lync Server 2013 で更新プログラムの機能をテストするためのデバイスを作成する</span><span class="sxs-lookup"><span data-stu-id="c663e-102">Create a device to test update functionality in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c663e-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c663e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c663e-104">[**テスト デバイス**] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。</span><span class="sxs-lookup"><span data-stu-id="c663e-104">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="c663e-105">デバイスは、(Lync Server 環境全体を通じて) グローバルに、または単一のサイト内で一括してテストできます。</span><span class="sxs-lookup"><span data-stu-id="c663e-105">You can test a device globally (throughout your entire Lync Server environment) or within a single site.</span></span> <span data-ttu-id="c663e-106">テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。</span><span class="sxs-lookup"><span data-stu-id="c663e-106">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="c663e-107">デバイスを追加すると、そのデバイスは Lync Server コントロールパネルの [**テストデバイス**] ページの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c663e-107">When you add a device, it appears in the list on the **Test Device** page of the Lync Server Control Panel.</span></span>

<div>

## <a name="to-add-a-test-device"></a><span data-ttu-id="c663e-108">テスト デバイスを追加するには</span><span class="sxs-lookup"><span data-stu-id="c663e-108">To add a test device</span></span>

1.  <span data-ttu-id="c663e-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c663e-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c663e-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c663e-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="c663e-111">左側のナビゲーション バーで [**クライアント**] をクリックしてから、[**テスト デバイス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c663e-111">In the left navigation bar, click **Clients**, and then click **Test Device**.</span></span>

3.  <span data-ttu-id="c663e-112">[**新規**] をクリックし、[**グローバル テスト デバイス**] か [**サイト テスト デバイス**] のどちらかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c663e-112">Click **New**, and then click either **Global test device** or **Site test device**.</span></span>

4.  <span data-ttu-id="c663e-113">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c663e-113">Do one of the following:</span></span>
    
      - <span data-ttu-id="c663e-114">[**グローバル テスト デバイス**] をクリックした場合は、次の手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="c663e-114">If you clicked **Global test device**, skip to the next step.</span></span>
    
      - <span data-ttu-id="c663e-115">[**サイト テスト デバイス**] をクリックした場合は、使用可能なサイトの一覧からサイトを選択して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c663e-115">If you clicked **Site test device**, select a site from the list of available sites, and then click **OK**.</span></span>

5.  <span data-ttu-id="c663e-116">[**新しいテスト デバイス**] の [**デバイス名**] にデバイスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c663e-116">In **New Test Device**, type a name for the device in **Device name**.</span></span>

6.  <span data-ttu-id="c663e-117">[**識別子の種類**] で、[**MAC アドレス**] または [**シリアル番号**] のどちらかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c663e-117">Under **Identifier type**, click either **MAC address** or **Serial number**.</span></span>

7.  <span data-ttu-id="c663e-118">[**一意識別子**] ボックスに、デバイスの MAC アドレスかシリアル番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="c663e-118">In the **Unique identifier** box, type the MAC address or serial number of the device.</span></span>

8.  <span data-ttu-id="c663e-119">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c663e-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c663e-120">Windows PowerShell コマンドレットを使用してテストデバイスを作成する</span><span class="sxs-lookup"><span data-stu-id="c663e-120">Creating Test Devices by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c663e-121">テストデバイスは、Windows PowerShell と New-cstestdevice コマンドレットを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="c663e-121">Test devices can be created by using Windows PowerShell and the New-CsTestDevice cmdlet.</span></span> <span data-ttu-id="c663e-122">このコマンドレットは、Lync Server 2013 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="c663e-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c663e-123">リモート Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Microsoft Lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)を使用したリモート PowerShell の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c663e-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="c663e-124">このコマンドレットを使用してテスト デバイスを作成するには、以下の 2 つを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c663e-124">When creating test devices using this cmdlet, you must do two things:</span></span>

  - <span data-ttu-id="c663e-125">MACAddress または SerialNumber のいずれかを IdentifierType として指定します。</span><span class="sxs-lookup"><span data-stu-id="c663e-125">Specify either MACAddress or SerialNumber as the IdentifierType.</span></span>

  - <span data-ttu-id="c663e-p104">デバイス識別子を指定するときにスコープを含めます。グローバル スコープでデバイスを作成するには、次のような構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c663e-p104">Include the scope when specifying the device Identity. To create a new device at the global scope use syntax similar to this:</span></span>
    
        -Identity "global/WindowsPhone"
    
    <span data-ttu-id="c663e-128">サイト スコープでテスト デバイスを作成するには、次のような構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c663e-128">To create a test device at the site scope use syntax similar to this:</span></span>
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a><span data-ttu-id="c663e-129">MAC アドレスを使用してテストデバイスを作成するには</span><span class="sxs-lookup"><span data-stu-id="c663e-129">To create a test device by using the MAC address</span></span>

  - <span data-ttu-id="c663e-130">このコマンドはテスト デバイスを、グローバル スコープで、MAC アドレスを IdentifierType として使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="c663e-130">This command creates a test device at the global scope, and using the MAC address as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a><span data-ttu-id="c663e-131">シリアル番号を使用してテストデバイスを作成するには</span><span class="sxs-lookup"><span data-stu-id="c663e-131">To create a test device by using the serial number</span></span>

  - <span data-ttu-id="c663e-132">このコマンドは新しいテスト デバイスを、サイトスコープ (Redmond サイト) で、シリアル番号を IdentifierType として使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="c663e-132">This command creates a new test device at the site scope (for the Redmond site) and uses the serial number as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

<span data-ttu-id="c663e-133">詳細については、 [new-cstestdevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c663e-133">For more information, see the help topic for the [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

