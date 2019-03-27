---
title: Skype for Business Server 2015 の計画ツールのインストール
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: 前に設計を開始して、ビジネス サーバー 2015 計画ツールは、Skype を使用して、Skype をビジネス サーバー 2015 インフラストラクチャを計画する必要があります最初にツールをインストールする計画です。 計画ツールは、ワークステーションまたはサーバー 2015 のビジネス用の Skype をインストールしようとするドメインまたはインフラストラクチャの一部であるサーバーに展開する必要はありません。 計画ツールに付属する Readme ファイルをインストールして、ツールの使用に関する重要な情報について詳しく説明します。 わかりやすくするために、Readme ファイルの情報の一部をここに転載します。
ms.openlocfilehash: 616cec026dfc5890cffc3975ea421d98ec13e412
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884133"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="4dd19-106">Skype for Business Server 2015 の計画ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="4dd19-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="4dd19-107">前に設計を開始して、ビジネス サーバー 2015 計画ツールは、Skype を使用して、Skype をビジネス サーバー 2015 インフラストラクチャを計画する必要があります最初にツールをインストールする計画です。</span><span class="sxs-lookup"><span data-stu-id="4dd19-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="4dd19-108">計画ツールは、ワークステーションまたはサーバー 2015 のビジネス用の Skype をインストールしようとするドメインまたはインフラストラクチャの一部であるサーバーに展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4dd19-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="4dd19-109">計画ツールに付属する Readme ファイルをインストールして、ツールの使用に関する重要な情報について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="4dd19-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="4dd19-110">わかりやすくするために、Readme ファイルの情報の一部をここに転載します。</span><span class="sxs-lookup"><span data-stu-id="4dd19-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4dd19-111">計画ツールには、管理者の権限およびツールをインストールするコンピューターに対するアクセス許可を持つユーザーによってインストールが必要です。</span><span class="sxs-lookup"><span data-stu-id="4dd19-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="4dd19-112">計画ツールのインストールや操作のサポートされているオペレーティング システムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4dd19-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="4dd19-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="4dd19-113">Windows 10</span></span>

- <span data-ttu-id="4dd19-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="4dd19-114">Windows 8</span></span>

- <span data-ttu-id="4dd19-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="4dd19-115">Windows 8.1</span></span>

- <span data-ttu-id="4dd19-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="4dd19-116">Windows Server 2012</span></span>

- <span data-ttu-id="4dd19-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4dd19-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="4dd19-118">Windows 7、32 ビット版</span><span class="sxs-lookup"><span data-stu-id="4dd19-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="4dd19-119">Windows 7、64 ビット版、Windows on Win32 (WOW) 使用</span><span class="sxs-lookup"><span data-stu-id="4dd19-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="4dd19-120">Windows Server 2008 R2、WOW 使用</span><span class="sxs-lookup"><span data-stu-id="4dd19-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="4dd19-121">さらに、計画ツールでは、Microsoft.NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="4dd19-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="4dd19-122">プレインストールの要件が満たされて後、に、計画ツールをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4dd19-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="4dd19-123">計画ツールをインストールするには</span><span class="sxs-lookup"><span data-stu-id="4dd19-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="4dd19-124">Administrators グループのメンバーとして、ローカル コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4dd19-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="4dd19-125">Windows エクスプ ローラーまたはコマンド ウィンドウを使用して、計画ツールのインストール ファイルをダウンロードしたディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="4dd19-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="4dd19-p103">SkypeForBusinessPlanningTool.msi を検索します。Windows Explorer で、ファイルをダブルクリックします。コマンド ウィンドウで、ファイル名を入力してから、**Enter** キーを押してファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="4dd19-p103">Locate the SkypeForBusinessPlanningTool.msi. In Windows Explorer, double-click the file. In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="4dd19-129">**Skype for Business Server 2015、計画ツール セットアップ ウィザード  \*\* の [ようこそ] ページで、[**次へ\*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dd19-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="4dd19-130">[**使用許諾契約書**] を読んでから、使用許諾契約書に同意する場合には [**使用許諾契約書に同意します**] チェック ボックスをオンにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dd19-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="4dd19-p104">計画ツール ファイルをインストールする場所を選択します。既定の場所は C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool です。インストール先を変更するには、[**変更 **] をクリックします。[**インストール先フォルダーの変更**] で、ファイルをインストールする場所を参照または入力し、[**OK **] をクリックしてから、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dd19-p104">Choose where to install the Planning Tool files. The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. If you want to change the installation location, click **Change**. On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="4dd19-135">計画ツールをインストールする準備がようになりました。</span><span class="sxs-lookup"><span data-stu-id="4dd19-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="4dd19-136">[**インストール**] をクリックして、インストール プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="4dd19-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="4dd19-137">インストールが開始され、進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dd19-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="4dd19-138">インストールが正常に完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dd19-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="4dd19-139">計画ツールは、使用できる状態です。</span><span class="sxs-lookup"><span data-stu-id="4dd19-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="4dd19-140">オプション ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="4dd19-140">Optional Software</span></span>
<span data-ttu-id="4dd19-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="4dd19-141"></span></span>

