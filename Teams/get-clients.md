---
title: Microsoft Teams のクライアントを取得する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で利用できる Web、デスクトップ (Windows、Mac)、およびモバイル (Android、iOS) などのさまざまなクライアントを使用する方法を知る。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: f3332f25366ea79d69bb95727f01651cb158de53
ms.sourcegitcommit: c2e315d0fcec742d2e1ba5ad90dffd1a1157a466
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2019
ms.locfileid: "40002241"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="8363f-103">Microsoft Teams のクライアントを取得する</span><span class="sxs-lookup"><span data-stu-id="8363f-103">Get clients for Microsoft Teams</span></span> 


<span data-ttu-id="8363f-104">Microsoft Teams には、デスクトップ (Windows、Mac、Linux)、web、モバイル (Android および iOS) で使用できるクライアントがあります。</span><span class="sxs-lookup"><span data-stu-id="8363f-104">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS).</span></span> <span data-ttu-id="8363f-105">これらのクライアントはすべてアクティブなインターネット接続が必要で、オフライン モードをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8363f-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="8363f-106">2018 年 11 月 29 日付で、Microsoft Store から入手可能な Microsoft Teams の Windows 10 S (プレビュー) アプリが使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8363f-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="8363f-107">代わりに、Windows 10 S モードを実行しているデバイスに Teams デスクトップクライアントをダウンロードしてインストールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8363f-107">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="8363f-108">デスクトップクライアントをダウンロードするには、 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="8363f-108">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="8363f-109">Teams デスクトップクライアントの MSI ビルドは、Windows 10 S モードを実行しているデバイスではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="8363f-109">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="8363f-110">Windows 10 S モードの詳細については、「 [windows 10 を S モードで導入](https://www.microsoft.com/windows/s-mode)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8363f-110">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="8363f-111">デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="8363f-111">Desktop client</span></span>

