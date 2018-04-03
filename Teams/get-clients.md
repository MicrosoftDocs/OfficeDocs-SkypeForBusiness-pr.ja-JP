---
title: Microsoft Teams のクライアントを取得する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/27/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
localization_priority: Normal
description: Microsoft Teams で利用できる、Web、デスクトップ (Windows および Mac)、およびモバイル (Android、iOS、Windows Phone) などのさまざまなクライアントを使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61bfc43321433a06eba8196b732f8f12dded0d8d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
<a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="2cd15-103">Microsoft Teams のクライアントを取得する</span><span class="sxs-lookup"><span data-stu-id="2cd15-103">Get clients for Microsoft Teams</span></span> 
===========================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="2cd15-p101">Microsoft Teams には、Web、デスクトップ (Windows および Mac)、およびモバイル (Android、iOS、Windows Phone) で利用できるクライアントがあります。これらのクライアントはすべてアクティブなインターネット接続が必要で、オフライン モードをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2cd15-p101">Microsoft Teams has clients available for web, desktop (Windows and Mac), and mobile (Android, iOS, and Windows Phone). These clients all require an active internet connection and do not support an offline mode.</span></span>

<a name="web-client"></a><span data-ttu-id="2cd15-106">Web クライアント</span><span class="sxs-lookup"><span data-stu-id="2cd15-106">Web client</span></span> 
----------

<span data-ttu-id="2cd15-107">Web クライアント ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) は、完全な機能のクライアントで、さまざまなブラウザーから使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2cd15-107">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="2cd15-108">Web クライアントでは、プラグインがあるため、webRTC または web ブラウザーでのチームを実行するために必要なダウンロードを使用して通話や会議をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2cd15-108">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="2cd15-109">ブラウザーを構成して、サード パーティの cookie を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cd15-109">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="2cd15-110">Web クライアントへの接続時にブラウザーのバージョンの検出を実行する[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)、サポートされていないブラウザーのバージョンが検出された場合、web インターフェイスへのアクセスをブロックし、ユーザーがデスクトップ クライアントまたはモバイル アプリケーションをダウンロードすることをお勧めしています。</span><span class="sxs-lookup"><span data-stu-id="2cd15-110">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) and if an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

<a name="desktop-client"></a><span data-ttu-id="2cd15-111">デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="2cd15-111">Desktop client</span></span>
--------------

<span data-ttu-id="2cd15-112">マイクロソフト チームのデスクトップ クライアントは、スタンドアロン アプリケーションと現在の Office Pro との一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="2cd15-112">The Microsoft Teams desktop client is a standalone application and currently not part of Office Pro Plus.</span></span> <span data-ttu-id="2cd15-113">チームは、Windows (7 +)、32 ビットと 64 ビットの両方のバージョンと MacOS (10.10 +) の両方に使用できます。</span><span class="sxs-lookup"><span data-stu-id="2cd15-113">Teams is available for both Windows (7+), both 32-bit and 64-bit versions, and MacOS (10.10+).</span></span> <span data-ttu-id="2cd15-114">Windows では、.NET framework 4.5 以降のチームする必要があります。チームのインストーラーは、インストールすることがない場合に提供されます。</span><span class="sxs-lookup"><span data-stu-id="2cd15-114">On Windows, Teams requires .NET framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> 

