---
title: プライマリ管理サーバーを構成する
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: プライマリ管理サーバーを構成し、System Center Operations Manager をインストールして、Skype for Business Server 2019 用の管理パックをインポートします。'
ms.openlocfilehash: 2ad04419ec60e7c752d22c4cdc5c4e82fdb853f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150554"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="3bf23-103">プライマリ管理サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="3bf23-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="3bf23-104">**概要:** プライマリ管理サーバーを構成し、System Center Operations Manager をインストールして、Skype for Business Server 2019 用の管理パックをインポートします。</span><span class="sxs-lookup"><span data-stu-id="3bf23-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2019.</span></span>

<span data-ttu-id="3bf23-105">Skype for Business Server 2019 に含まれている新しい正常性監視機能を十分に活用するには、まず、プライマリ管理サーバーとして動作するコンピューターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bf23-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2019, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="3bf23-106">その後、そのコンピューターに System Center Operations Manager 2012 SP1 または R2 または System Center Operations Manager 2007 R2 をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bf23-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="3bf23-107">また、Operations Manager のバックエンドデータベースとして機能するために、サポートされているバージョンの SQL Server をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bf23-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="3bf23-108">System Center Operations Manager をインストールするときには、次のような製品のすべてのコンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bf23-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="3bf23-109">オペレーション データベース</span><span class="sxs-lookup"><span data-stu-id="3bf23-109">Operational database</span></span>

- <span data-ttu-id="3bf23-110">サーバー</span><span class="sxs-lookup"><span data-stu-id="3bf23-110">Server</span></span>

- <span data-ttu-id="3bf23-111">コンソール</span><span class="sxs-lookup"><span data-stu-id="3bf23-111">Console</span></span>

- <span data-ttu-id="3bf23-112">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="3bf23-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="3bf23-113">Web コンソール</span><span class="sxs-lookup"><span data-stu-id="3bf23-113">Web console</span></span>

- <span data-ttu-id="3bf23-114">Reporting</span><span class="sxs-lookup"><span data-stu-id="3bf23-114">Reporting</span></span>

