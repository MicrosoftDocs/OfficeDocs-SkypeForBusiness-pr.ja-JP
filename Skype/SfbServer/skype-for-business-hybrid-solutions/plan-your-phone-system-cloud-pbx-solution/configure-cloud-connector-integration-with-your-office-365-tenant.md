---
title: Cloud Connector と Office 365 テナントの統合を構成する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Cloud Connector と Office 365 テナントの統合を構成する方法を説明します。
ms.openlocfilehash: 01e5135a4b0ac6de391140bc6fc0d80bcc00e2ce
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375770"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="4c629-103">Cloud Connector と Office 365 テナントの統合を構成する</span><span class="sxs-lookup"><span data-stu-id="4c629-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="4c629-104">Cloud Connector と Office 365 テナントの統合を構成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="4c629-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="4c629-105">Skype for Business Cloud Connector エディションのインストールが完成したら、このセクションの手順を実行して展開を設定し、Office 365 テナントに接続します。</span><span class="sxs-lookup"><span data-stu-id="4c629-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="4c629-106">ファイアウォール設定を構成する</span><span class="sxs-lookup"><span data-stu-id="4c629-106">Configure firewall settings</span></span>

<span data-ttu-id="4c629-107">境界領域のネットワーク[ポートおよびプロトコル](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)で[ビジネス クラウド コネクタ ・ エディションの Skype の計画](plan-skype-for-business-cloud-connector-edition.md)に従って、必要なポートを開く、内部および外部のファイアウォールの設定のファイアウォール設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="4c629-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="4c629-108">公衆交換電話網 (PSTN) ゲートウェイをセットアップする</span><span class="sxs-lookup"><span data-stu-id="4c629-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="4c629-p101">すべてのアプライアンスで仲介サーバーをポイントするように、各 PSTN ゲートウェイのトランクを設定します。プール FQDN はプール内のすべてのサーバーで同じであるため、各トランクは、仲介サーバー プール FQDN ではなく、1 つの仲介サーバーの FQDN または IP アドレスをポイントする必要があります。トランクは同じ優先順位で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c629-p101">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="4c629-112">仲介サーバーとゲートウェイ間で TLS を使用している場合は、ゲートウェイと仲介サーバーが MTLS をサポートするように、次のように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c629-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="4c629-113">ルート CA を Cloud Connector Active Directory コンピューターからエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="4c629-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="4c629-114">ルート CA のインポートについては、PSTN ゲートウェイ ベンダーの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="4c629-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="4c629-p102">ゲートウェイ用に発行された証明書のルート CA 証明書を仲介サーバーにインポートします。ゲートウェイ用の SSL 証明書を入手する必要がある場合は、次のように Cloud Connector Active Directory コンピューターで証明機関サービスを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4c629-p102">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="4c629-117">既存の Web Server テンプレートを変更して認証済みユーザーを登録できるようにするか、新しい Web Server テンプレートを作成して別のプロパティを構成して認証済みユーザーが登録できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4c629-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="4c629-118">詳細については、[証明書テンプレート](https://technet.microsoft.com/en-us/library/cc730705.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c629-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="4c629-119">有効にした Web Server テンプレートを選択して、証明書スナップインを使用して証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="4c629-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="4c629-120">件名に共通名を追加し、別名に DNS 名とゲートウェイの FQDN を追加して、[キー] オプションで秘密キーをエクスポート可能にする [秘密キー] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c629-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="4c629-121">秘密キーを使用して SSL 証明書をエクスポートし、PSTN ゲートウェイ ベンダーから提供された指示に従って、証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="4c629-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="4c629-122">テナントのドメインを更新する</span><span class="sxs-lookup"><span data-stu-id="4c629-122">Update the domain for your tenant</span></span>

<span data-ttu-id="4c629-123">Office 365 でドメインを更新する手順を完了し、DNS レコードを追加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c629-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="4c629-124">Office 365 でドメインを設定する方法の詳細については、 [Office 365 にドメインの追加](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c629-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="4c629-125">Office 365 でのエッジに必要な DNS レコードの追加</span><span class="sxs-lookup"><span data-stu-id="4c629-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="4c629-126">以下の DNS レコードを Office 365 テナントに追加します。</span><span class="sxs-lookup"><span data-stu-id="4c629-126">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="4c629-127">DNS レコードを Office 365 テナントに追加する方法の詳細については、[追加または編集カスタムの DNS レコード](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c629-127">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="4c629-128">アクセス エッジの DNS A レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4c629-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="4c629-p107">SRV レコードは Office 365 と展開スクリプトで自動的に作成されます。エッジ サーバーで _sip と _sipfederationtls の 2 つの SIP サービスを検索できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c629-p107">SRV records will automatically be created by Office 365 and the deployment scripts. Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![SRV レコードの確認](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="4c629-132">Cloud Connector エディションと Office 365 との間でのハイブリッド接続をセットアップする</span><span class="sxs-lookup"><span data-stu-id="4c629-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="4c629-133">ビジネス クラウド コネクタのエディションの展開では、Skype と、Office 365 テナントとの間のハイブリッドの接続を構成するには、リモート PowerShell セッションで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4c629-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="4c629-134">リモート PowerShell セッションを確立する方法についてを参照してください: [Windows PowerShell には、コンピューターを設定](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="4c629-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="4c629-135">このコマンドレットでは、アクセス エッジ外部 FQDN が設定されます。</span><span class="sxs-lookup"><span data-stu-id="4c629-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="4c629-136">コマンドの最初に、\<アクセス エッジの外部 FQDN\> SIP アクセス エッジ ロールの 1 つにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c629-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="4c629-137">既定では、この必要があります ap.\<ドメイン名\>。</span><span class="sxs-lookup"><span data-stu-id="4c629-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="4c629-138">ユーザーが PSTN のサイトに割り当てられていない場合にだけ、フォールバックとしてに使用される PSTN のサイトには、ピア ・ ターゲットに使用される外部アクセス エッジの FQDN を設定してください。</span><span class="sxs-lookup"><span data-stu-id="4c629-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="4c629-139">詳細については、[クラウドのコネクタで 1 つのサイトを展開](deploy-a-single-site-in-cloud-connector.md)し、[クラウドのコネクタで複数のサイトを展開](deploy-multiple-sites-in-cloud-connector.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c629-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="4c629-140">PSTN ゲートウェイの設定</span><span class="sxs-lookup"><span data-stu-id="4c629-140">Set up PSTN gateways</span></span>

<span data-ttu-id="4c629-p111">すべてのアプライアンスで仲介サーバーをポイントするように、各 PSTN ゲートウェイのトランクを設定します。プール FQDN はプール内のすべてのサービス プロファイルバージョンで同じであるため、各トランクは、仲介サーバー プール FQDN ではなく、1 つの仲介サーバーの FQDN または IP アドレスをポイントする必要があります。トランクは、同じ優先順位で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c629-p111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="4c629-144">仲介サーバーとゲートウェイ間で TLS を使用している場合は、ゲートウェイと仲介サーバーが MTLS をサポートするように、次のように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c629-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="4c629-145">ルート CA を Cloud Connector Active Directory コンピューターからエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="4c629-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="4c629-146">ルート CA のインポートについては、PSTN ゲートウェイ ベンダーの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="4c629-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="4c629-p112">ゲートウェイ用に発行された証明書のルート CA 証明書を仲介サーバーにインポートします。ゲートウェイ用の SSL 証明書を入手する必要がある場合は、次のように Cloud Connector Active Directory コンピューターで証明機関サービスを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4c629-p112">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="4c629-149">既存の Web Server テンプレートを変更して認証済みユーザーを登録できるようにするか、新しい Web Server テンプレートを作成して別のプロパティを構成して認証済みユーザーが登録できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4c629-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="4c629-150">詳細については、[証明書テンプレート](https://technet.microsoft.com/library/cc730705.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c629-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="4c629-151">有効にした Web Server テンプレートを選択して、証明書スナップインを使用して証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="4c629-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="4c629-152">件名に共通名を追加し、別名に DNS 名とゲートウェイの FQDN を追加して、[キー] オプションで秘密キーをエクスポート可能にする [秘密キー] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c629-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="4c629-153">秘密キーを使用して SSL 証明書をエクスポートし、PSTN ゲートウェイ ベンダーから提供された指示に従って、証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="4c629-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="4c629-154">1 つの PSTN サイトの PSTN ゲートウェイは、必ず同じサイトの仲介サーバーのみに接続します。</span><span class="sxs-lookup"><span data-stu-id="4c629-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="4c629-155">Office 365 でユーザーを設定する</span><span class="sxs-lookup"><span data-stu-id="4c629-155">Set up your users in Office 365</span></span>

<span data-ttu-id="4c629-156">Office 365 管理ポータルにログインし、オンラインの音声サービスに対応するユーザーを追加し、これらのユーザーに E5 ライセンスまたは、E3 ライセンスへの Office 365 の電話システム アドオンを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4c629-156">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="4c629-157">ユーザーを追加する方法の詳細については、[ビジネス向けの Office 365 のユーザーの追加](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c629-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="4c629-158">Office 365 の電話システムの音声およびボイスメール サービスを利用できるようにする</span><span class="sxs-lookup"><span data-stu-id="4c629-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="4c629-159">ユーザーを Office 365 に追加したら、ボイス メールを含む、Office 365 の電話システムの音声サービスを利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4c629-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="4c629-160">これらの機能を有効にするには、Office 365 Global Administrator ロールのアカウントを使用して Office 365 テナントにログ インし、リモート PowerShell を実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c629-160">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="4c629-161">リモート PowerShell セッションを確立する方法についてを参照してください: [Windows PowerShell には、コンピューターを設定します](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4c629-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="4c629-162">ユーザーに、ポリシーを設定し、ユーザーのビジネス電話番号、 **Id**パラメーターの値を指定するを構成します。</span><span class="sxs-lookup"><span data-stu-id="4c629-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="4c629-163">また、SIP アドレス、ユーザー プリンシパル名 (UPN)、ドメイン名とユーザー名 (domain\username)、および Active Directory での表示名 ("小林 良太") でユーザーの ID を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4c629-163">You can also specify a user's Identity by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
<span data-ttu-id="4c629-164">これで、次のスクリプトを使ってユーザーが追加され有効化されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4c629-164">You can then verify that the users were added and enabled using the following script:</span></span>
  
```
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="4c629-p117">ユーザーが国際通話を使えるようにするかどうかを決める必要があります。デフォルトでは、国際通話は有効です。オンラインの Skype for Business 管理センターを使ってユーザーの国際電話を無効化または有効化できます。</span><span class="sxs-lookup"><span data-stu-id="4c629-p117">You'll need to decide whether your users should be able to make international calls. By default, international calling is enabled. You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="4c629-168">ユーザー単位で国際電話を無効にするには、Skype for Business Online PowerShell で次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4c629-168">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="4c629-169">国際ユーザーごとに無効になっていますが後に呼び出すことを再度有効に、同じコマンドレットを実行、**グループ**の値を*InternationalCallsAllowed*に変更します。</span><span class="sxs-lookup"><span data-stu-id="4c629-169">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="4c629-170">ユーザーを PSTN サイトに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4c629-170">Assign users to PSTN sites</span></span>

<span data-ttu-id="4c629-171">サイトを 1 つだけ展開した場合でも、テナントのリモート PowerShell を使用して、サイトをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4c629-171">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="4c629-172">リモート PowerShell セッションを確立する方法についてを参照してください: [Windows PowerShell には、コンピューターを設定](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="4c629-172">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="4c629-173">ユーザーに PSTN サイトを割り当てないと、Skype for Business Cloud Connector エディションの展開と Office 365 テナント間のハイブリッド接続がフォールバックし、通話が完了できるようにテナント レベルの既定のもの (ピア ターゲット) が使用されることになります。</span><span class="sxs-lookup"><span data-stu-id="4c629-173">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="4c629-174">オンラインのハイブリッド仲介サーバーの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="4c629-174">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="4c629-175"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="4c629-175"></span></span>

<span data-ttu-id="4c629-176">P2P の呼び出しは、PSTN 会議にエスカレートされ、オンライン ビジネスの会議サーバーの Skype は招待をクラウド コネクタの仲介サーバーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="4c629-176">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="4c629-177">Office 365 のルーティングで招待が正常に処理できることを確認するには、次のように、オンラインのテナント クラウド コネクタの仲介サーバーごとに設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c629-177">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="4c629-178">Office 365 管理ポータルでユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4c629-178">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="4c629-179">」MediationServer1。」などの必要な任意のユーザー名を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c629-179">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="4c629-180">クラウド コネクタ (.ini ファイルの最初の SIP ドメイン) の既定の SIP ドメインをユーザー ドメインとして使用します。</span><span class="sxs-lookup"><span data-stu-id="4c629-180">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="4c629-181">なお、ライセンスの割り当てはのみ、ユーザーに伝達、Skype のビジネスのオンライン ディレクトリに必要な。</span><span class="sxs-lookup"><span data-stu-id="4c629-181">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="4c629-182">アカウントを作成、変更を反映するためには、最大で 1 時間を許可し、このアカウントからライセンスを削除するには、(E5) などの Office 365 のライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4c629-182">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate, then remove the license from this account.</span></span>
    
2. <span data-ttu-id="4c629-183">グローバルを使用してテナント Azure AD リモート PowerShell セッションまたはユーザー管理者の資格情報を起動し、Azure AD ユーザー アカウントの部門を設定するのには次のコマンドレットのように構成しの実行はステップ 1 を"HybridMediationServer"にします。</span><span class="sxs-lookup"><span data-stu-id="4c629-183">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="4c629-184">テナント Skype をビジネス テナント管理者の資格情報、し、そのユーザーに、仲介サーバーとエッジ サーバーの FQDN を設定するのには次のコマンドレットのアカウント、交換用の Skype を使用してビジネス リモート PowerShell セッションを開始\<表示名\>アカウントのユーザーの表示名では、手順 1 で作成します。</span><span class="sxs-lookup"><span data-stu-id="4c629-184">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="4c629-185">ID については、仲介サーバーに対して作成した Office 365 ユーザー　アカウントの表示名を使用してください。</span><span class="sxs-lookup"><span data-stu-id="4c629-185">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="4c629-186">*MediationServerFQDN* 、仲介サーバーの定義の内部 FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c629-186">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="4c629-187">*EdgeServerExternalFQDN* 、エッジ サーバーのアクセス プロキシに定義されている外部 FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c629-187">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="4c629-188">複数の Cloud Connector　PSTN サイトがある場合は、仲介サーバーが配置されているサイトに割り当てられているエッジ サーバー アクセス プロキシ の FQDN を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c629-188">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="4c629-189">複数の Cloud Connector 仲介サーバー (マルチサイト、HA) がある場合は、前述の手順を各サーバーに対して繰り返してください。</span><span class="sxs-lookup"><span data-stu-id="4c629-189">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

