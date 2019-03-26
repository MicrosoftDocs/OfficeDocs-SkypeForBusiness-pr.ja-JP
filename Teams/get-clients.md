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
description: Web、デスクトップ (Windows および Mac) は、モバイルなど、マイクロソフトのチームの利用可能なさまざまなクライアントを使用する方法について説明 (Android と iOS) です。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32fba747deb73b7f4e2c19b96cb4c0c62b741722
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458909"
---
<a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="a3079-103">Microsoft Teams のクライアントを取得する</span><span class="sxs-lookup"><span data-stu-id="a3079-103">Get clients for Microsoft Teams</span></span> 
===========================

<span data-ttu-id="a3079-104">マイクロソフトのチームには、クライアントのデスクトップ (Windows および Mac) は、web、およびモバイル (Android と iOS) があります。</span><span class="sxs-lookup"><span data-stu-id="a3079-104">Microsoft Teams has clients available for desktop (Windows and Mac), web, and mobile (Android and  iOS).</span></span> <span data-ttu-id="a3079-105">これらのクライアントはすべてアクティブなインターネット接続が必要で、オフライン モードをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a3079-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="a3079-106">2018 年 11 月 29日効果的な不要になったことができます Windows 10 S (プレビュー) アプリケーションでは、Microsoft ストアから利用可能なため、マイクロソフトのチームを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3079-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="a3079-107">11 月 29 日後、この資料で後述のチームのアプリケーションのいずれかを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3079-107">We recommend that you use one of the Teams apps described below in this article after November 29.</span></span>

<a name="desktop-client"></a><span data-ttu-id="a3079-108">デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="a3079-108">Desktop client</span></span>
--------------

