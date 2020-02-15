---
title: 'Lync Server 2013: Lync Server 2013 管理パックのインポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adaf9fe1c6d5d4cc0769810aece05bcb46681e79
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a><span data-ttu-id="75372-102">Lync Server 2013 管理パックのインポート</span><span class="sxs-lookup"><span data-stu-id="75372-102">Importing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75372-103">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="75372-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="75372-104">System Center Operations Manager の機能を拡張するには、System Center Operations Manager が監視できるアイテム、およびそれらのアイテムを監視する方法と、アラートをトリガーする方法を決定するソフトウェアをインストールします。返さ.</span><span class="sxs-lookup"><span data-stu-id="75372-104">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, and how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="75372-105">Lync Server 2013 には、次の機能を提供する2つの System Center Operations Manager 管理パックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="75372-105">Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="75372-106">コンポーネントおよびユーザー管理パック (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) は、イベントログに記録された Lync Server の問題を追跡し、パフォーマンスカウンターで登録するか、または通話詳細記録 (CDR) または QoE (Quality of Experience) に記録します。databases.</span><span class="sxs-lookup"><span data-stu-id="75372-106">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="75372-107">重大な問題については、System Center Operations Manager を構成して、電子メール、インスタントメッセージ、またはショートメッセージサービス (SMS) のメッセージングを介して管理者に即座に通知できます。</span><span class="sxs-lookup"><span data-stu-id="75372-107">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="75372-108">SMS は、モバイル デバイス間でテキスト メッセージを送信するために使用されるテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="75372-108">SMS is the technology used to send text messages from one mobile device to another.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75372-109">Operations Manager 通知の構成の詳細については、TechNet ライブラリの「構成<A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>の通知」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75372-109">For details about configuring Operations Manager notification, see the Configuring Notification in the TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="75372-110">アクティブな監視管理パック (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) は、システムへのサインイン、インスタントメッセージの交換、パブリックスイッチに配置された電話機への通話の作成などの主要な Lync Server コンポーネントを事前にテストします。電話網 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="75372-110">The Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="75372-111">これらのテストは、Lync Server 代理トランザクションコマンドレットを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="75372-111">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="75372-112">たとえば、**Test-CsIM** コマンドレットを使用すると、テスト ユーザーのペア間のインスタント メッセージング (IM) の会話をシミュレーションできます。</span><span class="sxs-lookup"><span data-stu-id="75372-112">For example, you can use the **Test-CsIM** cmdlet to simulate an instant messaging (IM) conversation between a pair of test users.</span></span> <span data-ttu-id="75372-113">このシミュレーションされたメッセージの会話が失敗すると、通知が生成されます。</span><span class="sxs-lookup"><span data-stu-id="75372-113">If this simulated messaging conversation fails an alert is generated.</span></span>

<span data-ttu-id="75372-114">管理パックをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="75372-114">You need to import the management packs.</span></span> <span data-ttu-id="75372-115">管理パックをインポートしない場合、Operations Manager を使用して Lync Server イベントを監視したり、Lync Server 代理トランザクションを実行したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="75372-115">If you do not import the management packs, you cannot use Operations Manager to monitor Lync Server events or run Lync Server synthetic transactions.</span></span>

<span data-ttu-id="75372-116">コンポーネントおよびユーザー管理パックは、Lync Server 2013 の監視にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="75372-116">The Component and User Management Pack is only used to monitor Lync Server 2013.</span></span> <span data-ttu-id="75372-117">Lync Server 2013 と Lync Server 2010 の両方がインストールされている共存シナリオでは、lync server 2010 コンピューターで Lync Server 2010 管理パックを引き続き使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75372-117">If you are in a coexistence scenario, where you have both Lync Server 2013 and Lync Server 2010 installed, you should continue to use the Lync Server 2010 management packs for your Lync Server 2010 computers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75372-118">Lync server 2010 の管理パックには、Lync Server 2010 の監視管理パックと Lync Server の2010グループチャット監視管理パックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="75372-118">Management packs for Lync Server 2010 include the Lync Server 2010 Monitoring Management Pack and the Lync Server 2010 Group Chat Monitoring Management Pack.</span></span>



</div>

<span data-ttu-id="75372-119">次のいずれかのツールを使用して、管理パックをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="75372-119">You can use one of the following tools to import management packs:</span></span>

  - <span data-ttu-id="75372-120">**System Center Operations manager**   この方法では、Operations manager を使用して Lync Server の監視を追加します。</span><span class="sxs-lookup"><span data-stu-id="75372-120">**System Center Operations Manager**   With this method, you use the Operations Manager to add monitoring for Lync Server.</span></span>

  - <span data-ttu-id="75372-121">**Operations manager シェル**   operations manager シェルを使用して、System Center Operations manager コンソールを使用して、管理パックのインポート時に発生した問題のトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="75372-121">**Operations Manager Shell**   You can use the Operations Manager Shell to import directly or to troubleshoot any issues you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="75372-122">System Center Operations Manager を使用した管理パックのインポート</span><span class="sxs-lookup"><span data-stu-id="75372-122">Importing the Management Packs by Using System Center Operations Manager</span></span>

1.  <span data-ttu-id="75372-123">ファイル Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp と Microsoft.LS.2013.Monitoring.ComponentAndUser.mp をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="75372-123">Download the files Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span></span>

