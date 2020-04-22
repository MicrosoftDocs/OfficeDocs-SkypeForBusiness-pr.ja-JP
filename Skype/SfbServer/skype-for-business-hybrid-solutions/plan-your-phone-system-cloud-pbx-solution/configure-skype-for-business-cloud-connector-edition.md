---
title: Skype for Business Cloud Connector エディションを構成および管理する
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
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Skype for business Cloud Connector エディションを構成する方法について説明します。これには、オンプレミスの音声インフラストラクチャと、Skype for Business Online の Office 365 (クラウド PBX) の電話システムとの統合を可能にするための最小限のオンプレミスのトポロジがあります。
ms.openlocfilehash: aa0d8fb37dcaddaca3835b25b94eba6a18e03636
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779163"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="fb11d-103">Skype for Business Cloud Connector エディションを構成および管理する</span><span class="sxs-lookup"><span data-stu-id="fb11d-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="fb11d-104">Skype for business Cloud Connector エディションを構成する方法について説明します。これには、オンプレミスの音声インフラストラクチャと、Skype for Business Online の Office 365 (クラウド PBX) の電話システムとの統合を可能にするための最小限のオンプレミスのトポロジがあります。</span><span class="sxs-lookup"><span data-stu-id="fb11d-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="fb11d-105">開始する前に、「 [Plan For Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)」の前提条件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="fb11d-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fb11d-106">このトピックの手順は、Cloud Connector エディション1.4.1 以降にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="fb11d-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="fb11d-107">まだ Cloud Connector Edition 2.1 にアップグレードしていない場合は、「 [Cloud connector の新しいバージョンへのアップグレード](upgrade-to-a-new-version-of-cloud-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb11d-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="fb11d-108">インストールファイルはから[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="fb11d-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="fb11d-109">Skype for Business Cloud Connector エディションを構成する手順</span><span class="sxs-lookup"><span data-stu-id="fb11d-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="fb11d-110">次の表に、Cloud Connector エディションをインストールして構成するために必要な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="fb11d-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="fb11d-111">**手順**</span><span class="sxs-lookup"><span data-stu-id="fb11d-111">**Step**</span></span>|<span data-ttu-id="fb11d-112">**説明**</span><span class="sxs-lookup"><span data-stu-id="fb11d-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="fb11d-113">Cloud Connector アプライアンスの準備</span><span class="sxs-lookup"><span data-stu-id="fb11d-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="fb11d-114">インストールファイルをダウンロードし、証明書を準備し、Hyper-v を構成して、クラウドコネクタ展開用に環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="fb11d-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="fb11d-115">Cloud Connector で単一のサイトを展開する</span><span class="sxs-lookup"><span data-stu-id="fb11d-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="fb11d-116">Cloud Connector の展開にサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb11d-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="fb11d-117">Cloud Connector で複数のサイトを展開する</span><span class="sxs-lookup"><span data-stu-id="fb11d-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="fb11d-118">展開にサイトを追加し、単一展開とマルチサイト展開の違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fb11d-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="fb11d-119">Office 365 組織とのクラウドコネクタ統合を構成する</span><span class="sxs-lookup"><span data-stu-id="fb11d-119">Configure Cloud Connector integration with your Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="fb11d-120">DNS レコードを追加し、ハイブリッドを構成し、PSTN ゲートウェイを設定し、Office 365 ボイスメールの電話システムに対してユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fb11d-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="fb11d-121">Cloud Connector の展開を検証する</span><span class="sxs-lookup"><span data-stu-id="fb11d-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="fb11d-122">展開が正しく動作していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fb11d-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="fb11d-123">Cloud Connector の新しいバージョンにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="fb11d-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="fb11d-124">既存の Cloud Connector の展開をバージョン2.1 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="fb11d-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="fb11d-125">既存の Cloud Connector の展開の構成を変更する</span><span class="sxs-lookup"><span data-stu-id="fb11d-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="fb11d-126">既に展開されている場合、Cloud Connector の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="fb11d-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="fb11d-127">Cloud Connector エディションでのメディアバイパスの展開</span><span class="sxs-lookup"><span data-stu-id="fb11d-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="fb11d-128">Cloud Connector でメディアバイパスを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb11d-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="fb11d-129">Cloud Connector コマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="fb11d-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="fb11d-130">Cloud Connector で使用される PowerShell コマンドレットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fb11d-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="fb11d-131">Cloud Connector の展開のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="fb11d-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="fb11d-132">Cloud Connector の展開で発生する一般的な問題の解決方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fb11d-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