> [!TIP]
> <span data-ttu-id="8363f-112">Windows Desktop Clientの効果、計画や展開の方法については次のセッションを参照してください。[Teams Windows Desktop Client](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="8363f-112">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="8363f-113">Microsoft Teams デスクトップクライアントは、スタンドアロンアプリケーションであり、 [Office 365 ProPlus でも利用でき](https://docs.microsoft.com/deployoffice/teams-install)ます。</span><span class="sxs-lookup"><span data-stu-id="8363f-113">The Microsoft Teams desktop client is a standalone application and is also [available in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span> <span data-ttu-id="8363f-114">Teams は Windows (7 +)、32ビットバージョンと64ビットバージョン、macOS (10.10 +)、Linux (in `.deb`と`.rpm` format) の両方で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8363f-114">Teams is available for Windows (7+), both 32-bit and 64-bit versions, macOS (10.10+), and Linux (in `.deb` and `.rpm` formats.).</span></span> <span data-ttu-id="8363f-115">Windows で Teams を使用するには .NET Framework 4.5 以降が必要です。.NET Framework 4.5 以降がない場合は、Teams のインストーラーでインストールすることを勧めます。</span><span class="sxs-lookup"><span data-stu-id="8363f-115">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="8363f-116">Linux では、apt、yum などのパッケージマネージャーが、必要な要件をすべてインストールしようとします。</span><span class="sxs-lookup"><span data-stu-id="8363f-116">On Linux, package managers such as apt and yum will try to install any requirements for you.</span></span> <span data-ttu-id="8363f-117">ただし、このようになっていない場合は、チームを Linux にインストールする前に、報告された要件をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8363f-117">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="8363f-118">デスクトップ クライアントは、チーム会議、グループ通話、およびプライベートな 1 対 1 での通話に対応するリアルタイム通信のサポート (オーディオ、ビデオ、およびコンテンツ共有) を提供します。</span><span class="sxs-lookup"><span data-stu-id="8363f-118">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="8363f-119">デスクトップ クライアントは、適切なローカルのアクセス許可を持っているエンド ユーザーによって、[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) から直接ダウンロードおよびインストールできます (管理者権限は、Teams クライアントを PC にインストールする場合には必要ありませんが、Mac では必要になります) 。</span><span class="sxs-lookup"><span data-stu-id="8363f-119">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="8363f-120">IT 管理者は、組織内のコンピューターにインストールファイルを配布するのに適した方法を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="8363f-120">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="8363f-121">たとえば、System Center Configuration Manager (Windows) または Jamf Pro (macOS) などがあります。</span><span class="sxs-lookup"><span data-stu-id="8363f-121">Some examples include System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="8363f-122">Windows ディストリビューションの MSI パッケージを取得するには、[MSI を使用して Microsoft Teams をインストールする](msi-deployment.md)を参照ください。</span><span class="sxs-lookup"><span data-stu-id="8363f-122">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="8363f-123">これらのメカニズムによるクライアントの配布は、Microsoft Teams クライアントの初回インストール時にのみ利用でき、それ以降の更新では利用できません。</span><span class="sxs-lookup"><span data-stu-id="8363f-123">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="8363f-124">Windows</span><span class="sxs-lookup"><span data-stu-id="8363f-124">Windows</span></span>

<span data-ttu-id="8363f-125">Windows での Microsoft Teams のインストールでは、32 ビットと 64 ビット アーキテクチャでダウンロード可能なインストーラーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="8363f-125">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="8363f-126">Microsoft Teams のアーキテクチャ (32 ビットと 64 ビット) はインストールされている Windows および Office のアーキテクチャに依存しません。</span><span class="sxs-lookup"><span data-stu-id="8363f-126">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="8363f-127">Windows クライアントは、ユーザーのプロファイルの AppData フォルダーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="8363f-127">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="8363f-128">ユーザーのローカル プロファイルへの展開で、権限を必要とせずクライアントをインストールする事ができます。</span><span class="sxs-lookup"><span data-stu-id="8363f-128">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="8363f-129">Windows クライアントは、次の場所を利用します。</span><span class="sxs-lookup"><span data-stu-id="8363f-129">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="8363f-130">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="8363f-130">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="8363f-131">% LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="8363f-131">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="8363f-132">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="8363f-132">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="8363f-133">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="8363f-133">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="8363f-134">ユーザーが Microsoft Teams クライアントを使用して初めて通話を開始する時は、ユーザーに通信の許可を求める Windows ファイアウォール設定の警告が通知される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8363f-134">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="8363f-135">警告を受け入れなくても通話は機能するため、このメッセージを無視するように指示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8363f-135">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![[Windows セキュリティの重要な警告] ダイアログのスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="8363f-p107">Windows ファイアウォール設定は、[キャンセル] の選択によりプロンプトが受け入れられなかった場合でも変更されます。TCP および UDP プロトコルの両方に関するブロック アクションで、teams.exe に関する2 つの着信ルールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8363f-p107">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”. Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="8363f-139">Mac</span><span class="sxs-lookup"><span data-stu-id="8363f-139">Mac</span></span>

<span data-ttu-id="8363f-140">Mac ユーザーは、macOS コンピューターのパッケージ インストール ファイルを使用して、Teams をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="8363f-140">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="8363f-141">Mac クライアントをインストールするには、管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="8363f-141">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="8363f-142">macOS クライアントは /Applications フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8363f-142">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="8363f-143">パッケージ ファイルを使用して Teams をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8363f-143">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="8363f-144">[Teams のダウンロード ページ](https://teams.microsoft.com/downloads)の、**Mac**で、**Download**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8363f-144">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="8363f-145">パッケージ ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="8363f-145">Double click the PKG file.</span></span>
3. <span data-ttu-id="8363f-146">インストール ウィザードに従ってインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="8363f-146">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="8363f-147">Teams は、/Applications フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8363f-147">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="8363f-148">これはコンピューター全体のインストールです。</span><span class="sxs-lookup"><span data-stu-id="8363f-148">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="8363f-149">インストール時に、パッケージが管理者認証情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="8363f-149">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="8363f-150">ユーザーは、管理者であるかどうかに関係なく、管理者認証情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8363f-150">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="8363f-151">もしユーザーが現時点で Teams の DMG インストールをしていて、パッケージのインストールと置き換えたい場合は、以下を実行してください。</span><span class="sxs-lookup"><span data-stu-id="8363f-151">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="8363f-152">Teams アプリを終了します。</span><span class="sxs-lookup"><span data-stu-id="8363f-152">Exit the Teams app.</span></span>
2. <span data-ttu-id="8363f-153">Teams アプリをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="8363f-153">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="8363f-154">パッケージ ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8363f-154">Install the PKG file.</span></span>

<span data-ttu-id="8363f-155">IT 管理者は、Teams の管理の展開を使用して、Jamf Pro などの組織のすべての Mac にインストール ファイルを配布することができます。</span><span class="sxs-lookup"><span data-stu-id="8363f-155">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="8363f-156">パッケージのインストールで問題が発生した場合は、報告してください。</span><span class="sxs-lookup"><span data-stu-id="8363f-156">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="8363f-157">この記事の最後の**フィードバック**セクションで、**製品のフィードバック**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8363f-157">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="8363f-158">Linux</span><span class="sxs-lookup"><span data-stu-id="8363f-158">Linux</span></span>

<span data-ttu-id="8363f-159">ユーザーは、ネイティブの`.deb` Linux パッケージと`.rpm`形式をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="8363f-159">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span>
<span data-ttu-id="8363f-160">DEB または RPM パッケージをインストールすると、パッケージリポジトリが自動的にインストールされる</span><span class="sxs-lookup"><span data-stu-id="8363f-160">Installing the DEB or RPM package will automatically install the package repository</span></span>
- <span data-ttu-id="8363f-161">DEB`https://packages.microsoft.com/repos/ms-teams stable main`</span><span class="sxs-lookup"><span data-stu-id="8363f-161">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span></span>
- <span data-ttu-id="8363f-162">RPM`https://packages.microsoft.com/yumrepos/ms-teams`</span><span class="sxs-lookup"><span data-stu-id="8363f-162">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span></span> 

<span data-ttu-id="8363f-163">システムのパッケージマネージャーを使用した自動更新を有効にするための署名キーが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8363f-163">The signing key to enable auto-updating using the system's package manager is installed automatically.</span></span> <span data-ttu-id="8363f-164">ただし、は (https://packages.microsoft.com/keys/microsoft.asc)) でも見つかります。</span><span class="sxs-lookup"><span data-stu-id="8363f-164">However, it can also be found at: (https://packages.microsoft.com/keys/microsoft.asc).</span></span> <span data-ttu-id="8363f-165">Microsoft Teams は毎月出荷され、リポジトリが正常にインストールされている場合は、システムパッケージマネージャーがシステム上の他のパッケージと同じ方法で自動更新を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8363f-165">Microsoft Teams ships monthly and if the repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.</span></span>

> [!NOTE] 
> <span data-ttu-id="8363f-166">バグが見つかった場合は、クライアント内`Report a Problem`からそのバグを送信します。</span><span class="sxs-lookup"><span data-stu-id="8363f-166">If you find a bug, submit it using `Report a Problem` from within the client.</span></span> <span data-ttu-id="8363f-167">既知の問題については、「[既知の問題](Known-issues.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8363f-167">For known issues, see [Known Issues](Known-issues.md).</span></span>
> <span data-ttu-id="8363f-168">Linux 向け Teams のサポートについては[、Microsoft Q&A の linux フォーラムサポートチャネル](https://docs.microsoft.com/answers/topics/teams.html)をご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="8363f-168">For Teams for Linux support you can use the [Linux forum support channel on Microsoft Q&A](https://docs.microsoft.com/answers/topics/teams.html).</span></span> <span data-ttu-id="8363f-169">質問を投稿するとき`teams-linux`は必ずタグを使用してください。</span><span class="sxs-lookup"><span data-stu-id="8363f-169">Be sure to use the `teams-linux` tag when posting questions.</span></span> 

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="8363f-170">DEB パッケージを使用して Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="8363f-170">Install Teams using DEB package</span></span>

1. <span data-ttu-id="8363f-171">からhttps://aka.ms/getteamsパッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8363f-171">Download the package from https://aka.ms/getteams.</span></span> <span data-ttu-id="8363f-172">(Linux クライアントは、限定されたプレビューであり、まもなく起動されます。</span><span class="sxs-lookup"><span data-stu-id="8363f-172">(The Linux client is in limited preview and will launch soon.</span></span> <span data-ttu-id="8363f-173">ダウンロードページに Linux クライアントが表示されない場合は、まだ起動していません。)</span><span class="sxs-lookup"><span data-stu-id="8363f-173">If you don't see the Linux client on the downloads page then it has not launched yet.)</span></span>
2. <span data-ttu-id="8363f-174">次のいずれかの方法でインストールします。</span><span class="sxs-lookup"><span data-stu-id="8363f-174">Install using one of the following:</span></span>  
    - <span data-ttu-id="8363f-175">関連するパッケージ管理ツールを開き、自己紹介の Linux アプリのインストールプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="8363f-175">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="8363f-176">または、端末を気に入った場合は、次のように入力します。`sudo apt install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="8363f-176">Or if you love Terminal, type: `sudo apt install **teams download file**`</span></span>

<span data-ttu-id="8363f-177">アクティビティを通じて、または「ターミナルから」 `Teams`と入力して、チームを起動できます。</span><span class="sxs-lookup"><span data-stu-id="8363f-177">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="8363f-178">RPM パッケージを使用してチームをインストールする</span><span class="sxs-lookup"><span data-stu-id="8363f-178">Install Teams using RPM package</span></span>

1. <span data-ttu-id="8363f-179">からhttps://aka.ms/getteamsパッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8363f-179">Download the package from https://aka.ms/getteams.</span></span> <span data-ttu-id="8363f-180">(Linux クライアントは、限定されたプレビューであり、まもなく起動されます。</span><span class="sxs-lookup"><span data-stu-id="8363f-180">(The Linux client is in limited preview and will launch soon.</span></span> <span data-ttu-id="8363f-181">ダウンロードページに Linux クライアントが表示されない場合は、まだ起動していません。)</span><span class="sxs-lookup"><span data-stu-id="8363f-181">If you don't see the Linux client on the downloads page then it has not launched yet.)</span></span>
2. <span data-ttu-id="8363f-182">次のいずれかの方法でインストールします。</span><span class="sxs-lookup"><span data-stu-id="8363f-182">Install using one of the following:</span></span>
    - <span data-ttu-id="8363f-183">関連するパッケージ管理ツールを開き、自己紹介の Linux アプリのインストールプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="8363f-183">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="8363f-184">または、端末を気に入った場合は、次のように入力します。`sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="8363f-184">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="8363f-185">アクティビティを通じて、または「ターミナルから」 `Teams`と入力して、チームを起動できます。</span><span class="sxs-lookup"><span data-stu-id="8363f-185">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span>

## <a name="web-client"></a><span data-ttu-id="8363f-186">Web クライアント</span><span class="sxs-lookup"><span data-stu-id="8363f-186">Web client</span></span> 

<span data-ttu-id="8363f-187">Web クライアント ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) は、さまざまなブラウザーから使用できる、完全な機能クライアントです。</span><span class="sxs-lookup"><span data-stu-id="8363f-187">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="8363f-188">Web クライアントは WebRTC を使用することによって通話と会議をサポートするため、Web ブラウザーで Teams を実行するためのプラグインやダウンロードの必要がありません。</span><span class="sxs-lookup"><span data-stu-id="8363f-188">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="8363f-189">ブラウザーはサードパーティの Cookie を許可するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8363f-189">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="8363f-190">Web クライアントは[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)への接続時にブラウザーのバージョンの検出を実行します。</span><span class="sxs-lookup"><span data-stu-id="8363f-190">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="8363f-191">サポートされていないブラウザー バージョンを検出した場合、Web インターフェイスへのアクセスをブロックし、デスクトップ クライアントまたはモバイル アプリのダウンロードをユーザーに推奨します。</span><span class="sxs-lookup"><span data-stu-id="8363f-191">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="8363f-192">モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="8363f-192">Mobile clients</span></span>

<span data-ttu-id="8363f-193">Microsoft Teams モバイル アプリは Android および iOS で利用可能で、外出先でチャット会話に参加しているユーザーを対象とし、ピア ツー ピアの音声通話を許可します。</span><span class="sxs-lookup"><span data-stu-id="8363f-193">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="8363f-194">モバイル アプリを使用する場合は、Google Play と Apple App Store の関連モバイル ストアに移動します。</span><span class="sxs-lookup"><span data-stu-id="8363f-194">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="8363f-195">Windows Phone App は 2018 年 7 月 20 日に廃止された為、動作しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8363f-195">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="8363f-196">Microsoft Teams モバイル アプリのサポートされるモバイル プラットフォームは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8363f-196">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="8363f-197">**Android**: 5.0 以降</span><span class="sxs-lookup"><span data-stu-id="8363f-197">**Android**: 5.0 or later</span></span>

-   <span data-ttu-id="8363f-198">**iOS**: 10.0 以降</span><span class="sxs-lookup"><span data-stu-id="8363f-198">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="8363f-199">Teams が問題なく動作するためには、モバイル バージョンが利用可能な状態である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8363f-199">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="8363f-200">モバイルアプリは、対応するモバイルプラットフォームのアプリストアのみを通じて配布および更新されます。</span><span class="sxs-lookup"><span data-stu-id="8363f-200">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="8363f-201">MDM またはサイドローディングによるモバイルアプリの配布は、Microsoft によってサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8363f-201">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="8363f-202">サポートされているモバイルプラットフォームにモバイルアプリをインストールすると、そのバージョンが現在のリリースの3か月間に含まれている場合は、Teams モバイルアプリ自体がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8363f-202">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![判断ポイントを示すアイコン](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="8363f-204">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="8363f-204">Decision Point</span></span>         |<span data-ttu-id="8363f-205">ユーザーが適切な Microsoft Teams クライアントをデバイスにインストールすることを妨げる制限事項はありますか?</span><span class="sxs-lookup"><span data-stu-id="8363f-205">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![次の手順を示すアイコン](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="8363f-207">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8363f-207">Next Steps</span></span>         |<span data-ttu-id="8363f-p121">組織によってソフトウェアのインストールが制限されている場合、処理が Microsoft Teams に対応していることを確認してください。注意: 管理者権限は、PC クライアント インストールでは必要ありませんが、Mac へのインストールでは必要になります。</span><span class="sxs-lookup"><span data-stu-id="8363f-p121">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams. Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="8363f-210">クライアントの更新管理</span><span class="sxs-lookup"><span data-stu-id="8363f-210">Client update management</span></span>

<span data-ttu-id="8363f-211">現在、クライアントは、IT 管理者による介入を必要とせずに、Microsoft Teams サービスによって自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="8363f-211">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="8363f-212">更新プログラムが利用可能な場合、クライアントは更新プログラムを自動的にダウンロードします。アプリの有効期限 led が一定期間続いた場合は、更新プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="8363f-212">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="8363f-213">クライアント側の設定</span><span class="sxs-lookup"><span data-stu-id="8363f-213">Client-side configurations</span></span>

<span data-ttu-id="8363f-214">現在、テナント管理者、PowerShell、グループ ポリシー オブジェクトまたはレジストリのいずれかを介してクライアントを設定するオプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8363f-214">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="8363f-215">通知の設定</span><span class="sxs-lookup"><span data-stu-id="8363f-215">Notification settings</span></span>

<span data-ttu-id="8363f-p123">現在、IT 管理者がクライアント側の通知設定を設定するオプションはありません。通知オプションはすべてユーザーによって設定されます。次の図に、既定のクライアント設定の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="8363f-p123">There are currently no options available for IT administrators to configure client-side notification settings. All notification options are set by the user. The figure below outlines the default client settings.</span></span>

![通知設定のスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script"></a><span data-ttu-id="8363f-220">PowerShell のサンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="8363f-220">Sample PowerShell Script</span></span>

<span data-ttu-id="8363f-221">このサンプル スクリプトは、管理者アカウントのコンテキスト内のクライアント コンピューターで実行する必要があり、c:\users にある各ユーザーのフォルダーの新しい受信ファイアウォール ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="8363f-221">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="8363f-222">Teams がこのルールを検出すると、ユーザーが Teams からの最初の呼び出しを行うときに、ファイアウォール ルールを作成する為の Teams アプリケーションからユーザーへの指示ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="8363f-222">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

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
