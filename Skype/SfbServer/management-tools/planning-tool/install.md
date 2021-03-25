---
title: Skype for Business Server 2015 に計画ツールをインストールする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Skype for Business Server 2015 計画ツールを使用して Skype for Business Server 2015 インフラストラクチャの設計と計画を開始する前に、まず計画ツールをインストールする必要があります。 計画ツールは、Skype for Business Server 2015 をインストールする予定のドメインまたはインフラストラクチャの一部であるワークステーションまたはサーバーに展開する必要があります。 計画ツールに関連する Readme ファイルは、ツールのインストールと使用に関する重要な情報を詳細に示します。 わかりやすくするために、Readme ファイルの情報の一部をここに転載します。
ms.openlocfilehash: 29a3bd35191cf326cafd1f4ad4f14fab50e47ea3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122381"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="ce6bd-106">Skype for Business Server 2015 に計画ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="ce6bd-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="ce6bd-107">Skype for Business Server 2015 計画ツールを使用して Skype for Business Server 2015 インフラストラクチャの設計と計画を開始する前に、まず計画ツールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="ce6bd-108">計画ツールは、Skype for Business Server 2015 をインストールする予定のドメインまたはインフラストラクチャの一部であるワークステーションまたはサーバーに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="ce6bd-109">計画ツールに関連する Readme ファイルは、ツールのインストールと使用に関する重要な情報を詳細に示します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="ce6bd-110">わかりやすくするために、Readme ファイルの情報の一部をここに転載します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce6bd-111">計画ツールでは、ツールをインストールするコンピューターに対する管理者権限とアクセス許可を持つユーザーによるインストールが必要です。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="ce6bd-112">計画ツールのインストールと操作でサポートされているオペレーティング システムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="ce6bd-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ce6bd-113">Windows 10</span></span>

- <span data-ttu-id="ce6bd-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="ce6bd-114">Windows 8</span></span>

- <span data-ttu-id="ce6bd-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ce6bd-115">Windows 8.1</span></span>

- <span data-ttu-id="ce6bd-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ce6bd-116">Windows Server 2012</span></span>

