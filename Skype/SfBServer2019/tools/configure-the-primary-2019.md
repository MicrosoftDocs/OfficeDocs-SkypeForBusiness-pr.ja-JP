---
title: プライマリ管理サーバーの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: プライマリ管理サーバーを構成し、System Center Operations Manager をインストールし、Skype for Business Server 2019 の管理パックをインポートします。'
ms.openlocfilehash: 02a174fb5c5fd6f06188553d8b2647c7162966e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120468"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="25404-103">プライマリ管理サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="25404-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="25404-104">**概要:** プライマリ管理サーバーを構成し、System Center Operations Manager をインストールし、Skype for Business Server 2019 の管理パックをインポートします。</span><span class="sxs-lookup"><span data-stu-id="25404-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2019.</span></span>

<span data-ttu-id="25404-105">Skype for Business Server 2019 に含まれる新しい正常性監視機能を活用するには、最初にプライマリ管理サーバーとして機能するコンピューターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25404-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2019, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="25404-106">その後、そのコンピューターに System Center Operations Manager 2012 SP1 または R2 または System Center Operations Manager 2007 R2 をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="25404-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="25404-107">さらに、Operations Manager のバック エンド データベースとして機能するには、SQL Serverバージョンのサポートされているデータベースを最初にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="25404-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="25404-108">System Center Operations Manager をインストールする場合は、以下を含む、その製品のすべてのコンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="25404-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="25404-109">オペレーション データベース</span><span class="sxs-lookup"><span data-stu-id="25404-109">Operational database</span></span>

- <span data-ttu-id="25404-110">Server</span><span class="sxs-lookup"><span data-stu-id="25404-110">Server</span></span>

- <span data-ttu-id="25404-111">コンソール</span><span class="sxs-lookup"><span data-stu-id="25404-111">Console</span></span>

- <span data-ttu-id="25404-112">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="25404-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="25404-113">Web コンソール</span><span class="sxs-lookup"><span data-stu-id="25404-113">Web console</span></span>

- <span data-ttu-id="25404-114">Reporting</span><span class="sxs-lookup"><span data-stu-id="25404-114">Reporting</span></span>

- <span data-ttu-id="25404-115">データ ウェアハウス</span><span class="sxs-lookup"><span data-stu-id="25404-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25404-116">System Center Operations Manager 2012 をインストールする前に、「Microsoft Report[Viewer 2010 再](https://www.microsoft.com/download/details.aspx?id=6442)頒布可能パッケージ」をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="25404-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="25404-117">これらの製品とそのインストールの詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="25404-117">For details about these products and their installation, see the following links:</span></span>

- <span data-ttu-id="25404-118">[System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))</span><span class="sxs-lookup"><span data-stu-id="25404-118">[System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))</span></span>

- [<span data-ttu-id="25404-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="25404-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/library/bb735860.aspx)

<span data-ttu-id="25404-120">Skype for Business Server 展開ごとに使用できるルート管理サーバーは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="25404-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a><span data-ttu-id="25404-121">Skype for Business Server 2019 管理パックのインポート</span><span class="sxs-lookup"><span data-stu-id="25404-121">Importing the Skype for Business Server 2019 Management Packs</span></span>

<span data-ttu-id="25404-122">System Center Operations Manager の機能を拡張するには、管理パック (System Center Operations Manager で監視できるアイテム、それらのアイテムの監視方法、アラートのトリガーと報告方法を指示するソフトウェア) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="25404-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="25404-123">Skype for Business Server 2019 には、次の機能を提供する 2 つの System Center Operations Manager 管理パックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="25404-123">Skype for Business Server 2019 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="25404-124">コンポーネントおよび **ユーザー** 管理パック (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) は、イベント ログに記録された Skype for Business Server の問題、パフォーマンス カウンターによって登録された、または通話詳細レコード (CDRs) または QoE (Quality of Experience) データベースに記録された Skype を追跡します。</span><span class="sxs-lookup"><span data-stu-id="25404-124">**The Component and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="25404-125">重大な問題については、System Center Operations Manager を構成して、電子メール、インスタント メッセージ、または SMS メッセージングを通じて管理者に直ちに通知できます。</span><span class="sxs-lookup"><span data-stu-id="25404-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="25404-126">(SMS、またはショート メッセージ サービスは、あるモバイル デバイスから別のモバイル デバイスにテキスト メッセージを送信するために使用されるテクノロジです)。</span><span class="sxs-lookup"><span data-stu-id="25404-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="25404-127">Operations Manager 通知の構成の詳細については、「通知の [構成」を参照してください](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10))。</span><span class="sxs-lookup"><span data-stu-id="25404-127">For details about configuring Operations Manager notification, see [Configuring Notification](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10)).</span></span>

