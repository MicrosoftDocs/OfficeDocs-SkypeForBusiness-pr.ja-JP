---
title: プライマリ管理サーバーの構成
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: プライマリ management server を構成し、System Center Operations Manager をインストールし、Skype for Business Server 2019 の管理パックをインポートします。'
ms.openlocfilehash: a4fda367307b99bb952e6673b3b4d1c2967299c6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824001"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="97a88-103">プライマリ管理サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="97a88-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="97a88-104">**概要:** プライマリ管理サーバーを構成し、System Center Operations Manager をインストールし、Skype for Business Server 2019 の管理パックをインポートします。</span><span class="sxs-lookup"><span data-stu-id="97a88-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2019.</span></span>

<span data-ttu-id="97a88-105">Skype for Business Server 2019 に含まれている新しい正常性監視機能を最大限に活用するには、まず、プライマリ管理サーバーとして動作するようにコンピューターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97a88-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2019, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="97a88-106">次に、そのコンピューターに System Center Operations Manager 2012 SP1 または R2 または System Center Operations Manager 2007 R2 をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97a88-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="97a88-107">さらに、サポートされているバージョンの SQL Server を、Operations Manager バックエンドデータベースとして機能するようにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97a88-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="97a88-108">System Center Operations Manager をインストールする場合は、次のような製品のすべてのコンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97a88-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="97a88-109">オペレーション データベース</span><span class="sxs-lookup"><span data-stu-id="97a88-109">Operational database</span></span>

- <span data-ttu-id="97a88-110">サーバー</span><span class="sxs-lookup"><span data-stu-id="97a88-110">Server</span></span>

- <span data-ttu-id="97a88-111">コンソール</span><span class="sxs-lookup"><span data-stu-id="97a88-111">Console</span></span>

- <span data-ttu-id="97a88-112">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="97a88-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="97a88-113">Web コンソール</span><span class="sxs-lookup"><span data-stu-id="97a88-113">Web console</span></span>

- <span data-ttu-id="97a88-114">レポート</span><span class="sxs-lookup"><span data-stu-id="97a88-114">Reporting</span></span>

- <span data-ttu-id="97a88-115">データ ウェアハウス</span><span class="sxs-lookup"><span data-stu-id="97a88-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97a88-116">System Center Operations Manager 2012 をインストールする前に、"[Microsoft Report Viewer 2010 再頒布可能パッケージ](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="97a88-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="97a88-117">これらの製品とインストールの詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="97a88-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="97a88-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="97a88-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="97a88-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="97a88-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/en-us/library/bb735860.aspx)

<span data-ttu-id="97a88-120">Skype for Business Server の展開には、1つのルート管理サーバーしか設定できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="97a88-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a><span data-ttu-id="97a88-121">Skype for Business Server 2019 管理パックのインポート</span><span class="sxs-lookup"><span data-stu-id="97a88-121">Importing the Skype for Business Server 2019 Management Packs</span></span>

