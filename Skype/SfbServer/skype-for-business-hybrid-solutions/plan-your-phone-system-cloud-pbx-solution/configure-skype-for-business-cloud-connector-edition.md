---
title: Skype for Business Cloud Connector Edition の構成と管理
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
description: Skype for Business Cloud Connector Edition (最小限のオンプレミス トポロジ) を構成して、Skype for Business Online でオンプレミスの音声インフラストラクチャと電話システム (Cloud PBX) 音声サービスを統合する方法について学習します。
ms.openlocfilehash: 4d24e5a312275158f276856aa78396ad63dff615
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094875"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="62db2-103">Skype for Business Cloud Connector Edition の構成と管理</span><span class="sxs-lookup"><span data-stu-id="62db2-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="62db2-104">Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="62db2-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="62db2-105">組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="62db2-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="62db2-106">Skype for Business Cloud Connector Edition (最小限のオンプレミス トポロジ) を構成して、Skype for Business Online でオンプレミスの音声インフラストラクチャと電話システム (Cloud PBX) 音声サービスを統合する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="62db2-106">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="62db2-107">開始する前に [、「Plan for Skype for Business Cloud Connector Edition」の前提条件を確認する必要があります](plan-skype-for-business-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="62db2-107">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="62db2-108">このトピックの手順は、Cloud Connector Edition 1.4.1 以降にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="62db2-108">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="62db2-109">まだ Cloud Connector Edition 2.1 にアップグレードしていない場合は、「新しいバージョンのクラウド コネクタにアップグレードする」 [を参照してください](upgrade-to-a-new-version-of-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="62db2-109">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="62db2-110">インストール ファイルは、 からダウンロードできます [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。</span><span class="sxs-lookup"><span data-stu-id="62db2-110">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="62db2-111">Skype for Business Cloud Connector Edition を構成する手順</span><span class="sxs-lookup"><span data-stu-id="62db2-111">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="62db2-112">次の表に、Cloud Connector Edition をインストールして構成する必要がある手順を示します。</span><span class="sxs-lookup"><span data-stu-id="62db2-112">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="62db2-113">**手順**</span><span class="sxs-lookup"><span data-stu-id="62db2-113">**Step**</span></span>|<span data-ttu-id="62db2-114">**説明**</span><span class="sxs-lookup"><span data-stu-id="62db2-114">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="62db2-115">Cloud Connector アプライアンスの準備</span><span class="sxs-lookup"><span data-stu-id="62db2-115">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="62db2-116">インストール ファイルをダウンロードし、証明書を準備し、Hyper-V を構成し、クラウド コネクタの展開に備える環境を取得します。</span><span class="sxs-lookup"><span data-stu-id="62db2-116">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="62db2-117">Cloud Connector での単一サイトの展開</span><span class="sxs-lookup"><span data-stu-id="62db2-117">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="62db2-118">クラウド コネクタ展開でサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="62db2-118">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="62db2-119">Cloud Connector での複数サイトの展開</span><span class="sxs-lookup"><span data-stu-id="62db2-119">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="62db2-120">展開にサイトを追加し、単一サイト展開と複数サイト展開の違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="62db2-120">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="62db2-121">Microsoft 365 または 365 組織とのクラウド コネクタOffice構成する</span><span class="sxs-lookup"><span data-stu-id="62db2-121">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="62db2-122">DNS レコードの追加、ハイブリッドの構成、PSTN ゲートウェイのセットアップ、および電話システムボイス メールのユーザーの有効化。</span><span class="sxs-lookup"><span data-stu-id="62db2-122">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="62db2-123">Cloud Connector 展開の検証</span><span class="sxs-lookup"><span data-stu-id="62db2-123">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="62db2-124">展開が正しく動作するようにします。</span><span class="sxs-lookup"><span data-stu-id="62db2-124">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="62db2-125">Cloud Connector 新バージョンへのアップグレード</span><span class="sxs-lookup"><span data-stu-id="62db2-125">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="62db2-126">既存のクラウド コネクタ展開をバージョン 2.1 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="62db2-126">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="62db2-127">既存の Cloud Connector の展開構成の変更</span><span class="sxs-lookup"><span data-stu-id="62db2-127">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="62db2-128">クラウド コネクタが既に展開された後で、クラウド コネクタの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="62db2-128">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="62db2-129">Cloud Connector Edition でのメディア バイパスの展開</span><span class="sxs-lookup"><span data-stu-id="62db2-129">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="62db2-130">クラウド コネクタでメディア バイパスを展開する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="62db2-130">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="62db2-131">Cloud Connector コマンドレットのリファレンス</span><span class="sxs-lookup"><span data-stu-id="62db2-131">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="62db2-132">クラウド コネクタで使用される PowerShell コマンドレットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="62db2-132">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="62db2-133">Cloud Connector 展開のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="62db2-133">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="62db2-134">クラウド コネクタの展開で発生する一般的な問題に対する解決策。</span><span class="sxs-lookup"><span data-stu-id="62db2-134">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
