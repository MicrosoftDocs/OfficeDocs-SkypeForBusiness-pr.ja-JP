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
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で利用できる Web、デスクトップ (Windows、Mac)、およびモバイル (Android、iOS) などのさまざまなクライアントを使用する方法を知る。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 47341662267a3da0a83174cbccb2b2cd251538b6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245754"
---
<a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="6ca1d-103">Microsoft Teams のクライアントを取得する</span><span class="sxs-lookup"><span data-stu-id="6ca1d-103">Get clients for Microsoft Teams</span></span> 
===========================

<span data-ttu-id="6ca1d-p101">Microsoft Teams には、Web、デスクトップ (Windows、Mac)、およびモバイル (Android、iOS) で利用できるクライアントがあります。これらのクライアントはすべてインターネット接続が必要で、オフライン モードをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-p101">Microsoft Teams has clients available for desktop (Windows and Mac), web, and mobile (Android and  iOS). These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="6ca1d-106">2018 年 11 月 29 日付で、Microsoft Store から入手可能な Microsoft Teams の Windows 10 S (プレビュー) アプリが使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="6ca1d-107">代わりに、Windows 10 S モードを実行しているデバイスに Teams デスクトップクライアントをダウンロードしてインストールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-107">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="6ca1d-108">デスクトップクライアントをダウンロードするには、 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-108">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="6ca1d-109">Teams デスクトップクライアントの MSI ビルドは、Windows 10 S モードを実行しているデバイスではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-109">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="6ca1d-110">Windows 10 S モードの詳細については、「 [windows 10 を S モードで導入](https://www.microsoft.com/windows/s-mode)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-110">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

<a name="desktop-client"></a><span data-ttu-id="6ca1d-111">デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="6ca1d-111">Desktop client</span></span>
--------------

> [!Tip]
> <span data-ttu-id="6ca1d-112">Windows Desktop Clientの効果、計画や展開の方法については次のセッションを参照してください。[Teams Windows Desktop Client](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="6ca1d-112">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="6ca1d-113">Microsoft Teams デスクトップクライアントは、スタンドアロンアプリケーションであり、 [Office 365 ProPlus でも利用でき](https://docs.microsoft.com/en-us/deployoffice/teams-install)ます。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-113">The Microsoft Teams desktop client is a standalone application and is also [available in Office 365 ProPlus](https://docs.microsoft.com/en-us/deployoffice/teams-install).</span></span> <span data-ttu-id="6ca1d-114">Microsoft Teams は、Windows (7 以上) の32 ビット、 64 ビット バージョン、および macOS (10.10 以上) で利用できます。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-114">Teams is available for both Windows (7+), both 32-bit and 64-bit versions, and macOS (10.10+).</span></span> <span data-ttu-id="6ca1d-115">Windows で Teams を使用するには .NET Framework 4.5 以降が必要です。.NET Framework 4.5 以降がない場合は、Teams のインストーラーでインストールすることを勧めます。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-115">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> 

<span data-ttu-id="6ca1d-116">デスクトップ クライアントは、チーム会議、グループ通話、およびプライベートな 1 対 1 での通話に対応するリアルタイム通信のサポート (オーディオ、ビデオ、およびコンテンツ共有) を提供します。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-116">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="6ca1d-117">デスクトップ クライアントは、適切なローカルのアクセス許可を持っているエンド ユーザーによって、[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) から直接ダウンロードおよびインストールできます (管理者権限は、Teams クライアントを PC にインストールする場合には必要ありませんが、Mac では必要になります) 。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-117">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="6ca1d-118">IT 管理者は好きな方法で、System Center Configuration Manager (Windows)、または Jamf Pro (macOS) などのインストール ファイルを組織のコンピューターに配布できます。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-118">IT admins can choose their preferred method to distribute the installation files to computers in their organization, such as System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="6ca1d-119">Windows ディストリビューションの MSI パッケージを取得するには、[MSI を使用して Microsoft Teams をインストールする](msi-deployment.md)を参照ください。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-119">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="6ca1d-120">これらのメカニズムによるクライアントの配布は、Microsoft Teams クライアントの初回インストール時にのみ利用でき、それ以降の更新では利用できません。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-120">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="6ca1d-121">Windows</span><span class="sxs-lookup"><span data-stu-id="6ca1d-121">Windows</span></span>

<span data-ttu-id="6ca1d-122">Windows での Microsoft Teams のインストールでは、32 ビットと 64 ビット アーキテクチャでダウンロード可能なインストーラーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-122">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="6ca1d-123">Microsoft Teams のアーキテクチャ (32 ビットと 64 ビット) はインストールされている Windows および Office のアーキテクチャに依存しません。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-123">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="6ca1d-124">Windows クライアントは、ユーザーのプロファイルの AppData フォルダーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-124">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="6ca1d-125">ユーザーのローカル プロファイルへの展開で、権限を必要とせずクライアントをインストールする事ができます。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-125">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="6ca1d-126">Windows クライアントは、次の場所を利用します。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-126">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="6ca1d-127">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="6ca1d-127">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="6ca1d-128">%LocalAppData%\\Microsoft\\TeamsMeetingsAddin</span><span class="sxs-lookup"><span data-stu-id="6ca1d-128">%LocalAppData%\\Microsoft\\TeamsMeetingsAddin</span></span>

- <span data-ttu-id="6ca1d-129">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="6ca1d-129">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="6ca1d-130">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="6ca1d-130">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="6ca1d-131">ユーザーが Microsoft Teams クライアントを使用して初めて通話を開始する時は、ユーザーに通信の許可を求める Windows ファイアウォール設定の警告が通知される場合があります。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-131">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="6ca1d-132">警告を受け入れなくても通話は機能するため、このメッセージを無視するように指示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-132">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![[Windows セキュリティの重要な警告] ダイアログのスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="6ca1d-p107">Windows ファイアウォール設定は、[キャンセル] の選択によりプロンプトが受け入れられなかった場合でも変更されます。TCP および UDP プロトコルの両方に関するブロック アクションで、teams.exe に関する2 つの着信ルールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-p107">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”. Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="6ca1d-136">Mac</span><span class="sxs-lookup"><span data-stu-id="6ca1d-136">Mac</span></span>

<span data-ttu-id="6ca1d-137">Mac ユーザーは、macOS コンピューターのパッケージ インストール ファイルを使用して、Teams をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-137">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="6ca1d-138">Mac クライアントをインストールするには、管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-138">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="6ca1d-139">macOS クライアントは /Applications フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-139">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="6ca1d-140">パッケージ ファイルを使用して Teams をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-140">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="6ca1d-141">[Teams のダウンロード ページ](https://teams.microsoft.com/downloads)の、**Mac**で、**Download**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-141">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="6ca1d-142">パッケージ ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-142">Double click the PKG file.</span></span>
3. <span data-ttu-id="6ca1d-143">インストール ウィザードに従ってインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-143">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="6ca1d-144">Teams は、/Applications フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-144">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="6ca1d-145">これはコンピューター全体のインストールです。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-145">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="6ca1d-146">インストール時に、パッケージが管理者認証情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-146">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="6ca1d-147">ユーザーは、管理者であるかどうかに関係なく、管理者認証情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-147">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="6ca1d-148">もしユーザーが現時点で Teams の DMG インストールをしていて、パッケージのインストールと置き換えたい場合は、以下を実行してください。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-148">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="6ca1d-149">Teams アプリを終了します。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-149">Exit the Teams app.</span></span>
2. <span data-ttu-id="6ca1d-150">Teams アプリをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-150">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="6ca1d-151">パッケージ ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-151">Install the PKG file.</span></span>

<span data-ttu-id="6ca1d-152">IT 管理者は、Teams の管理の展開を使用して、Jamf Pro などの組織のすべての Mac にインストール ファイルを配布することができます。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-152">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="6ca1d-153">パッケージのインストールで問題が発生した場合は、報告してください。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-153">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="6ca1d-154">この記事の最後の**フィードバック**セクションで、**製品のフィードバック**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-154">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

<a name="web-client"></a><span data-ttu-id="6ca1d-155">Web クライアント</span><span class="sxs-lookup"><span data-stu-id="6ca1d-155">Web client</span></span> 
----------

<span data-ttu-id="6ca1d-156">Web クライアント ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) は、さまざまなブラウザーから使用できる、完全な機能クライアントです。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-156">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="6ca1d-157">Web クライアントは WebRTC を使用することによって通話と会議をサポートするため、Web ブラウザーで Teams を実行するためのプラグインやダウンロードの必要がありません。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-157">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="6ca1d-158">ブラウザーはサードパーティの Cookie を許可するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-158">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="6ca1d-159">Web クライアントは[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)への接続時にブラウザーのバージョンの検出を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-159">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="6ca1d-160">サポートされていないブラウザー バージョンを検出した場合、Web インターフェイスへのアクセスをブロックし、デスクトップ クライアントまたはモバイル アプリのダウンロードをユーザーに推奨します。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-160">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

<a name="mobile-clients"></a><span data-ttu-id="6ca1d-161">モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="6ca1d-161">Mobile clients</span></span>
--------------

<span data-ttu-id="6ca1d-162">Microsoft Teams モバイル アプリは Android および iOS で利用可能で、外出先でチャット会話に参加しているユーザーを対象とし、ピア ツー ピアの音声通話を許可します。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-162">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="6ca1d-163">モバイル アプリを使用する場合は、Google Play と Apple App Store の関連モバイル ストアに移動します。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-163">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="6ca1d-164">Windows Phone App は 2018 年 7 月 20 日に廃止された為、動作しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-164">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="6ca1d-165">Microsoft Teams モバイル アプリのサポートされるモバイル プラットフォームは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-165">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="6ca1d-166">**Android**: 4.4 以降</span><span class="sxs-lookup"><span data-stu-id="6ca1d-166">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="6ca1d-167">**iOS**: 10.0 以降</span><span class="sxs-lookup"><span data-stu-id="6ca1d-167">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="6ca1d-168">Teams が問題なく動作するためには、モバイル バージョンが利用可能な状態である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-168">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="6ca1d-169">モバイル アプリはそれぞれのモバイル プラットフォームのアプリ ストアからのみ配布および更新され、MDM (モバイル デバイス管理) ソリューションまたはサイド ロードからは配布することはできません。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-169">Mobile apps are distributed and updated through the respective mobile platform’s app store only, and are not available to be distributed through MDM (mobile device management) solutions or side-loaded.</span></span>


| | | |
|---------|---------|---------|
|![判断ポイントを示すアイコン](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="6ca1d-171">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="6ca1d-171">Decision Point</span></span>         |<span data-ttu-id="6ca1d-172">ユーザーが適切な Microsoft Teams クライアントをデバイスにインストールすることを妨げる制限事項はありますか?</span><span class="sxs-lookup"><span data-stu-id="6ca1d-172">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![次の手順を示すアイコン](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="6ca1d-174">次のステップ</span><span class="sxs-lookup"><span data-stu-id="6ca1d-174">Next Steps</span></span>         |<span data-ttu-id="6ca1d-p115">組織によってソフトウェアのインストールが制限されている場合、処理が Microsoft Teams に対応していることを確認してください。注意: 管理者権限は、PC クライアント インストールでは必要ありませんが、Mac へのインストールでは必要になります。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-p115">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams. Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

<a name="client-update-management"></a><span data-ttu-id="6ca1d-177">クライアントの更新管理</span><span class="sxs-lookup"><span data-stu-id="6ca1d-177">Client update management</span></span>
------------------------

<span data-ttu-id="6ca1d-178">現在、クライアントは、IT 管理者による介入を必要とせずに、Microsoft Teams サービスによって自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-178">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="6ca1d-179">更新プログラムが利用可能な場合、クライアントは更新プログラムを自動的にダウンロードします。アプリの有効期限 led が一定期間続いた場合は、更新プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-179">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

<a name="client-side-configurations"></a><span data-ttu-id="6ca1d-180">クライアント側の設定</span><span class="sxs-lookup"><span data-stu-id="6ca1d-180">Client-side configurations</span></span>
---------------------------

<span data-ttu-id="6ca1d-181">現在、テナント管理者、PowerShell、グループ ポリシー オブジェクトまたはレジストリのいずれかを介してクライアントを設定するオプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-181">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

<a name="notification-settings"></a><span data-ttu-id="6ca1d-182">通知の設定</span><span class="sxs-lookup"><span data-stu-id="6ca1d-182">Notification settings</span></span>
----------------------------

<span data-ttu-id="6ca1d-p117">現在、IT 管理者がクライアント側の通知設定を設定するオプションはありません。通知オプションはすべてユーザーによって設定されます。次の図に、既定のクライアント設定の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-p117">There are currently no options available for IT administrators to configure client-side notification settings. All notification options are set by the user. The figure below outlines the default client settings.</span></span>

![通知設定のスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image6.png)

<a name="sample-powershell-script"></a><span data-ttu-id="6ca1d-187">PowerShell のサンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="6ca1d-187">Sample PowerShell Script</span></span>
----------------------------

<span data-ttu-id="6ca1d-188">このサンプル スクリプトは、管理者アカウントのコンテキスト内のクライアント コンピューターで実行する必要があり、c:\users にある各ユーザーのフォルダーの新しい受信ファイアウォール ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-188">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="6ca1d-189">Teams がこのルールを検出すると、ユーザーが Teams からの最初の呼び出しを行うときに、ファイアウォール ルールを作成する為の Teams アプリケーションからユーザーへの指示ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="6ca1d-189">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

```

<#
.Synopsis
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($users.Length -gt 0)
{
    foreach ($user in $users)
    {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath)
        {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue))
            {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
