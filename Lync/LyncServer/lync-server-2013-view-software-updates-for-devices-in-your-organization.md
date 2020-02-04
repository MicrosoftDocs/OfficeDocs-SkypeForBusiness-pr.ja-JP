---
title: 'Lync Server 2013: 組織内のデバイスのソフトウェア更新プログラムを表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9a969aac4559f02ee7d05f36bece84e40f65aca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a><span data-ttu-id="57e61-102">Lync Server 2013 でのデバイスのソフトウェア更新プログラムの表示</span><span class="sxs-lookup"><span data-stu-id="57e61-102">View software updates for devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57e61-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="57e61-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="57e61-104">Lync Server 2013 では、デバイス更新 Web サービスを使って、組織のデバイスのソフトウェア更新プログラムを表示して管理します。</span><span class="sxs-lookup"><span data-stu-id="57e61-104">With Lync Server 2013, you use Device Update Web service to view and manage software updates for your organization’s devices.</span></span> <span data-ttu-id="57e61-105">これらの更新プログラムは、の Microsoft サポート web サイトから .cab (キャビネット) ファイル[http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)で入手できます。</span><span class="sxs-lookup"><span data-stu-id="57e61-105">These updates are available in .cab (cabinet) files from the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091).</span></span> <span data-ttu-id="57e61-106">.Cab ファイルをダウンロードした後、**インポート-CSDeviceUpdate**コマンドレットを実行して、.cab ファイルからデバイス更新ルールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="57e61-106">After you download the .cab file, run the **Import-CSDeviceUpdate** cmdlet to import the device update rules from the .cab file.</span></span> <span data-ttu-id="57e61-107">**Csdeviceupdate**コマンドレットの詳細については、「Lync Server 管理シェルドキュメントの[インポート-csdeviceupdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57e61-107">For details about the **Import-CSDeviceUpdate** cmdlet, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="57e61-108">新しい更新プログラムを組織に展開する前に、テストデバイスで正しく機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="57e61-108">Before deploying a new update to your organization, verify that it functions correctly on a test device.</span></span>



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a><span data-ttu-id="57e61-109">UC デバイスのソフトウェア更新プログラムを表示するには</span><span class="sxs-lookup"><span data-stu-id="57e61-109">To view software updates for UC devices</span></span>

1.  <span data-ttu-id="57e61-110">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="57e61-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="57e61-111">Microsoft サポート web サイトで[http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)、.cab ファイルを Lync Server 2013 コンピューター上の場所にダウンロードします (たとえば、C:\\updates\\ucupdates)。</span><span class="sxs-lookup"><span data-stu-id="57e61-111">From the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091), download the .cab file to a location on a Lync Server 2013 computer (for example, C:\\Updates\\UCUpdates.cab).</span></span>

3.  <span data-ttu-id="57e61-112">次のコマンドレットのいずれかを実行\\し\\て、C: update ucupdates ファイルからデバイス更新ルールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="57e61-112">Import the device update rules from the C:\\Updates\\UCUpdates.cab file by running one of the following cmdlets:</span></span>
    
      - <span data-ttu-id="57e61-113">.Cab ファイルが、更新されるサービスを実行しているコンピューターと同じコンピューター上にある場合 (サービス: レドモンド-websvc-2)、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="57e61-113">If the .cab file is located on the same computer as the one running the service to be updated (service:Redmond-websvc-2), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - <span data-ttu-id="57e61-114">.Cab ファイルが、更新されるサービスを実行しているコンピューターとは異なるコンピューター上にある場合 (サービス: Redmond-websvc-3)、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="57e61-114">If the .cab file is located on a different computer than the one running the service to be updated (service:Redmond-websvc-3), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  <span data-ttu-id="57e61-115">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="57e61-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="57e61-116">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="57e61-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

5.  <span data-ttu-id="57e61-117">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイスの更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57e61-117">In the left navigation bar, click **Clients**, and then click **Device Update**.</span></span>

6.  <span data-ttu-id="57e61-118">[**デバイス更新**] ページで、一覧から更新プログラムをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="57e61-118">On the **Device Update** page, click an update in the list, and then do one of the following:</span></span>
    
      - <span data-ttu-id="57e61-119">**保留中の更新をキャンセルします。**</span><span class="sxs-lookup"><span data-stu-id="57e61-119">**Cancel a pending update.**</span></span> <span data-ttu-id="57e61-120">選択した更新プログラムが組織のデバイスに展開されないようにするには、[**操作**] メニューをクリックし、[**保留中の更新をキャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57e61-120">To prevent the selected update from being deployed to your organization’s devices, click the **Action** menu, and then click **Cancel pending updates**.</span></span>
    
      - <span data-ttu-id="57e61-121">**更新を承認します。**</span><span class="sxs-lookup"><span data-stu-id="57e61-121">**Approve an update.**</span></span> <span data-ttu-id="57e61-122">選択した更新を組織のデバイスに展開できるようにするには、[**操作**] メニューをクリックし、[**承認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57e61-122">To allow the selected update to be deployed to your organization’s devices, click the **Action** menu, and then click **Approve**.</span></span>
    
      - <span data-ttu-id="57e61-123">**更新プログラムを復元します。**</span><span class="sxs-lookup"><span data-stu-id="57e61-123">**Restore an update.**</span></span> <span data-ttu-id="57e61-124">以前に承認された更新を組織のデバイスに展開できるようにするには、[**操作**] メニューをクリックし、[**復元**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57e61-124">To allow a previously approved update to be deployed to your organization’s devices, click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="57e61-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="57e61-125">See Also</span></span>


[<span data-ttu-id="57e61-126">Lync Server 2013 でのデバイス、電話、クライアント アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="57e61-126">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

