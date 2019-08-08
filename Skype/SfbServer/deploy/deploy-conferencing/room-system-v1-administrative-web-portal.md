---
title: Skype for Business Server で SRS v1 管理 Web ポータルを展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Skype for Business Server の Skype Room Systems v1 (旧称 SRS v1、旧称 Lync Room System) 管理 Web ポータルは、組織が Skype Room Systems 会議室を管理するために使用できる web ポータルです。 管理者は、SRS v1 管理 Web ポータルを使用して、オーディオ/ビデオデバイスを監視するなどして、デバイスの正常性を監視することができます。 このポータルでは、管理者はリモートで診断情報を収集して、会議室の正常性を監視することができます。
ms.openlocfilehash: bf18cefbdaa5beeaef63d16b5447cce2969fc147
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234176"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="f6ebc-105">Skype for Business Server で SRS v1 管理 Web ポータルを展開する</span><span class="sxs-lookup"><span data-stu-id="f6ebc-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="f6ebc-106">Skype for Business Server の Skype Room Systems v1 (旧称 SRS v1、旧称 Lync Room System) 管理 Web ポータルは、組織が Skype Room Systems 会議室を管理するために使用できる web ポータルです。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="f6ebc-107">管理者は、SRS v1 管理 Web ポータルを使用して、オーディオ/ビデオデバイスを監視するなどして、デバイスの正常性を監視することができます。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="f6ebc-108">このポータルでは、管理者はリモートで診断情報を収集して、会議室の正常性を監視することができます。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="f6ebc-109">この機能を使用するには、SRS v1 管理 Web ポータルをすべての Skype for Business Server フロントエンドサーバーに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="f6ebc-110">このガイドでは、管理者向けに SRS 管理 Web ポータルのインストールおよび設定方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="f6ebc-111">これは、Skype for Business Server の管理について知識を持っている管理者、および Skype for Business Server トポロジを変更する管理者のユーザー権限を持つ管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="f6ebc-112">SRS v1 管理 Web ポータルをサーバーに展開した後、管理者は、自分のコンピューターまたはノート pc からサイトにログオンして、状態の SRS v1 デバイスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6ebc-113">Skype for [Business Server 2015 の Microsoft Skype Room Systems V1 管理 Web ポータル](https://www.microsoft.com/en-us/download/details.aspx?id=46906)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="f6ebc-114">このトピックでは、以下について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-114">In this topic:</span></span>

