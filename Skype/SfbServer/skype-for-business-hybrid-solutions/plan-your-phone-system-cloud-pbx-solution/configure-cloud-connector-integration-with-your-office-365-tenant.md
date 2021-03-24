---
title: Microsoft 365 または 365 組織とのクラウド コネクタOffice構成する
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
description: Microsoft 365 組織または Microsoft 365 組織とのクラウド コネクタOffice説明します。
ms.openlocfilehash: 74696023dcffbc91641bb4e9950f2988a89abbdd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095091"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="663d7-103">Microsoft 365 または 365 組織とのクラウド コネクタOffice構成する</span><span class="sxs-lookup"><span data-stu-id="663d7-103">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>

> [!Important] 
> <span data-ttu-id="663d7-104">Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="663d7-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="663d7-105">組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="663d7-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="663d7-106">Microsoft 365 組織または Microsoft 365 組織とのクラウド コネクタOffice説明します。</span><span class="sxs-lookup"><span data-stu-id="663d7-106">Learn how to configure Cloud Connector integration with your Microsoft 365 or Office 365 organization.</span></span>
  
<span data-ttu-id="663d7-107">Skype for Business Cloud Connector Edition のインストールが完了したら、このセクションの手順を実行して展開を構成し、Microsoft 365 または Office 365 組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="663d7-107">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Microsoft 365 or Office 365 organization.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="663d7-108">ファイアウォール設定の構成</span><span class="sxs-lookup"><span data-stu-id="663d7-108">Configure firewall settings</span></span>

<span data-ttu-id="663d7-109">「Plan [for Skype for Business Cloud Connector Edition」](plan-skype-for-business-cloud-connector-edition.md)の「ポートとプロトコル」[](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)の説明に従って、境界ネットワークの内部および外部ファイアウォール設定のファイアウォール設定を構成して、必要なポートを開きます。</span><span class="sxs-lookup"><span data-stu-id="663d7-109">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="663d7-110">公衆交換電話網 (PSTN) ゲートウェイのセットアップ</span><span class="sxs-lookup"><span data-stu-id="663d7-110">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="663d7-111">すべてのアプライアンスの仲介サーバーを指し示すトランクを各 PSTN ゲートウェイに設定します。</span><span class="sxs-lookup"><span data-stu-id="663d7-111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="663d7-112">プールの FQDN はプール内のすべてのサーバーで同じなので、各トランクは仲介サーバー プールの FQDN ではなく 1 つの仲介サーバー FQDN または IP アドレスを指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="663d7-112">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="663d7-113">トランクは同じ優先度で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="663d7-113">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="663d7-114">仲介サーバーとゲートウェイの間で TLS を使用している場合は、MTLS をサポートするためにゲートウェイと仲介サーバーを次のように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="663d7-114">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="663d7-115">クラウド コネクタ Active Directory コンピューターからルート CA をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="663d7-115">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="663d7-116">ルート CA のインポートについては、PSTN ゲートウェイ ベンダーの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="663d7-116">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="663d7-117">仲介サーバー上のゲートウェイに発行された証明書のルート CA 証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="663d7-117">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="663d7-118">ゲートウェイの SSL 証明書を取得する必要がある場合は、次のようにクラウド コネクタ Active Directory コンピューターで実行されている証明機関サービスを使用してこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="663d7-118">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="663d7-119">既存の Web Server テンプレートを変更して、認証済みユーザーが登録を有効にするか、新しい Web Server テンプレートを作成して他のプロパティを構成し、認証済みユーザーが登録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="663d7-119">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="663d7-120">詳細な手順については、「証明書テンプレート [」を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="663d7-120">For detailed instructions, see [Certificate Templates](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).</span></span>
    
   - <span data-ttu-id="663d7-121">有効にした Web サーバー テンプレートを選択する証明書スナップインを使用して証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="663d7-121">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="663d7-122">ゲートウェイの FQDN を持つ代替名のサブジェクトと DNS 名に共通名を必ず追加し、キー オプションの下で [プライベート キーをエクスポート可能にする] が選択されている [プライベート キー] で確認します。</span><span class="sxs-lookup"><span data-stu-id="663d7-122">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="663d7-123">プライベート キーを使用して SSL 証明書をエクスポートし、PSTN ゲートウェイ ベンダーの指示に従って証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="663d7-123">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="663d7-124">テナントのドメインを更新する</span><span class="sxs-lookup"><span data-stu-id="663d7-124">Update the domain for your tenant</span></span>

