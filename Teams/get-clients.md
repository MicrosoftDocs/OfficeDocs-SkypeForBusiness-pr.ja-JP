---
title: Microsoft Teams のクライアントを取得する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vichau, majafry
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で利用できる、Web、デスクトップ (Windows および Mac)、およびモバイル (Android、iOS、Windows Phone) などのさまざまなクライアントを使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: bbadb9324942cdb354570673a0fd923c9e04bdbd
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "23891330"
---
<a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="2d55f-103">Microsoft Teams のクライアントを取得する</span><span class="sxs-lookup"><span data-stu-id="2d55f-103">Get clients for Microsoft Teams</span></span> 
===========================

<span data-ttu-id="2d55f-104">マイクロソフトのチームには、クライアント デスクトップ (Windows および Mac) は、web、およびモバイル (Android、iOS、および Windows Phone) があります。</span><span class="sxs-lookup"><span data-stu-id="2d55f-104">Microsoft Teams has clients available for desktop (Windows and Mac), web, and mobile (Android,  iOS, and Windows Phone).</span></span> <span data-ttu-id="2d55f-105">これらのクライアントはすべてアクティブなインターネット接続が必要で、オフライン モードをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2d55f-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

<a name="desktop-client"></a><span data-ttu-id="2d55f-106">デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="2d55f-106">Desktop client</span></span>
--------------

<span data-ttu-id="2d55f-107">マイクロソフト チームのデスクトップ クライアントは、スタンドアロン アプリケーションと現在の Office 365 用リソースの一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="2d55f-107">The Microsoft Teams desktop client is a standalone application and currently not part of Office 365 ProPlus.</span></span> <span data-ttu-id="2d55f-108">チームは、Windows (7 +)、32 ビットと 64 ビットの両方のバージョンと macOS (10.10 +) の両方に使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d55f-108">Teams is available for both Windows (7+), both 32-bit and 64-bit versions, and macOS (10.10+).</span></span> <span data-ttu-id="2d55f-109">Windows で Teams を使用するには .NET Framework 4.5 以降が必要です。.NET Framework 4.5 以降がない場合は、Teams のインストーラーでインストールすることになります。</span><span class="sxs-lookup"><span data-stu-id="2d55f-109">On Windows, Teams requires .NET framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> 

<span data-ttu-id="2d55f-110">デスクトップ クライアントは、チーム会議、グループ通話、およびプライベートな 1 対 1 での通話に対応するリアルタイム通信のサポート (オーディオ、ビデオ、およびコンテンツ共有) を提供します。</span><span class="sxs-lookup"><span data-stu-id="2d55f-110">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="2d55f-111">デスクトップ クライアントは、適切なローカルのアクセス許可を持っているエンド ユーザーによって、[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) から直接ダウンロードおよびインストールできます (管理者権限は、Teams クライアントを PC にインストールする場合には必要ありませんが、Mac では必要になります) 。</span><span class="sxs-lookup"><span data-stu-id="2d55f-111">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="2d55f-112">IT 管理者は、システム センター構成マネージャー (Windows) または Jamf Pro (macOS) など、組織内のコンピューターにインストール ファイルを配布するが推奨される方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2d55f-112">IT admins can choose their preferred method to distribute the installation files to computers in their organization, such as System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="2d55f-113">Windows ディストリビューションの MSI パッケージを取得するには、[マイクロソフト チームのインストールは、MSI を使用して](msi-deployment.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d55f-113">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2d55f-114">これらのメカニズムによるクライアントの配布は、Microsoft Teams クライアントの初回インストール時にのみ利用でき、それ以降の更新では利用できません。</span><span class="sxs-lookup"><span data-stu-id="2d55f-114">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="2d55f-115">Windows</span><span class="sxs-lookup"><span data-stu-id="2d55f-115">Windows</span></span>

<span data-ttu-id="2d55f-116">Windows のマイクロソフトのチームのインストールには、32 ビットおよび 64 ビット アーキテクチャでは、ダウンロード可能なインストーラーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="2d55f-116">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="2d55f-117">マイクロソフト チームのアーキテクチャ (32 ビットと 64 ビット) は、Windows とインストールされている Office のアーキテクチャに依存しません。</span><span class="sxs-lookup"><span data-stu-id="2d55f-117">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="2d55f-p104">Windows クライアントは、ユーザーのプロファイルにある AppData フォルダーに展開されます。ユーザーのローカル プロファイルに展開すると、クライアントは管理者特権を必要とせずにインストール可能になります。Windows クライアントは次の場所にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2d55f-p104">The Windows client is deployed to the AppData folder located in the user’s profile. Deploying to the user’s local profile allows the client to be installed without requiring elevated rights. The Windows client is installed in the following locations:</span></span>