2.  <span data-ttu-id="75372-124">System Center Operations Manager で、[**管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75372-124">In System Center Operations Manager, click **Administration**.</span></span>

3.  <span data-ttu-id="75372-125">[**管理**] ウィンドウで、[**管理パック**] を右クリックして [**管理パックのインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75372-125">In the **Administration** pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4.  <span data-ttu-id="75372-126">[**管理パックの選択**] ダイアログ ボックスで、[**追加**] をクリックし、[**ディスクから追加する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75372-126">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5.  <span data-ttu-id="75372-127">[**オンラインカタログ接続**] ダイアログボックスで、[**キャンセル**] をクリックして、Lync Server 管理パックの依存関係が存在するかどうかを、Operations Manager がオンラインにならないようにします。</span><span class="sxs-lookup"><span data-stu-id="75372-127">In the **Online Catalog Connection** dialog box, click **Cancel** to prevent Operations Manager from going online to see if any dependencies exist for the Lync Server management packs.</span></span> <span data-ttu-id="75372-128">System Center Operations Manager 2012 を使用している場合は、[**いいえ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75372-128">If you are using System Center Operations Manager 2012, click **No**.</span></span>

6.  <span data-ttu-id="75372-p107">[**インポートする管理パックの選択**] ダイアログ ボックスで、ファイル **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** と **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** を探して選択し、[**開く**] をクリックします。ダイアログ ボックスで複数のファイルを選択するには、最初のファイルをクリックした後、Ctrl キーを押しながら 2 番目のファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="75372-p107">In the **Select Management Packs to import** dialog box, locate and select the files **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** and **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** and then click **Open**. To select multiple files in the dialog box, click the first file, hold down the Ctrl key and then click the second file.</span></span>

7.  <span data-ttu-id="75372-p108">[**管理パックの選択**] ダイアログ ボックスで、[**インストール**] をクリックします。エラー メッセージが表示されてインストールが失敗する場合は、通常、管理パックのファイルが Windows ユーザー アカウント制御によって保護されているフォルダー内にあることを意味します。その場合は、ファイルを別のフォルダーにコピーした後、インポートとインストールの処理を再度開始します。</span><span class="sxs-lookup"><span data-stu-id="75372-p108">In the **Select Management Packs** dialog box, click **Install**. If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control. If this occurs, copy the files to a different folder and then restart the import and installation process.</span></span>

8.  <span data-ttu-id="75372-p109">[**管理パックの選択**] ダイアログ ボックスで、[**閉じる**] をクリックします。インポートとインストールの処理には数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="75372-p109">In the **Select Management Packs** dialog box, click **Close**. Note that the import and installation process might require several minutes to complete.</span></span>

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="75372-136">Operations Manager シェルを使用した管理パックのインポート</span><span class="sxs-lookup"><span data-stu-id="75372-136">Importing Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="75372-137">通常は、Operations Manager を使用して、管理パックをインポートする方が簡単です。ただし、エラーが発生してインポートが失敗した場合、コンソールは、適切なエラーレポートを常に提供するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="75372-137">In general it is easier to import the management packs by using the Operations Manager.However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="75372-138">これに対して、Operations Manager シェルは詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="75372-138">By comparison, the Operations Manager Shell, provides detailed information.</span></span> <span data-ttu-id="75372-139">Operations Manager を使用していて、管理パックのインポートで問題が発生した場合は、Operations Manager シェルを使用してパックをインポートします。</span><span class="sxs-lookup"><span data-stu-id="75372-139">If you are using Operations Manager and you run into problems importing a management pack, import the pack by using the Operations Manager Shell .</span></span> <span data-ttu-id="75372-140">Operations Manager シェルには、インポートが失敗した理由を判断するのに役立つ情報が詳細に記載されています。</span><span class="sxs-lookup"><span data-stu-id="75372-140">The Operations Manager Shell provides more information that might help you determine why the import failed.</span></span>

<span data-ttu-id="75372-141">System Center Operations Manager 2007 R2 を使用している場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="75372-141">If you are using System Center Operations Manager 2007 R2, complete the following procedure:</span></span>

1.  <span data-ttu-id="75372-142">[**スタート**]、[**すべてのプログラム**]、[ **System Center Operations manager 2007 R2**]、[ **operations manager Shell**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="75372-142">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007 R2**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="75372-143">Operations Manager シェルで、Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp ファイルのコピーへの実際のパスを使用して、コマンドプロンプトで次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="75372-143">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  <span data-ttu-id="75372-144">最初の管理パックをインポートした後、Microsoft.LS.2013.Monitoring.ComponentAndUser.mp ファイルのコピーのパスを使用して処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="75372-144">After you import the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  <span data-ttu-id="75372-145">Operations Manager シェルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="75372-145">Close the Operations Manager Shell.</span></span>

<span data-ttu-id="75372-146">System Center Operations Manager 2012 を使用している場合は、代わりに次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="75372-146">If you are using System Center Operations Manager 2012, complete this procedure instead:</span></span>

1.  <span data-ttu-id="75372-147">[**スタート**]、[**すべてのプログラム**]、[ **Microsoft System Center 2012**]、[ **Operations manager**]、[ **operations manager Shell**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="75372-147">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="75372-148">Operations Manager シェルで、Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp ファイルのコピーへの実際のパスを使用して、コマンドプロンプトで次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="75372-148">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  <span data-ttu-id="75372-149">最初の管理パックをインポートした後、Microsoft.LS.2013.Monitoring.ComponentAndUser.mp ファイルのコピーのパスを使用して処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="75372-149">After you have imported the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