> [!Tip]
> <span data-ttu-id="a3079-109">クライアント、それを計画する方法および配置方法は、Windows デスクトップの利点について説明するのには次のセッションを監視する:[チームの Windows デスクトップ クライアント](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="a3079-109">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="a3079-110">マイクロソフト チームのデスクトップ クライアントは、スタンドアロン アプリケーションと現在の Office 365 用リソースの一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="a3079-110">The Microsoft Teams desktop client is a standalone application and currently not part of Office 365 ProPlus.</span></span> <span data-ttu-id="a3079-111">チームは、Windows (7 +)、32 ビットと 64 ビットの両方のバージョンと macOS (10.10 +) の両方に使用できます。</span><span class="sxs-lookup"><span data-stu-id="a3079-111">Teams is available for both Windows (7+), both 32-bit and 64-bit versions, and macOS (10.10+).</span></span> <span data-ttu-id="a3079-112">Windows では、4.5 以降の.NET Framework チームする必要があります。チームのインストーラーは、インストールすることがない場合に提供されます。</span><span class="sxs-lookup"><span data-stu-id="a3079-112">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> 

<span data-ttu-id="a3079-113">デスクトップ クライアントは、チーム会議、グループ通話、およびプライベートな 1 対 1 での通話に対応するリアルタイム通信のサポート (オーディオ、ビデオ、およびコンテンツ共有) を提供します。</span><span class="sxs-lookup"><span data-stu-id="a3079-113">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="a3079-114">デスクトップ クライアントは、適切なローカルのアクセス許可を持っているエンド ユーザーによって、[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) から直接ダウンロードおよびインストールできます (管理者権限は、Teams クライアントを PC にインストールする場合には必要ありませんが、Mac では必要になります) 。</span><span class="sxs-lookup"><span data-stu-id="a3079-114">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="a3079-115">IT 管理者は、システム センター構成マネージャー (Windows) または Jamf Pro (macOS) など、組織内のコンピューターにインストール ファイルを配布するが推奨される方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="a3079-115">IT admins can choose their preferred method to distribute the installation files to computers in their organization, such as System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="a3079-116">Windows ディストリビューションの MSI パッケージを取得するには、[マイクロソフト チームのインストールは、MSI を使用して](msi-deployment.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3079-116">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a3079-117">これらのメカニズムによるクライアントの配布は、Microsoft Teams クライアントの初回インストール時にのみ利用でき、それ以降の更新では利用できません。</span><span class="sxs-lookup"><span data-stu-id="a3079-117">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="a3079-118">Windows</span><span class="sxs-lookup"><span data-stu-id="a3079-118">Windows</span></span>

<span data-ttu-id="a3079-119">Windows のマイクロソフトのチームのインストールには、32 ビットおよび 64 ビット アーキテクチャでは、ダウンロード可能なインストーラーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="a3079-119">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="a3079-120">マイクロソフト チームのアーキテクチャ (32 ビットと 64 ビット) は、Windows とインストールされている Office のアーキテクチャに依存しません。</span><span class="sxs-lookup"><span data-stu-id="a3079-120">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="a3079-121">Windows クライアントは、ユーザーのプロファイル内にある AppData フォルダーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="a3079-121">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="a3079-122">ユーザーのローカル プロファイルを展開すると、昇格された権限を必要とせずにインストールされるようにクライアントが使用できます。</span><span class="sxs-lookup"><span data-stu-id="a3079-122">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="a3079-123">Windows クライアントは、次の場所を活用します。</span><span class="sxs-lookup"><span data-stu-id="a3079-123">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="a3079-124">%Localappdata%\\Microsoft\\チーム</span><span class="sxs-lookup"><span data-stu-id="a3079-124">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="a3079-125">%Localappdata%\\Microsoft\\TeamsMeetingsAddin</span><span class="sxs-lookup"><span data-stu-id="a3079-125">%LocalAppData%\\Microsoft\\TeamsMeetingsAddin</span></span>

- <span data-ttu-id="a3079-126">%Appdata%\\Microsoft\\チーム</span><span class="sxs-lookup"><span data-stu-id="a3079-126">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="a3079-127">%Localappdata\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="a3079-127">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="a3079-128">ユーザーは、最初にマイクロソフトのチームのクライアントを使用して呼び出しを開始するとき、Windows ファイアウォールの設定で通信を許可するユーザーの入力を求める警告がわかります。</span><span class="sxs-lookup"><span data-stu-id="a3079-128">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="a3079-129">呼び出し機能しますが、警告を終了したときにもあるために、このメッセージを無視するようにユーザーを指示することがあります。</span><span class="sxs-lookup"><span data-stu-id="a3079-129">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![[Windows セキュリティの重要な警告] ダイアログのスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="a3079-p107">Windows ファイアウォール設定は、[キャンセル] の選択によりプロンプトが受け入れられなかった場合でも変更されます。TCP および UDP プロトコルの両方に関するブロック アクションで、teams.exe に関する2 つの着信ルールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a3079-p107">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”. Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="a3079-133">Mac</span><span class="sxs-lookup"><span data-stu-id="a3079-133">Mac</span></span>

<span data-ttu-id="a3079-134">Mac ユーザーは、macOS のコンピューターでパッケージのインストール ファイルを使用してチームをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="a3079-134">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="a3079-135">Mac クライアントをインストールするには管理アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="a3079-135">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="a3079-136">/Applications フォルダーには、macOS クライアントがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="a3079-136">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="a3079-137">PKG ファイルを使用してチームをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a3079-137">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="a3079-138">[チームがページをダウンロード](https://teams.microsoft.com/downloads)するから**Mac**では、下の [**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3079-138">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="a3079-139">PKG ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3079-139">Double click the PKG file.</span></span>
3. <span data-ttu-id="a3079-140">インストールを完了するのにはインストール ウィザードに従います。</span><span class="sxs-lookup"><span data-stu-id="a3079-140">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="a3079-141">チームは、/Applications フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a3079-141">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="a3079-142">コンピューター全体にインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3079-142">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="a3079-143">、インストール中に、PKG は、管理者の資格情報を求められます。</span><span class="sxs-lookup"><span data-stu-id="a3079-143">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="a3079-144">ユーザーは、ユーザーが管理者かどうかに関係なく、管理者の資格情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3079-144">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="a3079-145">ユーザー現在チームの攻撃力のインストールには、パッケージのインストールを交換したい場合、ユーザーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3079-145">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="a3079-146">チームのアプリケーションを終了します。</span><span class="sxs-lookup"><span data-stu-id="a3079-146">Exit the Teams app.</span></span>
2. <span data-ttu-id="a3079-147">チームのアプリケーションをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a3079-147">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="a3079-148">PKG ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a3079-148">Install the PKG file.</span></span>

<span data-ttu-id="a3079-149">IT 管理者は、Jamf Pro など、組織内のすべての Mac にインストール ファイルを配布するのには、チームの管理された展開を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a3079-149">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="a3079-150">パッケージのインストールで問題が発生する場合お知らせします。</span><span class="sxs-lookup"><span data-stu-id="a3079-150">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="a3079-151">この資料の最後にある [**フィードバック**] セクションでは、**製品に関するフィードバック**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3079-151">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

<a name="web-client"></a><span data-ttu-id="a3079-152">Web クライアント</span><span class="sxs-lookup"><span data-stu-id="a3079-152">Web client</span></span> 
----------

<span data-ttu-id="a3079-153">Web クライアント ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) は、さまざまなブラウザーから使用できる、完全な機能クライアントです。</span><span class="sxs-lookup"><span data-stu-id="a3079-153">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="a3079-154">Web クライアントは WebRTC を使用することによって通話と会議をサポートするため、Web ブラウザーで Teams を実行するためのプラグインやダウンロードの必要がありません。</span><span class="sxs-lookup"><span data-stu-id="a3079-154">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="a3079-155">ブラウザーはサードパーティの Cookie を許可するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3079-155">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="a3079-156">Web クライアントへの接続時にブラウザーのバージョンの検出を実行する[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)。</span><span class="sxs-lookup"><span data-stu-id="a3079-156">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="a3079-157">サポートされていないブラウザーのバージョンが検出された場合、web インタ フェースへのアクセスをブロックし、ユーザーがデスクトップ クライアントまたはモバイル アプリケーションをダウンロードすることをお勧めです。</span><span class="sxs-lookup"><span data-stu-id="a3079-157">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

<a name="mobile-clients"></a><span data-ttu-id="a3079-158">モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="a3079-158">Mobile clients</span></span>
--------------

<span data-ttu-id="a3079-159">マイクロソフト チームのモバイル アプリケーションは、Android と iOS、チャット ベースで会話に参加している上、移動ユーザーを対象としていますし、ピア ツー ピア音声通話を許可します。</span><span class="sxs-lookup"><span data-stu-id="a3079-159">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="a3079-160">モバイル アプリケーションは、Google のプレイと Apple のアプリケーション ストア関連のモバイル ストアをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a3079-160">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="a3079-161">Windows Phone アプリケーションは、2018 年 7 月 20日が廃止され、動作しなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3079-161">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="a3079-162">Microsoft Teams モバイル アプリのサポートされるモバイル プラットフォームは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a3079-162">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="a3079-163">**Android**: 4.4 以降</span><span class="sxs-lookup"><span data-stu-id="a3079-163">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="a3079-164">**iOS**: 10.0 以降</span><span class="sxs-lookup"><span data-stu-id="a3079-164">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="a3079-165">モバイル版は、チームが正常に機能するために一般に公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3079-165">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="a3079-166">モバイル アプリはそれぞれのモバイル プラットフォームのアプリ ストアからのみ配布および更新され、MDM (モバイル デバイス管理) ソリューションまたはサイド ロードからは配布することはできません。</span><span class="sxs-lookup"><span data-stu-id="a3079-166">Mobile apps are distributed and updated through the respective mobile platform’s app store only, and are not available to be distributed through MDM (mobile device management) solutions or side-loaded.</span></span>


| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="a3079-168">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="a3079-168">Decision Point</span></span>         |<span data-ttu-id="a3079-169">ユーザーが適切な Microsoft Teams クライアントをデバイスにインストールすることを妨げる制限事項はありますか?</span><span class="sxs-lookup"><span data-stu-id="a3079-169">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![次のステップ アイコン。](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="a3079-171">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a3079-171">Next Steps</span></span>         |<span data-ttu-id="a3079-p115">組織によってソフトウェアのインストールが制限されている場合、処理が Microsoft Teams に対応していることを確認してください。注意: 管理者権限は、PC クライアント インストールでは必要ありませんが、Mac へのインストールでは必要になります。</span><span class="sxs-lookup"><span data-stu-id="a3079-p115">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams. Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

<a name="client-update-management"></a><span data-ttu-id="a3079-174">クライアントの更新管理</span><span class="sxs-lookup"><span data-stu-id="a3079-174">Client update management</span></span>
------------------------

<span data-ttu-id="a3079-p116">クライアントは現在、IT 管理者の介入を必要とせずに Microsoft Teams サービスによって自動的に更新されています。利用可能な更新がある場合、クライアントは自動的にその更新をダウンロードします。アプリが一定時間アイドル状態となった場合には更新処理が開始されます。</span><span class="sxs-lookup"><span data-stu-id="a3079-p116">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required. If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will kick off.</span></span>

<a name="client-side-configurations"></a><span data-ttu-id="a3079-177">クライアント側の設定</span><span class="sxs-lookup"><span data-stu-id="a3079-177">Client-side configurations</span></span>
---------------------------

<span data-ttu-id="a3079-178">現在、テナント管理者、PowerShell、グループ ポリシー オブジェクトまたはレジストリのいずれかを介してクライアントを設定するオプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a3079-178">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

<a name="notification-settings"></a><span data-ttu-id="a3079-179">通知設定</span><span class="sxs-lookup"><span data-stu-id="a3079-179">Notification settings</span></span>
----------------------------

<span data-ttu-id="a3079-p117">現在、IT 管理者がクライアント側の通知設定を設定するオプションはありません。通知オプションはすべてユーザーによって設定されます。次の図に、既定のクライアント設定の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="a3079-p117">There are currently no options available for IT administrators to configure client-side notification settings. All notification options are set by the user. The figure below outlines the default client settings.</span></span>

![通知設定のスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image6.png)

<a name="sample-powershell-script"></a><span data-ttu-id="a3079-184">PowerShell スクリプトをサンプルします。</span><span class="sxs-lookup"><span data-stu-id="a3079-184">Sample PowerShell Script</span></span>
----------------------------

<span data-ttu-id="a3079-185">管理者アカウントのコンテキスト内のクライアント コンピューター上で実行する必要がある、次のサンプル スクリプトでは、c:\users に各ユーザーのフォルダーの新しい受信ファイアウォール規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="a3079-185">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="a3079-186">チームには、このルールが検出されると、チーム アプリケーションをユーザーに要求するから、ユーザーがチームからの最初の呼び出しを行うと、ファイアウォール規則を作成するのにはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="a3079-186">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

```
$users = Get-Childitem c:\users
foreach ($user in $users) 
{
    $Path = "c:\users\" + $user.Name + "\appdata\local\Microsoft\Teams\Current\Teams.exe"
    if (Test-Path $Path) 
    {
            $name = "teams.exe " + $user.Name
            if (!(Get-NetFirewallRule -DisplayName $name))
        {
                New-NetFirewallRule -DisplayName “teams.exe” -Direction Inbound -Profile Domain -Program $Path -Action Allow
        }
    }
}
<#
        .ABOUT THIS SCRIPT
        (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.

        Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 

        The script will create a new inbound firewall rule for each user folder found in c:\users. 

        Requires PowerShell 3.0
        
#>

```