<span data-ttu-id="2cd15-115">デスクトップのクライアントでは、チーム ミーティング、グループの呼び出し、およびプライベート 1 対 1 の呼び出しのリアルタイム通信のサポート (オーディオ、ビデオ、およびコンテンツの共有) を提供します。</span><span class="sxs-lookup"><span data-stu-id="2cd15-115">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="2cd15-116">デスクトップ クライアントをダウンロードしてから直接のエンド ・ ユーザーによってインストールされている[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)、適切なローカルのアクセス許可 (管理者権限は、PC 上でチームのクライアントをインストールする必要はありませんが、Mac のために必要な) があります。</span><span class="sxs-lookup"><span data-stu-id="2cd15-116">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="2cd15-117">IT 管理者は好みの方法で、System Center Configuration Manager (Windows)、Casper Suite (MacOS) のような組織内のコンピューターにインストール ファイルを配布できます。</span><span class="sxs-lookup"><span data-stu-id="2cd15-117">IT admins can choose their preferred method to distribute the installation files to machines in their organization such as System Center Configuration Manager (Windows) or Casper Suite (MacOS).</span></span> <span data-ttu-id="2cd15-118">Windows 用の MSI パッケージの配布を取得するには、[マイクロソフト チームのインストールは、MSI を使用して](msi-deployment.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cd15-118">To get the MSI Package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2cd15-119">これらのメカニズムによるクライアントの配布は、Microsoft Teams クライアントの初回インストール時にのみ利用でき、それ以降の更新では利用できません。</span><span class="sxs-lookup"><span data-stu-id="2cd15-119">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>


#### <a name="windows"></a><span data-ttu-id="2cd15-120">Windows</span><span class="sxs-lookup"><span data-stu-id="2cd15-120">Windows</span></span>

<span data-ttu-id="2cd15-p105">Windows 用のMicrosoft Teams インストールでは、32 ビットおよび 64 ビット アーキテクチャでダウンロード可能なインストーラーを提供しています。そのアーキテクチャは、オンライン ダウンロードで既定として提示される OS のアーキテクチャと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cd15-p105">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture. The architecture should match that of the OS, which is what the online download defaults to.</span></span>



> [!NOTE]
> <span data-ttu-id="2cd15-123">Microsoft Teams のアーキテクチャ (32 ビットと 64 ビット) はインストールされている Office のアーキテクチャに依存しません。</span><span class="sxs-lookup"><span data-stu-id="2cd15-123">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Office that is installed.</span></span>

<span data-ttu-id="2cd15-p106">Windows クライアントは、ユーザーのプロファイルにある AppData フォルダーに展開されます。ユーザーのローカル プロファイルに展開すると、クライアントは管理者特権を必要とせずにインストール可能になります。Windows クライアントは次の場所にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2cd15-p106">The Windows client is deployed to the AppData folder located in the user’s profile. Deploying to the user’s local profile allows the client to be installed without requiring elevated rights. The Windows client is installed in the following locations:</span></span>

-   <span data-ttu-id="2cd15-127">%appdata%\\local\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="2cd15-127">%appdata%\\local\\Microsoft\\Teams</span></span>

-   <span data-ttu-id="2cd15-128">%appdata%\\roaming\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="2cd15-128">%appdata%\\roaming\\Microsoft\\Teams</span></span>

<span data-ttu-id="2cd15-p107">ユーザーが Microsoft Teams クライアントを使用して初めて通話を開始すると、ユーザーに通信の許可を求める Windows ファイアウォール設定に関する警告が通知される場合があります。警告を受け入れなくても通話は機能するため、このメッセージを無視するように指示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="2cd15-p107">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication. Users may be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![[Windows セキュリティの重要な警告] ダイアログのスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image3.png)


> [!NOTE]
> <span data-ttu-id="2cd15-p108">Windows ファイアウォール設定は、[キャンセル] の選択によりプロンプトが受け入れられなかった場合でも変更されます。TCP および UDP プロトコルの両方に関するブロック アクションで、teams.exe に関する2 つの着信ルールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2cd15-p108">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”. Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

#### <a name="mac"></a><span data-ttu-id="2cd15-134">Mac</span><span class="sxs-lookup"><span data-stu-id="2cd15-134">Mac</span></span>

<span data-ttu-id="2cd15-135">Microsoft は Mac OSX コンピュータ用の DMG インストール ファイルも提供しています。</span><span class="sxs-lookup"><span data-stu-id="2cd15-135">Microsoft also provides a DMG installation file for Mac OSX computers.</span></span> <span data-ttu-id="2cd15-136">Mac クライアントをインストールするには管理アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2cd15-136">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="2cd15-137">Mac OSX クライアントは /Applications フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2cd15-137">The Mac OSX client is installed to the /Applications folder.</span></span>


<a name="mobile-clients"></a><span data-ttu-id="2cd15-138">モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="2cd15-138">Mobile clients</span></span>
--------------

<span data-ttu-id="2cd15-p110">Microsoft Teams のモバイル アプリは Android、iOS、および Windows Phone で利用でき、チャットベースの会話に参加している外出中のユーザーを対象としており、ピアツーピアの音声通話が使用できます。モバイル アプリについては、Google Play、Apple App Store、および Microsoft Store の関連するモバイル ストアにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="2cd15-p110">The Microsoft Teams mobile apps are available for Android, iOS, and Windows Phones, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls. For mobile apps, go to the relevant mobile store for Google Play, Apple App Store, and Microsoft Store.</span></span>

<span data-ttu-id="2cd15-141">Microsoft Teams モバイル アプリのサポートされるモバイル プラットフォームは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2cd15-141">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="2cd15-142">**Android**: 4.4 以降</span><span class="sxs-lookup"><span data-stu-id="2cd15-142">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="2cd15-143">**iOS**: 10.0 以降</span><span class="sxs-lookup"><span data-stu-id="2cd15-143">**iOS**: 10.0 or later</span></span>

-   <span data-ttu-id="2cd15-144">**Windows Phone**: Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="2cd15-144">**Windows Phone**: Windows 10 Mobile</span></span>

<span data-ttu-id="2cd15-145">モバイル アプリはそれぞれのモバイル プラットフォームのアプリ ストアからのみ配布および更新され、MDM (モバイル デバイス管理) ソリューションまたはサイド ロードからは配布することはできません。</span><span class="sxs-lookup"><span data-stu-id="2cd15-145">Mobile apps are distributed and updated through the respective mobile platform’s app store only, and are not available to be distributed through MDM (mobile device management) solutions or side-loaded.</span></span>


| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="2cd15-147">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="2cd15-147">Decision Point</span></span>         |<span data-ttu-id="2cd15-148">ユーザーが適切な Microsoft Teams クライアントをデバイスにインストールすることを妨げる制限事項はありますか?</span><span class="sxs-lookup"><span data-stu-id="2cd15-148">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![次のステップ アイコン。](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="2cd15-150">次のステップ</span><span class="sxs-lookup"><span data-stu-id="2cd15-150">Next Steps</span></span>         |<span data-ttu-id="2cd15-p111">組織によってソフトウェアのインストールが制限されている場合、処理が Microsoft Teams に対応していることを確認してください。注意: 管理者権限は、PC クライアント インストールでは必要ありませんが、Mac へのインストールでは必要になります。</span><span class="sxs-lookup"><span data-stu-id="2cd15-p111">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams. Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |


  <span data-ttu-id="2cd15-153"><span id="_Hlk477176062" class="anchor"></span>  判断ポイント   ユーザーが適切な Microsoft Teams クライアントをデバイスにインストールすることを妨げる制限事項はありますか?</span><span class="sxs-lookup"><span data-stu-id="2cd15-153"><span id="_Hlk477176062" class="anchor"></span>  Decision Point   Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>

<a name="client-update-management"></a><span data-ttu-id="2cd15-154">クライアントの更新管理</span><span class="sxs-lookup"><span data-stu-id="2cd15-154">Client update management</span></span>
------------------------

<span data-ttu-id="2cd15-p112">クライアントは現在、IT 管理者の介入を必要とせずに Microsoft Teams サービスによって自動的に更新されています。利用可能な更新がある場合、クライアントは自動的にその更新をダウンロードします。アプリが一定時間アイドル状態となった場合には更新処理が開始されます。</span><span class="sxs-lookup"><span data-stu-id="2cd15-p112">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required. If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will kick off.</span></span>

<a name="client-side-configurations"></a><span data-ttu-id="2cd15-157">クライアント側の設定</span><span class="sxs-lookup"><span data-stu-id="2cd15-157">Client-side configurations</span></span>
---------------------------

<span data-ttu-id="2cd15-158">現在、テナント管理者、PowerShell、グループ ポリシー オブジェクトまたはレジストリのいずれかを介してクライアントを設定するオプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2cd15-158">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

<a name="notification-settings"></a><span data-ttu-id="2cd15-159">通知設定</span><span class="sxs-lookup"><span data-stu-id="2cd15-159">Notification settings</span></span>
----------------------------

<span data-ttu-id="2cd15-p113">現在、IT 管理者がクライアント側の通知設定を設定するオプションはありません。通知オプションはすべてユーザーによって設定されます。次の図に、既定のクライアント設定の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="2cd15-p113">There are currently no options available for IT administrators to configure client-side notification settings. All notification options are set by the user. The figure below outlines the default client settings.</span></span>

![通知設定のスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image6.png)
