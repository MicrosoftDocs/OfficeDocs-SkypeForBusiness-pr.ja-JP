---
title: 'Skype for Business Server 2015 での SRS v1 管理 Web ポータルの展開 '
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/3/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
description: ビジネス サーバー 2015 Skype ルーム システム v1 の Skype (SRS v1、Lync ルームのシステムと呼ばれていました) 管理用の Web ポータルは、組織が、Skype ルーム システムの会議室を維持するために使用できる web ポータルです。 管理者は、オーディオ/ビデオ デバイスを監視することによってなど、デバイスの稼働状態を監視するのに SRS v1 を管理する Web ポータルを使用できます。 このポータルでは、管理者はリモートで会議室の稼働状態を監視するための診断情報を収集できます。
ms.openlocfilehash: 84f9d84861980f970fb496f957c712a1d7dfead4
ms.sourcegitcommit: 9c5c67eb50006f84c425456dfb3ecfcf4638d5fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "20088533"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server-2015"></a><span data-ttu-id="c8ff2-105">Skype for Business Server 2015 での SRS v1 管理 Web ポータルの展開 </span><span class="sxs-lookup"><span data-stu-id="c8ff2-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c8ff2-106">ビジネス サーバー 2015 Skype ルーム システム v1 の Skype (SRS v1、Lync ルームのシステムと呼ばれていました) 管理用の Web ポータルは、組織が、Skype ルーム システムの会議室を維持するために使用できる web ポータルです。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-106">The Skype for Business Server 2015 Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="c8ff2-107">管理者は、オーディオ/ビデオ デバイスを監視することによってなど、デバイスの稼働状態を監視するのに SRS v1 を管理する Web ポータルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="c8ff2-108">このポータルでは、管理者はリモートで会議室の稼働状態を監視するための診断情報を収集できます。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>
  
<span data-ttu-id="c8ff2-109">この機能を使用するのには SRS v1 を管理する Web ポータルをすべての Skype のビジネス サーバーのフロント エンド サーバーに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="c8ff2-110">このガイドでは、管理者向けに SRS 管理 Web ポータルのインストールおよび設定方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="c8ff2-111">Skype のビジネス サーバーの管理のための知識があるユーザーおよびビジネスのサーバー トポロジの Skype を変更するのには管理者権限があるユーザーに管理者のものです。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>
  
<span data-ttu-id="c8ff2-112">SRS v1 は、管理用の Web ポータルは、サーバー上に配置は後、管理者は、自分のコンピューターまたはラップトップ コンピューターからサイトにログオンし、ステータス SRS v1 デバイスをチェックすることができます。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c8ff2-113">の[Microsoft Skype ルームのビジネス サーバー 2015 の Skype のシステム v1 の管理用の Web ポータル](https://www.microsoft.com/en-us/download/details.aspx?id=46906)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span> 
  
<span data-ttu-id="c8ff2-114">このトピックでは、以下について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-114">In this topic:</span></span>
  
