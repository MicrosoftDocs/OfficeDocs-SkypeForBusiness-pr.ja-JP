---
title: Skype for Business Server で SRS v1 管理 Web ポータルを展開する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Skype for Business Server Skype Room Systems v1 (SRS v1, 旧称 Lync Room System) 管理 Web ポータルは、組織が Skype Room Systems の会議室を維持するために使用できる Web ポータルです。 管理者は、SRS v1 管理 Web ポータルを使用して、オーディオ/ビデオ デバイスの監視など、デバイスの正常性を監視できます。 このポータルを使用すると、管理者はリモートで診断情報を収集して会議室の正常性を監視できます。
ms.openlocfilehash: 94e163ccbeff3bde78569aa864b44525b267ccd8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103883"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="60994-105">Skype for Business Server で SRS v1 管理 Web ポータルを展開する</span><span class="sxs-lookup"><span data-stu-id="60994-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="60994-106">Skype for Business Server Skype Room Systems v1 (SRS v1, 旧称 Lync Room System) 管理 Web ポータルは、組織が Skype Room Systems の会議室を維持するために使用できる Web ポータルです。</span><span class="sxs-lookup"><span data-stu-id="60994-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="60994-107">管理者は、SRS v1 管理 Web ポータルを使用して、オーディオ/ビデオ デバイスの監視など、デバイスの正常性を監視できます。</span><span class="sxs-lookup"><span data-stu-id="60994-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="60994-108">このポータルを使用すると、管理者はリモートで診断情報を収集して会議室の正常性を監視できます。</span><span class="sxs-lookup"><span data-stu-id="60994-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="60994-109">この機能を使用するには、SRS v1 管理 Web ポータルをすべての Skype for Business Server フロントエンド サーバーに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60994-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="60994-110">このガイドでは、SRS 管理 Web ポータルをインストールして構成する方法について管理者向け手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="60994-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="60994-111">これは、Skype for Business Server の管理に関する知識を持ち、Skype for Business Server トポロジを変更する管理者ユーザー権限を持つ管理者を対象にしています。</span><span class="sxs-lookup"><span data-stu-id="60994-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="60994-112">SRS v1 管理 Web ポータルがサーバーに展開された後、管理者は自分のコンピューターまたはラップトップからサイトにログオンして、SRS v1 デバイスの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="60994-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60994-113">Microsoft [Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015 をダウンロードします](https://www.microsoft.com/download/details.aspx?id=46906)。</span><span class="sxs-lookup"><span data-stu-id="60994-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="60994-114">このトピックの内容</span><span class="sxs-lookup"><span data-stu-id="60994-114">In this topic:</span></span>

