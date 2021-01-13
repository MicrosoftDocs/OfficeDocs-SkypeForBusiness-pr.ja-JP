---
title: Skype for Business Server での SRS v1 管理 Web ポータルの展開
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
description: Skype for Business Server Skype Room Systems v1 (SRS v1、旧称 Lync Room System) 管理 Web ポータルは、組織が Skype Room Systems の会議室を維持するために使用できる Web ポータルです。 管理者は SRS v1 管理 Web ポータルを使用して、音声/ビデオ デバイスの監視などによってデバイスの正常性を監視できます。 管理者は、このポータルを使用して診断情報をリモートで収集し、会議室の正常性を監視できます。
ms.openlocfilehash: 7d7bef99149d09ebf72c9b633370f262e535b23f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804537"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="d0b61-105">Skype for Business Server での SRS v1 管理 Web ポータルの展開</span><span class="sxs-lookup"><span data-stu-id="d0b61-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="d0b61-106">Skype for Business Server Skype Room Systems v1 (SRS v1、旧称 Lync Room System) 管理 Web ポータルは、組織が Skype Room Systems の会議室を維持するために使用できる Web ポータルです。</span><span class="sxs-lookup"><span data-stu-id="d0b61-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="d0b61-107">管理者は SRS v1 管理 Web ポータルを使用して、音声/ビデオ デバイスの監視などによってデバイスの正常性を監視できます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="d0b61-108">管理者は、このポータルを使用して診断情報をリモートで収集し、会議室の正常性を監視できます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="d0b61-109">この機能を使用するには、SRS v1 管理 Web ポータルをすべての Skype for Business Server フロントエンド サーバーに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b61-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="d0b61-110">このガイドでは、SRS 管理 Web ポータルをインストールおよび構成する方法について管理者向け手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="d0b61-111">これは、Skype for Business Server の管理に関する知識を持ち、Skype for Business Server トポロジを変更する管理者ユーザー権限を持つ管理者を対象にしています。</span><span class="sxs-lookup"><span data-stu-id="d0b61-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="d0b61-112">SRS v1 管理 Web ポータルがサーバーに展開された後、管理者は自分のコンピューターまたはノート PC からサイトにログオンすることで、SRS v1 デバイスの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0b61-113">Microsoft [Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015 をダウンロードします](https://www.microsoft.com/download/details.aspx?id=46906)。</span><span class="sxs-lookup"><span data-stu-id="d0b61-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="d0b61-114">このトピックの内容</span><span class="sxs-lookup"><span data-stu-id="d0b61-114">In this topic:</span></span>

