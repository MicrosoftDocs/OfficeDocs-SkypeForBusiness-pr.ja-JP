---
title: Skype for Business Server での SRS v1 管理 Web ポータルの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Skype for Business Server Skype Room Systems v1 (旧称 Lync Room System) 管理 Web ポータルは、組織が Skype Room Systems の会議室を維持するために使用できる web ポータルです。 管理者は、SRS v1 管理 Web ポータルを使用して、デバイスの正常性を監視できます (オーディオ/ビデオデバイスの監視など)。 このポータルを使用すると、管理者はリモートで診断情報を収集して、会議室の状態を監視できます。
ms.openlocfilehash: d718adb60437fdd7e08724a5ba5fc48fa120425e
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "42045900"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="2f9c7-105">Skype for Business Server での SRS v1 管理 Web ポータルの展開</span><span class="sxs-lookup"><span data-stu-id="2f9c7-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="2f9c7-106">Skype for Business Server Skype Room Systems v1 (旧称 Lync Room System) 管理 Web ポータルは、組織が Skype Room Systems の会議室を維持するために使用できる web ポータルです。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="2f9c7-107">管理者は、SRS v1 管理 Web ポータルを使用して、デバイスの正常性を監視できます (オーディオ/ビデオデバイスの監視など)。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="2f9c7-108">このポータルを使用すると、管理者はリモートで診断情報を収集して、会議室の状態を監視できます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="2f9c7-109">この機能を使用するには、すべての Skype for Business Server フロントエンドサーバーに SRS v1 管理 Web ポータルを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="2f9c7-110">このガイドでは、管理者が SRS 管理 Web ポータルをインストールおよび構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="2f9c7-111">Skype for business Server の管理について理解している管理者と、Skype for Business Server のトポロジを変更するための管理者ユーザー権限を持つ管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="2f9c7-112">SRS v1 管理 Web ポータルがサーバーに展開されると、管理者は、自分のコンピューターまたはラップトップからサイトにログオンすることによって、ステータス SRS v1 デバイスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f9c7-113">Skype for business [Server 2015 の Microsoft Skype Room Systems V1 管理 Web ポータルを](https://www.microsoft.com/download/details.aspx?id=46906)ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="2f9c7-114">このトピックの内容</span><span class="sxs-lookup"><span data-stu-id="2f9c7-114">In this topic:</span></span>

- [<span data-ttu-id="2f9c7-115">SRS v1 管理 Web ポータルの環境を構成する</span><span class="sxs-lookup"><span data-stu-id="2f9c7-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="2f9c7-116">SRS v1 管理 Web ポータルをインストールする</span><span class="sxs-lookup"><span data-stu-id="2f9c7-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="2f9c7-117">SRS 管理 Web ポータルを使用する</span><span class="sxs-lookup"><span data-stu-id="2f9c7-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="2f9c7-118">SRS v1 管理 Web ポータルの環境を構成する</span><span class="sxs-lookup"><span data-stu-id="2f9c7-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="2f9c7-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="2f9c7-119"><a name="Config_Env"> </a></span></span>

<span data-ttu-id="2f9c7-120">SRS v1 管理 Web ポータルを使用するには、次の前提条件をインストールまたは構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f9c7-121">サーバーが Kerberos 認証と NTLM 認証の両方を使用して構成されていて、ドメインに参加していないコンピューター上で SRS が実行されている場合、Kerberos 認証が失敗し、ユーザーには管理ポータルの SRS の状態が表示されません。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-121">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal.</span></span> <span data-ttu-id="2f9c7-122">この問題を解決するには、サーバーを NTLM 認証または NTLM と DSK 認証 (Kerberos を使用しない) の両方で構成するか、または SRS コンピューターをドメインに参加させます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-122">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="2f9c7-123">Skype for business Server トポロジで Skype for Business Server の累積的な更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="2f9c7-124">更新プログラムを入手するには、「 [Skype For Business Server 2015 の](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)更新プログラム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="2f9c7-125">SIP 対応の Active Directory ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="2f9c7-126">SRS v1 管理 Web ポータルは、これらの資格情報を使用して Skype for Business Server から情報を照会します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="2f9c7-127">指定された例のユーザー名は LRSApp です。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="2f9c7-128">LRSSupportAdminGroup という名前の Active Directory セキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="2f9c7-129">グループスコープを持つグループを [グローバル] および [グループの種類] としてセキュリティとして作成します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-129">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="2f9c7-130">このグループに追加される SIP 対応ユーザーは、ルームのリストを確認し、ログの収集などの特定のコマンドを実行することを承認されます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-130">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="2f9c7-131">LRSFullAccessAdminGroup という名前の Active Directory セキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="2f9c7-132">グループスコープを持つグループを [グローバル] および [グループの種類] として [セキュリティ] として作成します。このグループに追加される SIP 対応ユーザーは、1つの Skype 会議室ですべての管理ポータル機能を使用することを承認されています。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-132">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room.</span></span> <span data-ttu-id="2f9c7-133">Skype ルームの一括管理のサポートを含めるには、手順5を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-133">To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![セキュリティグループの役割を持つ管理グループの一覧](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="2f9c7-135">LRSPowerUserAdminsGroup という名前の Active Directory セキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="2f9c7-136">グループスコープを持つグループを [グローバル] および [グループの種類] としてセキュリティとして作成します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="2f9c7-137">このグループに追加された SIP 対応ユーザーは、Skype for Business ルームの一括管理を含む、すべての管理ポータル機能を使用することを承認されています。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="2f9c7-138">LRSFullAccessAdminGroup を LRSSupportAdminGroup のメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup Properties メンバーページ](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="2f9c7-140">LRSSupport という名前の SIP 対応 Active Directory ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="2f9c7-141">このユーザーを LRSSupportAdminGroup に追加します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup Properties メンバーページ](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="2f9c7-143">[ASP.NET MVC 4 For Visual Studio 2010 sp1 および Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="2f9c7-144">SRS v1 管理 Web ポータルをインストールする</span><span class="sxs-lookup"><span data-stu-id="2f9c7-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="2f9c7-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="2f9c7-145"><a name="Install_SRS"> </a></span></span>

<span data-ttu-id="2f9c7-146">Skype for business [Server 2015 の Microsoft Skype Room Systems V1 管理 Web ポータルを](https://www.microsoft.com/download/details.aspx?id=46906)ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="2f9c7-147">SRS v1 管理 Web ポータルをインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="2f9c7-148">Skype for Business Server 管理シェルで次のコマンドレットを実行して、信頼されたアプリケーションポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="2f9c7-149">会議室ポータルをインストールするには、 **MeetingRoomPortalInstaller**をダウンロードして、管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="2f9c7-150">Web.config ファイルを次の場所から開きます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="2f9c7-151">% Program Files%\Skype for Business Server 2015 (Web Components\Meeting Room Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="2f9c7-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="2f9c7-152">Web.config ファイルで、PortalUserName を次の手順2で作成したユーザー名に変更します。セクション「[SRS V1 管理 Web ポータルの環境を構成する](room-system-v1-administrative-web-portal.md#Config_Env)」 (手順は LRSApp の推奨名)。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="2f9c7-153">SRS v1 管理ポータルは信頼されたアプリケーションなので、portal 構成でパスワードを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="2f9c7-154">このユーザーがローカルレジストラーとは別のレジストラーを使用している場合は、Web.config ファイルに次の行を追加して、レジストラーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="2f9c7-155">使用しているポートが5061以外の場合は、web.config ファイルに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="2f9c7-156">SRS 管理 Web ポータルのインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="2f9c7-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="2f9c7-157">SRS v1 管理 Web ポータルのインストールを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="2f9c7-158">フロントエンドサーバーで、次の URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="2f9c7-159">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="2f9c7-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="2f9c7-160">次の図に示すように、エラーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-160">You should not see any errors, as shown in the following image:</span></span>

     ![Lync Room System 管理者ポータルのサインイン画面](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="2f9c7-162">エラーが表示されない場合は、トポロジ内の他のコンピュータから次の URL にアクセスしてみてください。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="2f9c7-163">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="2f9c7-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="2f9c7-164">ページにアクセスするには、「[自動クライアントサインインに必要な Dns レコード](https://go.microsoft.com/fwlink/p/?LinkId=318056)」の説明に従って、dns レコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="2f9c7-165">SRS 管理 Web ポータルを使用する</span><span class="sxs-lookup"><span data-stu-id="2f9c7-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="2f9c7-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="2f9c7-166"><a name="Use_Portal"> </a></span></span>

<span data-ttu-id="2f9c7-167">サーバーに SRS を展開した後、ブラウザーから SRS v1 管理 Web ポータルにサインインして、すべての SRS ルームの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="2f9c7-168">サインイン</span><span class="sxs-lookup"><span data-stu-id="2f9c7-168">Sign in</span></span>

1. <span data-ttu-id="2f9c7-169">次の URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-169">Browse to the following URL:</span></span>

    <span data-ttu-id="2f9c7-170">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="2f9c7-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="2f9c7-171">LRSSupport アカウントの資格情報、または LRSSupportAdminGroup セキュリティグループに追加されたアカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Lync Room System 管理者ポータルのサインイン画面](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="2f9c7-173">SRS 管理 Web ポータルの概要ページ</span><span class="sxs-lookup"><span data-stu-id="2f9c7-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="2f9c7-174">概要ページには、サーバーに展開されているすべての SRS ルームに関する次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="2f9c7-175">**タグ**管理者がルームに付与するカスタム名。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="2f9c7-176">タグは、ルーム名をクリックすることで、ポータルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="2f9c7-177">**正常性**ルームの正常性の状態。会議室の設定ページの [正常性] セクションに表示されている、会議室の状態の総計から導出されます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="2f9c7-178">**次の会議**次の会議がスケジュールされた日時。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="2f9c7-179">**SRS のバージョン、製造元、モデル**これらの値は、SRS で事前設定されています。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="2f9c7-180">製造元によっては、これらのフィールドが空白のままになっている場合があります。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="2f9c7-181">**最終更新**Web ページが最後に更新された日時を表示します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Lync Room System 管理ポータルの概要ビュー](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="2f9c7-183">LRSPowerUserAdminsGroup セキュリティグループに属している場合にのみ、[一括管理] メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="2f9c7-184">SRS ルーム情報</span><span class="sxs-lookup"><span data-stu-id="2f9c7-184">SRS Room Information</span></span>

<span data-ttu-id="2f9c7-185">ポータルの [Room Info] セクションでは、個々の SRS ルームを表示および構成できます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="2f9c7-186">このセクションには、[設定]、[詳細]、[ログ]、[正常性] の4つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="2f9c7-187">設定</span><span class="sxs-lookup"><span data-stu-id="2f9c7-187">Settings</span></span>

<span data-ttu-id="2f9c7-188">[設定] セクションでは、ルームのパスワード、会議室タグ、および既定の音量レベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="2f9c7-189">これらの設定を構成した場合、変更は SRS コンソールを再起動した後にのみレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="2f9c7-190">SRS デバイスのシステム更新設定は、リリース15.12 以降を使用してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Lync Room System 管理ポータルルームの設定](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="2f9c7-192">詳細</span><span class="sxs-lookup"><span data-stu-id="2f9c7-192">Details</span></span>

<span data-ttu-id="2f9c7-193">[詳細] セクションには、SRS ルームの設定の読み取り専用の概要が表示されます。これには、最終更新日時が含まれます。次の会議。最終更新、メンテナンス、調整、既定のスピーカー、マイク、および着信音の設定。4.0SIP URI。画面の数と各画面の詳細。状態、およびアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Lync Room System 管理ポータル詳細ビュー](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="2f9c7-195">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2f9c7-195">Troubleshooting</span></span>

<span data-ttu-id="2f9c7-196">トラブルシューティングのセクションは、ログをリモートで収集し、指定した場所に保存するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="2f9c7-197">SRS コンソール (SRS ユーザーインターフェイス) を再起動するか、システム全体を再起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="2f9c7-198">ログを収集するには、指定された形式のフォルダーパスを指定し、SRS コンピューターアカウントに指定された書き込み権限がフォルダーにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="2f9c7-199">ログサイズが大きすぎる場合は、ログの収集が完了するまでに最大5分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="2f9c7-200">ページを更新すると、最新の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="2f9c7-201">正常性</span><span class="sxs-lookup"><span data-stu-id="2f9c7-201">Health</span></span>

<span data-ttu-id="2f9c7-202">[正常性] セクションには、Skype for Business Server の接続、オーディオデバイス、ビデオデバイス、復元状態、画面デバイスの状態が視覚的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Lync Room System 管理ポータルルームの正常性](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="2f9c7-204">管理 Web ポータルに関するその他の注意事項</span><span class="sxs-lookup"><span data-stu-id="2f9c7-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="2f9c7-205">設定変更は、SRS システムが再起動された後にのみ適用されます。 LRSApp アカウントのパスワードの有効期限が切れた場合、ルームの状態を表示することはできません。 >。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="2f9c7-206">LRSAppuser アカウントのパスワードを有効期限切れにならないように構成するか、有効期限が近づいたときにパスワードを更新してください。 >、SRS 管理 web ポータルは社内展開でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="2f9c7-207">一括管理</span><span class="sxs-lookup"><span data-stu-id="2f9c7-207">Bulk management</span></span>

<span data-ttu-id="2f9c7-208">SRS ルームの一括管理は、高度な IT 管理者向けに設計された機能で、ワークフローを簡素化し、複数の部屋を一括で管理するための便利な時間を節約することができます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="2f9c7-209">この機能を確認するには、ユーザーが特別なセキュリティグループ**LRSPowerUserAdminsGroup**のメンバーとしてプロビジョニングされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="2f9c7-210">一括管理のために選択できる SRS ルームの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="2f9c7-211">ただし、一度に実行できる一括管理操作は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="2f9c7-212">一括管理操作を実行するには、監視するルームを選択し、[一括管理] メニューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="2f9c7-213">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="2f9c7-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="2f9c7-214">管理 web ポータルにサインインできないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="2f9c7-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="2f9c7-215">を開くと、 https://localhost/lrs サインインページを表示できるようになりますが、サインイン情報を入力するときにサインインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="2f9c7-216">この場合は、 https://FQDNofFEserver/SRS を開いて、管理 web ポータルにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="2f9c7-217">管理 web ポータルで SRS v1 が表示されないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="2f9c7-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="2f9c7-218">展開に SRS アカウントがあり、SRS の管理 Web ポータルの展開に関する推奨事項に従って作成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="2f9c7-219">Skype for Business Server で、SRS アカウントが、Enable-CsUser ではなく、enable-Csの会議室を使用してプロビジョニングされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="2f9c7-220">SRS アカウントを作成済みで、管理 web ポータルにアカウントが表示されていない場合は、「Skype for Business Server Logging tool」を使用してサーバーログを収集し、[**会議ポータル**] コンポーネントを選択した後、それを srs サポート連絡先に送信します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="2f9c7-221">SRS アカウントを作成済みで、管理 web ポータルにアカウントが表示されない場合は、Fiddler を使用してクライアントログを収集し、ブラウザー開発ツールからコンソールログをコピーしてから、SRS サポート連絡先に送信します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="2f9c7-222">Web.config でトレースレベルの値を変更して、より詳細なログを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="2f9c7-223">管理 web ポータルで SRS の状態を確認できないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="2f9c7-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="2f9c7-224">LRSApp ユーザーアカウントの SIP が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="2f9c7-225">それでも問題が解決しない場合は、D:\Tracing\LRSAdminLogs から SRS システムの**トレースログ**ファイルを収集して、 \, srs サポート連絡先に送信します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="2f9c7-226">管理 web ポータルで SRS のバルク管理メニューが表示されないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="2f9c7-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="2f9c7-227">LRSApp ユーザーアカウントが SIP 対応で、LRSPowerUserAdminsGroup セキュリティグループの一部であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="2f9c7-228">SRS v1 管理 web ポータルは Microsoft Teams ルームと連携していますか?</span><span class="sxs-lookup"><span data-stu-id="2f9c7-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="2f9c7-229">いいえ。</span><span class="sxs-lookup"><span data-stu-id="2f9c7-229">No.</span></span>