- <span data-ttu-id="25404-128">Active **Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) は、システムへのサインイン、インスタント メッセージの交換、公衆交換電話網 (PSTN) にある電話への通話など、Skype for Business Server の主要なコンポーネントを積極的にテストします。</span><span class="sxs-lookup"><span data-stu-id="25404-128">**The Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="25404-129">これらのテストは、Skype for Business Server 代理トランザクション コマンドレットを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="25404-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="25404-130">たとえば、**Test-CsIM** コマンドレットは、1 組のテスト ユーザー間でインスタント メッセージングの会話をシミュレートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="25404-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="25404-131">このシミュレートされた会話が失敗すると、アラートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="25404-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="25404-132">管理パックのインポートは重要な手順です。</span><span class="sxs-lookup"><span data-stu-id="25404-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="25404-133">管理パックがインポートされていない場合、Operations Manager を使用して Skype for Business Server イベントを監視したり、Skype for Business Server 代理トランザクションを実行したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="25404-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="25404-134">コンポーネントとユーザー管理パックは、Skype for Business Server 2019 のみを監視するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="25404-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2019.</span></span> <span data-ttu-id="25404-135">Skype for Business Server 2019 と Skype for Business Server 2015 の両方がインストールされている共存シナリオの場合は、引き続き Skype for Business Server 2015 コンピューター用の Skype for Business Server 2015 管理パックを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25404-135">If you are in a coexistence scenario where both Skype for Business Server 2019 and Skype for Business Server 2015 are installed, you should continue to use the Skype for Business Server 2015 management packs for your Skype for Business Server 2015 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="25404-136">Skype for Business Server 2019 の管理パックには、Skype for Business Server 2019 コンポーネントとユーザー管理パック、Skype for Business Server 2019 Active Monitoring Management Pack が含まれます。</span><span class="sxs-lookup"><span data-stu-id="25404-136">Management packs for Skype for Business Server 2019 include the Skype for Business Server 2019 Component and User Management Pack and the Skype for Business Server 2019 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="25404-137">次のいずれかのツールを使用して、管理パックをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="25404-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="25404-138">**System Center Operations Manager** このメソッドでは、Operations Manager を使用して Skype for Business Server の監視を追加します。</span><span class="sxs-lookup"><span data-stu-id="25404-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="25404-139">**Operations Manager シェル** Operations Manager シェルを使用して直接インポートしたり、System Center Operations Manager コンソールを使用して管理パックをインポートするときに発生する問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="25404-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="25404-140">System Center Operations Manager を使用した管理パックのインポート</span><span class="sxs-lookup"><span data-stu-id="25404-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="25404-141">Microsoft Web ダウンロードSkypeForBusiness2019ManagementPacks.msiをダウンロードし、msi をインストールします。</span><span class="sxs-lookup"><span data-stu-id="25404-141">Download the SkypeForBusiness2019ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="25404-142">System Center Operations Manager で、[管理] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="25404-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="25404-143">[管理] ウィンドウで、[**管理パック**] を右クリックして [**管理パックのインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25404-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="25404-144">[**管理パックの選択**] ダイアログ ボックスで、[**追加**] をクリックし、[**ディスクから追加する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25404-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="25404-145">[オンライン カタログ **接続] ダイアログ ボックスで** 、[いいえ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="25404-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="25404-146">[インポートする **管理パック** の選択] ダイアログ ボックスで、ファイルを検索して選択し、[開 Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp Microsoft.LS.2019.Monitoring.ComponentAndUser.mp をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="25404-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2019.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="25404-147">ダイアログ ボックスで複数のファイルを選択するには、最初のファイルをクリックし、Ctrl キーを押しながら後続のファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="25404-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="25404-148">[**管理パックの選択**] ダイアログ ボックスで、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25404-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="25404-149">エラー メッセージが表示されてインストールが失敗する場合は、通常、管理パックのファイルが Windows ユーザー アカウント制御によって保護されているフォルダー内にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="25404-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="25404-150">この場合は、ファイルを別のフォルダーにコピーし、インポートおよびインストール プロセスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="25404-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="25404-151">[**管理パックの選択**] ダイアログ ボックスで、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25404-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="25404-152">インポートおよびインストール プロセスの完了に数分が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="25404-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="25404-153">Operations Manager シェルを使用した管理パックのインポート</span><span class="sxs-lookup"><span data-stu-id="25404-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="25404-154">一般に、Operations Manager コンソールを使用して管理パックをインポートする方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="25404-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="25404-155">ただし、エラーが発生してインポートが失敗した場合、コンソールは必ずしも適切なエラー レポートを提供するとは限らない。</span><span class="sxs-lookup"><span data-stu-id="25404-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="25404-156">一方、Operations Manager シェルは詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="25404-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="25404-157">Operations Manager を使用している場合に、管理パックをインポートするときに問題が発生した場合は、Operations Manager シェルを使用してパックをインポートします。</span><span class="sxs-lookup"><span data-stu-id="25404-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="25404-158">Operations Manager シェルによって提供される情報は、インポートが失敗した理由を判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="25404-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="25404-159">[ **スタート] ボタン**、[ **すべてのプログラム] の** 順にクリックし **、[Microsoft System Center 2012]** をクリックし **、[Operations Manager]** をクリックし **、[Operations Manager シェル] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="25404-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="25404-160">[Operations Manager Shell] で、コマンド プロンプトで、ファイル のコピーへの実際のパスを使用して次のコマンド Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp 入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="25404-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="25404-161">最初の管理パックをインポートした後、次の手順に示すファイルのコピーへのパスを使用して、プロセスを繰り Microsoft.LS.2019.Monitoring.ComponentAndUser.mp。</span><span class="sxs-lookup"><span data-stu-id="25404-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```