- <span data-ttu-id="3bf23-115">データ ウェアハウス</span><span class="sxs-lookup"><span data-stu-id="3bf23-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bf23-116">System Center Operations Manager 2012 をインストールする前に、「[Microsoft Report Viewer 2010 再頒布可能パッケージ](https://www.microsoft.com/download/details.aspx?id=6442)」をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bf23-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="3bf23-117">これらの製品とそのインストールの詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bf23-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="3bf23-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="3bf23-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="3bf23-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="3bf23-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/library/bb735860.aspx)

<span data-ttu-id="3bf23-120">Skype for Business Server 展開ごとに1つのルート管理サーバーしか使用できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3bf23-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a><span data-ttu-id="3bf23-121">Skype for Business Server 2019 管理パックのインポート</span><span class="sxs-lookup"><span data-stu-id="3bf23-121">Importing the Skype for Business Server 2019 Management Packs</span></span>

<span data-ttu-id="3bf23-122">System Center Operations Manager の機能を拡張するには、System Center Operations Manager が監視できるアイテム、それらのアイテムを監視する方法、およびアラートをトリガーする方法を決定するソフトウェアをインストールします。返さ.</span><span class="sxs-lookup"><span data-stu-id="3bf23-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="3bf23-123">Skype for Business Server 2019 には、次の機能を提供する2つの System Center Operations Manager 管理パックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3bf23-123">Skype for Business Server 2019 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="3bf23-124">**コンポーネントおよびユーザー管理パック**(Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) は、イベントログに記録された Skype For business Server の問題、パフォーマンスカウンターでの登録、または通話詳細レコード (cdr) または Qoe (Quality of Experience) データベースに記録された問題を追跡します。</span><span class="sxs-lookup"><span data-stu-id="3bf23-124">**The Component and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="3bf23-125">重大な問題については、System Center Operations Manager を構成して、管理者に電子メール、インスタントメッセージ、または SMS メッセージングをすぐに通知できます。</span><span class="sxs-lookup"><span data-stu-id="3bf23-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="3bf23-126">(SMS または Short Message Service) は、あるモバイルデバイスから別のモバイルデバイスにテキストメッセージを送信するために使用されるテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="3bf23-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="3bf23-127">Operations Manager 通知の構成の詳細については、「[通知の構成](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bf23-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="3bf23-128">**Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) は、システムへのサインイン、インスタントメッセージの交換、または公衆交換電話網 (PSTN) に配置された電話機への通話の作成など、主要な Skype For business Server コンポーネントを事前にテストします。</span><span class="sxs-lookup"><span data-stu-id="3bf23-128">**The Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="3bf23-129">これらのテストは、Skype for Business Server 代理トランザクションコマンドレットを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="3bf23-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="3bf23-130">たとえば、**Test-CsIM** コマンドレットは、1 組のテスト ユーザー間でインスタント メッセージングの会話をシミュレートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3bf23-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="3bf23-131">このシミュレートされた会話が失敗すると、アラートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3bf23-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="3bf23-132">管理パックのインポートは、重要な手順です。</span><span class="sxs-lookup"><span data-stu-id="3bf23-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="3bf23-133">管理パックがインポートされていない場合、Operations Manager を使用して Skype for business Server イベントを監視したり、Skype for Business Server 代理トランザクションを実行したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3bf23-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="3bf23-134">コンポーネントおよびユーザー管理パックは、Skype for Business Server 2019 のみを監視するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3bf23-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2019.</span></span> <span data-ttu-id="3bf23-135">Skype for business server 2019 と Skype for Business Server 2015 の両方がインストールされている共存シナリオでは、skype for business server の2015コンピューターで Skype for Business Server の2015管理パックを引き続き使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bf23-135">If you are in a coexistence scenario where both Skype for Business Server 2019 and Skype for Business Server 2015 are installed, you should continue to use the Skype for Business Server 2015 management packs for your Skype for Business Server 2015 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="3bf23-136">Skype for business Server 2019 用の管理パックには、Skype for Business Server 2019 コンポーネントおよびユーザー管理パックと、Skype for Business Server 2019 アクティブ監視管理パックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3bf23-136">Management packs for Skype for Business Server 2019 include the Skype for Business Server 2019 Component and User Management Pack and the Skype for Business Server 2019 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="3bf23-137">次のいずれかのツールを使用して、管理パックをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="3bf23-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="3bf23-138">**System Center Operations Manager**この方法では、Operations Manager を使用して Skype for Business Server の監視を追加します。</span><span class="sxs-lookup"><span data-stu-id="3bf23-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="3bf23-139">**Operations Manager シェル**Operations Manager シェルを使用して、System Center Operations Manager コンソールを使用して、管理パックのインポート時に発生した問題のトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3bf23-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="3bf23-140">System Center Operations Manager を使用した管理パックのインポート</span><span class="sxs-lookup"><span data-stu-id="3bf23-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="3bf23-141">Microsoft Web ダウンロードから SkypeForBusiness2019ManagementPacks をダウンロードし、msi をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3bf23-141">Download the SkypeForBusiness2019ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="3bf23-142">System Center Operations Manager で、[**管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bf23-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="3bf23-143">[管理] ウィンドウで、[**管理パック**] を右クリックして [**管理パックのインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bf23-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="3bf23-144">[**管理パックの選択**] ダイアログ ボックスで、[**追加**] をクリックし、[**ディスクから追加する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bf23-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="3bf23-145">[**オンラインカタログ接続**] ダイアログボックスで、[**いいえ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bf23-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="3bf23-146">[**インポートする管理パックの選択**] ダイアログボックスで、Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp および Microsoft.LS.2019.Monitoring.ComponentAndUser.mp ファイルを見つけて選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bf23-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2019.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="3bf23-147">ダイアログボックスで複数のファイルを選択するには、最初のファイルをクリックし、Ctrl キーを押しながら、次のファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bf23-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="3bf23-148">[**管理パックの選択**] ダイアログ ボックスで、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bf23-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="3bf23-149">エラー メッセージが表示されてインストールが失敗する場合は、通常、管理パックのファイルが Windows ユーザー アカウント制御によって保護されているフォルダー内にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3bf23-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="3bf23-150">その場合は、ファイルを別のフォルダーにコピーしてから、インポートとインストールのプロセスを再実行してください。</span><span class="sxs-lookup"><span data-stu-id="3bf23-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="3bf23-151">[**管理パックの選択**] ダイアログ ボックスで、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bf23-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="3bf23-152">インポートとインストールのプロセスが完了するまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="3bf23-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="3bf23-153">Operations Manager シェルを使用した管理パックのインポート</span><span class="sxs-lookup"><span data-stu-id="3bf23-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="3bf23-154">通常、Operations Manager コンソールを使用して、管理パックをインポートする方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="3bf23-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="3bf23-155">ただし、エラーが発生してインポートが失敗した場合、コンソールは、適切なエラーレポートを常に提供するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="3bf23-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="3bf23-156">比較すると、Operations Manager シェルは詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="3bf23-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="3bf23-157">Operations Manager を使用していて、管理パックをインポートするときに問題が発生した場合は、Operations Manager シェルを使用してパックをインポートします。</span><span class="sxs-lookup"><span data-stu-id="3bf23-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="3bf23-158">Operations Manager シェルによって提供される情報は、インポートが失敗した理由を判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3bf23-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="3bf23-159">[**スタート**]、[**すべてのプログラム**]、[ **Microsoft System Center 2012**]、[ **Operations manager**]、[ **operations manager Shell**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bf23-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="3bf23-160">Operations Manager シェルで、Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp ファイルのコピーへの実際のパスを使用して、コマンドプロンプトで次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3bf23-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="3bf23-161">最初の管理パックをインポートした後、Microsoft.LS.2019.Monitoring.ComponentAndUser.mp ファイルのコピーのパスを使用して、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3bf23-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