- <span data-ttu-id="2d55f-121">%appdata%\\local\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="2d55f-121">%appdata%\\local\\Microsoft\\Teams</span></span>

- <span data-ttu-id="2d55f-122">%appdata%\\roaming\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="2d55f-122">%appdata%\\roaming\\Microsoft\\Teams</span></span>

<span data-ttu-id="2d55f-123">ユーザーは、最初にマイクロソフトのチームのクライアントを使用して呼び出しを開始するとき、Windows ファイアウォールの設定で通信を許可するユーザーの入力を求める警告がわかります。</span><span class="sxs-lookup"><span data-stu-id="2d55f-123">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="2d55f-124">呼び出し機能しますが、警告を終了したときにもあるために、このメッセージを無視するようにユーザーを指示することがあります。</span><span class="sxs-lookup"><span data-stu-id="2d55f-124">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![[Windows セキュリティの重要な警告] ダイアログのスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="2d55f-p106">Windows ファイアウォール設定は、[キャンセル] の選択によりプロンプトが受け入れられなかった場合でも変更されます。TCP および UDP プロトコルの両方に関するブロック アクションで、teams.exe に関する2 つの着信ルールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2d55f-p106">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”. Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="2d55f-128">Mac</span><span class="sxs-lookup"><span data-stu-id="2d55f-128">Mac</span></span>

<span data-ttu-id="2d55f-129">Mac ユーザーは、macOS のコンピューターでパッケージのインストール ファイルを使用してチームをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2d55f-129">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="2d55f-130">Mac クライアントをインストールするには管理アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2d55f-130">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="2d55f-131">/Applications フォルダーには、macOS クライアントがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="2d55f-131">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="2d55f-132">PKG ファイルを使用してチームをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2d55f-132">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="2d55f-133">[チームがページをダウンロード](https://teams.microsoft.com/downloads)するから**Mac**では、下の [**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d55f-133">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="2d55f-134">PKG ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d55f-134">Double click the PKG file.</span></span>
3. <span data-ttu-id="2d55f-135">インストールを完了するのにはインストール ウィザードに従います。</span><span class="sxs-lookup"><span data-stu-id="2d55f-135">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="2d55f-136">チームは、/Applications フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2d55f-136">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="2d55f-137">コンピューター全体にインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2d55f-137">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="2d55f-138">、インストール中に、PKG は、管理者の資格情報を求められます。</span><span class="sxs-lookup"><span data-stu-id="2d55f-138">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="2d55f-139">ユーザーは、ユーザーが管理者かどうかに関係なく、管理者の資格情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d55f-139">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="2d55f-140">ユーザー現在チームの攻撃力のインストールには、パッケージのインストールを交換したい場合、ユーザーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d55f-140">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="2d55f-141">チームのアプリケーションを終了します。</span><span class="sxs-lookup"><span data-stu-id="2d55f-141">Exit the Teams app.</span></span>
2. <span data-ttu-id="2d55f-142">チームのアプリケーションをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="2d55f-142">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="2d55f-143">PKG ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2d55f-143">Install the PKG file.</span></span>

<span data-ttu-id="2d55f-144">IT 管理者は、Jamf Pro など、組織内のすべての Mac にインストール ファイルを配布するのには、チームの管理された展開を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d55f-144">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="2d55f-145">パッケージのインストールで問題が発生する場合お知らせします。</span><span class="sxs-lookup"><span data-stu-id="2d55f-145">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="2d55f-146">この資料の最後にある [**フィードバック**] セクションでは、**製品に関するフィードバック**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d55f-146">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

<a name="web-client"></a><span data-ttu-id="2d55f-147">Web クライアント</span><span class="sxs-lookup"><span data-stu-id="2d55f-147">Web client</span></span> 
----------

<span data-ttu-id="2d55f-148">Web クライアント ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) は、さまざまなブラウザーから使用できる、完全な機能クライアントです。</span><span class="sxs-lookup"><span data-stu-id="2d55f-148">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="2d55f-149">Web クライアントは WebRTC を使用することによって通話と会議をサポートするため、Web ブラウザーで Teams を実行するためのプラグインやダウンロードの必要がありません。</span><span class="sxs-lookup"><span data-stu-id="2d55f-149">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="2d55f-150">ブラウザーはサードパーティの Cookie を許可するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d55f-150">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="2d55f-151">Web クライアントへの接続時にブラウザーのバージョンの検出を実行する[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)。</span><span class="sxs-lookup"><span data-stu-id="2d55f-151">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="2d55f-152">サポートされていないブラウザーのバージョンが検出された場合、web インタ フェースへのアクセスをブロックし、ユーザーがデスクトップ クライアントまたはモバイル アプリケーションをダウンロードすることをお勧めです。</span><span class="sxs-lookup"><span data-stu-id="2d55f-152">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

