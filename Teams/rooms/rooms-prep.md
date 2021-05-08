---
title: 環境を準備する
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Microsoft Teams Rooms を展開するためのインフラストラクチャを準備して、すべての機能を利用できるようにする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 81aa41895f11b65c9406bd30311f2fcb974949a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117425"
---
# <a name="prepare-your-environment"></a><span data-ttu-id="24d0a-103">環境を準備する</span><span class="sxs-lookup"><span data-stu-id="24d0a-103">Prepare your environment</span></span>

<span data-ttu-id="24d0a-104">このセクションでは、Microsoft Teams Rooms の全機能を使用できるように環境を準備するために必要な手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="24d0a-104">This section contains an overview of the steps required to prepare your environment so that you can use all of the features of Microsoft Teams Rooms.</span></span>
  
1. <span data-ttu-id="24d0a-105">Microsoft Teams Rooms の各コンソールにデバイス アカウントを準備します。</span><span class="sxs-lookup"><span data-stu-id="24d0a-105">Prepare a device account for each Microsoft Teams Rooms console.</span></span> <span data-ttu-id="24d0a-106">詳細については、「[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24d0a-106">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
    
2. <span data-ttu-id="24d0a-107">デバイスが使用できるように動作するネットワークまたはインターネット接続があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24d0a-107">Ensure that there is a working network/Internet connection for the device to use.</span></span> 
    
   <span data-ttu-id="24d0a-108">DHCP を使用して IP アドレスを受信できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="24d0a-108">It must be able to receive an IP address by using DHCP.</span></span> <span data-ttu-id="24d0a-109">(Microsoft Teams ミーティングユニットの起動時に静的 IP アドレスを使用して構成することはできませんが、その後、デバイスまたはアップストリーム スイッチまたはルーターでデバイスの静的 IP アドレスを構成できます)。</span><span class="sxs-lookup"><span data-stu-id="24d0a-109">(Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup, but afterwards, a static IP address for the device could be configured on the device or on the upstream switch or router.)</span></span>

   <span data-ttu-id="24d0a-110">次のポートが開かれている必要があります (メディアの通常のポートも開かれている必要があります)。</span><span class="sxs-lookup"><span data-stu-id="24d0a-110">It must have these ports open (in addition to opening the normal ports for media):</span></span>
   - <span data-ttu-id="24d0a-111">HTTPS: 443</span><span class="sxs-lookup"><span data-stu-id="24d0a-111">HTTPS: 443</span></span>
   - <span data-ttu-id="24d0a-112">HTTP:80</span><span class="sxs-lookup"><span data-stu-id="24d0a-112">HTTP: 80</span></span>

   <span data-ttu-id="24d0a-113">プロキシを介してネットワークが動作している場合は、プロキシのアドレスまたはスクリプトの情報も必要です。</span><span class="sxs-lookup"><span data-stu-id="24d0a-113">If your network runs through a proxy, you'll need the proxy address or script information as well.</span></span>
    
   > [!IMPORTANT]
   > <span data-ttu-id="24d0a-114">Microsoft Teams Rooms は、会議室の通常の操作を妨害する可能性があるため、プロキシ認証をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="24d0a-114">Microsoft Teams Rooms does not support proxy authentication as it may interfere with regular operations of the room.</span></span> <span data-ttu-id="24d0a-115">運用環境に移行する前に、Microsoft Teams Rooms がプロキシ認証から除外されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="24d0a-115">Ensure that Microsoft Teams Rooms have been exempted from proxy authentication before going into production.</span></span>
  
3. <span data-ttu-id="24d0a-116">エクスペリエンスを向上させるために、Microsoft ではデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="24d0a-116">In order to improve your experience, Microsoft collects data.</span></span> <span data-ttu-id="24d0a-117">Microsoft にデータの収集を許可するには、次のサイトを許可します。</span><span class="sxs-lookup"><span data-stu-id="24d0a-117">To allow Microsoft to collect data, allow these sites:</span></span>

   - <span data-ttu-id="24d0a-118">テレメトリ クライアント エンドポイント: https://vortex.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="24d0a-118">Telemetry client endpoint: https://vortex.data.microsoft.com/</span></span>
   - <span data-ttu-id="24d0a-119">テレメトリ設定エンドポイント: https://settings.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="24d0a-119">Telemetry settings endpoint: https://settings.data.microsoft.com/</span></span>
    
### <a name="create-and-test-a-device-account"></a><span data-ttu-id="24d0a-120">デバイス アカウントを作成してテストする</span><span class="sxs-lookup"><span data-stu-id="24d0a-120">Create and test a device account</span></span>

<span data-ttu-id="24d0a-121">*デバイス アカウント* は、Microsoft Teams Rooms クライアントが、予定表などの Exchange の機能にアクセスし、Skype for Business を有効にするために使用するアカウントです。</span><span class="sxs-lookup"><span data-stu-id="24d0a-121">A  *device account*  is an account that the Microsoft Teams Rooms client uses to access features from Exchange, like calendar, and to enable Skype for Business.</span></span> <span data-ttu-id="24d0a-122">詳細については、「[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24d0a-122">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
  
### <a name="check-network-availability"></a><span data-ttu-id="24d0a-123">ネットワークの可用性を確認する</span><span class="sxs-lookup"><span data-stu-id="24d0a-123">Check network availability</span></span>

<span data-ttu-id="24d0a-124">適切に機能するために、Microsoft Teams Rooms デバイスには、以下の要件を満たす有線ネットワークにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="24d0a-124">In order to function properly, the Microsoft Teams Rooms device must have access to a wired network that meets these requirements:</span></span>
  
- <span data-ttu-id="24d0a-125">Active Directory または Azure Active Directory (Azure AD) インスタンスと、Microsoft Exchange および Skype for Business Server へのアクセス。</span><span class="sxs-lookup"><span data-stu-id="24d0a-125">Access to your Active Directory or Azure Active Directory (Azure AD) instance, as well as your Microsoft Exchange and Skype for Business servers.</span></span>

- <span data-ttu-id="24d0a-126">DHCP を使用して IP アドレスを提供することができるサーバーへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="24d0a-126">Access to a server that can provide an IP address using DHCP.</span></span> <span data-ttu-id="24d0a-127">最初のユニットの起動時に、静的 IP アドレスを使用して Microsoft Teams Rooms を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="24d0a-127">Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup.</span></span>

- <span data-ttu-id="24d0a-128">HTTP ポート 80 および 443 にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="24d0a-128">Access to HTTP ports 80 and 443.</span></span>

- <span data-ttu-id="24d0a-129">オンプレミスの Skype for Business Server の実装については「[サーバーのポートとプロトコルの要件](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)」、または Microsoft Teams や Skype for Business Online の実装については「[Microsoft 365 および Office 365 の URL と IP アドレスの範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)」の説明に従って構成された TCP および UDP ポート。</span><span class="sxs-lookup"><span data-stu-id="24d0a-129">TCP and UDP ports configured as described in [Port and protocol requirements for servers](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) for on-premise Skype for Business Server implementations, or [Microsoft 365 and Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) for Microsoft Teams or Skype for Business online implementations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24d0a-130">有線の 1 Gbps ネットワーク接続を使用して、必要な帯域幅を確保してください。</span><span class="sxs-lookup"><span data-stu-id="24d0a-130">Be sure to use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span>

> [!NOTE]
> <span data-ttu-id="24d0a-131">Microsoft Teams Rooms のソフトウェア更新プログラムは、ビジネス向け Microsoft Store から自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="24d0a-131">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="24d0a-132">会議室コンソールがストアにアクセスして自己更新できるかどうかを確認するには、「[ビジネスおよび教育機関向け Microsoft Store の前提条件](/microsoft-store/prerequisites-microsoft-store-for-business)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24d0a-132">See [Prerequisites for Microsoft Store for Business and Education](/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>
  
### <a name="certificates"></a><span data-ttu-id="24d0a-133">証明書</span><span class="sxs-lookup"><span data-stu-id="24d0a-133">Certificates</span></span>

<span data-ttu-id="24d0a-134">Microsoft Teams Rooms のデバイスでは、Exchange Web サービス、Microsoft Teams、Skype for Business、ネットワークの使用量および認証に証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="24d0a-134">Your Microsoft Teams Rooms device uses certificates for Exchange Web Services, Microsoft Teams or Skype for Business, network usage, and authentication.</span></span> <span data-ttu-id="24d0a-135">関連のあるサーバーがパブリック証明書を使用していて、これがオンラインおよびオンプレミスのデプロイの場合、管理者が証明書をインストールするために必要な操作はありません。</span><span class="sxs-lookup"><span data-stu-id="24d0a-135">If the related servers use public certificates, which is the case for Online and some On-Premises deployments, there should be no further action required on the part of the admin to install certificates.</span></span> <span data-ttu-id="24d0a-136">一方、証明機関がプライベート CA (オンプレミスのデプロイでは一般的) の場合、デバイスはこの CA を信頼する必要があります。これは、デバイスに CA と CA チェーン証明書がインストールされていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="24d0a-136">If, on the other hand, the certificate authority is a private CA (typical for On-Premises deployments) then the device needs to trust that CA which means having the CA + CA chain certificates installed on the device.</span></span> <span data-ttu-id="24d0a-137">デバイスをドメインに追加すると、このタスクが自動的に実行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="24d0a-137">Adding the device to the domain may perform this task automatically.</span></span>
  
<span data-ttu-id="24d0a-138">他の Windows クライアントの場合と同じ方法で、証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="24d0a-138">You will install certificates the same way you would for any other Windows client.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="24d0a-139">Microsoft Teams Rooms で Skype for Business Server を使用するには、証明書が必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="24d0a-139">Certificates may be required in order to have Microsoft Teams Rooms use Skype for Business Server.</span></span>
  
### <a name="proxy"></a><span data-ttu-id="24d0a-140">プロキシ</span><span class="sxs-lookup"><span data-stu-id="24d0a-140">Proxy</span></span>

<span data-ttu-id="24d0a-141">Microsoft Teams Rooms は、Windows OS からプロキシ設定を継承するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="24d0a-141">Microsoft Teams Rooms is designed to inherit Proxy settings from the Windows OS.</span></span> <span data-ttu-id="24d0a-142">Windows OS には、次の方法でアクセスします。</span><span class="sxs-lookup"><span data-stu-id="24d0a-142">Access the Windows OS in the following manner:</span></span>
  
1. <span data-ttu-id="24d0a-143">Microsoft Teams Rooms UI で、設定ギア アイコンをクリックします。これにより、デバイスのローカルの管理者パスワード (既定のパスワードは「**sfb**」) が求められます。</span><span class="sxs-lookup"><span data-stu-id="24d0a-143">In the Microsoft Teams Rooms UI, click on the Settings gear icon where you'll be prompted for the local Administrator password on the device (the default password is **sfb**).</span></span>
2. <span data-ttu-id="24d0a-144">**[設定]** をタップし、**[Windows に移動]** ボタンをタップします。次に、**[管理サインインに移動]** ボタンをタップしてから、**[管理者]** ボタンをクリックします (コンピューターが参加しているドメインである場合は **[その他のユーザー]** を選択してから、ユーザー名として .\admin を使用します)。</span><span class="sxs-lookup"><span data-stu-id="24d0a-144">Tap on **Settings** followed by tapping on the **Go to Windows** button and then tapping on the **go to Admin Sign In** button and then clicking the **Administrator** button (if the computer is domain joined choose **Other User,** then use .\admin as the user name).</span></span>
3. <span data-ttu-id="24d0a-145">**[Windows を検索]** ボックスの左下で regedit を入力します (画面を長押しするか、右クリックして **[管理者として実行]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="24d0a-145">In the **Search Windows** box bottom left type in regedit (either long press the screen or right click and choose **Run as administrator**).</span></span>
4. <span data-ttu-id="24d0a-146">HKEY_USERS フォルダーをクリックして (コンピューター ユーザーの SID の一覧が表示されます)、ルート フォルダー HKEY_USERS が選択されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="24d0a-146">Click on the HKEY_USERS folder (you'll see a list of machine user SIDs) ensure the root folder HKEY_USERS is selected.</span></span>
       
5. <span data-ttu-id="24d0a-147">[ファイル] をクリックし、**[ハイブの読み込み]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="24d0a-147">Click on File and then choose **Load Hive.**</span></span>
6. <span data-ttu-id="24d0a-148">**C:\Users\Skype** フォルダーを参照し、[ファイル名] ボックスに NTUSER.dat を入力し、[開く] ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="24d0a-148">Browse to the **C:\Users\Skype** folder and type in the File name box NTUSER.dat and press the open button</span></span>

7. <span data-ttu-id="24d0a-149">新たに読み込まれたハイブのキー名が求められます。「Skype」と入力します (Skype ユーザーのレジストリ設定が表示されます)。</span><span class="sxs-lookup"><span data-stu-id="24d0a-149">You'll be prompted for a Key Name for your newly loaded Hive; type in Skype (you should now see the registry settings for the Skype User).</span></span>
 
8. <span data-ttu-id="24d0a-150">Skype キーを開き、HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings を参照して、次の設定が入力されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24d0a-150">Open the Skype key and browse to HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings then ensure these settings are entered:</span></span> 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    <span data-ttu-id="24d0a-151">ProxyServer が存在しない場合は、このキーを文字列として追加し、xx.xx.xx.xx:8080 をプロキシ サーバーの IP/ホストとポートに変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24d0a-151">If ProxyServer doesn't exist you may have to add this key as a string, change the xx.xx.xx.xx:8080 to the ip/host and port of your Proxy server.</span></span>
 
    <span data-ttu-id="24d0a-152">顧客が PAC ファイルを使用している場合、構成は次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="24d0a-152">If the customer is using a PAC file the configuration would look like the example below:</span></span>

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. <span data-ttu-id="24d0a-153">変更を完了したら、Skype ユーザー キー (Skype のルート フォルダー) を強調表示し、レジストリのファイル メニューから [ハイブのアンロード] を選択します (確認が求められるので、[**はい**] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="24d0a-153">Once you are finished making your changes highlight the Skype User key (root folder for Skype) and choose unload Hive from the Registry file menu (you'll be prompted for confirmation - select **Yes**).</span></span>
    
10. <span data-ttu-id="24d0a-154">これで、レジストリ エディターを閉じて、Windows の検索ボックスに logoff と入力できます。</span><span class="sxs-lookup"><span data-stu-id="24d0a-154">You can now close the registry editor and type logoff into the Windows search box.</span></span>
    
11. <span data-ttu-id="24d0a-155">サインイン画面に戻り、**Skype** ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="24d0a-155">Back at the sign-in screen, choose the **Skype** user.</span></span> <span data-ttu-id="24d0a-156">上記のすべての手順を正常に完了した場合は、Microsoft Teams Rooms デバイスのサインインに成功します。</span><span class="sxs-lookup"><span data-stu-id="24d0a-156">If all the previous steps were successful, the Microsoft Teams Rooms device will sign-in successfully.</span></span>
    
<span data-ttu-id="24d0a-157">ネットワーク セキュリティ[に必要](./security.md#network-security)な FQDN、ポート、IP アドレス範囲の詳細については、ネットワーク セキュリティに関する記事をMicrosoft Teams ミーティング。</span><span class="sxs-lookup"><span data-stu-id="24d0a-157">See the [Network Security](./security.md#network-security) article for full details on FQDNs, ports, and IP address ranges required for Microsoft Teams Rooms.</span></span>
  
  
### <a name="create-provisioning-packages"></a><span data-ttu-id="24d0a-158">プロビジョニング パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="24d0a-158">Create provisioning packages</span></span>

<span data-ttu-id="24d0a-159">プロビジョニング パッケージは、Exchange Server、Microsoft 365、または Office 365 の認証に使用します。</span><span class="sxs-lookup"><span data-stu-id="24d0a-159">You will use provisioning packages to authenticate to Exchange Server, Microsoft 365, or Office 365.</span></span>
  
### <a name="admin-group-management"></a><span data-ttu-id="24d0a-160">管理グループの管理</span><span class="sxs-lookup"><span data-stu-id="24d0a-160">Admin group management</span></span>

<span data-ttu-id="24d0a-161">ドメインの参加後、ドメイン内の Widonws PC の場合と同じ方法で、グループ ポリシーまたはローカルのコンピュータの管理を使用して、ローカル管理者としてセキュリティ グループを設定できます。</span><span class="sxs-lookup"><span data-stu-id="24d0a-161">After domain joining, you can use Group Policy or the Local Computer Management to set a Security Group as local administrator just like you would for a Windows PC in your domain.</span></span> <span data-ttu-id="24d0a-162">そのセキュリティ グループのどのメンバーでも、各自の資格情報を入力して設定をロック解除することができます。</span><span class="sxs-lookup"><span data-stu-id="24d0a-162">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="24d0a-163">Microsoft Teams Rooms デバイスがドメインとの信頼関係を失った場合 (たとえば、Microsoft Teams Rooms をドメインに参加させた後にドメインから削除した場合)、デバイスを認証して設定を開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="24d0a-163">If your Microsoft Teams Rooms device loses trust with the domain (for example, if you remove the Microsoft Teams Rooms from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="24d0a-164">回避策では、ローカルの管理者アカウントでログインします。</span><span class="sxs-lookup"><span data-stu-id="24d0a-164">The workaround is to log in with the local Admin account.</span></span> 
  
## <a name="local-accounts"></a><span data-ttu-id="24d0a-165">ローカル アカウント</span><span class="sxs-lookup"><span data-stu-id="24d0a-165">Local accounts</span></span>

### <a name="microsoft-teams-rooms-local-user-account"></a><span data-ttu-id="24d0a-166">Microsoft Teams Rooms のローカル ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="24d0a-166">Microsoft Teams Rooms Local User Account</span></span>

<span data-ttu-id="24d0a-167">通常、デバイス アカウントではパスワードを使用しません。</span><span class="sxs-lookup"><span data-stu-id="24d0a-167">The Device Account does not typically use a password.</span></span> <span data-ttu-id="24d0a-168">パスワードを指定することは可能ですが、パスワードが期限切れとなった場合にユーザーがコンソール アプリケーションケーションからロックアウトされる可能性などの因果関係があります。</span><span class="sxs-lookup"><span data-stu-id="24d0a-168">It is possible to give it a password, but there are consequences, including a possibility that users might get locked out of the console application when that password expires.</span></span> <span data-ttu-id="24d0a-169">その結果として、管理者は、パスワードが期限切れにならないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="24d0a-169">Consequently, the administrator should take are to ensure that the password is not allowed to expire.</span></span>
  
### <a name="admin---local-administrator-account"></a><span data-ttu-id="24d0a-170">"Admin" - ローカル管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="24d0a-170">"Admin" - Local Administrator Account</span></span>

<span data-ttu-id="24d0a-171">Microsoft Teams Rooms の既定のパスワードは "sfb" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="24d0a-171">Microsoft Teams Rooms default password is set to "sfb".</span></span> <span data-ttu-id="24d0a-172">パスワードは、[Windows の設定] \>[Windows に移動] の順に移動してローカルで変更するか、AutoUnattend.xml ファイルで変更することができます (ADK からの Windows システム イメージ マネージャーを使用して xml ファイルを変更します)。</span><span class="sxs-lookup"><span data-stu-id="24d0a-172">The Password can be changed locally by going to Windows Settings \> Go to Windows or in the AutoUnattend.xml file (use the Windows System Image manager from ADK to make the change to the xml file).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="24d0a-173">できるだけ早く Microsoft Teams Rooms のパスワードを変更してください。</span><span class="sxs-lookup"><span data-stu-id="24d0a-173">Be sure to change the Microsoft Teams Rooms password as soon as possible.</span></span> 
  
<span data-ttu-id="24d0a-174">ドメイン管理者をローカル管理者として設定したグループ ポリシーを設定することで、ローカル管理者のパスワードを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="24d0a-174">You can also manage the Local Administrator password by setting up a group policy where domain admins are made local admins.</span></span>
  
<span data-ttu-id="24d0a-175">ローカル管理者パスワードは設定時の選択肢として含まれません。</span><span class="sxs-lookup"><span data-stu-id="24d0a-175">The Local admin password is not included as a choice during Setup.</span></span>
  
### <a name="machine-account"></a><span data-ttu-id="24d0a-176">コンピューター アカウント</span><span class="sxs-lookup"><span data-stu-id="24d0a-176">Machine Account</span></span>

<span data-ttu-id="24d0a-177">他のデバイスと同様Windowsコンピューター名の名前を変更するには、[PC 名の変更について]を右クリック設定 \> **クリック** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="24d0a-177">Much like any Windows device, the Machine Name can be renamed by right-clicking in **Settings** \> **About** \> **Rename PC**.</span></span>
  
<span data-ttu-id="24d0a-178">ドメインに参加した後にコンピューターの名前を変更する場合は **、Rename-Computer** を使用し、PowerShell コマンドに続いてコンピューターの新しい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="24d0a-178">If you would like to rename the computer after joining it to a domain, use **Rename-Computer**, a PowerShell command, followed by the computer's new name.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="24d0a-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="24d0a-179">Related topics</span></span>

[<span data-ttu-id="24d0a-180">Microsoft Teams Rooms を計画する</span><span class="sxs-lookup"><span data-stu-id="24d0a-180">Plan Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="24d0a-181">Microsoft Teams Rooms の要件</span><span class="sxs-lookup"><span data-stu-id="24d0a-181">Microsoft Teams Rooms requirements</span></span>](requirements.md)
  
[<span data-ttu-id="24d0a-182">Microsoft Teams Rooms をデプロイする</span><span class="sxs-lookup"><span data-stu-id="24d0a-182">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="24d0a-183">Microsoft Teams Rooms コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="24d0a-183">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="24d0a-184">Microsoft Teams Rooms の管理</span><span class="sxs-lookup"><span data-stu-id="24d0a-184">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="24d0a-185">ビジネスおよび教育機関向け Microsoft Store の前提条件</span><span class="sxs-lookup"><span data-stu-id="24d0a-185">Prerequisites for Microsoft Store for Business and Education</span></span>](/microsoft-store/prerequisites-microsoft-store-for-business)