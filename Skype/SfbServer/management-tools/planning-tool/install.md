---
title: Skype for Business Server 2015 の計画ツールのインストール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for business Server 2015 計画ツールを使用して、Skype for Business Server 2015 インフラストラクチャの設計と計画を開始する前に、まず計画ツールをインストールする必要があります。 計画ツールは、Skype for Business Server 2015 のインストールを計画しているドメインまたはインフラストラクチャの一部であるワークステーションまたはサーバーに展開する必要はありません。 計画ツールに付随する Readme ファイルには、ツールのインストールと使用に関する重要な情報が説明されています。 わかりやすくするために、Readme ファイルの情報の一部をここに転載します。
ms.openlocfilehash: 29cadae219faadb68a8a027de11309efc8e3f10b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816386"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="e5e91-106">Skype for Business Server 2015 の計画ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="e5e91-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="e5e91-107">Skype for business Server 2015 計画ツールを使用して、Skype for Business Server 2015 インフラストラクチャの設計と計画を開始する前に、まず計画ツールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5e91-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="e5e91-108">計画ツールは、Skype for Business Server 2015 のインストールを計画しているドメインまたはインフラストラクチャの一部であるワークステーションまたはサーバーに展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e5e91-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="e5e91-109">計画ツールに付随する Readme ファイルには、ツールのインストールと使用に関する重要な情報が説明されています。</span><span class="sxs-lookup"><span data-stu-id="e5e91-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="e5e91-110">わかりやすくするために、Readme ファイルの情報の一部をここに転載します。</span><span class="sxs-lookup"><span data-stu-id="e5e91-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5e91-111">計画ツールをインストールするには、ツールをインストールするコンピューターの管理者権限と権限を持つユーザーによるインストールが必要です。</span><span class="sxs-lookup"><span data-stu-id="e5e91-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="e5e91-112">計画ツールのインストールと運用でサポートされているオペレーティングシステムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5e91-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="e5e91-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e5e91-113">Windows 10</span></span>

- <span data-ttu-id="e5e91-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="e5e91-114">Windows 8</span></span>

- <span data-ttu-id="e5e91-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="e5e91-115">Windows 8.1</span></span>

- <span data-ttu-id="e5e91-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="e5e91-116">Windows Server 2012</span></span>

- <span data-ttu-id="e5e91-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="e5e91-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="e5e91-118">Windows 7、32 ビット版</span><span class="sxs-lookup"><span data-stu-id="e5e91-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="e5e91-119">Windows 7、64 ビット版、Windows on Win32 (WOW) 使用</span><span class="sxs-lookup"><span data-stu-id="e5e91-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="e5e91-120">Windows Server 2008 R2、WOW 使用</span><span class="sxs-lookup"><span data-stu-id="e5e91-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="e5e91-121">さらに、計画ツールには Microsoft .NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="e5e91-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="e5e91-122">プレインストールの要件が満たされたら、計画ツールをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5e91-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="e5e91-123">計画ツールをインストールするには</span><span class="sxs-lookup"><span data-stu-id="e5e91-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="e5e91-124">Administrators グループのメンバーとして、ローカル コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e5e91-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="e5e91-125">Windows エクスプローラーまたはコマンドウィンドウを使って、計画ツールのインストールファイルをダウンロードしたディレクトリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="e5e91-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="e5e91-p103">SkypeForBusinessPlanningTool.msi を検索します。Windows Explorer で、ファイルをダブルクリックします。コマンド ウィンドウで、ファイル名を入力してから、**Enter** キーを押してファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5e91-p103">Locate the SkypeForBusinessPlanningTool.msi. In Windows Explorer, double-click the file. In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="e5e91-129">**Skype for Business Server 2015、計画ツール セットアップ ウィザード  \*\* の [ようこそ] ページで、[**次へ\*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5e91-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="e5e91-130">[**使用許諾契約書**] を読んでから、使用許諾契約書に同意する場合には [**使用許諾契約書に同意します**] チェック ボックスをオンにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5e91-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="e5e91-p104">計画ツール ファイルをインストールする場所を選択します。既定の場所は C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool です。インストール先を変更するには、[**変更 **] をクリックします。[**インストール先フォルダーの変更**] で、ファイルをインストールする場所を参照または入力し、[**OK **] をクリックしてから、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5e91-p104">Choose where to install the Planning Tool files. The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. If you want to change the installation location, click **Change**. On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="e5e91-135">これで、インストーラーで計画ツールをインストールする準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="e5e91-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="e5e91-136">[**インストール**] をクリックして、インストール プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="e5e91-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="e5e91-137">インストールが開始され、進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5e91-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="e5e91-138">インストールが正常に完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5e91-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="e5e91-139">計画ツールを使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="e5e91-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="e5e91-140">オプション ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="e5e91-140">Optional Software</span></span>
<span data-ttu-id="e5e91-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="e5e91-141"><a name="Optional_Software"> </a></span></span>

