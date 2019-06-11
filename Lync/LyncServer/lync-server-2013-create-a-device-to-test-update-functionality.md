---
title: 'Lync Server 2013: 更新機能をテストするためのデバイスを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad2fa5283561e1096cfe7e3053db59c3cd2e40e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a><span data-ttu-id="8714f-102">Lync Server 2013 で更新機能をテストするためのデバイスを作成する</span><span class="sxs-lookup"><span data-stu-id="8714f-102">Create a device to test update functionality in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8714f-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8714f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8714f-104">[**テスト デバイス**] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。</span><span class="sxs-lookup"><span data-stu-id="8714f-104">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="8714f-105">(Lync Server 環境全体で)、または1つのサイト内でグローバルにデバイスをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="8714f-105">You can test a device globally (throughout your entire Lync Server environment) or within a single site.</span></span> <span data-ttu-id="8714f-106">テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。</span><span class="sxs-lookup"><span data-stu-id="8714f-106">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="8714f-107">デバイスを追加すると、そのデバイスは Lync Server コントロールパネルの [**テストデバイス**] ページの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8714f-107">When you add a device, it appears in the list on the **Test Device** page of the Lync Server Control Panel.</span></span>

<div>

## <a name="to-add-a-test-device"></a><span data-ttu-id="8714f-108">テストデバイスを追加するには</span><span class="sxs-lookup"><span data-stu-id="8714f-108">To add a test device</span></span>

1.  <span data-ttu-id="8714f-109">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8714f-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8714f-110">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8714f-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="8714f-111">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイスのテスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8714f-111">In the left navigation bar, click **Clients**, and then click **Test Device**.</span></span>

3.  <span data-ttu-id="8714f-112">[**新規作成**] をクリックし、[**グローバルテストデバイス**] または [**サイトテストデバイス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8714f-112">Click **New**, and then click either **Global test device** or **Site test device**.</span></span>

4.  <span data-ttu-id="8714f-113">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8714f-113">Do one of the following:</span></span>
    
      - <span data-ttu-id="8714f-114">[**グローバルテストデバイス**] をクリックした場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="8714f-114">If you clicked **Global test device**, skip to the next step.</span></span>
    
      - <span data-ttu-id="8714f-115">[**サイトテストデバイス**] をクリックした場合は、利用可能なサイトの一覧からサイトを選んで、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8714f-115">If you clicked **Site test device**, select a site from the list of available sites, and then click **OK**.</span></span>

5.  <span data-ttu-id="8714f-116">[**新しいテストデバイス**] で、デバイスの名前を [**デバイス名**] に入力します。</span><span class="sxs-lookup"><span data-stu-id="8714f-116">In **New Test Device**, type a name for the device in **Device name**.</span></span>

6.  <span data-ttu-id="8714f-117">[**識別子の種類**] で、[ **MAC アドレス**] または [**シリアル番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8714f-117">Under **Identifier type**, click either **MAC address** or **Serial number**.</span></span>

7.  <span data-ttu-id="8714f-118">[**一意の識別子**] ボックスに、デバイスの MAC アドレスまたはシリアル番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="8714f-118">In the **Unique identifier** box, type the MAC address or serial number of the device.</span></span>

8.  <span data-ttu-id="8714f-119">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8714f-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8714f-120">Windows PowerShell コマンドレットを使用したテストデバイスの作成</span><span class="sxs-lookup"><span data-stu-id="8714f-120">Creating Test Devices by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8714f-121">テストデバイスは、Windows PowerShell と CsTestDevice コマンドレットを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="8714f-121">Test devices can be created by using Windows PowerShell and the New-CsTestDevice cmdlet.</span></span> <span data-ttu-id="8714f-122">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="8714f-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8714f-123">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8714f-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="8714f-124">このコマンドレットを使用してテストデバイスを作成する場合は、次の2つの操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8714f-124">When creating test devices using this cmdlet, you must do two things:</span></span>

  - <span data-ttu-id="8714f-125">IdentifierType として MACAddress またはシリアルを指定します。</span><span class="sxs-lookup"><span data-stu-id="8714f-125">Specify either MACAddress or SerialNumber as the IdentifierType.</span></span>

  - <span data-ttu-id="8714f-126">デバイス Id を指定するときにスコープを含めます。</span><span class="sxs-lookup"><span data-stu-id="8714f-126">Include the scope when specifying the device Identity.</span></span> <span data-ttu-id="8714f-127">グローバルスコープで新しいデバイスを作成するには、次のような構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="8714f-127">To create a new device at the global scope use syntax similar to this:</span></span>
    
        -Identity "global/WindowsPhone"
    
    <span data-ttu-id="8714f-128">サイトスコープでテストデバイスを作成するには、次のような構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="8714f-128">To create a test device at the site scope use syntax similar to this:</span></span>
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a><span data-ttu-id="8714f-129">MAC アドレスを使ってテストデバイスを作成するには</span><span class="sxs-lookup"><span data-stu-id="8714f-129">To create a test device by using the MAC address</span></span>

  - <span data-ttu-id="8714f-130">このコマンドは、グローバルスコープでテストデバイスを作成し、MAC アドレスを IdentifierType として使用します。</span><span class="sxs-lookup"><span data-stu-id="8714f-130">This command creates a test device at the global scope, and using the MAC address as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a><span data-ttu-id="8714f-131">シリアル番号を使用してテストデバイスを作成するには</span><span class="sxs-lookup"><span data-stu-id="8714f-131">To create a test device by using the serial number</span></span>

  - <span data-ttu-id="8714f-132">このコマンドは、新しいテストデバイスを (Redmond サイトの) サイトのスコープで作成し、シリアル番号を IdentifierType として使用します。</span><span class="sxs-lookup"><span data-stu-id="8714f-132">This command creates a new test device at the site scope (for the Redmond site) and uses the serial number as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

<span data-ttu-id="8714f-133">詳細については、 [CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8714f-133">For more information, see the help topic for the [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