<span data-ttu-id="97a88-122">管理パック (System Center Operations Manager で監視できる項目、それらの項目の監視方法、およびアラートのトリガー方法を決定するソフトウェア) をインストールすることによって System Center Operations Manager の機能を拡張することができます。発生.</span><span class="sxs-lookup"><span data-stu-id="97a88-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="97a88-123">Skype for Business Server 2019 には、次の機能を提供する System Center Operations Manager 管理パックが2つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="97a88-123">Skype for Business Server 2019 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="97a88-124">**コンポーネントとユーザー管理パック**(Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) は、イベントログに記録された Skype For business Server の問題を追跡し、パフォーマンスカウンターで登録するか、または通話の詳細レコード (CDRs) または Quality of Experience (qoe) データベースに記録します。</span><span class="sxs-lookup"><span data-stu-id="97a88-124">**The Component and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="97a88-125">重要な問題については、System Center Operations Manager を構成して、メール、インスタントメッセージ、または SMS メッセージングを介して管理者にすぐに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="97a88-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="97a88-126">(SMS、またはショートメッセージサービス) は、あるモバイルデバイスから別のモバイルデバイスにテキストメッセージを送信するために使用されるテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="97a88-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="97a88-127">Operations Manager の通知の構成について詳しくは、「[通知の構成](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="97a88-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="97a88-128">**アクティブな監視管理パック**(Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) は、システムにサインインしたり、インスタントメッセージを交換したり、公衆交換電話網 (PSTN) にある電話への通話を発信したりするなど、Skype For business Server の主要なコンポーネントを事前にテストします。</span><span class="sxs-lookup"><span data-stu-id="97a88-128">**The Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="97a88-129">これらのテストは、Skype for Business Server の代理トランザクションコマンドレットを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="97a88-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="97a88-130">たとえば、テスト用の**cgi**コマンドレットを使って、一連のテストユーザー間のインスタントメッセージの会話をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="97a88-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="97a88-131">このシミュレートされた会話が失敗すると、アラートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="97a88-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="97a88-p105">管理パックのインポートは、必要不可欠なステップです。管理パックをインポートしていない場合は、Operations Manager を使用して Skype for Business Server イベントを監視することや、Skype for Business Server 代理トランザクションを実行することができません。</span><span class="sxs-lookup"><span data-stu-id="97a88-p105">Importing the management packs is a crucial step. If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="97a88-134">コンポーネントとユーザー管理パックは、Skype for Business Server 2019 のみを監視するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="97a88-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2019.</span></span> <span data-ttu-id="97a88-135">Skype for business server 2019 と Skype for Business Server 2015 の両方がインストールされている共存シナリオの場合は、引き続き skype for business server 2015 コンピューター用の Skype for Business Server 2015 管理パックを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97a88-135">If you are in a coexistence scenario where both Skype for Business Server 2019 and Skype for Business Server 2015 are installed, you should continue to use the Skype for Business Server 2015 management packs for your Skype for Business Server 2015 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="97a88-136">Skype for business Server 2019 用の管理パックには、Skype for Business Server 2019 コンポーネントとユーザー管理パック、および Skype for Business Server 2019 Active Monitoring Management Pack が含まれています。</span><span class="sxs-lookup"><span data-stu-id="97a88-136">Management packs for Skype for Business Server 2019 include the Skype for Business Server 2019 Component and User Management Pack and the Skype for Business Server 2019 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="97a88-137">次のいずれかのツールを使用して、管理パックをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="97a88-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="97a88-138">**System Center Operations Manager**この方法では、Operations Manager を使用して、Skype for Business Server の監視を追加します。</span><span class="sxs-lookup"><span data-stu-id="97a88-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="97a88-139">**Operations Manager Shell**Operations Manager Shell を使用して直接インポートすることも、System Center Operations Manager コンソールを使用して管理パックをインポートするときに発生する問題のトラブルシューティングを行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="97a88-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="97a88-140">System Center Operations Manager を使用した管理パックのインポート</span><span class="sxs-lookup"><span data-stu-id="97a88-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="97a88-141">Microsoft Web ダウンロードから SkypeForBusiness2019ManagementPacks をダウンロードし、msi をインストールします。</span><span class="sxs-lookup"><span data-stu-id="97a88-141">Download the SkypeForBusiness2019ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="97a88-142">System Center Operations Manager で、[**管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97a88-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="97a88-143">[管理] ウィンドウで、[**管理パック**] を右クリックし、[**管理パックのインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97a88-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="97a88-144">[**管理パックの選択**] ダイアログ ボックスで、[**追加**] をクリックし、[**ディスクから追加する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97a88-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="97a88-145">[**オンライン カタログ接続**] ダイアログ ボックスで、[**いいえ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97a88-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="97a88-146">[**インポートする管理パックの選択**] ダイアログボックスで、Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp と Microsoft.LS.2019.Monitoring.ComponentAndUser.mp のファイルを見つけて選び、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97a88-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2019.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="97a88-147">ダイアログ ボックスで複数のファイルを選択するには、最初のファイルをクリックした後、Ctrl キーを押しながら 2 番目のファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="97a88-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="97a88-p108">[**管理パックの選択**] ダイアログ ボックスで、[**インストール**] をクリックします。エラー メッセージが表示されてインストールが失敗する場合は、通常、管理パックのファイルが Windows ユーザー アカウント制御によって保護されているフォルダー内にあることを意味します。その場合は、ファイルを別のフォルダーにコピーした後、インポートとインストールの処理を再度開始します。</span><span class="sxs-lookup"><span data-stu-id="97a88-p108">In the **Select Management Packs** dialog box, click **Install**. If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control. If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="97a88-p109">[**管理パックの選択**] ダイアログ ボックスで、[**閉じる**] をクリックします。インポートとインストールの処理には数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="97a88-p109">In the **Select Management Packs** dialog box, click **Close**. The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="97a88-153">Operations Manager シェルを使用した管理パックのインポート</span><span class="sxs-lookup"><span data-stu-id="97a88-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="97a88-p110">一般には、管理パックをインポートするには Operations Manager コンソールを使用する方が簡単です。ただし、エラーが発生してインポートが失敗する場合、コンソールでは適切にエラーが報告されないことがあります。これに対し、Operations Manager シェルでは詳細な情報が提供されます。Operations Manager を使用していて、管理パックのインポートに問題がある場合は、Operations Manager シェルを使用してパックをインポートしてください。Operations Manager シェルではインポートが失敗した理由の特定に役立つ可能性のある詳細な情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="97a88-p110">In general, it is easier to import the management packs by using the Operations Manager console. However, if an error occurs and the import fails, the console does not always provide adequate error reports. By comparison, the Operations Manager Shell provides detailed information. If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell. The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="97a88-159">[**スタート**]、[**すべてのプログラム**]、[**Microsoft System Center 2012**]、[**Operations Manager**] の順にクリックし、[**Operations Manager シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97a88-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="97a88-160">Operations Manager Shell で、コマンドプロンプトで次のコマンドを入力します。これには、Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp ファイルの実際のパスを使用し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="97a88-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="97a88-161">最初の管理パックをインポートした後、Microsoft.LS.2019.Monitoring.ComponentAndUser.mp ファイルのコピーのパスを使用して、次の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="97a88-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
