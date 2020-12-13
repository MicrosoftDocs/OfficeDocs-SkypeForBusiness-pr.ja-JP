---
title: Microsoft Teams のクライアントを取得する
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で利用できる Web、デスクトップ (Windows、Mac)、およびモバイル (Android、iOS) などのさまざまなクライアントを使用する方法を知る。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2cb28295b0a9700a0eb7531111022a9498517d93
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611591"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="9d3fe-103">Microsoft Teams のクライアントを取得する</span><span class="sxs-lookup"><span data-stu-id="9d3fe-103">Get clients for Microsoft Teams</span></span> 

<span data-ttu-id="9d3fe-104">Microsoft Teams には、デスクトップ (Windows、Mac、Linux)、Web、モバイル (Android および iOS) で利用できるクライアントがあります。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-104">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS).</span></span> <span data-ttu-id="9d3fe-105">これらのクライアントすべてにアクティブなインターネット接続が必要で、オフライン モードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-105">These clients all require an active internet connection and do not support an offline mode.</span></span> 

> [!Note]
> <span data-ttu-id="9d3fe-106">別のプラットフォームでの機能についての詳細は、 [プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-106">For details about each clients' capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

> [!NOTE]
> <span data-ttu-id="9d3fe-107">2018 年 11 月 29 日付で、Microsoft Store から入手可能な Microsoft Teams の Windows 10 S (プレビュー) アプリが使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-107">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="9d3fe-108">代わりに、Windows 10 S モードを実行しているデバイスに、Teams デスクトップ クライアントをダウンロードしてインストールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-108">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="9d3fe-109">デスクトップ クライアントをダウンロードするには、[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-109">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="9d3fe-110">Teams デスクトップ クライアントの MSI ビルドは、Windows 10 S モードを実行しているデバイスではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-110">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="9d3fe-111">Windows 10 S モードの詳細については、「[Windows 10 (S モード) について](https://www.microsoft.com/windows/s-mode)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-111">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="9d3fe-112">デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="9d3fe-112">Desktop client</span></span>

> [!TIP]
> <span data-ttu-id="9d3fe-113">Windows Desktop Clientの効果、計画や展開の方法については次のセッションを参照してください。[Teams Windows Desktop Client](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="9d3fe-113">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="9d3fe-114">Microsoft Teams デスクトップ クライアントはスタンドアロン アプリケーションであり、[Microsoft 365 Apps for enterprise でも利用できます](https://docs.microsoft.com/deployoffice/teams-install)。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-114">The Microsoft Teams desktop client is a standalone application and is also [available in Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/teams-install).</span></span> <span data-ttu-id="9d3fe-115">Teams は、32 ビット版と 64 ビット版の Windows (8.1 以降) ARM 上の Windows 10用の ARM 64および Windows Server (2012 R2 以降) に加えて、macOS および Linux (`.deb` 形式と `.rpm` 形式) でも利用できます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-115">Teams is available for 32-bit and 64-bit versions of Windows (8.1 or later), ARM64 for Windows 10 on ARM, and Windows Server (2012 R2 or later), as well as for macOS and Linux (in `.deb` and `.rpm` formats).</span></span> <span data-ttu-id="9d3fe-116">Windows で Teams を使用するには .NET Framework 4.5 以降が必要です。.NET Framework 4.5 以降がない場合は、Teams のインストーラーでインストールすることを勧めます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-116">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="9d3fe-117">Linux では、`apt` や `yum` などのパッケージ マネージャーにより、要件すべてのインストールが自動的に試みられます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-117">On Linux, package managers such as `apt` and `yum` will try to install any requirements for you.</span></span> <span data-ttu-id="9d3fe-118">しかし、インストールされない場合は、Linux に Teams をインストールする前に、報告されている要件すべてをユーザーがインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-118">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="9d3fe-119">デスクトップ クライアントは、チーム会議、グループ通話、およびプライベートな 1 対 1 での通話に対応するリアルタイム通信のサポート (オーディオ、ビデオ、およびコンテンツ共有) を提供します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-119">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="9d3fe-120">デスクトップ クライアントは、適切なローカルのアクセス許可を持っているエンド ユーザーによって、[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) から直接ダウンロードおよびインストールできます (管理者権限は、Teams クライアントを PC にインストールする場合には必要ありませんが、Mac では必要になります) 。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-120">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

> [!NOTE]
> <span data-ttu-id="9d3fe-121">Chromebook に Teams をインストールする方法についての詳細情報については、[Chromebook に Microsoft Office をインストールして実行する方法](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-121">For more details about installing Teams on a Chromebook, please see [How to install and run Microsoft Office on a Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad).</span></span>

<span data-ttu-id="9d3fe-122">IT 管理者は、組織内のコンピューターにインストール ファイルを配布する方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-122">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="9d3fe-123">Microsoft Endpoint Configuration Manager (Windows) や Jamf Pro (macOS) などを選択できます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-123">Some examples include Microsoft Endpoint Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="9d3fe-124">Windows ディストリビューションの MSI パッケージを取得するには、[MSI を使用して Microsoft Teams をインストールする](msi-deployment.md)を参照ください。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-124">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="9d3fe-125">これらのメカニズムによるクライアントの配布は、Microsoft Teams クライアントの初回インストール時にのみ利用でき、それ以降の更新では利用できません。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-125">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="9d3fe-126">Windows</span><span class="sxs-lookup"><span data-stu-id="9d3fe-126">Windows</span></span>

<span data-ttu-id="9d3fe-127">Windows での Microsoft Teams のインストールでは、32 ビットと 64 ビット アーキテクチャでダウンロード可能なインストーラーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-127">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="9d3fe-128">Microsoft Teams のアーキテクチャ (32 ビットと 64 ビット) はインストールされている Windows および Office のアーキテクチャに依存しません。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-128">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="9d3fe-129">Windows クライアントは、ユーザーのプロファイルの AppData フォルダーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-129">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="9d3fe-130">ユーザーのローカル プロファイルへの展開で、権限を必要とせずクライアントをインストールする事ができます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-130">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="9d3fe-131">Windows クライアントは、次の場所を利用します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-131">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="9d3fe-132">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="9d3fe-132">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="9d3fe-133">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="9d3fe-133">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="9d3fe-134">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="9d3fe-134">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="9d3fe-135">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="9d3fe-135">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="9d3fe-136">ユーザーが Microsoft Teams クライアントを使用して初めて通話を開始する時は、ユーザーに通信の許可を求める Windows ファイアウォール設定の警告が通知される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-136">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="9d3fe-137">警告を受け入れなくても通話は機能するため、このメッセージを無視するように指示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-137">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![[Windows セキュリティの重要な警告] ダイアログのスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="9d3fe-139">Windows ファイアウォール設定は、[キャンセル] の選択によりプロンプトが受け入れられなかった場合でも変更されます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-139">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="9d3fe-140">TCP および UDP プロトコルの両方に関する許可アクションで、teams.exe に関する2 つの着信ルールが作成されます。 </span><span class="sxs-lookup"><span data-stu-id="9d3fe-140">Two inbound rules for teams.exe will be created with Allow action for both TCP and UDP protocols.</span></span>

<span data-ttu-id="9d3fe-141">ユーザーが Teams で最初の通話を行うときに、 Teams がユーザーにファイアウォール ルールの作成を要求しないようにする場合は、以下の[PowerShell のサンプル スクリプト（受信ファイアウォール ルール）](#sample-powershell-script---inbound-firewall-rule)を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-141">If you want to prevent Teams from prompting users to create firewall rules when the users make their first call from Teams, use the [Sample PowerShell script - inbound firewall rule](#sample-powershell-script---inbound-firewall-rule) below.</span></span> 

### <a name="mac"></a><span data-ttu-id="9d3fe-142">Mac</span><span class="sxs-lookup"><span data-stu-id="9d3fe-142">Mac</span></span>

<span data-ttu-id="9d3fe-143">Mac ユーザーは、macOS コンピューターのパッケージ インストール ファイルを使用して、Teams をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-143">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="9d3fe-144">Mac クライアントをインストールするには、管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-144">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="9d3fe-145">macOS クライアントは /Applications フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-145">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="9d3fe-146">パッケージ ファイルを使用して Teams をインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-146">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="9d3fe-147">[Teams のダウンロード ページ](https://teams.microsoft.com/downloads)の、**Mac** で、**Download** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-147">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="9d3fe-148">パッケージ ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-148">Double click the PKG file.</span></span>
3. <span data-ttu-id="9d3fe-149">インストール ウィザードに従ってインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-149">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="9d3fe-150">Teams は、/Applications フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-150">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="9d3fe-151">これはコンピューター全体のインストールです。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-151">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="9d3fe-152">インストール時に、パッケージが管理者認証情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-152">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="9d3fe-153">ユーザーは、管理者であるかどうかに関係なく、管理者認証情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-153">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="9d3fe-154">もしユーザーが現時点で Teams の DMG インストールをしていて、パッケージのインストールと置き換えたい場合は、以下を実行してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-154">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="9d3fe-155">Teams アプリを終了します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-155">Exit the Teams app.</span></span>
2. <span data-ttu-id="9d3fe-156">Teams アプリをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-156">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="9d3fe-157">パッケージ ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-157">Install the PKG file.</span></span>

<span data-ttu-id="9d3fe-158">IT 管理者は、Teams の管理の展開を使用して、Jamf Pro などの組織のすべての Mac にインストール ファイルを配布することができます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-158">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="9d3fe-159">パッケージのインストールで問題が発生した場合は、報告してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-159">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="9d3fe-160">この記事の最後の **フィードバック** セクションで、**製品のフィードバック** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-160">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="9d3fe-161">Linux</span><span class="sxs-lookup"><span data-stu-id="9d3fe-161">Linux</span></span>

<span data-ttu-id="9d3fe-162">ユーザーは、ネイティブの Linux パッケージを `.deb` 形式と `.rpm` 形式でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-162">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span>
<span data-ttu-id="9d3fe-163">DEB パッケージか RPM パッケージをインストールすると、パッケージ リポジトリが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-163">Installing the DEB or RPM package will automatically install the package repository.</span></span>
- <span data-ttu-id="9d3fe-164">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span><span class="sxs-lookup"><span data-stu-id="9d3fe-164">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span></span>
- <span data-ttu-id="9d3fe-165">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span><span class="sxs-lookup"><span data-stu-id="9d3fe-165">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span></span> 

<span data-ttu-id="9d3fe-166">システムのパッケージ マネージャーを使用して自動更新を有効にするための署名キーが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-166">The signing key to enable auto-updating using the system's package manager is installed automatically.</span></span> <span data-ttu-id="9d3fe-167">ただし、これは (https://packages.microsoft.com/keys/microsoft.asc) にもあります。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-167">However, it can also be found at: (https://packages.microsoft.com/keys/microsoft.asc).</span></span> <span data-ttu-id="9d3fe-168">Microsoft Teams は毎月更新されており、リポジトリが正常にインストールされていれば、システム上の他のパッケージと同様に、システム パッケージ マネージャーによって自動更新が処理されます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-168">Microsoft Teams ships monthly and if the repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.</span></span>

> [!NOTE] 
> <span data-ttu-id="9d3fe-169">バグが見つかった場合は、クライアント内から `Report a Problem` を使用してご報告ください。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-169">If you find a bug, submit it using `Report a Problem` from within the client.</span></span> <span data-ttu-id="9d3fe-170">既知の問題については、「[組織で Teams をサポートする](Known-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-170">For known issues, see [Support Teams in your organization](Known-issues.md).</span></span>
> <span data-ttu-id="9d3fe-171">Linux 向けの Teams のサポートについては、[Microsoft Q&A の Linux フォーラム サポート チャネル](https://docs.microsoft.com/answers/topics/teams.html) をご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-171">For Teams for Linux support you can use the [Linux forum support channel on Microsoft Q&A](https://docs.microsoft.com/answers/topics/teams.html).</span></span> <span data-ttu-id="9d3fe-172">質問を投稿するときは、必ず `teams-linux` タグを使用してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-172">Be sure to use the `teams-linux` tag when posting questions.</span></span> 

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="9d3fe-173">DEB パッケージを使用して Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="9d3fe-173">Install Teams using DEB package</span></span>

1. <span data-ttu-id="9d3fe-174">https://aka.ms/getteams からパッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-174">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="9d3fe-175">次のいずれかの方法でインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-175">Install using one of the following:</span></span>  
    - <span data-ttu-id="9d3fe-176">適切なパッケージ管理ツールを開き、Linux アプリのセルフガイド インストール プロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-176">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="9d3fe-177">ターミナルから実行する場合は、「`sudo dpkg -i **teams download file**`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-177">Or if you love Terminal, type: `sudo dpkg -i **teams download file**`</span></span>

<span data-ttu-id="9d3fe-178">Teams は、アクティビティから起動することも、ターミナルから「`teams`」と入力して起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-178">You can launch Teams via Activities or via Terminal by typing `teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="9d3fe-179">RPM パッケージを使用して Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="9d3fe-179">Install Teams using RPM package</span></span>

1. <span data-ttu-id="9d3fe-180">https://aka.ms/getteams からパッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-180">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="9d3fe-181">次のいずれかの方法でインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-181">Install using one of the following:</span></span>
    - <span data-ttu-id="9d3fe-182">適切なパッケージ管理ツールを開き、Linux アプリのセルフガイド インストール プロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-182">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="9d3fe-183">ターミナルから実行する場合は、「`sudo yum install **teams download file**`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-183">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="9d3fe-184">Teams は、アクティビティから起動することも、ターミナルから「`teams`」と入力して起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-184">You can launch Teams via Activities or via Terminal by typing `teams`.</span></span>

#### <a name="install-manually-from-the-command-line"></a><span data-ttu-id="9d3fe-185">コマンド ラインから手動でインストールする</span><span class="sxs-lookup"><span data-stu-id="9d3fe-185">Install manually from the command line</span></span>

<span data-ttu-id="9d3fe-186">Debian や Ubuntu のディストリビューションには、次のようにして手動でインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-186">Install manually on Debian and Ubuntu distributions:</span></span>

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

<span data-ttu-id="9d3fe-187">RHEL、Fedora、CentOS ベースのディストリビューションには、次のようにして手動でインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-187">Install manually on RHEL, Fedora and CentOS based distributions:</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

<span data-ttu-id="9d3fe-188">dnf の代わりに yum を使用する場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-188">Alternatively, to use yum instead of dnf:</span></span>

```bash
yum check-update
sudo yum install teams
```

<span data-ttu-id="9d3fe-189">openSUSE ベースのディストリビューションには、次のようにして手動でインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-189">Install manually on openSUSE based distributions:</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a><span data-ttu-id="9d3fe-190">Web クライアント</span><span class="sxs-lookup"><span data-stu-id="9d3fe-190">Web client</span></span> 

<span data-ttu-id="9d3fe-191">Web クライアント ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) は、さまざまなブラウザーから使用できる、完全な機能クライアントです。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-191">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="9d3fe-192">Web クライアントは WebRTC を使用することによって通話と会議をサポートするため、Web ブラウザーで Teams を実行するためのプラグインやダウンロードの必要がありません。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-192">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="9d3fe-193">ブラウザーはサードパーティの Cookie を許可するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-193">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="9d3fe-194">Web クライアントは[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)への接続時にブラウザーのバージョンの検出を実行します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-194">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="9d3fe-195">サポートされていないブラウザー バージョンを検出した場合、Web インターフェイスへのアクセスをブロックし、デスクトップ クライアントまたはモバイル アプリのダウンロードをユーザーに推奨します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-195">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="9d3fe-196">モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="9d3fe-196">Mobile clients</span></span>

<span data-ttu-id="9d3fe-197">Microsoft Teams モバイル アプリは Android および iOS で利用可能で、外出先でチャット会話に参加しているユーザーを対象とし、ピア ツー ピアの音声通話を許可します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-197">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="9d3fe-198">モバイル アプリを使用する場合は、Google Play と Apple App Store の関連モバイル ストアに移動します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-198">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="9d3fe-199">Windows Phone App は 2018 年 7 月 20 日に廃止された為、動作しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-199">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="9d3fe-200">中国で Android 用 Teams を取得する方法については、[こちら](get-teams-android-in-china.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-200">In China, here's how to [get Teams for Android](get-teams-android-in-china.md).</span></span> 

<span data-ttu-id="9d3fe-201">Microsoft Teams モバイル アプリをサポートしているモバイル プラットフォームは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-201">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="9d3fe-202">**Android**: サポート対象は、最新の 4 つのメジャー バージョンの Android に限られています。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-202">**Android**: Support is limited to the last four major versions of Android.</span></span> <span data-ttu-id="9d3fe-203">新しいメジャー バージョンの Android がリリースされると、その新しいバージョンと、その前の 3 つのバージョンが正式にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-203">When a new major version of Android is released, the new version and the previous three versions are officially supported.</span></span>

-   <span data-ttu-id="9d3fe-204">**iOS**: サポート対象は、最新の 2 つのメジャー バージョンの iOS に限られています。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-204">**iOS**: Support is limited to the two most recent major versions of iOS.</span></span> <span data-ttu-id="9d3fe-205">新しいメジャー バージョンの iOS がリリースされると、その新しいバージョンの iOS と、その 1 つ前のバージョンが正式にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-205">When a new major version of iOS is released, the new version of iOS and the previous version are officially supported.</span></span>

> [!NOTE]
> <span data-ttu-id="9d3fe-206">Teams が正常に動作するには、そのモバイル バージョンが公開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-206">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="9d3fe-207">モバイル アプリは、それぞれのモバイル プラットフォームのアプリ ストアからのみ配布および更新されます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-207">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="9d3fe-208">MDM やサイド ロードからモバイル アプリを配布することは、Microsoft ではサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-208">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="9d3fe-209">サポートされているモバイル プラットフォームにモバイル アプリがインストールされると、Teams モバイル アプリ自体、そのバージョンが現在のリリースから 3 か月以内であればサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-209">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![判断ポイントを表すアイコン](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="9d3fe-211">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="9d3fe-211">Decision Point</span></span>         |<span data-ttu-id="9d3fe-212">ユーザーが適切な Microsoft Teams クライアントをデバイスにインストールすることを妨げる制限事項はありますか?</span><span class="sxs-lookup"><span data-stu-id="9d3fe-212">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![次のステップを表すアイコン](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="9d3fe-214">次のステップ</span><span class="sxs-lookup"><span data-stu-id="9d3fe-214">Next Steps</span></span>         |<span data-ttu-id="9d3fe-p121">組織によってソフトウェアのインストールが制限されている場合、処理が Microsoft Teams に対応していることを確認してください。注意: 管理者権限は、PC クライアント インストールでは必要ありませんが、Mac へのインストールでは必要になります。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-p121">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams. Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="9d3fe-217">クライアントの更新管理</span><span class="sxs-lookup"><span data-stu-id="9d3fe-217">Client update management</span></span>

<span data-ttu-id="9d3fe-218">クライアントは現在、Microsoft Teams サービスによって自動的に更新されています。IT 管理者が介入する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-218">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="9d3fe-219">利用可能な更新プログラムがある場合、クライアントは自動的にその更新プログラムをダウンロードします。アプリが一定時間アイドル状態となった場合には更新処理が開始されます。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-219">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="9d3fe-220">クライアント側の設定</span><span class="sxs-lookup"><span data-stu-id="9d3fe-220">Client-side configurations</span></span>

<span data-ttu-id="9d3fe-221">現在、テナント管理者、PowerShell、グループ ポリシー オブジェクトまたはレジストリのいずれかを介してクライアントを設定するオプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-221">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="9d3fe-222">通知の設定</span><span class="sxs-lookup"><span data-stu-id="9d3fe-222">Notification settings</span></span>

<span data-ttu-id="9d3fe-p123">現在、IT 管理者がクライアント側の通知設定を設定するオプションはありません。通知オプションはすべてユーザーによって設定されます。次の図に、既定のクライアント設定の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-p123">There are currently no options available for IT administrators to configure client-side notification settings. All notification options are set by the user. The figure below outlines the default client settings.</span></span>

![通知設定のスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script---inbound-firewall-rule"></a><span data-ttu-id="9d3fe-227">PowerShell のサンプル スクリプト - 受信ファイアウォール ルール</span><span class="sxs-lookup"><span data-stu-id="9d3fe-227">Sample PowerShell script - inbound firewall rule</span></span>

<span data-ttu-id="9d3fe-228">このサンプル スクリプトは、管理者アカウントのコンテキスト内のクライアント コンピューターで実行する必要があり、c:\users にある各ユーザーのフォルダーの新しい受信ファイアウォール ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-228">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="9d3fe-229">Teams がこのルールを検出すると、ユーザーが Teams からの最初の呼び出しを行うときに、ファイアウォール ルールを作成する為の Teams アプリケーションからユーザーへの指示ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="9d3fe-229">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