- [<span data-ttu-id="c8ff2-115">SRS v1 管理 Web ポータルの環境の構成</span><span class="sxs-lookup"><span data-stu-id="c8ff2-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)
    
- [<span data-ttu-id="c8ff2-116">SRS v1 管理 Web ポータルのインストール</span><span class="sxs-lookup"><span data-stu-id="c8ff2-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)
    
- [<span data-ttu-id="c8ff2-117">SRS 管理 Web ポータルの使用</span><span class="sxs-lookup"><span data-stu-id="c8ff2-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)
    
## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="c8ff2-118">SRS v1 管理 Web ポータルの環境の構成</span><span class="sxs-lookup"><span data-stu-id="c8ff2-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="c8ff2-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="c8ff2-119"></span></span>

<span data-ttu-id="c8ff2-120">SRS v1 管理 Web ポータルを使用するには、次の前提条件をインストールまたは構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c8ff2-p104">サーバーが Kerberos 認証と NTLM 認証の両方で構成されており、SRS がドメインに参加していないコンピューターで実行されている場合、Kerberos 認証は失敗し、管理ポータルで SRS のステータスを見ることはできません。この問題を解決するには、NTLM 認証、または NTLM 認証と TLS-DSK 認証の両方で (Kerberos を使って) サーバーを構成するか、SRS コンピューターをドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-p104">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal. To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span> 
  
1. <span data-ttu-id="c8ff2-123">ビジネス サーバーの累積的な更新はビジネスのサーバー トポロジの Skype では、Skype をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span> 
    
    <span data-ttu-id="c8ff2-124">更新プログラムを取得またはそれに含まれる機能を参照してください、 [Skype ビジネス サーバー 2015 用の更新プログラム](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    
2. <span data-ttu-id="c8ff2-125">SIP 対応の Active Directory ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-125">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="c8ff2-126">SRS v1 の管理用の Web ポータルは、ビジネスのサーバーの Skype から情報を照会するこれらの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="c8ff2-127">ここでの例のユーザー名は LRSApp です。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-127">The username in the examples given is LRSApp.</span></span>
    
3. <span data-ttu-id="c8ff2-128">LRSSupportAdminGroup という名前の Active Directory セキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="c8ff2-p106">[グループのスコープ] が [グローバル]、[グループの種類] が [セキュリティ] のグループを作成します。このグループに追加される SIP 対応ユーザーは、部屋の一覧を参照したり、ログの収集などの特定のコマンドを実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-p106">Create the group with Group Scope as Global and Group Type as Security. SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>
    
4. <span data-ttu-id="c8ff2-131">LRSFullAccessAdminGroup という名前の Active Directory セキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span> 
    
    <span data-ttu-id="c8ff2-p107">[グループのスコープ] が [グローバル]、[グループの種類] が [セキュリティ] のグループを作成します。このグループに追加される SIP 対応ユーザーは、単一の Skype ルームで管理ポータルのすべての機能を使用できます。Skype ルームの一括管理のサポートを含める場合は、手順 5 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-p107">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room. To include support for bulk management of Skype rooms, refer to step 5.</span></span> 
    
     ![セキュリティ グループの役割を持つ Admin グループの一覧](../../media/LRS_LRSFullAccessAdminGroup.png)
  
5. <span data-ttu-id="c8ff2-135">LRSPowerUserAdminsGroup という名前の Active Directory セキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span> 
    
    <span data-ttu-id="c8ff2-136">[グループのスコープ] が [グローバル]、[グループの種類] が [セキュリティ] のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="c8ff2-137">このグループに追加されている SIP が有効になっているユーザーが承認すると、Skype ビジネス室の一括管理を含むすべての管理ポータルの機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span> 
    
6. <span data-ttu-id="c8ff2-138">LRSFullAccessAdminGroup は、LRSSupportAdminGroup のメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
     ![LRSSupportAdminGroup プロパティ メンバー ページ](../../media/LRS_Add_LRSSupportAdminGroup.png)
  
7. <span data-ttu-id="c8ff2-p109">LRSSupport という名前の SIP 対応の Active Directory ユーザーを作成します。このユーザーを LRSSupportAdminGroup に追加します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-p109">Create a SIP enabled Active Directory user with name LRSSupport. Add this user to LRSSupportAdminGroup.</span></span>
    
     ![LRSSupportAdminGroup プロパティ メンバー ページ](../../media/LRS_Add_LRS_SIP_SupportUser.png)
  
8. <span data-ttu-id="c8ff2-143">[ASP.NET MVC 4 の Visual Studio 2010 SP1 および Visual Web の開発者 2010 SP1](http://go.microsoft.com/fwlink/p/?LinkId=323967)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](http://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>
    
## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="c8ff2-144">SRS v1 管理 Web ポータルのインストール</span><span class="sxs-lookup"><span data-stu-id="c8ff2-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="c8ff2-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="c8ff2-145"></span></span>

<span data-ttu-id="c8ff2-146">の[Microsoft Skype ルームのビジネス サーバー 2015 の Skype のシステム v1 の管理用の Web ポータル](https://www.microsoft.com/en-us/download/details.aspx?id=46906)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span> 
  
<span data-ttu-id="c8ff2-147">SRS v1 管理 Web ポータルをインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>
  
1. <span data-ttu-id="c8ff2-148">ビジネス サーバー管理シェルの Skype で次のコマンドレットを実行することによって、信頼されたアプリケーションのポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>
    
   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="c8ff2-149">会議室ポータルをインストールするには、**MeetingRoomPortalInstaller.msi** をダウンロードして管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>
    
3. <span data-ttu-id="c8ff2-150">Web.config ファイルを次の場所から開きます。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-150">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="c8ff2-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\\</span><span class="sxs-lookup"><span data-stu-id="c8ff2-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\\</span></span>
    
4. <span data-ttu-id="c8ff2-152">Web.Config ファイルで、PortalUserName を「[SRS v1 を管理する Web ポータル用に環境を構成する](room-system-v1-administrative-web-portal.md#Config_Env)」は (推奨される名前のステップでは、LRSApp)」下にある手順 2 で作成したユーザー名に変更します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span> 
    
    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="c8ff2-p110">SRS v1 管理ポータルは信頼済みアプリケーションであるため、ポータルの構成でパスワードを提示する必要はありません。このユーザーがローカル レジストラーとは別のレジストラーを使用している場合、Web.Config ファイルで次の行を追加してレジストラを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-p110">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration. If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span> 
    
   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="c8ff2-155">5061 以外のポートが使用されている場合は、Web.Config ファイルに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span> 
    
   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="c8ff2-156">SRS 管理 Web ポータルのインストールの検証</span><span class="sxs-lookup"><span data-stu-id="c8ff2-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="c8ff2-157">SRS v1 管理 Web ポータルのインストールを検証するには、次を行います。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>
  
1. <span data-ttu-id="c8ff2-158">フロントエンド サーバーで、次の URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-158">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="c8ff2-159">https://\<fe サーバー\>/lrs</span><span class="sxs-lookup"><span data-stu-id="c8ff2-159">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="c8ff2-160">下記の画像のように、エラーが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-160">You should not see any errors, as shown in the following image:</span></span>
    
     ![Lync Room System、管理用ポータル サインイン画面](../../media/LRS_AdminPortalSignIn.png)
  
2. <span data-ttu-id="c8ff2-162">エラーが表示されない場合は、トポロジ内の他のいずれかのコンピューターから次の URL へのアクセスを試行します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="c8ff2-163">https://\<fe サーバー\>/lrs</span><span class="sxs-lookup"><span data-stu-id="c8ff2-163">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="c8ff2-164">ページにアクセスするには、「の[自動クライアント サインインの DNS レコードが必要](https://go.microsoft.com/fwlink/p/?LinkId=318056)です」で説明するように DNS レコードを追加する必要</span><span class="sxs-lookup"><span data-stu-id="c8ff2-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>
    
## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="c8ff2-165">SRS 管理 Web ポータルの使用</span><span class="sxs-lookup"><span data-stu-id="c8ff2-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="c8ff2-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="c8ff2-166"></span></span>

<span data-ttu-id="c8ff2-167">サーバーで SRS を展開した後、ブラウザーから SRS v1 管理 Web ポータルにサインインして、すべての SRS ルームの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>
  
### <a name="sign-in"></a><span data-ttu-id="c8ff2-168">サインイン</span><span class="sxs-lookup"><span data-stu-id="c8ff2-168">Sign in</span></span>

1. <span data-ttu-id="c8ff2-169">次の URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-169">Browse to the following URL:</span></span>
    
    <span data-ttu-id="c8ff2-170">https://\<fe サーバー\>/lrs</span><span class="sxs-lookup"><span data-stu-id="c8ff2-170">https://\<fe-server\>/lrs</span></span>
    
2. <span data-ttu-id="c8ff2-171">LRSSupport アカウントの資格情報、または LRSSupportAdminGroup セキュリティ グループに追加されたアカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>
    
![Lync Room System、管理用ポータル サインイン画面](../../media/LRS_AdminPortalSignIn.png)
  
### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="c8ff2-173">SRS 管理 Web ポータルの概要ページ</span><span class="sxs-lookup"><span data-stu-id="c8ff2-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="c8ff2-174">この概要ページには、サーバーで展開されたすべての SRS ルームに関する次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>
  
- <span data-ttu-id="c8ff2-175">**タグ**ルームに、管理者が提供するカスタムの名前です。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="c8ff2-176">ルームの名前をクリックすると、ポータルでタグを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-176">The Tag can be set in the portal by clicking on the room name.</span></span>
    
- <span data-ttu-id="c8ff2-177">**稼働状態**[スペース設定] ページの [チェック] セクションの下に表示されていると、部屋の状態を集計から派生すると、部屋の状態です。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>
    
- <span data-ttu-id="c8ff2-178">**次の会議**日付と時刻、次の会議をスケジュールするとします。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>
    
- <span data-ttu-id="c8ff2-179">**SRS のバージョン、製造元、モデル**SRS では、これらの値が事前設定されます。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="c8ff2-180">製造元によって、これらのフィールドは空白のままである場合があります。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-180">Depending on the manufacturer, these fields might be left blank.</span></span>
    
- <span data-ttu-id="c8ff2-181">**最終更新**Web ページが更新された最終時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>
    
![Lync Room System、管理用ポータル概要ビュー](../../media/LRS_AdminPortal_Summary_view.png)
  
> [!NOTE]
> <span data-ttu-id="c8ff2-183">一括管理」メニューは、LRSPowerUserAdminsGroup のセキュリティ グループに属している場合のみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span> 
  
### <a name="srs-room-information"></a><span data-ttu-id="c8ff2-184">SRS ルーム情報</span><span class="sxs-lookup"><span data-stu-id="c8ff2-184">SRS Room Information</span></span>

<span data-ttu-id="c8ff2-p113">ポータルの [ルーム情報] セクションでは、個々の SRS ルームを表示および構成することができます。これには、[設定]、[詳細]、[ログ記録]、[動作状態] の 4 つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-p113">The Room Info section of the portal allows you to view and configure individual SRS rooms. It contains four sections: Settings, Details, Logging, and Health.</span></span>
  
#### <a name="settings"></a><span data-ttu-id="c8ff2-187">設定</span><span class="sxs-lookup"><span data-stu-id="c8ff2-187">Settings</span></span>

<span data-ttu-id="c8ff2-p114">[設定] セクションでは、パスワード、ルーム タグ、ルームの既定のボリューム レベルを設定できます。これらの設定を構成すると、SRS コンソールを再起動した後に、変更がレプリケートされます。SRS デバイスのシステム更新設定は、リリース 15.12 以降を使用してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-p114">In the Settings section, you can set the password, room tag, and default volume levels for the room. If you configure these settings, the changes are replicated only after you restart the SRS console. You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>
  
![Lync Room System、管理用ポータル ルームの設定](../../media/LRS_AdminPortal_RoomInfoSettings.png)
  
#### <a name="details"></a><span data-ttu-id="c8ff2-192">詳細</span><span class="sxs-lookup"><span data-stu-id="c8ff2-192">Details</span></span>

<span data-ttu-id="c8ff2-193">[詳細] セクションには、SRS ルームの設定などの読み取り専用で概要が用意されています: 時間の最後の更新です。次の会議です。最後の更新、保守、および調整します。デフォルトのスピーカー、マイク、および呼び出しの設定。バージョンです。SIP URI です。画面および各画面の詳細の数ステータス、および活動。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>
  
![Lync Room System、管理用ポータル詳細ビュー](../../media/LRS_AdminPortal_Detail_view.png)
  
#### <a name="troubleshooting"></a><span data-ttu-id="c8ff2-195">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c8ff2-195">Troubleshooting</span></span>

<span data-ttu-id="c8ff2-p115">[トラブルシューティング] セクションを使用して、ログをリモートで収集し、指定した場所に保存できます。また、SRS コンソール (SRS ユーザー インターフェイス) を再起動したり、システム全体を再起動したりすることもできます。ログを収集するには、フォルダー パスを指定された形式で入力して、そのフォルダーに対して SRS コンピューターのアカウントに与えられた書き込みアクセス許可が設定されていることを確認します。ログ サイズが大きすぎる場合は、ログの収集を完了するのに最大約 5 分かかる可能性があります。ページを更新すると、最新の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-p115">The Troubleshooting section can be used to remotely collect logs and save them to a specified location. You can also restart the SRS console (SRS user interface) or restart the entire system. To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account. If the log size is too big, it can take up to 5 minutes to finish collecting logs. Refreshing the page will give you the latest status.</span></span>
  
#### <a name="health"></a><span data-ttu-id="c8ff2-201">動作状態</span><span class="sxs-lookup"><span data-stu-id="c8ff2-201">Health</span></span>

<span data-ttu-id="c8ff2-202">チェック] セクションでは、ビジネス サーバー接続、オーディオ デバイス、ビデオ デバイス、弾力性の状態、およびデバイスの画面の Skype の状態をビジュアルに示しますを説明します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>
  
![Lync Room System、管理用ポータル ルームの正常性](../../media/LRS_AdminPortal_RoomInfoHealth.png)
  
### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="c8ff2-204">管理 Web ポータルに関する追加の注意事項</span><span class="sxs-lookup"><span data-stu-id="c8ff2-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="c8ff2-205">SRS システムを再起動後に設定の変更が適用されます。 > 部屋の状態を確認することはできません LRSApp アカウントのパスワードが期限切れになった場合。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="c8ff2-206">決して有効期限が切れる、またはです。 有効期限の近くになる場合は、パスワードを更新することを確認するように、LRSAppuser のアカウントのパスワードを構成する > の SRS の管理用の web ポータルは設置型展開でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>
  
### <a name="bulk-management"></a><span data-ttu-id="c8ff2-207">一括管理 </span><span class="sxs-lookup"><span data-stu-id="c8ff2-207">Bulk management</span></span>

<span data-ttu-id="c8ff2-208">SRS ルームの一括管理は、高度な IT 管理者向けに設計された機能で、ワークフローを簡素化し、管理者が時間を節約できる便利なツールを利用してリモートで複数のルームを一括方式で管理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>
  
<span data-ttu-id="c8ff2-209">この機能を確認するには、ユーザーは特別なセキュリティ グループ **LRSPowerUserAdminsGroup** のメンバーとして配備されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span> 
  
<span data-ttu-id="c8ff2-p117">一括管理のために選択できる SRS ルームの数に制限はありません。ただし、同時に実行できる一括管理の操作は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-p117">There is no limit to the number of SRS rooms you can select for bulk management. However, you can perform only one bulk management operation at a time.</span></span>
  
<span data-ttu-id="c8ff2-212">一括管理の操作を実行するには、監視するルームを選択してから一括管理メニュー上でクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span> 
  
### <a name="frequently-asked-questions"></a><span data-ttu-id="c8ff2-213">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="c8ff2-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="c8ff2-214">なぜサインインできない管理用の web ポータルにしますか。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="c8ff2-215">開くとhttps://localhost/lrs、ページで、記号を表示することができますが、ユーザーの資格情報を入力するとサインインできない場合。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="c8ff2-216">この場合、開く必要がありますhttps://FQDNofFEserver/SRS管理用の web ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>
  
#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="c8ff2-217">管理用の web ポータルでの SRS の v1 が見えないのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="c8ff2-218">展開で SRS アカウントを取得していること、それらのアカウントが 	SRS 管理 Web ポータルの展開の推奨事項に従って作成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="c8ff2-219">ビジネス サーバーの Skype を有効にする CsMeetingRoom を有効にする-csuser からしないを使用して、SRS のアカウントを準備することを確認します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>
    
- <span data-ttu-id="c8ff2-220">SRS のアカウントを作成して管理用の web ポータルでアカウントが表示されない場合ビジネス サーバーのログ収集ツールの選択すると、 **MeetingPortal**コンポーネントを使用して、Skype を使用してサーバーのログを収集し、SRS サポート担当者に送信します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>
    
- <span data-ttu-id="c8ff2-p120">SRS アカウントを作成しても、管理 Web ポータルでそのアカウントを確認できない場合は、Fiddler を使用してクライアント ログを収集し、ブラウザー開発ツールからコンソール ログもコピーして、それらのログを SRS サポートの連絡先に送信してください。より詳細なログを取得するために Web.config でトレース レベルの値を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-p120">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact. You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>
    
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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="c8ff2-223">管理用の web ポータルでの SRS の状態が見えないのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="c8ff2-224">LRSApp ユーザー アカウントが SIP 対応であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>
    
- <span data-ttu-id="c8ff2-225">場合は問題が発生しても、**そう**ファイルで SRS システムから収集 D:\Tracing\LRSAdminLogs\,し、SRS サポート担当者に送信します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>
    
#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="c8ff2-226">表示されない理由、一括管理メニュー SRS の管理用の web ポータルのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="c8ff2-227">LRSApp ユーザー アカウントは、SIP が有効になってし、LRSPowerUserAdminsGroup のセキュリティ グループの一部である確認します。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span> 
  
#### <a name="does-the-srs-v1-administrative-web-portal-work-with-skype-room-systems-v2"></a><span data-ttu-id="c8ff2-228">SRS v1 管理 Web ポータルは Skype Room Systems v2 と連携しますか。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-228">Does the SRS v1 administrative web portal work with Skype Room Systems v2?</span></span>

<span data-ttu-id="c8ff2-229">いいえ。</span><span class="sxs-lookup"><span data-stu-id="c8ff2-229">No.</span></span>
  