<span data-ttu-id="663d7-125">Microsoft 365 または Office 365 でドメインを更新する手順が完了し、DNS レコードを追加する機能を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="663d7-125">Make sure that you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="663d7-126">Microsoft 365 または Office 365 でドメインをセットアップする方法の詳細については [、「Add a domain to Microsoft 365 or Office 365」を参照](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)してください。</span><span class="sxs-lookup"><span data-stu-id="663d7-126">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-for-your-edge"></a><span data-ttu-id="663d7-127">エッジの DNS レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="663d7-127">Add DNS records for your Edge</span></span>

<span data-ttu-id="663d7-128">Microsoft 365 または 365 組織に次Office追加します。</span><span class="sxs-lookup"><span data-stu-id="663d7-128">Add the following DNS records to your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="663d7-129">DNS レコードを追加する方法の詳細については [、「Microsoft 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)または microsoft 365 または Office 365 のカスタム DNS レコードを追加または編集する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="663d7-129">For information about how to add DNS records, see [Add or edit custom DNS records in Microsoft 365 or Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="663d7-130">アクセス エッジの DNS A レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="663d7-130">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="663d7-131">SRV レコードは、Microsoft 365 または 365 Office展開スクリプトによって自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="663d7-131">SRV records will automatically be created by Microsoft 365 or Office 365 and the deployment scripts.</span></span> <span data-ttu-id="663d7-132">エッジで次の 2 つの SIP サービス (sip と \_ \_ sipfederationtls) を参照できる点を確認します。</span><span class="sxs-lookup"><span data-stu-id="663d7-132">Confirm that you can look up the following two SIP services on the Edge: \_sip and \_sipfederationtls.</span></span>
    
     ![SRV レコードの確認](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a><span data-ttu-id="663d7-134">クラウド コネクタエディションと Microsoft 365 または Microsoft 365 または microsoft 365 Officeセットアップ</span><span class="sxs-lookup"><span data-stu-id="663d7-134">Set up hybrid connectivity between Cloud Connector Edition and Microsoft 365 or Office 365</span></span>

<span data-ttu-id="663d7-135">Skype for Business Cloud Connector Edition 展開と Microsoft 365 または Office 365 組織とのハイブリッド接続を構成するには、リモート PowerShell セッションで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="663d7-135">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="663d7-136">リモート PowerShell セッションを確立する方法については、「コンピューターのセットアップ」を参照[Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="663d7-136">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
<span data-ttu-id="663d7-137">コマンドレットは、Access Edge 外部 FQDN を設定します。</span><span class="sxs-lookup"><span data-stu-id="663d7-137">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="663d7-138">最初のコマンドでは \<External Access Edge FQDN\> 、SIP アクセス エッジの役割の 1 つが必要です。</span><span class="sxs-lookup"><span data-stu-id="663d7-138">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="663d7-139">既定では、これは ap である必要があります \<Domain Name\> 。</span><span class="sxs-lookup"><span data-stu-id="663d7-139">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="663d7-140">ピア宛先に使用される外部アクセス エッジ FQDN は、ユーザーが PSTN サイトに割り当てられていない場合にのみフォールバックとして使用される PSTN サイトに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="663d7-140">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="663d7-141">詳細については、「単一サイト [をクラウド コネクタに展開](deploy-a-single-site-in-cloud-connector.md) する」および「Cloud Connector で複数のサイトを展開する」 [を参照してください](deploy-multiple-sites-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="663d7-141">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="663d7-142">PSTN ゲートウェイのセットアップ</span><span class="sxs-lookup"><span data-stu-id="663d7-142">Set up PSTN gateways</span></span>

<span data-ttu-id="663d7-143">すべてのアプライアンスの仲介サーバーを指し示すトランクを各 PSTN ゲートウェイに設定します。</span><span class="sxs-lookup"><span data-stu-id="663d7-143">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="663d7-144">プール FQDN はプール内のすべてのサーバーで同じなので、各トランクは仲介サーバー プールの FQDN ではなく 1 つの仲介サーバー FQDN または IP アドレスを指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="663d7-144">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="663d7-145">トランクは同じ優先度で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="663d7-145">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="663d7-146">仲介サーバーとゲートウェイの間で TLS を使用している場合は、MTLS をサポートするためにゲートウェイと仲介サーバーを次のように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="663d7-146">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="663d7-147">クラウド コネクタ Active Directory コンピューターからルート CA をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="663d7-147">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="663d7-148">ルート CA のインポートについては、PSTN ゲートウェイ ベンダーの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="663d7-148">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="663d7-149">仲介サーバー上のゲートウェイに発行された証明書のルート CA 証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="663d7-149">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="663d7-150">ゲートウェイの SSL 証明書を取得する必要がある場合は、次のようにクラウド コネクタ Active Directory コンピューターで実行されている証明機関サービスを使用してこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="663d7-150">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="663d7-151">既存の Web Server テンプレートを変更して、認証済みユーザーが登録を有効にするか、新しい Web サーバー テンプレートを作成して他のプロパティを構成し、認証済みユーザーが登録できます。</span><span class="sxs-lookup"><span data-stu-id="663d7-151">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="663d7-152">詳細な手順については、「証明書テンプレート [」を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="663d7-152">For detailed instructions, see [Certificate Templates](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).</span></span>
    
   - <span data-ttu-id="663d7-153">有効にした Web サーバー テンプレートを選択する証明書スナップインを使用して証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="663d7-153">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="663d7-154">ゲートウェイの FQDN を持つ代替名のサブジェクトと DNS 名に共通名を必ず追加し、キー オプションの下で [プライベート キーをエクスポート可能にする] が選択されている [プライベート キー] で確認します。</span><span class="sxs-lookup"><span data-stu-id="663d7-154">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="663d7-155">プライベート キーを使用して SSL 証明書をエクスポートし、PSTN ゲートウェイ ベンダーの指示に従って証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="663d7-155">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="663d7-156">1 つの PSTN サイトの PSTN ゲートウェイは、同じサイト内の仲介サーバーにのみ接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="663d7-156">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users"></a><span data-ttu-id="663d7-157">ユーザーを設定する</span><span class="sxs-lookup"><span data-stu-id="663d7-157">Set up your users</span></span>

<span data-ttu-id="663d7-158">Microsoft 365 管理センターにログインし、オンライン 音声サービスを有効にするユーザーを追加し、E5 ライセンスまたは電話システム アドオンをこれらのユーザーに E3 ライセンスに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="663d7-158">Log in to the Microsoft 365 admin center, add the users that will be enabled for online voice services, and assign an E5 license or Phone System add-on to the E3 license to these users.</span></span> <span data-ttu-id="663d7-159">ユーザーの追加の詳細については、「 [ビジネス向け Microsoft 365 にユーザーを追加する」を参照してください](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)。</span><span class="sxs-lookup"><span data-stu-id="663d7-159">For information about adding users, see [Add users to Microsoft 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a><span data-ttu-id="663d7-160">電話システムの音声およびボイスメール サービスのユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="663d7-160">Enable users for Phone System voice and voicemail services</span></span>
 
<span data-ttu-id="663d7-161">Microsoft 365 または Office 365 にユーザーを追加した後、ボイスメールを含む電話システム音声サービスのアカウントを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="663d7-161">After adding your users to Microsoft 365 or Office 365, enable their accounts for Phone System voice services, including voicemail.</span></span> <span data-ttu-id="663d7-162">これらの機能を有効にするには、グローバル管理者の役割であるアカウントを使用して Microsoft 365 または Office 365 組織にログインし、リモート PowerShell を実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="663d7-162">To enable these capabilities, you must log in to your Microsoft 365 or Office 365 organization with an account that is a Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="663d7-163">リモート PowerShell セッションを確立する方法については、「デバイス用にコンピューターをセットアップする」 [を参照Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="663d7-163">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>
  
- <span data-ttu-id="663d7-164">ポリシーをユーザーに割り当て、Identity パラメーターの値で指定するユーザーのビジネス音声電話番号を **構成** します。</span><span class="sxs-lookup"><span data-stu-id="663d7-164">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="663d7-165">ユーザー ID は、ユーザーの SIP アドレス、ユーザー プリンシパル名 (UPN)、またはユーザーの Active Directory 表示名 ("Bob Kelly" など) を使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="663d7-165">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="663d7-166">アスタリスク ( \* ) 文字は、ユーザー ID として表示名と一緒に使用できます。</span><span class="sxs-lookup"><span data-stu-id="663d7-166">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="663d7-167">たとえば、Identity " Smith" は、文字列値 "Smith" で終わる表示名を持つすべてのユーザー \* を返します。</span><span class="sxs-lookup"><span data-stu-id="663d7-167">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="663d7-168">次のスクリプトを使用して、ユーザーが追加され、有効にされたと確認できます。</span><span class="sxs-lookup"><span data-stu-id="663d7-168">You can then verify that the users were added and enabled using the following script:</span></span>
  
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

<span data-ttu-id="663d7-169">ユーザーが国際通話を行えるかどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="663d7-169">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="663d7-170">既定では、国際通話は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="663d7-170">By default, international calling is enabled.</span></span> <span data-ttu-id="663d7-171">オンラインの Skype for Business 管理センターを使用して、ユーザーが国際ダイヤルを無効または有効にできます。</span><span class="sxs-lookup"><span data-stu-id="663d7-171">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="663d7-172">ユーザー単位で国際通話を無効にするには、Skype for Business Online PowerShell で次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="663d7-172">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="663d7-173">無効にした後にユーザーごとに国際通話を再び有効にするには、同じコマンドレットを実行しますが **、PolicyName** の値を *InternationalCallsAllowed に変更します*  。</span><span class="sxs-lookup"><span data-stu-id="663d7-173">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="663d7-174">PSTN サイトへのユーザーの割り当て</span><span class="sxs-lookup"><span data-stu-id="663d7-174">Assign users to PSTN sites</span></span>

<span data-ttu-id="663d7-175">1 つのサイトのみを展開した場合でも、テナントリモート PowerShell を使用してサイトをユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="663d7-175">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="663d7-176">リモート PowerShell セッションを確立する方法については、「コンピューターのセットアップ」を参照[Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="663d7-176">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="663d7-177">PSTN サイトがユーザーに割り当てられていない場合、Skype for Business Cloud Connector Edition 展開と Microsoft 365 または Office 365 組織間のハイブリッド接続は、テナント レベルの既定の 1 (ピア宛先) を使用して通話を完了できます。</span><span class="sxs-lookup"><span data-stu-id="663d7-177">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="663d7-178">オンライン ハイブリッド 仲介サーバーの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="663d7-178">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="663d7-179"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="663d7-179"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="663d7-180">P2P 通話が PSTN 会議にエスカレートすると、Skype for Business Online 会議サーバーはクラウド コネクタ仲介サーバーに招待を送信します。</span><span class="sxs-lookup"><span data-stu-id="663d7-180">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="663d7-181">Microsoft 365 または Office 365 でこの招待を正常にルーティングするには、次のように、クラウド コネクタ 仲介サーバーごとにオンライン テナントの設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="663d7-181">To ensure that Microsoft 365 or Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="663d7-182">Microsoft 365 管理センターでユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="663d7-182">Create a user in the Microsoft 365 admin center.</span></span> <span data-ttu-id="663d7-183">"MediationServer1" など、必要なユーザー名を使用します。</span><span class="sxs-lookup"><span data-stu-id="663d7-183">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="663d7-184">クラウド コネクタの既定の SIP ドメイン (.ini ファイルの最初の SIP ドメイン) をユーザー ドメインとして使用します。</span><span class="sxs-lookup"><span data-stu-id="663d7-184">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="663d7-185">ライセンスの割り当ては、Skype for Business オンライン ディレクトリへのユーザー伝達にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="663d7-185">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="663d7-186">作成したアカウントに Microsoft 365 または Office 365 ライセンス (E5 など) を割り当て、変更が反映されるように最大 1 時間を許可し、次のコマンドレットを実行して、Skype for Business オンライン ディレクトリにユーザー アカウントが正しくプロビジョニングされていることを確認し、このアカウントからライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="663d7-186">Assign a Microsoft 365 or Office 365 license (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="663d7-187">グローバルまたはユーザー管理者の資格情報を使用してテナント Azure AD リモート PowerShell セッションを開始し、次のコマンドレットを実行して、手順 1 で構成された Azure AD ユーザー アカウントの部門を "HybridMediationServer" に設定します。</span><span class="sxs-lookup"><span data-stu-id="663d7-187">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="663d7-188">Skype for Business テナント管理者資格情報を使用してテナント Skype for Business リモート PowerShell セッションを開始し、次のコマンドレットを実行して仲介サーバーとエッジ サーバーの FQDN をそのユーザー アカウントに設定し、手順 1 で作成したアカウントのユーザーの表示名に置き換えてください。 \<DisplayName\></span><span class="sxs-lookup"><span data-stu-id="663d7-188">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="663d7-189">Identity の場合は、この仲介サーバー用に作成したユーザー アカウントの表示名を使用します。</span><span class="sxs-lookup"><span data-stu-id="663d7-189">For Identity, use the Display Name of the user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="663d7-190">*MediationServerFQDN の* 場合は、仲介サーバーに定義されている内部 FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="663d7-190">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="663d7-191">*EdgeServerExternalFQDN の* 場合は、エッジ サーバー アクセス プロキシ用に定義されている外部 FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="663d7-191">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="663d7-192">複数のクラウド コネクタ PSTN サイトがある場合は、仲介サーバーがあるサイトに割り当てられているエッジ サーバー アクセス プロキシ FQDN を選択します。</span><span class="sxs-lookup"><span data-stu-id="663d7-192">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="663d7-193">複数のクラウド コネクタ 仲介サーバー (複数サイト、HA) がある場合は、それぞれの手順を繰り返してください。</span><span class="sxs-lookup"><span data-stu-id="663d7-193">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