<span data-ttu-id="4dd19-142">ビジネス サーバー 2015 計画ツールの Skype は、Microsoft Excel および Microsoft Visio にエクスポートするのには設計されています。</span><span class="sxs-lookup"><span data-stu-id="4dd19-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="4dd19-143">計画ツールの操作に必要なこれらのアプリケーションは、配置およびデザインのドキュメントに付加価値が高まるの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4dd19-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="4dd19-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="4dd19-144">Microsoft Excel</span></span>

<span data-ttu-id="4dd19-145">デザインを Microsoft Excel にエクスポートすると、次の 7 つのタブがあるスプレッドシートを表示するレポートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4dd19-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="4dd19-146">概要 - サイトの構成情報を表示しますは、ユーザー数、容量の設定、およびサーバーのプロファイル情報を含みます。</span><span class="sxs-lookup"><span data-stu-id="4dd19-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="4dd19-147">ハードウェア プロファイル - CPU、メモリ、ディスク、およびネットワーク ・ インタ フェースを含め、トポロジで指定されているサーバーの推奨ハードウェア構成を表示します。</span><span class="sxs-lookup"><span data-stu-id="4dd19-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="4dd19-148">サーバー コンポーネントの数量および推奨仕様も含まれます。</span><span class="sxs-lookup"><span data-stu-id="4dd19-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="4dd19-149">各サーバーはサイト別に定義されているので、サイトごとのサーバー要件を詳細に示します。</span><span class="sxs-lookup"><span data-stu-id="4dd19-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="4dd19-150">ポートの要件: ドメイン ネーム システム負荷分散 (DNS LB) およびハードウェア ロード バランサー機器 (HLB) を有効になっているすべてのポートとの関連付けのレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dd19-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="4dd19-151">このレポートは、ファイアウォール、DNS LB、および HLB の構成を計画するために使用します。</span><span class="sxs-lookup"><span data-stu-id="4dd19-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="4dd19-152">サマリー レポートには、エッジ サーバーのネットワークをセットアップする必要がある設定の概要を表示します。</span><span class="sxs-lookup"><span data-stu-id="4dd19-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="4dd19-153">サブジェクト名とサブジェクト代替名を実行しているエッジ トランスポート サーバーを取得するために必要な証明書に必要な証明書のレポート - が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dd19-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="4dd19-154">ファイアウォールのレポートの送信元と宛先のポートおよび IP アドレスを外部と内部の両方のインターフェイスを表示します。</span><span class="sxs-lookup"><span data-stu-id="4dd19-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="4dd19-155">DNS レポートの完全修飾ドメイン名 (FQDN) を表示して、IP/VIP アドレスに必要な各 DNS エントリを作成することです。</span><span class="sxs-lookup"><span data-stu-id="4dd19-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="4dd19-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="4dd19-156">Microsoft Visio</span></span>

<span data-ttu-id="4dd19-p110">設計を Microsoft Visio にエクスポートすると、構成されたトポロジおよびインフラストラクチャのドキュメントに使用できるダイアグラムが作成されます。インポートされたダイアグラムは、ドキュメントのニーズに合わせて編集や再編成ができます。一般的な Visio のダイアグラムには、次の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4dd19-p110">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="4dd19-160">デザインが 4 つ以上のフロント エンド サーバーを必要とするのに十分な大きさの場合は、フロント エンド プール、フロント エンド サーバー、SQL Server、IP アドレス、および Fqdn を実行するコンピューターの追加のページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4dd19-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="4dd19-161">グローバル トポロジでは、ビジネス サーバー 2015 サイトに対して構成されている Skype の図です。</span><span class="sxs-lookup"><span data-stu-id="4dd19-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="4dd19-162">サイト名] タブのサイト構成のトポロジにエッジ サーバー、ファイアウォール、パブリックの切り替え表示は電話網 (PSTN) ゲートウェイ、および内部サーバーの展開とです。</span><span class="sxs-lookup"><span data-stu-id="4dd19-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="4dd19-163">内部の配置は、構成されているサーバーとプール、フロント エンドを含むプール、SQL Server ベースのサーバー、Active Directory ドメイン サービスでは、ダイレクタでは、Exchange ユニファイド メッセージング (UM) サーバー、Exchange メールボックス サーバーでは、Office Web アプリケーション サーバーでは、仲介サーバー、および永続的なチャット サーバー。</span><span class="sxs-lookup"><span data-stu-id="4dd19-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="4dd19-164">エッジのネットワーク ダイアグラムに関連付けられている IP アドレスと Fqdn を使用してエッジ サーバー構成の詳細を示す図。</span><span class="sxs-lookup"><span data-stu-id="4dd19-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="4dd19-165">DNS 負荷分散やロード バランサー機器も含まれます。</span><span class="sxs-lookup"><span data-stu-id="4dd19-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="4dd19-166">また、ディレクターおよびフロント エンド サーバーまたはフロント エンド プールが表示されます、関連付けられた DNS LB または HLB (計画ツールには、IPv4 と IPv6 アドレスの両方がサポートされています)、割り当てられた IP アドレスと FQDN を持つ。</span><span class="sxs-lookup"><span data-stu-id="4dd19-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="4dd19-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="4dd19-167">See also</span></span>
<span data-ttu-id="4dd19-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="4dd19-168"></span></span>

[<span data-ttu-id="4dd19-169">Installing the Planning Tool</span><span class="sxs-lookup"><span data-stu-id="4dd19-169">Installing the Planning Tool</span></span>](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