- [<span data-ttu-id="60994-115">SRS v1 管理 Web ポータルの環境を構成する</span><span class="sxs-lookup"><span data-stu-id="60994-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="60994-116">SRS v1 管理 Web ポータルのインストール</span><span class="sxs-lookup"><span data-stu-id="60994-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="60994-117">SRS 管理 Web ポータルの使用</span><span class="sxs-lookup"><span data-stu-id="60994-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="60994-118">SRS v1 管理 Web ポータルの環境を構成する</span><span class="sxs-lookup"><span data-stu-id="60994-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="60994-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="60994-119"><a name="Config_Env"> </a></span></span>

<span data-ttu-id="60994-120">SRS v1 管理 Web ポータルを使用するには、次の前提条件をインストールまたは構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60994-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60994-121">サーバーが Kerberos 認証と NTLM 認証の両方で構成され、ドメインに参加していないコンピューターで SRS が実行されている場合、Kerberos 認証は失敗し、ユーザーは管理ポータルで SRS の状態を表示しません。</span><span class="sxs-lookup"><span data-stu-id="60994-121">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal.</span></span> <span data-ttu-id="60994-122">この問題を解決するには、NTLM 認証または NTLM 認証と TLS-DSK 認証 (Kerberos なし) の両方を使用してサーバーを構成するか、SRS コンピューターをドメインに参加します。</span><span class="sxs-lookup"><span data-stu-id="60994-122">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="60994-123">Skype for Business Server トポロジに Skype for Business Server の累積的な更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="60994-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="60994-124">更新プログラムを取得したり、その更新プログラムに含まれている内容を確認するには [、「Updates for Skype for Business Server 2015」を参照してください](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="60994-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="60994-125">SIP が有効な Active Directory ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="60994-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="60994-126">SRS v1 管理 Web ポータルは、これらの資格情報を使用して Skype for Business Server から情報を照会します。</span><span class="sxs-lookup"><span data-stu-id="60994-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="60994-127">与えられた例のユーザー名は LRSApp です。</span><span class="sxs-lookup"><span data-stu-id="60994-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="60994-128">LRSSupportAdminGroup という名前の Active Directory セキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="60994-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="60994-129">グループ スコープをグローバルとしてグループを作成し、セキュリティとしてグループの種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="60994-129">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="60994-130">このグループに追加された SIP が有効なユーザーには、会議室の一覧を表示し、ログの収集などの特定のコマンドを実行する権限が与わります。</span><span class="sxs-lookup"><span data-stu-id="60994-130">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="60994-131">LRSFullAccessAdminGroup という名前の Active Directory セキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="60994-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="60994-132">グループ スコープをグローバルとグループの種類としてグループを作成し、このグループに追加された Security.SIP が有効なユーザーは、1 つの Skype ルームですべての管理ポータル機能を使用する権限があります。</span><span class="sxs-lookup"><span data-stu-id="60994-132">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room.</span></span> <span data-ttu-id="60994-133">Skype ルームの一括管理のサポートを含めるには、手順 5 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60994-133">To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![セキュリティ グループの役割を持つ管理者グループの一覧](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="60994-135">LRSPowerUserAdminsGroup という名前の Active Directory セキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="60994-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="60994-136">グループ スコープをグローバルとしてグループを作成し、セキュリティとしてグループの種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="60994-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="60994-137">このグループに追加された SIP が有効なユーザーは、Skype for Business ルームの一括管理を含むすべての管理ポータル機能を使用する権限があります。</span><span class="sxs-lookup"><span data-stu-id="60994-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="60994-138">LRSSupportAdminGroup のメンバーとして LRSFullAccessAdminGroup を追加します。</span><span class="sxs-lookup"><span data-stu-id="60994-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup プロパティ メンバー ページ](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="60994-140">LRSSupport という名前の SIP が有効な Active Directory ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="60994-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="60994-141">このユーザーを LRSSupportAdminGroup に追加します。</span><span class="sxs-lookup"><span data-stu-id="60994-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup プロパティ メンバー ページ](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="60994-143">MVC [4 ASP.NET 2010 SP1 Visual Studio Visual Web Developer 2010 SP1 用にインストールします](https://go.microsoft.com/fwlink/p/?LinkId=323967)。</span><span class="sxs-lookup"><span data-stu-id="60994-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="60994-144">SRS v1 管理 Web ポータルのインストール</span><span class="sxs-lookup"><span data-stu-id="60994-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="60994-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="60994-145"><a name="Install_SRS"> </a></span></span>

<span data-ttu-id="60994-146">Microsoft [Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015 をダウンロードします](https://www.microsoft.com/download/details.aspx?id=46906)。</span><span class="sxs-lookup"><span data-stu-id="60994-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="60994-147">SRS v1 管理 Web ポータルをインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="60994-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="60994-148">Skype for Business Server 管理シェルで次のコマンドレットを実行して、信頼済みアプリケーション ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="60994-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="60994-149">ミーティング ルーム ポータルをインストールするには **、MeetingRoomPortalInstaller.msiを** ダウンロードし、管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="60994-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="60994-150">次の場所Web.configファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="60994-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="60994-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="60994-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="60994-152">Web.Config ファイルで[、「SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)管理 Web ポータルの環境を構成する」(手順の推奨名は LRSApp) の下の手順 2 で作成したユーザー名に変更します。</span><span class="sxs-lookup"><span data-stu-id="60994-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="60994-153">SRS v1 管理ポータルは信頼できるアプリケーションなので、ポータル構成でパスワードを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="60994-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="60994-154">このユーザーがローカル レジストラーとは異なるレジストラーを使用している場合は、レジストリ ファイルに次の行を追加してレジストラーを指定Web.Configがあります。</span><span class="sxs-lookup"><span data-stu-id="60994-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="60994-155">使用するポートが 5061 以外の場合は、次の行を次の行Web.Configします。</span><span class="sxs-lookup"><span data-stu-id="60994-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="60994-156">SRS 管理 Web ポータルのインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="60994-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="60994-157">SRS v1 管理 Web ポータルのインストールを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="60994-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="60994-158">フロントエンド サーバーで、次の URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="60994-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="60994-159">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="60994-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="60994-160">次の図に示すように、エラーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="60994-160">You should not see any errors, as shown in the following image:</span></span>

     ![Lync Room System Admin Portal サインイン画面](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="60994-162">エラーが表示されない場合は、トポロジ内の他のコンピューターから次の URL にアクセスしてみてください。</span><span class="sxs-lookup"><span data-stu-id="60994-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="60994-163">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="60994-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="60994-164">ページにアクセスするには、「自動クライアント サインインに必要な DNS レコード」の説明に従って[DNS レコードを追加する必要があります](/previous-versions/office/communications-server/bb663700(v=office.12))。</span><span class="sxs-lookup"><span data-stu-id="60994-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](/previous-versions/office/communications-server/bb663700(v=office.12))."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="60994-165">SRS 管理 Web ポータルの使用</span><span class="sxs-lookup"><span data-stu-id="60994-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="60994-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="60994-166"><a name="Use_Portal"> </a></span></span>

<span data-ttu-id="60994-167">サーバーに SRS を展開した後、ブラウザーから SRS v1 管理 Web ポータルにサインインすることで、すべての SRS ルームの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="60994-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="60994-168">サインイン</span><span class="sxs-lookup"><span data-stu-id="60994-168">Sign in</span></span>

1. <span data-ttu-id="60994-169">次の URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="60994-169">Browse to the following URL:</span></span>

    <span data-ttu-id="60994-170">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="60994-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="60994-171">LRSSupport アカウントの資格情報、または LRSSupportAdminGroup セキュリティ グループに追加されたアカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="60994-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Lync Room System Admin Portal サインイン画面](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="60994-173">SRS 管理 Web ポータルの概要ページ</span><span class="sxs-lookup"><span data-stu-id="60994-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="60994-174">概要ページには、サーバーに展開されているすべての SRS ルームに関する次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="60994-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="60994-175">**タグ** 管理者がルームに与えるカスタム名。</span><span class="sxs-lookup"><span data-stu-id="60994-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="60994-176">タグは、ルーム名をクリックしてポータルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="60994-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="60994-177">**正常性** [ルームの設定] ページの [正常性] セクションに表示される、部屋の正常性の集計状態から派生した、部屋の正常性状態。</span><span class="sxs-lookup"><span data-stu-id="60994-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="60994-178">**次の会議** 次の会議がスケジュールされる日時。</span><span class="sxs-lookup"><span data-stu-id="60994-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="60994-179">**SRS バージョン、製造元、モデル** これらの値は SRS で事前設定されています。</span><span class="sxs-lookup"><span data-stu-id="60994-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="60994-180">製造元によっては、これらのフィールドは空白のままになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="60994-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="60994-181">**最後の更新** Web ページが最後に更新された時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="60994-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Lync Room System Admin Portal の概要ビュー](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="60994-183">LRSPowerUserAdminsGroup セキュリティ グループの一部である場合にのみ、[一括管理] メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60994-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="60994-184">SRS ルーム情報</span><span class="sxs-lookup"><span data-stu-id="60994-184">SRS Room Information</span></span>

<span data-ttu-id="60994-185">ポータルの [会議室情報] セクションでは、個々の SRS ルームを表示および構成できます。</span><span class="sxs-lookup"><span data-stu-id="60994-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="60994-186">このセクションには、設定、詳細、ログ、正常性の 4 つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="60994-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="60994-187">設定</span><span class="sxs-lookup"><span data-stu-id="60994-187">Settings</span></span>

<span data-ttu-id="60994-188">[設定] セクションでは、ルームのパスワード、ルーム タグ、既定の音量レベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="60994-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="60994-189">これらの設定を構成した場合、変更は SRS コンソールを再起動した後にのみレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="60994-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="60994-190">リリース 15.12 以降を使用している SRS デバイスのシステム更新プログラムの設定だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60994-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Lync Room System Admin Portal Room の設定](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="60994-192">詳細</span><span class="sxs-lookup"><span data-stu-id="60994-192">Details</span></span>

<span data-ttu-id="60994-193">[詳細] セクションには、SRS ルームの設定の読み取り専用の概要 (最後の更新時刻など) が表示されます。次の会議。最後の更新、メンテナンス、調整。既定のスピーカー、マイク、および呼び出し音の設定。バージョン。SIP URI。各画面に関する画面と詳細の数。状態、およびアクティビティを指定します。</span><span class="sxs-lookup"><span data-stu-id="60994-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Lync Room System Admin Portal Detail View](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="60994-195">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="60994-195">Troubleshooting</span></span>

<span data-ttu-id="60994-196">[トラブルシューティング] セクションを使用して、ログをリモートで収集し、指定した場所に保存できます。</span><span class="sxs-lookup"><span data-stu-id="60994-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="60994-197">SRS コンソール (SRS ユーザー インターフェイス) を再起動するか、システム全体を再起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="60994-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="60994-198">ログを収集するには、指定した形式のフォルダー パスを指定し、フォルダーに SRS コンピューター アカウントに対する書き込みアクセス許可が付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="60994-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="60994-199">ログ サイズが大きすぎる場合、ログの収集が完了するには最大 5 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="60994-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="60994-200">ページを更新すると、最新の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="60994-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="60994-201">正常性</span><span class="sxs-lookup"><span data-stu-id="60994-201">Health</span></span>

<span data-ttu-id="60994-202">[正常性] セクションでは、Skype for Business Server 接続、オーディオ デバイス、ビデオ デバイス、復元状態、画面デバイスの正常性を視覚的に示します。</span><span class="sxs-lookup"><span data-stu-id="60994-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Lync Room System Admin Portal Room Health](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="60994-204">管理 Web ポータルに関するその他の注意事項</span><span class="sxs-lookup"><span data-stu-id="60994-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="60994-205">設定の変更は、SRS システムが再起動された後にのみ適用されます。> LRSApp アカウントのパスワードの有効期限が切れると、会議室の状態を確認できません。</span><span class="sxs-lookup"><span data-stu-id="60994-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="60994-206">LRSAppuser アカウント のパスワードが期限切れになることはありませんか、有効期限が近い場合は必ずパスワードを更新してください。> SRS 管理 Web ポータルは、オンプレミス展開でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="60994-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="60994-207">一括管理</span><span class="sxs-lookup"><span data-stu-id="60994-207">Bulk management</span></span>

<span data-ttu-id="60994-208">SRS ルームの一括管理は、高度な IT 管理者向けに設計された機能で、ワークフローを簡素化し、時間を節約できる便利なツールを使用して、複数のルームを一括でリモートで管理できます。</span><span class="sxs-lookup"><span data-stu-id="60994-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="60994-209">この機能を確認するには、ユーザーを特別なセキュリティ グループ **LRSPowerUserAdminsGroup のメンバーとしてプロビジョニングする必要があります**。</span><span class="sxs-lookup"><span data-stu-id="60994-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="60994-210">一括管理で選択できる SRS ルームの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="60994-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="60994-211">ただし、一度に実行できる一括管理操作は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="60994-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="60994-212">一括管理操作を実行するには、監視する会議室を選択し、[一括管理] メニューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="60994-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="60994-213">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="60994-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="60994-214">管理 Web ポータルにサインインできない理由</span><span class="sxs-lookup"><span data-stu-id="60994-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="60994-215">開いていると、サインイン ページが表示されますが、資格情報を入力するとサインイン https://localhost/lrs できません。</span><span class="sxs-lookup"><span data-stu-id="60994-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="60994-216">この場合は、管理 Web ポータル https://FQDNofFEserver/SRS にサインインするために開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="60994-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="60994-217">管理 Web ポータルに SRS v1 が表示できない理由</span><span class="sxs-lookup"><span data-stu-id="60994-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="60994-218">展開に SRS アカウントが含み、SRS 管理 Web ポータルの展開の推奨事項に従って作成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="60994-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="60994-219">Skype for Business Server で、Enable-CsUser ではなく Enable-CsMeetingRoom を使用して SRS アカウントがプロビジョニングされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="60994-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="60994-220">SRS アカウントを作成し、管理 Web ポータルにアカウントを表示できない場合は、Skype for Business Server Logging ツールを使用して **MeetingPortal** コンポーネントを選択してサーバー ログを収集し、SRS サポート連絡先に送信します。</span><span class="sxs-lookup"><span data-stu-id="60994-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="60994-221">SRS アカウントを作成し、管理 Web ポータルでアカウントを表示できない場合は、Fiddler を使用してクライアント ログを収集し、ブラウザー開発ツールからコンソール ログをコピーしてから、SRS サポート連絡先に送信します。</span><span class="sxs-lookup"><span data-stu-id="60994-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="60994-222">また、詳細なログを取得するために、Web.configのトレース レベルの値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="60994-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

  ```xml
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="60994-223">管理 Web ポータルで SRS の状態が表示できない理由</span><span class="sxs-lookup"><span data-stu-id="60994-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="60994-224">LRSApp ユーザー アカウントが SIP が有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="60994-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="60994-225">問題が解決し続ける場合は、D:\Trace\LRSAdminLogs から SRS システムの **Trace.log** ファイルを収集し、SRS サポート連絡先に \, 送信します。</span><span class="sxs-lookup"><span data-stu-id="60994-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="60994-226">管理 Web ポータルに SRS の一括管理メニューが表示できない理由</span><span class="sxs-lookup"><span data-stu-id="60994-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="60994-227">LRSApp ユーザー アカウントが SIP が有効であり、LRSPowerUserAdminsGroup セキュリティ グループの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="60994-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="60994-228">SRS v1 管理 Web ポータルは Microsoft Teams Rooms で動作しますか?</span><span class="sxs-lookup"><span data-stu-id="60994-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="60994-229">いいえ。</span><span class="sxs-lookup"><span data-stu-id="60994-229">No.</span></span>