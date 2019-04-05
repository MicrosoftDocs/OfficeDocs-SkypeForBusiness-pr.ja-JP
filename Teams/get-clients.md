---
title: Microsoft Teams のクライアントを取得する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
MS.collection:
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
ms.openlocfilehash: 43344ac9ea00c15bcb4fb7518d727ccc9cff92de
ms.sourcegitcommit: 5b33cfc828906917f76b0d2a9ae402c9336388a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30934716"
---
<a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="c679d-103">Microsoft Teams のクライアントを取得する</span><span class="sxs-lookup"><span data-stu-id="c679d-103">Get clients for Microsoft Teams</span></span> 
===========================

<span data-ttu-id="c679d-p101">Microsoft Teams には、Web、デスクトップ (Windows、Mac)、およびモバイル (Android、iOS) で利用できるクライアントがあります。これらのクライアントはすべてインターネット接続が必要で、オフライン モードをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c679d-p101">Microsoft Teams has clients available for web, desktop (Windows and Mac), and mobile (Android, iOS, and Windows Phone). These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="c679d-106">2018 年 11 月 29 日付で、Microsoft Store から入手可能な Microsoft Teams の Windows 10 S (プレビュー) アプリが使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c679d-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="c679d-107">11 月 29 日 以降は、この記事で後述するTeams アプリを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c679d-107">We recommend that you use one of the Teams apps described below in this article after November 29.</span></span>

<a name="desktop-client"></a><span data-ttu-id="c679d-108">デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="c679d-108">Desktop client</span></span>
--------------