- [<span data-ttu-id="d0b61-115">SRS v1 管理 Web ポータルの環境を構成する</span><span class="sxs-lookup"><span data-stu-id="d0b61-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="d0b61-116">SRS v1 管理 Web ポータルをインストールする</span><span class="sxs-lookup"><span data-stu-id="d0b61-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="d0b61-117">SRS 管理 Web ポータルを使用する</span><span class="sxs-lookup"><span data-stu-id="d0b61-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="d0b61-118">SRS v1 管理 Web ポータルの環境を構成する</span><span class="sxs-lookup"><span data-stu-id="d0b61-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="d0b61-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="d0b61-119"><a name="Config_Env"> </a></span></span>

<span data-ttu-id="d0b61-120">SRS v1 管理 Web ポータルを使用するには、次の前提条件をインストールまたは構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b61-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0b61-121">サーバーが Kerberos 認証と NTLM 認証の両方で構成され、SRS がドメインに参加していないコンピューターで実行されている場合、Kerberos 認証は失敗し、ユーザーは管理ポータルで SRS の状態を確認できません。</span><span class="sxs-lookup"><span data-stu-id="d0b61-121">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal.</span></span> <span data-ttu-id="d0b61-122">この問題を解決するには、NTLM 認証または NTLM 認証と TLS-DSK 認証 (Kerberos なし) の両方を使用してサーバーを構成するか、SRS コンピューターをドメインに参加します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-122">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="d0b61-123">Skype for Business Server の累積的な更新プログラムを Skype for Business Server トポロジにインストールします。</span><span class="sxs-lookup"><span data-stu-id="d0b61-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="d0b61-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="d0b61-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="d0b61-125">SIP 対応の Active Directory ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="d0b61-126">SRS v1 管理 Web ポータルは、これらの資格情報を使用して、Skype for Business Server からの情報を照会します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="d0b61-127">この例のユーザー名は LRSApp です。</span><span class="sxs-lookup"><span data-stu-id="d0b61-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="d0b61-128">LRSSupportAdminGroup という名前の Active Directory セキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="d0b61-129">グループ スコープをグローバル、グループの種類をセキュリティとして使用してグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-129">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="d0b61-130">このグループに追加された SIP が有効なユーザーは、ルームの一覧を表示し、ログの収集などの特定のコマンドを実行する権限を持つユーザーになります。</span><span class="sxs-lookup"><span data-stu-id="d0b61-130">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="d0b61-131">LRSFullAccessAdminGroup という名前の Active Directory セキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="d0b61-132">グループ スコープがグローバル、グループの種類が Security としてグループを作成します。このグループに追加された SIP 対応ユーザーは、単一の Skype ルームですべての管理ポータル機能を使用する権限を持つユーザーです。</span><span class="sxs-lookup"><span data-stu-id="d0b61-132">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room.</span></span> <span data-ttu-id="d0b61-133">Skype ルームの一括管理のサポートを含めるには、手順 5 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0b61-133">To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![セキュリティ グループの役割を持つ管理グループの一覧](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="d0b61-135">LRSPowerUserAdminsGroup という名前の Active Directory セキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="d0b61-136">グループ スコープをグローバル、グループの種類をセキュリティとして使用してグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="d0b61-137">このグループに追加された SIP 対応ユーザーは、Skype for Business ルームの一括管理を含むすべての管理ポータル機能を使用する権限を持っています。</span><span class="sxs-lookup"><span data-stu-id="d0b61-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="d0b61-138">LRSFullAccessAdminGroup を LRSSupportAdminGroup のメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup プロパティ のメンバー ページ](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="d0b61-140">LRSSupport という名前の SIP 対応 Active Directory ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="d0b61-141">このユーザーを LRSSupportAdminGroup に追加します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup プロパティ のメンバー ページ](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="d0b61-143">[MVC 4 ASP.NET 2010 SP1 Visual Studio Visual Web Developer 2010 SP1 をインストールします](https://go.microsoft.com/fwlink/p/?LinkId=323967)。</span><span class="sxs-lookup"><span data-stu-id="d0b61-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="d0b61-144">SRS v1 管理 Web ポータルをインストールする</span><span class="sxs-lookup"><span data-stu-id="d0b61-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="d0b61-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="d0b61-145"><a name="Install_SRS"> </a></span></span>

<span data-ttu-id="d0b61-146">Microsoft [Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015 をダウンロードします](https://www.microsoft.com/download/details.aspx?id=46906)。</span><span class="sxs-lookup"><span data-stu-id="d0b61-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="d0b61-147">SRS v1 管理 Web ポータルをインストールするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="d0b61-148">Skype for Business Server 管理シェルで次のコマンドレットを実行して、信頼済みアプリケーション ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="d0b61-149">ミーティング ルーム ポータルをインストールするには **、MeetingRoomPortalInstaller.msiを** ダウンロードし、管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="d0b61-150">次の場所Web.configファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="d0b61-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="d0b61-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="d0b61-152">Web.Config ファイルで、PortalUserName を[「SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)管理 Web ポータル用に環境を構成する」セクションの手順 2 で作成したユーザー名に変更します (手順の推奨名は LRSApp です)。</span><span class="sxs-lookup"><span data-stu-id="d0b61-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="d0b61-153">SRS v1 管理ポータルは信頼されたアプリケーションなので、ポータル構成でパスワードを入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d0b61-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="d0b61-154">このユーザーがローカル レジストラーとは異なるレジストラーを使用している場合は、次の行をローカル レジストラー ファイルに追加して、そのレジストラーを指定Web.Configがあります。</span><span class="sxs-lookup"><span data-stu-id="d0b61-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="d0b61-155">使用するポートが 5061 以外の場合は、次の行をファイルWeb.Configします。</span><span class="sxs-lookup"><span data-stu-id="d0b61-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="d0b61-156">SRS 管理 Web ポータルのインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="d0b61-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="d0b61-157">SRS v1 管理 Web ポータルのインストールを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="d0b61-158">フロントエンド サーバーで、次の URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="d0b61-159">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="d0b61-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="d0b61-160">次の図に示すように、エラーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="d0b61-160">You should not see any errors, as shown in the following image:</span></span>

     ![Lync Room System 管理ポータルのサインイン画面](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="d0b61-162">エラーが表示されない場合は、トポロジ内の他のコンピューターから次の URL にアクセスしてみてください。</span><span class="sxs-lookup"><span data-stu-id="d0b61-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="d0b61-163">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="d0b61-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="d0b61-164">このページにアクセスするには、「クライアントの自動サインインに必要な DNS レコード」の説明に従って DNS レコード[を追加する必要があります](https://go.microsoft.com/fwlink/p/?LinkId=318056)。</span><span class="sxs-lookup"><span data-stu-id="d0b61-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="d0b61-165">SRS 管理 Web ポータルを使用する</span><span class="sxs-lookup"><span data-stu-id="d0b61-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="d0b61-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="d0b61-166"><a name="Use_Portal"> </a></span></span>

<span data-ttu-id="d0b61-167">サーバーに SRS を展開した後、ブラウザーから SRS v1 管理 Web ポータルにサインインすることで、すべての SRS ルームの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="d0b61-168">サインイン</span><span class="sxs-lookup"><span data-stu-id="d0b61-168">Sign in</span></span>

1. <span data-ttu-id="d0b61-169">次の URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-169">Browse to the following URL:</span></span>

    <span data-ttu-id="d0b61-170">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="d0b61-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="d0b61-171">LRSSupport アカウントの資格情報、または LRSSupportAdminGroup セキュリティ グループに追加されたアカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Lync Room System 管理ポータルのサインイン画面](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="d0b61-173">SRS 管理 Web ポータルの概要ページ</span><span class="sxs-lookup"><span data-stu-id="d0b61-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="d0b61-174">概要ページには、サーバーに展開されている SRS ルームのすべてについて、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="d0b61-175">**Tag** 管理者がルームに指定するカスタム名。</span><span class="sxs-lookup"><span data-stu-id="d0b61-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="d0b61-176">ポータルでルーム名をクリックすると、タグを設定できます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="d0b61-177">**正常性** ルームの正常性状態。これは、ルームの集計正常性状態から派生します。これは、[ルームの設定] ページの [正常性] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="d0b61-178">**次の会議** 次の会議が予定されている日時。</span><span class="sxs-lookup"><span data-stu-id="d0b61-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="d0b61-179">**SRS バージョン、製造元、モデル** これらの値は SRS で事前に設定されています。</span><span class="sxs-lookup"><span data-stu-id="d0b61-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="d0b61-180">製造元によっては、これらのフィールドが空白のままになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0b61-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="d0b61-181">**Last Refresh** Web ページが最後に更新された時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Lync Room System 管理ポータルの概要ビュー](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="d0b61-183">LRSPowerUserAdminsGroup セキュリティ グループに参加している場合にのみ、[一括管理] メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="d0b61-184">SRS ルーム情報</span><span class="sxs-lookup"><span data-stu-id="d0b61-184">SRS Room Information</span></span>

<span data-ttu-id="d0b61-185">ポータルの [会議室情報] セクションでは、個々の SRS ルームを表示および構成できます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="d0b61-186">このセクションには、設定、詳細、ログ記録、正常性の 4 つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="d0b61-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="d0b61-187">設定</span><span class="sxs-lookup"><span data-stu-id="d0b61-187">Settings</span></span>

<span data-ttu-id="d0b61-188">[設定] セクションでは、パスワード、ルーム タグ、およびルームの既定のボリューム レベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="d0b61-189">これらの設定を構成した場合、変更は SRS コンソールを再起動した後にのみレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="d0b61-190">リリース 15.12 以降を使用している SRS デバイスのシステム更新設定だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Lync Room System 管理ポータル ルームの設定](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="d0b61-192">詳細</span><span class="sxs-lookup"><span data-stu-id="d0b61-192">Details</span></span>

<span data-ttu-id="d0b61-193">[詳細] セクションでは、SRS ルームの設定の読み取り専用の概要を示します。次に、最終更新時刻を示します。次の会議最後の更新、メンテナンス、調整既定のスピーカー、マイク、および呼び出し音の設定version;SIP URI;画面の数と各画面の詳細状態、およびアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="d0b61-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Lync Room System 管理ポータル詳細ビュー](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="d0b61-195">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d0b61-195">Troubleshooting</span></span>

<span data-ttu-id="d0b61-196">[トラブルシューティング] セクションを使用して、ログをリモートで収集し、指定した場所に保存できます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="d0b61-197">SRS コンソール (SRS ユーザー インターフェイス) を再起動するか、システム全体を再起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="d0b61-198">ログを収集するには、指定した形式のフォルダー パスを指定し、フォルダーに SRS コンピューター アカウントに与えられる書き込みアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b61-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="d0b61-199">ログ サイズが大きすぎる場合、ログの収集が完了するには最大 5 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0b61-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="d0b61-200">ページを更新すると、最新の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="d0b61-201">正常性</span><span class="sxs-lookup"><span data-stu-id="d0b61-201">Health</span></span>

<span data-ttu-id="d0b61-202">[正常性] セクションでは、Skype for Business Server 接続、オーディオ デバイス、ビデオ デバイス、復元状態、画面デバイスの正常性を視覚的に示します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Lync Room System 管理ポータル ルームの正常性](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="d0b61-204">管理 Web ポータルに関するその他の注意事項</span><span class="sxs-lookup"><span data-stu-id="d0b61-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="d0b61-205">設定の変更は、SRS システムを再起動した後にのみ適用されます。> LRSApp アカウントのパスワードの有効期限が切れると、ルームの状態を確認できません。</span><span class="sxs-lookup"><span data-stu-id="d0b61-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="d0b61-206">LRSAppuser アカウントパスワードを構成して、有効期限が切れることはありません。または、有効期限が近い場合は必ずパスワードを更新してください。> SRS 管理 Web ポータルは、オンプレミス展開でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d0b61-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="d0b61-207">一括管理</span><span class="sxs-lookup"><span data-stu-id="d0b61-207">Bulk management</span></span>

<span data-ttu-id="d0b61-208">SRS ルームの一括管理は、高度な IT 管理者向けに設計された機能で、ワークフローを簡素化し、時間の節約に便利なツールを使用して複数のルームを一括でリモートで管理できます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="d0b61-209">この機能を表示するには、ユーザーを特別なセキュリティ グループ **LRSPowerUserAdminsGroup** のメンバーとしてプロビジョニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b61-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="d0b61-210">一括管理用に選択できる SRS ルームの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="d0b61-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="d0b61-211">ただし、一度に実行できる一括管理操作は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="d0b61-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="d0b61-212">一括管理操作を実行するには、監視するルームを選択し、[一括管理] メニューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0b61-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="d0b61-213">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="d0b61-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="d0b61-214">管理 Web ポータルにサインインできない理由</span><span class="sxs-lookup"><span data-stu-id="d0b61-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="d0b61-215">When you https://localhost/lrs open, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span><span class="sxs-lookup"><span data-stu-id="d0b61-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="d0b61-216">この場合は、管理 Web ポータル https://FQDNofFEserver/SRS にサインインするために開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b61-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="d0b61-217">管理 Web ポータルで SRS v1 が表示できない理由</span><span class="sxs-lookup"><span data-stu-id="d0b61-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="d0b61-218">展開に SRS アカウントが含み、SRS 管理 Web ポータルの展開に関する推奨事項に従って作成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b61-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="d0b61-219">Skype for Business Server で Enable-CsUser ではなく Enable-CsMeetingRoom を使用して SRS アカウントがプロビジョニングされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b61-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="d0b61-220">SRS アカウントを作成し、管理 Web ポータルでアカウントを表示できない場合は、Skype for Business Server ログ ツールを使用して **MeetingPortal** コンポーネントを選択してサーバー ログを収集し、SRS サポート連絡先に送信します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="d0b61-221">SRS アカウントを作成し、管理 Web ポータルでアカウントを表示できない場合は、Fiddler を使用してクライアント ログを収集し、ブラウザー開発ツールからコンソール ログをコピーしてから、SRS サポート連絡先に送信します。</span><span class="sxs-lookup"><span data-stu-id="d0b61-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="d0b61-222">さらに詳細なログを取得するには、Web.configのトレース レベルの値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d0b61-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="d0b61-223">管理 Web ポータルで SRS の状態が表示できない理由</span><span class="sxs-lookup"><span data-stu-id="d0b61-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="d0b61-224">LRSApp ユーザー アカウントが SIP 対応になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b61-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="d0b61-225">引き続き問題が発生する場合は、D:\Tracing\LRSAdminLogs から SRS システムの **Trace.log** ファイルを収集し、SRS サポート連絡先に送信します。 \,</span><span class="sxs-lookup"><span data-stu-id="d0b61-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="d0b61-226">管理 Web ポータルで SRS の一括管理メニューが表示できない理由</span><span class="sxs-lookup"><span data-stu-id="d0b61-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="d0b61-227">LRSApp ユーザー アカウントが SIP 対応であり、LRSPowerUserAdminsGroup セキュリティ グループの一部になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b61-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="d0b61-228">SRS v1 管理 Web ポータルは Microsoft Teams Rooms で動作しますか?</span><span class="sxs-lookup"><span data-stu-id="d0b61-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="d0b61-229">いいえ。</span><span class="sxs-lookup"><span data-stu-id="d0b61-229">No.</span></span>