<a name="mobile-clients"></a><span data-ttu-id="2d55f-153">モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="2d55f-153">Mobile clients</span></span>
--------------

<span data-ttu-id="2d55f-p113">Microsoft Teams のモバイル アプリは Android、iOS、および Windows Phone で利用でき、チャットベースの会話に参加している外出中のユーザーを対象としており、ピアツーピアの音声通話が使用できます。モバイル アプリについては、Google Play、Apple App Store、および Microsoft Store の関連するモバイル ストアにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="2d55f-p113">The Microsoft Teams mobile apps are available for Android, iOS, and Windows Phones, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls. For mobile apps, go to the relevant mobile store for Google Play, Apple App Store, and Microsoft Store.</span></span>

<span data-ttu-id="2d55f-156">Microsoft Teams モバイル アプリのサポートされるモバイル プラットフォームは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d55f-156">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="2d55f-157">**Android**: 4.4 以降</span><span class="sxs-lookup"><span data-stu-id="2d55f-157">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="2d55f-158">**iOS**: 10.0 以降</span><span class="sxs-lookup"><span data-stu-id="2d55f-158">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="2d55f-159">モバイル版は、チームが正常に機能するために一般に公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d55f-159">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="2d55f-160">モバイル アプリはそれぞれのモバイル プラットフォームのアプリ ストアからのみ配布および更新され、MDM (モバイル デバイス管理) ソリューションまたはサイド ロードからは配布することはできません。</span><span class="sxs-lookup"><span data-stu-id="2d55f-160">Mobile apps are distributed and updated through the respective mobile platform’s app store only, and are not available to be distributed through MDM (mobile device management) solutions or side-loaded.</span></span>


| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="2d55f-162">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="2d55f-162">Decision Point</span></span>         |<span data-ttu-id="2d55f-163">ユーザーが適切な Microsoft Teams クライアントをデバイスにインストールすることを妨げる制限事項はありますか?</span><span class="sxs-lookup"><span data-stu-id="2d55f-163">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![次のステップ アイコン。](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="2d55f-165">次のステップ</span><span class="sxs-lookup"><span data-stu-id="2d55f-165">Next Steps</span></span>         |<span data-ttu-id="2d55f-p114">組織によってソフトウェアのインストールが制限されている場合、処理が Microsoft Teams に対応していることを確認してください。注意: 管理者権限は、PC クライアント インストールでは必要ありませんが、Mac へのインストールでは必要になります。</span><span class="sxs-lookup"><span data-stu-id="2d55f-p114">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams. Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |


  <span data-ttu-id="2d55f-168"><span id="_Hlk477176062" class="anchor"></span>  判断ポイント   ユーザーが適切な Microsoft Teams クライアントをデバイスにインストールすることを妨げる制限事項はありますか?</span><span class="sxs-lookup"><span data-stu-id="2d55f-168"><span id="_Hlk477176062" class="anchor"></span>  Decision Point   Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>

<a name="client-update-management"></a><span data-ttu-id="2d55f-169">クライアントの更新管理</span><span class="sxs-lookup"><span data-stu-id="2d55f-169">Client update management</span></span>
------------------------

<span data-ttu-id="2d55f-p115">クライアントは現在、IT 管理者の介入を必要とせずに Microsoft Teams サービスによって自動的に更新されています。利用可能な更新がある場合、クライアントは自動的にその更新をダウンロードします。アプリが一定時間アイドル状態となった場合には更新処理が開始されます。</span><span class="sxs-lookup"><span data-stu-id="2d55f-p115">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required. If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will kick off.</span></span>

<a name="client-side-configurations"></a><span data-ttu-id="2d55f-172">クライアント側の設定</span><span class="sxs-lookup"><span data-stu-id="2d55f-172">Client-side configurations</span></span>
---------------------------

<span data-ttu-id="2d55f-173">現在、テナント管理者、PowerShell、グループ ポリシー オブジェクトまたはレジストリのいずれかを介してクライアントを設定するオプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2d55f-173">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

<a name="notification-settings"></a><span data-ttu-id="2d55f-174">通知設定</span><span class="sxs-lookup"><span data-stu-id="2d55f-174">Notification settings</span></span>
----------------------------

<span data-ttu-id="2d55f-p116">現在、IT 管理者がクライアント側の通知設定を設定するオプションはありません。通知オプションはすべてユーザーによって設定されます。次の図に、既定のクライアント設定の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="2d55f-p116">There are currently no options available for IT administrators to configure client-side notification settings. All notification options are set by the user. The figure below outlines the default client settings.</span></span>

![通知設定のスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image6.png)
