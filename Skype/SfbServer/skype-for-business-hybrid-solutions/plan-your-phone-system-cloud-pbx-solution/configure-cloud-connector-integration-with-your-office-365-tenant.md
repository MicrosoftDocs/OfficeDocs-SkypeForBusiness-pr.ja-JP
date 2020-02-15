---
title: Office 365 テナントとのクラウドコネクタ統合を構成する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Office 365 テナントとのクラウドコネクタの統合を構成する方法について説明します。
ms.openlocfilehash: cf683743064ec377c827fe0c52a59e464f65ae19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050209"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="fb1b2-103">Office 365 テナントとのクラウドコネクタ統合を構成する</span><span class="sxs-lookup"><span data-stu-id="fb1b2-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="fb1b2-104">Office 365 テナントとのクラウドコネクタの統合を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="fb1b2-105">Skype for Business Cloud Connector エディションのインストールが完了したら、このセクションの手順を実行して展開を構成し、Office 365 テナントに接続します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="fb1b2-106">ファイアウォール設定を構成する</span><span class="sxs-lookup"><span data-stu-id="fb1b2-106">Configure firewall settings</span></span>

<span data-ttu-id="fb1b2-107">「 [Plan For Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)」の「[ポートとプロトコル](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)」で説明されているように、境界ネットワークの内部および外部ファイアウォール設定のファイアウォール設定を構成し、必要なポートを開きます。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="fb1b2-108">公衆交換電話網 (PSTN) ゲートウェイをセットアップする</span><span class="sxs-lookup"><span data-stu-id="fb1b2-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="fb1b2-109">すべてのアプライアンスの仲介サーバーをポイントするように、各 PSTN ゲートウェイのトランクを設定します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-109">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="fb1b2-110">プールの FQDN はプール内のすべてのサーバーで同じであるため、各トランクは仲介サーバープールの FQDN ではなく、1つの仲介サーバーの FQDN または IP アドレスをポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-110">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="fb1b2-111">トランクは同じ優先度で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-111">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="fb1b2-112">仲介サーバーとゲートウェイ間で TLS を使用している場合は、次のように MTLS をサポートするようにゲートウェイと仲介サーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="fb1b2-113">Cloud Connector Active Directory コンピューターからルート CA をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="fb1b2-114">ルート CA のインポートについては、PSTN ゲートウェイのベンダーの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="fb1b2-115">仲介サーバー上のゲートウェイに発行された証明書のルート CA 証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-115">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="fb1b2-116">ゲートウェイ用の SSL 証明書を取得する必要がある場合は、次のように Cloud Connector Active Directory コンピューター上で実行されている証明機関サービスを使用して、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-116">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="fb1b2-117">既存の Web サーバーテンプレートを変更して認証済みユーザーを登録できるようにするか、新しい Web サーバーテンプレートを作成して他のプロパティを構成し、認証されたユーザーを登録できるようにします。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="fb1b2-118">詳細な手順については、「[証明書テンプレート](https://technet.microsoft.com/library/cc730705.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="fb1b2-119">有効にした Web サーバーテンプレートを選択して、証明書スナップインを使用して証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="fb1b2-120">[キーのオプション] で秘密キーをエクスポートできるようにするには、[サブジェクト] と [DNS 名] に、「別名」と「別名」を使用して、秘密キーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="fb1b2-121">秘密キーを使用して SSL 証明書をエクスポートし、PSTN ゲートウェイベンダーからの指示に従って証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="fb1b2-122">テナントのドメインを更新する</span><span class="sxs-lookup"><span data-stu-id="fb1b2-122">Update the domain for your tenant</span></span>

<span data-ttu-id="fb1b2-123">Office 365 でドメインを更新する手順が完了しており、DNS レコードを追加できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="fb1b2-124">Office 365 でドメインをセットアップする方法の詳細については、「 [office 365 にドメインを追加](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="fb1b2-125">Office 365 でエッジ用の DNS レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="fb1b2-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="fb1b2-126">次の DNS レコードを Office 365 テナントに追加します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-126">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="fb1b2-127">Office 365 テナントに DNS レコードを追加する方法については、「 [office 365 でカスタムの dns レコードを追加または編集](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-127">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="fb1b2-128">アクセスエッジの DNS A レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="fb1b2-129">SRV レコードは、Office 365 と展開スクリプトによって自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-129">SRV records will automatically be created by Office 365 and the deployment scripts.</span></span> <span data-ttu-id="fb1b2-130">エッジに対して次の2つの SIP サービスを検索できることを確認します。 _sip と _sipfederationtls。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-130">Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![SRV レコードの確認](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="fb1b2-132">Cloud Connector エディションと Office 365 の間のハイブリッド接続をセットアップする</span><span class="sxs-lookup"><span data-stu-id="fb1b2-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="fb1b2-133">Skype for Business Cloud Connector エディションの展開と Office 365 テナントとの間にハイブリッド接続を構成するには、リモート PowerShell セッションで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="fb1b2-134">リモート PowerShell セッションを確立する方法については、「 [Windows PowerShell 用にコンピューター](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="fb1b2-135">コマンドレットは、アクセスエッジの外部 FQDN を設定します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="fb1b2-136">最初のコマンドの場合、 \<外部アクセスエッジの FQDN\>は、SIP アクセスエッジの役割に対応したものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="fb1b2-137">既定では、これは ap ドメイン\<名\>にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="fb1b2-138">ピアの宛先に使用される外部アクセスエッジの FQDN は、ユーザーが PSTN サイトに割り当てられていない場合にのみフォールバックとして使用される PSTN サイトに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="fb1b2-139">詳細については、「 [deploy a single site In Cloud connector](deploy-a-single-site-in-cloud-connector.md) 」および「 [deploy Multiple Sites in cloud connector](deploy-multiple-sites-in-cloud-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="fb1b2-140">PSTN ゲートウェイのセットアップ</span><span class="sxs-lookup"><span data-stu-id="fb1b2-140">Set up PSTN gateways</span></span>

<span data-ttu-id="fb1b2-141">すべてのアプライアンスの仲介サーバーをポイントするように、各 PSTN ゲートウェイのトランクを設定します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-141">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="fb1b2-142">プールの FQDN は、プール内のすべてのサーバーで同じであるため、各トランクは仲介サーバーの fqdn ではなく、1つの仲介サーバーの FQDN または IP アドレスをポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-142">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="fb1b2-143">トランクは同じ優先度で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-143">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="fb1b2-144">仲介サーバーとゲートウェイ間で TLS を使用している場合は、次のように MTLS をサポートするようにゲートウェイと仲介サーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="fb1b2-145">Cloud Connector Active Directory コンピューターからルート CA をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="fb1b2-146">ルート CA のインポートについては、PSTN ゲートウェイのベンダーの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="fb1b2-147">仲介サーバー上のゲートウェイに発行された証明書のルート CA 証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-147">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="fb1b2-148">ゲートウェイ用の SSL 証明書を取得する必要がある場合は、次のように Cloud Connector Active Directory コンピューター上で実行されている証明機関サービスを使用して、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-148">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="fb1b2-149">既存の Web サーバーテンプレートを変更して認証済みユーザーを登録できるようにするか、新しい Web サーバーテンプレートを作成して他のプロパティを構成し、認証されたユーザーを登録できるようにします。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="fb1b2-150">詳細な手順については、「[証明書テンプレート](https://technet.microsoft.com/library/cc730705.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="fb1b2-151">有効にした Web サーバーテンプレートを選択して、証明書スナップインを使用して証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="fb1b2-152">[キーのオプション] で秘密キーをエクスポートできるようにするには、[サブジェクト] と [DNS 名] に、「別名」と「別名」を使用して、秘密キーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="fb1b2-153">秘密キーを使用して SSL 証明書をエクスポートし、PSTN ゲートウェイベンダーからの指示に従って証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="fb1b2-154">1つの PSTN サイトの PSTN ゲートウェイは、同じサイトの仲介サーバーにのみ接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="fb1b2-155">Office 365 でユーザーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="fb1b2-155">Set up your users in Office 365</span></span>

<span data-ttu-id="fb1b2-156">Office 365 管理ポータルにログインし、オンライン音声サービスに対して有効にするユーザーを追加し、Office 365 アドオンの E5 ライセンスまたは電話システムをこれらのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-156">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="fb1b2-157">ユーザーの追加の詳細については、「 [Add users To Office 365 to business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="fb1b2-158">Office 365 の電話システムでユーザーを有効にする音声およびボイスメールサービス</span><span class="sxs-lookup"><span data-stu-id="fb1b2-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="fb1b2-159">Office 365 にユーザーを追加した後、ボイスメールを含む Office 365 音声サービスの電話システムに対してアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="fb1b2-160">これらの機能を有効にするには、office 365 グローバル管理者の役割であるアカウントを使用して Office 365 テナントにログインし、リモート PowerShell を実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-160">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="fb1b2-161">リモート PowerShell セッションを確立する方法については、「 [Windows PowerShell 用にコンピューター](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="fb1b2-162">ユーザーにポリシーを割り当て、ユーザーのビジネスボイス電話番号を構成します。これは、 **Identity**パラメーターの値を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="fb1b2-163">ユーザーの SIP アドレス、ユーザープリンシパル名 (UPN)、またはユーザーの Active Directory 表示名 (たとえば、「Bob 友野」) を使用して、ユーザー id を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-163">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="fb1b2-164">アスタリスク (\*) 文字をユーザー id として表示名と共に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-164">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="fb1b2-165">たとえば、"\*smith" という id は、"smith" という文字列値で終わる表示名を持つすべてのユーザーを返します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-165">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="fb1b2-166">その後、次のスクリプトを使用して、ユーザーが追加され、有効になっていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="fb1b2-167">ユーザーが国際電話をかけることができるようにするかどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-167">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="fb1b2-168">既定では、国際通話は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-168">By default, international calling is enabled.</span></span> <span data-ttu-id="fb1b2-169">オンラインの Skype for Business 管理センターを使用して、ユーザーの国際通話を無効または有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-169">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="fb1b2-170">ユーザー単位で国際通話を無効にするには、Skype for Business Online PowerShell で次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="fb1b2-171">無効にした後、ユーザー単位で国際通話を再び有効にするには、同じコマンドレットを実行しますが、 **PolicyName**の値を*InternationalCallsAllowed*に変更します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="fb1b2-172">ユーザーを PSTN サイトに割り当てる</span><span class="sxs-lookup"><span data-stu-id="fb1b2-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="fb1b2-173">テナントのリモート PowerShell を使用して、1つのサイトのみを展開した場合でも、ユーザーにサイトを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="fb1b2-174">リモート PowerShell セッションを確立する方法については、「 [Windows PowerShell 用にコンピューター](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-174">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="fb1b2-175">ユーザーに PSTN サイトが割り当てられていない場合、Skype for Business Cloud Connector エディションの展開と Office 365 テナントとの間のハイブリッド接続は、テナントレベルの既定 1 (ピアの宛先) を使用して通話を完了できるようになります。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="fb1b2-176">オンラインのハイブリッド仲介サーバーの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="fb1b2-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="fb1b2-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="fb1b2-177"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="fb1b2-178">P2P 電話が PSTN 会議にエスカレートされると、Skype for Business Online 会議サーバーは Cloud Connector 仲介サーバーに招待を送信します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="fb1b2-179">Office 365 がこの招待を正常にルーティングできるようにするには、次のように、各 Cloud Connector 仲介サーバーのオンラインテナントで設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-179">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="fb1b2-180">Office 365 管理ポータルでユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-180">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="fb1b2-181">必要なユーザー名 ("MediationServer1" など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="fb1b2-182">ユーザードメインとして、Cloud Connector の既定の SIP ドメイン (.ini ファイルの最初の SIP ドメイン) を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="fb1b2-183">ライセンスの割り当ては、ユーザーが Skype for Business online ディレクトリに伝播する場合にのみ必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-183">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="fb1b2-184">作成したアカウントに Office 365 ライセンス (E5 など) を割り当て、変更が反映されるまで最大1時間を待ち、次のコマンドレットを実行して、ユーザーアカウントが Skype for Business online ディレクトリに正しくプロビジョニングされていることを確認し、このアカウントからのライセンス。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-184">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="fb1b2-185">グローバルまたはユーザーの管理者の資格情報を使用してテナント Azure AD リモート PowerShell セッションを開始し、次のコマンドレットを実行して、手順1で構成した Azure AD ユーザーアカウントの部署を "HybridMediationServer" に設定します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-185">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="fb1b2-186">Skype for Business のテナント管理者の資格情報を使用して、テナントの Skype for Business リモート PowerShell セッションを開始し、次のコマンドレットを実行して、仲介サーバーと\<エッジ\>サーバーの FQDN を、そのユーザーアカウントに設定します。 DisplayName は、手順1で作成したアカウントのユーザーの表示名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-186">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="fb1b2-187">Identity の場合は、この仲介サーバー用に作成した Office 365 ユーザーアカウントの表示名を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-187">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="fb1b2-188">*Mediationserverfqdn*の場合は、仲介サーバーに対して定義されている内部 FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-188">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="fb1b2-189">*EdgeServerExternalFQDN*では、エッジサーバーアクセスプロキシに対して定義されている外部 FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-189">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="fb1b2-190">複数の Cloud Connector PSTN サイトがある場合は、仲介サーバーが配置されているサイトに割り当てられているエッジサーバーアクセスプロキシの FQDN を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-190">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="fb1b2-191">複数の Cloud Connector 仲介サーバー (複数サイト、HA) がある場合は、上記の手順をそれぞれに対して繰り返します。</span><span class="sxs-lookup"><span data-stu-id="fb1b2-191">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

