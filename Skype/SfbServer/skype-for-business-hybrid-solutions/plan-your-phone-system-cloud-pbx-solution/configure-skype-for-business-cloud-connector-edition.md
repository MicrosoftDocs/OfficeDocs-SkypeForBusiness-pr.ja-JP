---
title: Skype for Business Cloud Connector エディションの構成と管理
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Skype をビジネス クラウド コネクタ版、オンライン ビジネスの電話システムと Skype のインターネット電話サービスを Office 365 (クラウド PBX) で、設置型音声インフラストラクチャの統合を有効にするのには最小限の設置型のトポロジを構成する方法について説明します。
ms.openlocfilehash: 33843ed9bddbc5a935a75cf3b113dccaa325222b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="1953c-103">Skype for Business Cloud Connector エディションの構成と管理</span><span class="sxs-lookup"><span data-stu-id="1953c-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="1953c-104">Skype をビジネス クラウド コネクタ版、オンライン ビジネスの電話システムと Skype のインターネット電話サービスを Office 365 (クラウド PBX) で、設置型音声インフラストラクチャの統合を有効にするのには最小限の設置型のトポロジを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1953c-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="1953c-105">開始する前に[ビジネス クラウド コネクタ ・ エディションの Skype の計画](plan-skype-for-business-cloud-connector-edition.md)の前提条件を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1953c-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1953c-106">このトピックの手順は Cloud Connector Edition 1.4.1 以降のみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1953c-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="1953c-107">アップグレードした場合いないまだクラウド コネクタ版 2.1 に、[クラウドのコネクタの新しいバージョンへのアップグレード](upgrade-to-a-new-version-of-cloud-connector.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1953c-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="1953c-108">インストール ファイルをダウンロードすることができます[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)。</span><span class="sxs-lookup"><span data-stu-id="1953c-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="1953c-109">Skype for Business Cloud Connector エディションを構成する手順</span><span class="sxs-lookup"><span data-stu-id="1953c-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="1953c-110">次の表に、Cloud Connector エディションをインストールして構成するために必要な手順のリストを示します。</span><span class="sxs-lookup"><span data-stu-id="1953c-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="1953c-111">**手順**</span><span class="sxs-lookup"><span data-stu-id="1953c-111">**Step**</span></span>|<span data-ttu-id="1953c-112">**説明**</span><span class="sxs-lookup"><span data-stu-id="1953c-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="1953c-113">クラウド コネクタ アプライアンスを準備します。</span><span class="sxs-lookup"><span data-stu-id="1953c-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="1953c-114">インストール ファイルをダウンロード、証明書を準備、HYPER-V を構成し、環境の準備、クラウドのコネクタの配置。</span><span class="sxs-lookup"><span data-stu-id="1953c-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="1953c-115">クラウド コネクタで 1 つのサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="1953c-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="1953c-116">お使いの Cloud Connector 展開にサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1953c-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="1953c-117">クラウドのコネクタで複数のサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="1953c-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="1953c-118">展開にサイトを追加し、単一サイト展開とマルチサイト展開の違いを把握します。</span><span class="sxs-lookup"><span data-stu-id="1953c-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="1953c-119">Office 365 テナント クラウド コネクタの統合を構成します。</span><span class="sxs-lookup"><span data-stu-id="1953c-119">Configure Cloud Connector integration with your Office 365 tenant</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="1953c-120">DNS レコードを追加し、ハイブリッドを構成し、PSTN ゲートウェイを設定し、ユーザーが Office 365 の電話システムのボイス メールを使えるようにします。</span><span class="sxs-lookup"><span data-stu-id="1953c-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="1953c-121">クラウドのコネクタの配置を検証します。</span><span class="sxs-lookup"><span data-stu-id="1953c-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="1953c-122">展開が正常に機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1953c-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="1953c-123">クラウド コネクタを新しいバージョンにアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="1953c-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="1953c-124">既存の Cloud Connector 展開をバージョン 2.1 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="1953c-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="1953c-125">既存のコネクタのクラウド展開の構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="1953c-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="1953c-126">すでに配備されている後は、クラウドのコネクタの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="1953c-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="1953c-127">クラウド コネクタのエディションでのメディア バイ パスを展開します。</span><span class="sxs-lookup"><span data-stu-id="1953c-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="1953c-128">Cloud Connector でメディア バイパスを展開する方法。</span><span class="sxs-lookup"><span data-stu-id="1953c-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="1953c-129">クラウドのコネクタのコマンドレットのリファレンス</span><span class="sxs-lookup"><span data-stu-id="1953c-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="1953c-130">Cloud Connector で使用する PowerShell コマンドレットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1953c-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="1953c-131">クラウドのコネクタの配置をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="1953c-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="1953c-132">クラウド コネクタの展開に関する一般的な課題の解決策です。</span><span class="sxs-lookup"><span data-stu-id="1953c-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