- [<span data-ttu-id="f6ebc-115">SRS v1 管理 Web ポータルの環境の構成</span><span class="sxs-lookup"><span data-stu-id="f6ebc-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="f6ebc-116">SRS v1 管理 Web ポータルのインストール</span><span class="sxs-lookup"><span data-stu-id="f6ebc-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="f6ebc-117">SRS 管理 Web ポータルの使用</span><span class="sxs-lookup"><span data-stu-id="f6ebc-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="f6ebc-118">SRS v1 管理 Web ポータルの環境の構成</span><span class="sxs-lookup"><span data-stu-id="f6ebc-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="f6ebc-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="f6ebc-119"></span></span>

<span data-ttu-id="f6ebc-120">SRS v1 管理 Web ポータルを使用するには、次の前提条件をインストールまたは構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6ebc-p104">サーバーが Kerberos 認証と NTLM 認証の両方で構成されており、SRS がドメインに参加していないコンピューターで実行されている場合、Kerberos 認証は失敗し、管理ポータルで SRS のステータスを見ることはできません。この問題を解決するには、NTLM 認証、または NTLM 認証と TLS-DSK 認証の両方で (Kerberos を使って) サーバーを構成するか、SRS コンピューターをドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-p104">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal. To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="f6ebc-123">Skype for business Server トポロジで Skype for Business Server の累積的な更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="f6ebc-124">更新プログラムを入手したり、アプリに含まれている内容を確認したりするには、「 [Skype For Business Server 2015 の更新プログラム](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="f6ebc-125">SIP 対応の Active Directory ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="f6ebc-126">SRS v1 管理 Web ポータルでは、これらの資格情報を使用して、Skype for Business Server から情報を照会します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="f6ebc-127">ここでの例のユーザー名は LRSApp です。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="f6ebc-128">LRSSupportAdminGroup という名前の Active Directory セキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="f6ebc-p106">[グループのスコープ] が [グローバル]、[グループの種類] が [セキュリティ] のグループを作成します。このグループに追加される SIP 対応ユーザーは、部屋の一覧を参照したり、ログの収集などの特定のコマンドを実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-p106">Create the group with Group Scope as Global and Group Type as Security. SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="f6ebc-131">LRSFullAccessAdminGroup という名前の Active Directory セキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="f6ebc-p107">[グループのスコープ] が [グローバル]、[グループの種類] が [セキュリティ] のグループを作成します。このグループに追加される SIP 対応ユーザーは、単一の Skype ルームで管理ポータルのすべての機能を使用できます。Skype ルームの一括管理のサポートを含める場合は、手順 5 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-p107">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room. To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![セキュリティ グループの役割を持つ Admin グループの一覧](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="f6ebc-135">LRSPowerUserAdminsGroup という名前の Active Directory セキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="f6ebc-136">[グループのスコープ] が [グローバル]、[グループの種類] が [セキュリティ] のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="f6ebc-137">このグループに追加された SIP 対応ユーザーは、Skype for Business 会議室の一括管理を含むすべての管理ポータル機能を使用することを許可されています。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="f6ebc-138">LRSFullAccessAdminGroup を LRSSupportAdminGroup のメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup プロパティ メンバー ページ](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="f6ebc-140">LRSSupport という名前の SIP 対応の Active Directory ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="f6ebc-141">このユーザーを LRSSupportAdminGroup に追加します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup プロパティ メンバー ページ](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="f6ebc-143">[Visual Studio 2010 sp1 と Visual Web Developer 2010 SP1 用の ASP.NET MVC 4 を](https://go.microsoft.com/fwlink/p/?LinkId=323967)インストールします。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="f6ebc-144">SRS v1 管理 Web ポータルのインストール</span><span class="sxs-lookup"><span data-stu-id="f6ebc-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="f6ebc-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="f6ebc-145"></span></span>

<span data-ttu-id="f6ebc-146">Skype for [Business Server 2015 の Microsoft Skype Room Systems V1 管理 Web ポータル](https://www.microsoft.com/en-us/download/details.aspx?id=46906)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="f6ebc-147">SRS v1 管理 Web ポータルをインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="f6ebc-148">Skype for Business Server 管理シェルで次のコマンドレットを実行して、信頼できるアプリケーションポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="f6ebc-149">会議室ポータルをインストールするには、**MeetingRoomPortalInstaller.msi** をダウンロードして管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="f6ebc-150">Web.config ファイルを次の場所から開きます。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="f6ebc-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="f6ebc-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="f6ebc-152">Web.config ファイルで、PortalUserName を「[SRS V1 管理 Web ポータルの環境を構成](room-system-v1-administrative-web-portal.md#Config_Env)する」セクションの「手順2で作成したユーザー名に変更します (手順は LRSApp の推奨名)。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="f6ebc-p110">SRS v1 管理ポータルは信頼済みアプリケーションであるため、ポータルの構成でパスワードを提示する必要はありません。このユーザーがローカル レジストラーとは別のレジストラーを使用している場合、Web.Config ファイルで次の行を追加してレジストラを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-p110">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration. If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="f6ebc-155">5061 以外のポートが使用されている場合は、Web.Config ファイルに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="f6ebc-156">SRS 管理 Web ポータルのインストールの検証</span><span class="sxs-lookup"><span data-stu-id="f6ebc-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="f6ebc-157">SRS v1 管理 Web ポータルのインストールを検証するには、次を行います。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="f6ebc-158">フロントエンド サーバーで、次の URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="f6ebc-159">https://\<fe-サーバー\>/lrs</span><span class="sxs-lookup"><span data-stu-id="f6ebc-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="f6ebc-160">下記の画像のように、エラーが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-160">You should not see any errors, as shown in the following image:</span></span>

     ![Lync Room System、管理用ポータル サインイン画面](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="f6ebc-162">エラーが表示されない場合は、トポロジ内の他のいずれかのコンピューターから次の URL へのアクセスを試行します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="f6ebc-163">https://\<fe-サーバー\>/lrs</span><span class="sxs-lookup"><span data-stu-id="f6ebc-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="f6ebc-164">ページにアクセスするには、「[自動クライアントサインインのために必要な Dns レコード](https://go.microsoft.com/fwlink/p/?LinkId=318056)」の説明に従って DNS レコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="f6ebc-165">SRS 管理 Web ポータルの使用</span><span class="sxs-lookup"><span data-stu-id="f6ebc-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="f6ebc-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="f6ebc-166"></span></span>

<span data-ttu-id="f6ebc-167">サーバーで SRS を展開した後、ブラウザーから SRS v1 管理 Web ポータルにサインインして、すべての SRS ルームの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="f6ebc-168">サインイン</span><span class="sxs-lookup"><span data-stu-id="f6ebc-168">Sign in</span></span>

1. <span data-ttu-id="f6ebc-169">次の URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-169">Browse to the following URL:</span></span>

    <span data-ttu-id="f6ebc-170">https://\<fe-サーバー\>/lrs</span><span class="sxs-lookup"><span data-stu-id="f6ebc-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="f6ebc-171">LRSSupport アカウントの資格情報、または LRSSupportAdminGroup セキュリティ グループに追加されたアカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Lync Room System、管理用ポータル サインイン画面](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="f6ebc-173">SRS 管理 Web ポータルの概要ページ</span><span class="sxs-lookup"><span data-stu-id="f6ebc-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="f6ebc-174">この概要ページには、サーバーで展開されたすべての SRS ルームに関する次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="f6ebc-175">**タグ**管理者によってルームに付与されたカスタム名。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="f6ebc-176">ルームの名前をクリックすると、ポータルでタグを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="f6ebc-177">**正常性**会議室の正常性状態。会議室の [正常性] セクションの下に表示される、会議室の正常性状態。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="f6ebc-178">**次回の会議**次の会議がスケジュールされた日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="f6ebc-179">**SRS のバージョン、製造元、モデル**これらの値は、SRS で事前設定されています。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="f6ebc-180">製造元によって、これらのフィールドは空白のままである場合があります。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="f6ebc-181">**最終更新**Web ページが最後に更新された時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Lync Room System、管理用ポータル概要ビュー](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="f6ebc-183">LRSPowerUserAdminsGroup セキュリティグループの一部である場合にのみ、一括管理メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="f6ebc-184">SRS ルーム情報</span><span class="sxs-lookup"><span data-stu-id="f6ebc-184">SRS Room Information</span></span>

<span data-ttu-id="f6ebc-p113">ポータルの [ルーム情報] セクションでは、個々の SRS ルームを表示および構成することができます。これには、[設定]、[詳細]、[ログ記録]、[動作状態] の 4 つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-p113">The Room Info section of the portal allows you to view and configure individual SRS rooms. It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="f6ebc-187">設定</span><span class="sxs-lookup"><span data-stu-id="f6ebc-187">Settings</span></span>

<span data-ttu-id="f6ebc-p114">[設定] セクションでは、パスワード、ルーム タグ、ルームの既定のボリューム レベルを設定できます。これらの設定を構成すると、SRS コンソールを再起動した後に、変更がレプリケートされます。SRS デバイスのシステム更新設定は、リリース 15.12 以降を使用してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-p114">In the Settings section, you can set the password, room tag, and default volume levels for the room. If you configure these settings, the changes are replicated only after you restart the SRS console. You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Lync Room System、管理用ポータル ルームの設定](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="f6ebc-192">詳細</span><span class="sxs-lookup"><span data-stu-id="f6ebc-192">Details</span></span>

<span data-ttu-id="f6ebc-193">[詳細] セクションには、SRS ルームの設定の読み取り専用の概要が表示されます。これには、最終更新時刻が含まれます。次の会議最終更新、メンテナンス、調整。既定のスピーカー、マイク、着信音の設定バージョンSIP URI画面の数と各画面の詳細。状態、アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Lync Room System、管理用ポータル詳細ビュー](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="f6ebc-195">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f6ebc-195">Troubleshooting</span></span>

<span data-ttu-id="f6ebc-p115">[トラブルシューティング] セクションを使用して、ログをリモートで収集し、指定した場所に保存できます。また、SRS コンソール (SRS ユーザー インターフェイス) を再起動したり、システム全体を再起動したりすることもできます。ログを収集するには、フォルダー パスを指定された形式で入力して、そのフォルダーに対して SRS コンピューターのアカウントに与えられた書き込みアクセス許可が設定されていることを確認します。ログ サイズが大きすぎる場合は、ログの収集を完了するのに最大約 5 分かかる可能性があります。ページを更新すると、最新の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-p115">The Troubleshooting section can be used to remotely collect logs and save them to a specified location. You can also restart the SRS console (SRS user interface) or restart the entire system. To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account. If the log size is too big, it can take up to 5 minutes to finish collecting logs. Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="f6ebc-201">動作状態</span><span class="sxs-lookup"><span data-stu-id="f6ebc-201">Health</span></span>

<span data-ttu-id="f6ebc-202">[正常性] セクションには、Skype for Business Server 接続、オーディオデバイス、ビデオデバイス、復元の状態、画面デバイスの正常性が視覚的に示されます。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Lync Room System、管理用ポータル ルームの正常性](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="f6ebc-204">管理 Web ポータルに関する追加の注意事項</span><span class="sxs-lookup"><span data-stu-id="f6ebc-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="f6ebc-205">設定の変更は、SRS システムが再起動された後にのみ適用されます。 LRSApp アカウントのパスワードの有効期限が切れた場合、会議室の状態を表示することはできません。 ></span><span class="sxs-lookup"><span data-stu-id="f6ebc-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="f6ebc-206">LRSAppuser account のパスワードを無期限に設定するか、有効期限が近いときにパスワードを更新して > ください。 SRS 管理 web ポータルは、オンプレミスの展開でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="f6ebc-207">一括管理 </span><span class="sxs-lookup"><span data-stu-id="f6ebc-207">Bulk management</span></span>

<span data-ttu-id="f6ebc-208">SRS ルームの一括管理は、高度な IT 管理者向けに設計された機能で、ワークフローを簡素化し、管理者が時間を節約できる便利なツールを利用してリモートで複数のルームを一括方式で管理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="f6ebc-209">この機能を確認するには、ユーザーは特別なセキュリティ グループ **LRSPowerUserAdminsGroup** のメンバーとして配備されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="f6ebc-p117">一括管理のために選択できる SRS ルームの数に制限はありません。ただし、同時に実行できる一括管理の操作は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-p117">There is no limit to the number of SRS rooms you can select for bulk management. However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="f6ebc-212">一括管理の操作を実行するには、監視するルームを選択してから一括管理メニュー上でクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="f6ebc-213">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="f6ebc-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="f6ebc-214">管理 web ポータルにサインインできないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="f6ebc-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="f6ebc-215">を開くhttps://localhost/lrsと、サインインページが表示されますが、資格情報を入力するときにサインインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="f6ebc-216">この場合、管理 web ポータルにhttps://FQDNofFEserver/SRSサインインするには、を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="f6ebc-217">管理 web ポータルに SRS v1 が表示されないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="f6ebc-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="f6ebc-218">展開で SRS アカウントを取得していること、それらのアカウントが 	SRS 管理 Web ポータルの展開の推奨事項に従って作成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="f6ebc-219">Skype for Business Server で、お使いの SRS アカウントが、CsUser を有効にしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="f6ebc-220">SRS アカウントを作成していて、そのアカウントが管理 web ポータルに表示されない場合は、「Skype for Business Server ログツールを使って、**会議ポータル**コンポーネントが選択されている状態でサーバーログを収集し、srs サポートの連絡先に送信します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="f6ebc-p120">SRS アカウントを作成しても、管理 Web ポータルでそのアカウントを確認できない場合は、Fiddler を使用してクライアント ログを収集し、ブラウザー開発ツールからコンソール ログもコピーして、それらのログを SRS サポートの連絡先に送信してください。より詳細なログを取得するために Web.config でトレース レベルの値を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-p120">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact. You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

  ```
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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="f6ebc-223">管理 web ポータルで SRS の状態が表示されないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="f6ebc-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="f6ebc-224">LRSApp ユーザー アカウントが SIP 対応であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="f6ebc-225">それでも問題が解決されない場合は、D:\Tracing\LRSAdminLogs\,から srs システムの**Trace .log**ファイルを収集して、srs のサポート担当者に送信します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="f6ebc-226">管理 web ポータルで SRS の一括管理メニューが表示されないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="f6ebc-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="f6ebc-227">LRSApp のユーザーアカウントが SIP 対応であり、LRSPowerUserAdminsGroup セキュリティグループの一部であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="f6ebc-228">SRS v1 管理 web ポータルは Microsoft Teams のルームで動作しますか?</span><span class="sxs-lookup"><span data-stu-id="f6ebc-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="f6ebc-229">いいえ。</span><span class="sxs-lookup"><span data-stu-id="f6ebc-229">No.</span></span>


