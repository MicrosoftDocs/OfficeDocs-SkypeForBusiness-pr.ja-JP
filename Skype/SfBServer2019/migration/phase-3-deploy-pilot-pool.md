---
title: フェーズ 3 Skype for Business Server 2019 パイロットプールの展開
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f12b1517-fb56-4ded-8323-57aa9fc9ea48
description: このセクションでは、Skype for Business Server 2019 のパイロットプールを展開するために必要な手順について説明します。 Skype for Business Server 2019 の展開では、トポロジビルダーを使用して、展開するトポロジとコンポーネントを定義し、Skype for Business Server 2019 コンポーネントの展開のために環境を準備して、トポロジを公開する必要があります。第1のフロントエンドサーバーで設計し、次に、展開用のコンポーネント用に Skype for Business Server 2019 ソフトウェアをインストールして構成します。 完了すると、Skype for Business Server 2019 パイロットプールの展開は既存のレガシープールと共存します。
ms.openlocfilehash: d8524d74364bac111182182ecd1f6e22972fb898
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273925"
---
# <a name="phase-3-deploy-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="de5c1-105">フェーズ 3: Skype for Business Server 2019 パイロットプールの展開</span><span class="sxs-lookup"><span data-stu-id="de5c1-105">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>

<span data-ttu-id="de5c1-106">このセクションでは、Skype for Business Server 2019 のパイロットプールを展開するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="de5c1-106">This section covers the steps required to deploy a pilot pool of Skype for Business Server 2019.</span></span> <span data-ttu-id="de5c1-107">Skype for Business Server 2019 の展開では、トポロジビルダーを使用して、展開するトポロジとコンポーネントを定義し、Skype for Business Server 2019 コンポーネントの展開のために環境を準備して、トポロジを公開する必要があります。第1のフロントエンドサーバーで設計し、次に、展開用のコンポーネント用に Skype for Business Server 2019 ソフトウェアをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="de5c1-107">The deployment of Skype for Business Server 2019 requires using Topology Builder to define your topology and the components you want to deploy, preparing your environment for deployment of the Skype for Business Server 2019 components, publishing your topology design on the first Front End Server, and then installing and configuring Skype for Business Server 2019 software for the components for your deployment.</span></span> <span data-ttu-id="de5c1-108">完了すると、Skype for Business Server 2019 パイロットプールの展開は既存のレガシープールと共存します。</span><span class="sxs-lookup"><span data-stu-id="de5c1-108">When completed, your Skype for Business Server 2019 pilot pool deployment will coexist with an existing legacy pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="de5c1-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="de5c1-109">In this section</span></span>

- [<span data-ttu-id="de5c1-110">Skype for Business Server 用 Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="de5c1-110">Prepare Active Directory for Skype for Business Server</span></span>](prepare-active-directory.md)
    
- [<span data-ttu-id="de5c1-111">既存の展開環境からのトポロジのダウンロード</span><span class="sxs-lookup"><span data-stu-id="de5c1-111">Download topology from existing deployment</span></span>](download-topology-from-existing-deployment.md)
    
- [<span data-ttu-id="de5c1-112">Skype for Business Server 2019 パイロットプールの展開</span><span class="sxs-lookup"><span data-stu-id="de5c1-112">Deploy Skype for Business Server 2019 pilot pool</span></span>](deploy-pilot-pool.md)
    
- [<span data-ttu-id="de5c1-113">パイロット プールとレガシ プールの共存の確認</span><span class="sxs-lookup"><span data-stu-id="de5c1-113">Verify pilot pool coexistence with legacy pool</span></span>](verify-pilot-pool-coexistence-with-legacy-pool.md)
    
- [<span data-ttu-id="de5c1-114">パイロット プールのレガシ エッジ サーバーへの接続</span><span class="sxs-lookup"><span data-stu-id="de5c1-114">Connect pilot pool to legacy Edge Servers</span></span>](connect-pilot-pool-to-legacy-edge-servers.md)
    
- [<span data-ttu-id="de5c1-115">XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成</span><span class="sxs-lookup"><span data-stu-id="de5c1-115">Configure XMPP gateway access policies and certificates</span></span>](configure-xmpp-gateway-access-policies-and-certificates.md)
    