<span data-ttu-id="e5e91-142">Skype for Business Server 2015 計画ツールは、Microsoft Excel と Microsoft Visio にエクスポートするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="e5e91-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="e5e91-143">これらのアプリケーションは計画ツールの操作には必要ありませんが、設計の展開とドキュメントに大きな価値を加えることになります。</span><span class="sxs-lookup"><span data-stu-id="e5e91-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="e5e91-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="e5e91-144">Microsoft Excel</span></span>

<span data-ttu-id="e5e91-145">デザインを Microsoft Excel にエクスポートすると、次の 7 つのタブがあるスプレッドシートを表示するレポートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e5e91-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="e5e91-146">サマリー: ユーザー数、容量の設定、サーバーのプロファイル情報など、サイトの構成に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="e5e91-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="e5e91-147">ハードウェアプロファイル-CPU、メモリ、ディスク、ネットワークインターフェイスなど、トポロジで指定されているサーバーの推奨ハードウェア構成に関するレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="e5e91-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="e5e91-148">サーバー コンポーネントの数量および推奨仕様も含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5e91-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="e5e91-149">各サーバーはサイト別に定義されているので、サイトごとのサーバー要件を詳細に示します。</span><span class="sxs-lookup"><span data-stu-id="e5e91-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="e5e91-150">[ポート要件]-有効になっているすべてのポートのレポートと、ドメイン名システム負荷分散 (DNS LB) とハードウェアロードバランサー (HLB) との関連付けが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5e91-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="e5e91-151">このレポートは、ファイアウォール、DNS LB、および HLB の構成を計画するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e5e91-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="e5e91-152">サマリーレポート-エッジサーバーネットワークのセットアップに必要な設定の一般的な概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5e91-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="e5e91-153">証明書レポート-エッジサーバーを実行するために必要な証明書に必要なサブジェクト名とサブジェクトの代替名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5e91-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="e5e91-154">[ファイアウォールレポート]-外部インターフェイスと内部インターフェイスの両方について、ソースと宛先のポートと IP アドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5e91-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="e5e91-155">DNS レポート-作成する各 DNS エントリに必要な完全修飾ドメイン名 (FQDN) と IP/VIP アドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5e91-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="e5e91-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="e5e91-156">Microsoft Visio</span></span>

<span data-ttu-id="e5e91-p110">設計を Microsoft Visio にエクスポートすると、構成されたトポロジおよびインフラストラクチャのドキュメントに使用できるダイアグラムが作成されます。インポートされたダイアグラムは、ドキュメントのニーズに合わせて編集や再編成ができます。一般的な Visio のダイアグラムには、次の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5e91-p110">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="e5e91-160">3台以上のフロントエンドサーバーが必要な設計の場合は、フロントエンドプール、フロントエンドサーバー、SQL Server を実行しているコンピューター、IP アドレス、Fqdn の追加ページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e5e91-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="e5e91-161">グローバルトポロジ-構成済みの Skype for Business Server 2015 サイトの図。</span><span class="sxs-lookup"><span data-stu-id="e5e91-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="e5e91-162">[サイト名] タブ-microsoft Edge Server、ファイアウォール、公衆交換電話網 (PSTN)、および内部サーバー展開と共に、サイトの構成トポロジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5e91-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="e5e91-163">内部展開は、フロントエンドプール、SQL Server ベースのサーバー、Active Directory ドメインサービス、ディレクター、Exchange ユニファイドメッセージング (UM) サーバー、Exchange メールボックスサーバー、Office Web Apps サーバーなど、構成済みのサーバーとプールで構成されます。仲介サーバーと常設チャットサーバー。</span><span class="sxs-lookup"><span data-stu-id="e5e91-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="e5e91-164">エッジネットワーク図-関連する IP アドレスと Fqdn を含むエッジサーバー構成の詳細を示す図。</span><span class="sxs-lookup"><span data-stu-id="e5e91-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="e5e91-165">DNS 負荷分散やロード バランサー機器も含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5e91-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="e5e91-166">さらに、関連付けられた DNS LB または HLB および割り当てられた IP アドレス (計画ツールが IPv4 アドレスと IPv6 アドレスの両方をサポートします) と FQDN が表示されたディレクターとフロントエンドサーバーまたはフロントエンドプールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5e91-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5e91-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5e91-167">See also</span></span>
<span data-ttu-id="e5e91-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="e5e91-168"><a name="Optional_Software"> </a></span></span>

[<span data-ttu-id="e5e91-169">Installing the Planning Tool</span><span class="sxs-lookup"><span data-stu-id="e5e91-169">Installing the Planning Tool</span></span>](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