- <span data-ttu-id="ce6bd-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ce6bd-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="ce6bd-118">Windows 7、32 ビット版</span><span class="sxs-lookup"><span data-stu-id="ce6bd-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="ce6bd-119">Windows 7、64 ビット版、Windows on Win32 (WOW) 使用</span><span class="sxs-lookup"><span data-stu-id="ce6bd-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="ce6bd-120">Windows Server 2008 R2、WOW 使用</span><span class="sxs-lookup"><span data-stu-id="ce6bd-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="ce6bd-121">さらに、計画ツールには、Microsoft .NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="ce6bd-122">プレインストール要件が満たされた後、計画ツールをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="ce6bd-123">計画ツールをインストールするには</span><span class="sxs-lookup"><span data-stu-id="ce6bd-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="ce6bd-124">Administrators グループのメンバーとして、ローカル コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="ce6bd-125">Windows エクスプローラーまたはコマンド ウィンドウを使用して、計画ツールのインストール ファイルをダウンロードしたディレクトリを探します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="ce6bd-126">次のSkypeForBusinessPlanningTool.msi。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-126">Locate the SkypeForBusinessPlanningTool.msi.</span></span> <span data-ttu-id="ce6bd-127">Windows Explorer で、ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-127">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="ce6bd-128">コマンド ウィンドウで、ファイルの名前を入力し **、Enter** キーを押してファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-128">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="ce6bd-129">Skype for Business **Server 2015** の [ようこそ] ページの [計画ツールのセットアップ ウィザード] で、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="ce6bd-130">**[使用許諾契約書]** を読んでから、使用許諾契約書に同意する場合には **[使用許諾契約書に同意します]** チェック ボックスをオンにして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="ce6bd-131">計画ツール ファイルをインストールする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-131">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="ce6bd-132">既定の場所は C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool です。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-132">The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool.</span></span> <span data-ttu-id="ce6bd-133">インストール先を変更するには、**[変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-133">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="ce6bd-134">**[インストール先フォルダの変更]** で、ファイルをインストールする場所を参照または入力し、**[OK]** をクリックしてから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-134">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="ce6bd-135">これで、インストーラーは計画ツールをインストールする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="ce6bd-136">**[インストール]** をクリックして、インストール プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="ce6bd-137">インストールが開始され、進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="ce6bd-138">インストールが正常に完了したら、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="ce6bd-139">計画ツールを使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="ce6bd-140">オプション ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="ce6bd-140">Optional Software</span></span>
<span data-ttu-id="ce6bd-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="ce6bd-141"><a name="Optional_Software"> </a></span></span>

<span data-ttu-id="ce6bd-142">Skype for Business Server 2015 計画ツールは、Microsoft Excel と Microsoft Visio にエクスポートするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="ce6bd-143">これらのアプリケーションは計画ツールの操作には必要ありませんが、設計の展開とドキュメントに大きな価値を追加します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="ce6bd-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="ce6bd-144">Microsoft Excel</span></span>

<span data-ttu-id="ce6bd-145">デザインを Microsoft Excel にエクスポートすると、スプレッドシートに 7 つのタブが表示されるレポートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="ce6bd-146">概要 - ユーザー数、容量設定、サーバー プロファイル情報など、サイト構成に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="ce6bd-147">ハードウェア プロファイル - CPU、メモリ、ディスク、ネットワーク インターフェイスなど、トポロジで指定されたサーバーの推奨ハードウェア構成に関するレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="ce6bd-148">サーバー コンポーネントの数量と推奨仕様も含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="ce6bd-149">さらに、各サーバーはサイトによって定義され、サイトごとにサーバー要件を完全に表します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="ce6bd-150">ポート要件 - 有効になっているすべてのポートのレポートと、ドメイン ネーム システム負荷分散 (DNS LB) とハードウェア ロード バランサー (HLB) との関連付けを表示します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="ce6bd-151">このレポートを使用して、ファイアウォールと DNS LB および HLB 構成を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="ce6bd-152">概要レポート - エッジ サーバー ネットワークのセットアップに必要な設定の概要を表示します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="ce6bd-153">証明書レポート - エッジ サーバーを実行するために必要な証明書に必要なサブジェクト名とサブジェクト代替名を表示します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="ce6bd-154">ファイアウォール レポート - 外部インターフェイスと内部インターフェイスの両方の送信元ポートと宛先ポートと IP アドレスを表示します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="ce6bd-155">DNS レポート - 作成する各 DNS エントリに必要な完全修飾ドメイン名 (FQDN) と IP/VIP アドレスを表示します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="ce6bd-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="ce6bd-156">Microsoft Visio</span></span>

<span data-ttu-id="ce6bd-p110">設計を Microsoft Visio にエクスポートすると、構成されたトポロジおよびインフラストラクチャのドキュメントに使用できるダイアグラムが作成されます。インポートされたダイアグラムは、ドキュメントのニーズに合わせて編集や再編成ができます。一般的な Visio のダイアグラムには、次の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-p110">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="ce6bd-160">デザインが 3 台を超えるフロントエンド サーバーを必要とする十分な大きい場合は、フロントエンド プール、フロントエンド サーバー、SQL Server、IP アドレス、および FQDN を実行しているコンピューターに対して追加のページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="ce6bd-161">グローバル トポロジ - 構成済みの Skype for Business Server 2015 サイトの図。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="ce6bd-162">[サイト名] タブ - エッジ サーバー、ファイアウォール、ゲートウェイを備えた公衆交換電話網 (PSTN)、および内部サーバーの展開を含むサイト構成トポロジを表示します。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="ce6bd-163">内部展開は、フロントエンド プール、SQL Server ベースのサーバー、Active Directory ドメイン サービス、ディレクター、Exchange ユニファイド メッセージング (UM) サーバー、Exchange メールボックス サーバー、Office Web Apps サーバー、仲介サーバー、常設チャット サーバーなど、構成済みのサーバーとプールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="ce6bd-164">エッジ ネットワークダイアグラム - 関連付けられた IP アドレスと FQDN を含むエッジ サーバー構成の詳細を示す図。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="ce6bd-165">DNS 負荷分散とハードウェア ロード バランサーも含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="ce6bd-166">さらに、ディレクターとフロント エンド サーバーまたはフロント エンド プールが表示され、関連付けられた DNS LB または HLB と割り当てられた IP アドレス (計画ツールは IPv4 アドレスと IPv6 アドレスの両方をサポート) と FQDN が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce6bd-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce6bd-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce6bd-167">See also</span></span>
<span data-ttu-id="ce6bd-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="ce6bd-168"><a name="Optional_Software"> </a></span></span>

[<span data-ttu-id="ce6bd-169">計画ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="ce6bd-169">Installing the Planning Tool</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-installing-the-planning-tool)