> [!Tip]
> <span data-ttu-id="c679d-109">Windows Desktop Clientの効果、計画や展開の方法については次のセッションを参照してください。[Teams Windows Desktop Client](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="c679d-109">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="c679d-110">Microsoft Teams デスクトップ クライアントはスタンドアロン アプリケーションであり、現在は Office 365 Pro Plus の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="c679d-110">The Microsoft Teams desktop client is a standalone application and currently not part of Office Pro Plus.</span></span> <span data-ttu-id="c679d-111">Microsoft Teams は、Windows (7 以上) の32 ビット、 64 ビット バージョン、および macOS (10.10 以上) で利用できます。</span><span class="sxs-lookup"><span data-stu-id="c679d-111">Teams is available for both Windows (7+), both 32-bit and 64-bit versions, and MacOS (10.10+).</span></span> <span data-ttu-id="c679d-112">Windows で Teams を使用するには .NET Framework 4.5 以降が必要です。.NET Framework 4.5 以降がない場合は、Teams のインストーラーでインストールすることを勧めます。</span><span class="sxs-lookup"><span data-stu-id="c679d-112">On Windows, Teams requires .NET framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> 

<span data-ttu-id="c679d-113">デスクトップ クライアントは、チーム会議、グループ通話、およびプライベートな 1 対 1 での通話に対応するリアルタイム通信のサポート (オーディオ、ビデオ、およびコンテンツ共有) を提供します。</span><span class="sxs-lookup"><span data-stu-id="c679d-113">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="c679d-114">デスクトップ クライアントは、適切なローカルのアクセス許可を持っているエンド ユーザーによって、[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) から直接ダウンロードおよびインストールできます (管理者権限は、Teams クライアントを PC にインストールする場合には必要ありませんが、Mac では必要になります) 。</span><span class="sxs-lookup"><span data-stu-id="c679d-114">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="c679d-115">IT 管理者は好きな方法で、System Center Configuration Manager (Windows)、または Jamf Pro (macOS) などのインストール ファイルを組織のコンピューターに配布できます。</span><span class="sxs-lookup"><span data-stu-id="c679d-115">IT admins can choose their preferred method to distribute the installation files to machines in their organization such as System Center Configuration Manager (Windows) or Casper Suite (MacOS).</span></span> <span data-ttu-id="c679d-116">Windows ディストリビューションの MSI パッケージを取得するには、[MSI を使用して Microsoft Teams をインストールする](msi-deployment.md)を参照ください。</span><span class="sxs-lookup"><span data-stu-id="c679d-116">To get the MSI Package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c679d-117">これらのメカニズムによるクライアントの配布は、Microsoft Teams クライアントの初回インストール時にのみ利用でき、それ以降の更新では利用できません。</span><span class="sxs-lookup"><span data-stu-id="c679d-117">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="c679d-118">Windows</span><span class="sxs-lookup"><span data-stu-id="c679d-118">Windows</span></span>

<span data-ttu-id="c679d-119">Windows での Microsoft Teams のインストールでは、32 ビットと 64 ビット アーキテクチャでダウンロード可能なインストーラーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c679d-119">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture. The architecture should match that of the OS, which is what the online download defaults to.</span></span>

> [!NOTE]
> <span data-ttu-id="c679d-120">Microsoft Teams のアーキテクチャ (32 ビットと 64 ビット) はインストールされている Windows および Office のアーキテクチャに依存しません。</span><span class="sxs-lookup"><span data-stu-id="c679d-120">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Office that is installed.</span></span>

<span data-ttu-id="c679d-121">Windows クライアントは、ユーザーのプロファイルの AppData フォルダーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="c679d-121">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="c679d-122">ユーザーのローカル プロファイルへの展開で、権限を必要とせずクライアントをインストールする事ができます。</span><span class="sxs-lookup"><span data-stu-id="c679d-122">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="c679d-123">Windows クライアントは、次の場所を利用します。</span><span class="sxs-lookup"><span data-stu-id="c679d-123">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="c679d-124">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="c679d-124">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="c679d-125">%LocalAppData%\\Microsoft\\TeamsMeetingsAddin</span><span class="sxs-lookup"><span data-stu-id="c679d-125">%LocalAppData%\\Microsoft\\TeamsMeetingsAddin</span></span>

- <span data-ttu-id="c679d-126">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="c679d-126">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="c679d-127">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="c679d-127">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="c679d-128">ユーザーが Microsoft Teams クライアントを使用して初めて通話を開始する時は、ユーザーに通信の許可を求める Windows ファイアウォール設定の警告が通知される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c679d-128">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication. Users may be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span> <span data-ttu-id="c679d-129">警告を受け入れなくても通話は機能するため、このメッセージを無視するように指示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c679d-129">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![[Windows セキュリティの重要な警告] ダイアログのスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="c679d-p107">Windows ファイアウォール設定は、[キャンセル] の選択によりプロンプトが受け入れられなかった場合でも変更されます。TCP および UDP プロトコルの両方に関するブロック アクションで、teams.exe に関する2 つの着信ルールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c679d-p107">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”. Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="c679d-133">Mac</span><span class="sxs-lookup"><span data-stu-id="c679d-133">Mac</span></span>

<span data-ttu-id="c679d-134">Mac ユーザーは、macOs コンピューターのパッケージ インストール ファイルを使用して、Teams をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c679d-134">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="c679d-135">Mac クライアントをインストールするには、管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="c679d-135">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="c679d-136">macOS クライアントは Applications フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c679d-136">The Mac OSX client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="c679d-137">パッケージ ファイルを使用して Teams をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c679d-137">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="c679d-138">[Teams のダウンロード ページ](https://teams.microsoft.com/downloads)の、**Mac**、クリックして **Download**します。</span><span class="sxs-lookup"><span data-stu-id="c679d-138">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="c679d-139">パッケージ ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c679d-139">Double click the PKG file.</span></span>
3. <span data-ttu-id="c679d-140">インストール ウィザードに従ってインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="c679d-140">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="c679d-141">Teams は、/Applications フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c679d-141">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="c679d-142">これはコンピューター全体のインストールです。</span><span class="sxs-lookup"><span data-stu-id="c679d-142">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="c679d-143">インストール時に、パッケージが管理者認証情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="c679d-143">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="c679d-144">ユーザーは、管理者であるかどうかに関係なく、管理者認証情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c679d-144">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="c679d-145">もしユーザーが現時点で Teams の DMG インストールをしていて、パッケージのインストールと置き換えたい場合は、以下を実行してください。</span><span class="sxs-lookup"><span data-stu-id="c679d-145">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="c679d-146">Teams アプリを終了します。</span><span class="sxs-lookup"><span data-stu-id="c679d-146">Exit the Teams app.</span></span>
2. <span data-ttu-id="c679d-147">Teams アプリをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="c679d-147">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="c679d-148">パッケージ ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c679d-148">Install the PKG file.</span></span>

<span data-ttu-id="c679d-149">IT 管理者は、Teams の管理の展開を使用して、Jamf Pro などの組織のすべての Mac にインストール ファイルを配布することができます。</span><span class="sxs-lookup"><span data-stu-id="c679d-149">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="c679d-150">パッケージのインストールで問題が発生した場合は、報告してください。</span><span class="sxs-lookup"><span data-stu-id="c679d-150">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="c679d-151">**フィードバック**のこの記事の最後のセクションで、**製品のフィードバック**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c679d-151">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

<a name="web-client"></a><span data-ttu-id="c679d-152">Web クライアント</span><span class="sxs-lookup"><span data-stu-id="c679d-152">Web client</span></span> 
----------

<span data-ttu-id="c679d-153">Web クライアント ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) は、さまざまなブラウザーから使用できる、完全な機能クライアントです。</span><span class="sxs-lookup"><span data-stu-id="c679d-153">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="c679d-154">Web クライアントは WebRTC を使用することによって通話と会議をサポートするため、Web ブラウザーで Teams を実行するためのプラグインやダウンロードの必要がありません。</span><span class="sxs-lookup"><span data-stu-id="c679d-154">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="c679d-155">ブラウザーはサードパーティの Cookie を許可するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c679d-155">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="c679d-156">Web クライアントは[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)への接続時にブラウザーのバージョンの検出を実行します。</span><span class="sxs-lookup"><span data-stu-id="c679d-156">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="c679d-157">サポートされていないブラウザー バージョンを検出した場合、Web インターフェイスへのアクセスをブロックし、デスクトップ クライアントまたはモバイル アプリのダウンロードをユーザーに推奨します。</span><span class="sxs-lookup"><span data-stu-id="c679d-157">The web client performs browser version detection upon connecting to  and if an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

<a name="mobile-clients"></a><span data-ttu-id="c679d-158">モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="c679d-158">Mobile clients</span></span>
--------------

<span data-ttu-id="c679d-159">Microsoft Teams モバイル アプリは Android および iOS で利用可能で、外出先でチャット会話に参加しているユーザーを対象とし、ピア ツー ピアの音声通話を許可します。</span><span class="sxs-lookup"><span data-stu-id="c679d-159">The Microsoft Teams mobile apps are available for Android, iOS, and Windows Phones, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls. For mobile apps, go to the relevant mobile store for Google Play, Apple App Store, and Microsoft Store.</span></span> <span data-ttu-id="c679d-160">モバイル アプリを使用する場合は、Google Play と Apple App Store の関連モバイル ストアに移動します。</span><span class="sxs-lookup"><span data-stu-id="c679d-160">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="c679d-161">Windows Phone App は 2018 年 7 月 20 日に廃止された為、動作しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c679d-161">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="c679d-162">Microsoft Teams モバイル アプリのサポートされるモバイル プラットフォームは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c679d-162">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="c679d-163">**Android**: 4.4 以降</span><span class="sxs-lookup"><span data-stu-id="c679d-163">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="c679d-164">**iOS**: 10.0 以降</span><span class="sxs-lookup"><span data-stu-id="c679d-164">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="c679d-165">Teams が問題なく動作するためには、モバイル バージョンが利用可能な状態である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c679d-165">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="c679d-166">モバイル アプリはそれぞれのモバイル プラットフォームのアプリ ストアからのみ配布および更新され、MDM (モバイル デバイス管理) ソリューションまたはサイド ロードからは配布することはできません。</span><span class="sxs-lookup"><span data-stu-id="c679d-166">Mobile apps are distributed and updated through the respective mobile platform’s app store only, and are not available to be distributed through MDM (mobile device management) solutions or side-loaded.</span></span>


| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="c679d-168">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="c679d-168">Decision Point</span></span>         |<span data-ttu-id="c679d-169">ユーザーが適切な Microsoft Teams クライアントをデバイスにインストールすることを妨げる制限事項はありますか?</span><span class="sxs-lookup"><span data-stu-id="c679d-169">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![次のステップ アイコン。](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="c679d-171">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c679d-171">Next Steps</span></span>         |<span data-ttu-id="c679d-p115">組織によってソフトウェアのインストールが制限されている場合、処理が Microsoft Teams に対応していることを確認してください。注意: 管理者権限は、PC クライアント インストールでは必要ありませんが、Mac へのインストールでは必要になります。</span><span class="sxs-lookup"><span data-stu-id="c679d-p115">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams. Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

<a name="client-update-management"></a><span data-ttu-id="c679d-174">クライアントの更新管理</span><span class="sxs-lookup"><span data-stu-id="c679d-174">Client update management</span></span>
------------------------

<span data-ttu-id="c679d-p116">クライアントは現在、IT 管理者の介入を必要とせずに Microsoft Teams サービスによって自動的に更新されています。利用可能な更新がある場合、クライアントは自動的にその更新をダウンロードします。アプリが一定時間アイドル状態となった場合には更新処理が開始されます。</span><span class="sxs-lookup"><span data-stu-id="c679d-p116">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required. If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will kick off.</span></span>

<a name="client-side-configurations"></a><span data-ttu-id="c679d-177">クライアント側の設定</span><span class="sxs-lookup"><span data-stu-id="c679d-177">Client-side configurations</span></span>
---------------------------

<span data-ttu-id="c679d-178">現在、テナント管理者、PowerShell、グループ ポリシー オブジェクトまたはレジストリのいずれかを介してクライアントを設定するオプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c679d-178">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

<a name="notification-settings"></a><span data-ttu-id="c679d-179">通知の設定</span><span class="sxs-lookup"><span data-stu-id="c679d-179">Notification settings</span></span>
----------------------------

<span data-ttu-id="c679d-p117">現在、IT 管理者がクライアント側の通知設定を設定するオプションはありません。通知オプションはすべてユーザーによって設定されます。次の図に、既定のクライアント設定の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="c679d-p117">There are currently no options available for IT administrators to configure client-side notification settings. All notification options are set by the user. The figure below outlines the default client settings.</span></span>

![通知設定のスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image6.png)

<a name="sample-powershell-script"></a><span data-ttu-id="c679d-184">PowerShell のサンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="c679d-184">Sample PowerShell Script</span></span>
----------------------------

<span data-ttu-id="c679d-185">このサンプル スクリプトは、管理者アカウントのコンテキスト内のクライアント コンピューターで実行する必要があり、c:\users にある各ユーザーのフォルダーの新しい受信ファイアウォール ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c679d-185">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="c679d-186">Teams がこのルールを検出すると、ユーザーが Teams からの最初の呼び出しを行うときに、ファイアウォール ルールを作成する為の Teams アプリケーションからユーザーへの指示ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="c679d-186">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

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
