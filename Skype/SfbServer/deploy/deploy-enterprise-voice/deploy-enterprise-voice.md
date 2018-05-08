---
title: Skype for Business Server 2015 でのエンタープライズ VoIP の展開
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 概要では、Skype のセントラル サイトでのビジネス サーバー 2015 のエンタープライズ VoIP を展開する方法について説明します。
ms.openlocfilehash: 858519652b9f50e11e87c2ac9d3777bae9371ae0
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="b385f-103">Skype for Business Server 2015 でのエンタープライズ VoIP の展開</span><span class="sxs-lookup"><span data-stu-id="b385f-103">Deploy Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b385f-104">**の概要:** Skype のセントラル サイトでのビジネス サーバー 2015 のエンタープライズ VoIP を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b385f-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server 2015 at a central site.</span></span>
  
<span data-ttu-id="b385f-105">セントラル サイトでエンタープライズ VoIP を展開するのにには、このトピックを使用します。</span><span class="sxs-lookup"><span data-stu-id="b385f-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="b385f-106">ブランチ サイトでエンタープライズ VoIP を展開するには、[ブランチ サイトの展開](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)をスキップします。</span><span class="sxs-lookup"><span data-stu-id="b385f-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>
  
<span data-ttu-id="b385f-107">仲介サーバー併設されている各フロント エンド サーバーまたは Standard Edition サーバー上の指定どおり、および展開では、スタンドアロンの仲介サーバー プールには、展開の手順を説明します。定義し、展開ウィザードには既に自動的にファイルがインストールされているために、collocates の各フロント エンド サーバーまたは Standard Edition サーバー、仲介サーバーをトポロジを公開するのにはトポロジ ビルダーを使用する場合は、次の内容を省略できます。仲介サーバー、フロント エンド サーバー プールまたは Standard Edition サーバーのファイルをインストールしたとき。</span><span class="sxs-lookup"><span data-stu-id="b385f-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="b385f-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b385f-108">In this section</span></span>

- [<span data-ttu-id="b385f-109">ビジネス サーバー 2015 の Skype でエンタープライズ VoIP のセキュリティおよび構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="b385f-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015</span></span>](enterprise-voice-security.md)
    
- [<span data-ttu-id="b385f-110">ビジネス サーバー 2015 の Skype でトポロジ ビルダーで仲介サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="b385f-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015</span></span>](deploy-a-mediation-server.md)
    
- [<span data-ttu-id="b385f-111">ビジネス サーバー 2015 の Skype でトポロジ ビルダーでゲートウェイを定義します。</span><span class="sxs-lookup"><span data-stu-id="b385f-111">Define a gateway in Topology Builder in Skype for Business Server 2015</span></span>](define-a-gateway.md)
    
- [<span data-ttu-id="b385f-112">ビジネス サーバー 2015 の Skype でトポロジ ビルダーの追加トランクを定義します。</span><span class="sxs-lookup"><span data-stu-id="b385f-112">Define additional trunks in Topology Builder in Skype for Business Server 2015</span></span>](define-additional-trunks.md)
    
- [<span data-ttu-id="b385f-113">ビジネス サーバー 2015 の Skype での仲介サーバーのファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b385f-113">Install the files for Mediation Server in Skype for Business Server 2015</span></span>](install-mediation-server.md)
    
- [<span data-ttu-id="b385f-114">ビジネス サーバー 2015 の Skype でトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="b385f-114">Configure trunks in Skype for Business Server 2015</span></span>](configure-trunks.md)
    
- [<span data-ttu-id="b385f-115">作成または Skype にビジネス サーバー 2015 の呼び出し元の ID を表示するための変換ルールを変更します。</span><span class="sxs-lookup"><span data-stu-id="b385f-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server 2015</span></span>](caller-id-presentation-rules.md)
    
- [<span data-ttu-id="b385f-116">作成またはビジネス サーバー 2015 の Skype で呼び出された ID プレゼンテーションの変換ルールを変更します。</span><span class="sxs-lookup"><span data-stu-id="b385f-116">Create or modify a translation rule for called ID presentation in Skype for Business Server 2015</span></span>](called-id-presentation-rules.md)
    
- [<span data-ttu-id="b385f-117">作成またはビジネス 2015年の Skype の正規化ルールを変更します。</span><span class="sxs-lookup"><span data-stu-id="b385f-117">Create or modify a normalization rule in Skype for Business 2015</span></span>](normalization-rules.md)
    
- [<span data-ttu-id="b385f-118">作成またはビジネス サーバー 2015 の Skype のダイヤル プランを変更します。</span><span class="sxs-lookup"><span data-stu-id="b385f-118">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)
    
- [<span data-ttu-id="b385f-119">ビジネス 2015年の Skype での音声ポリシー、PSTN 使用法レコード、およびボイス ルートを構成します。</span><span class="sxs-lookup"><span data-stu-id="b385f-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business 2015</span></span>](voice-and-pstn.md)
    
- [<span data-ttu-id="b385f-120">ビジネス サーバー 2015 の Skype でエンタープライズ VoIP のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b385f-120">Enable users for Enterprise Voice in Skype for Business Server 2015</span></span>](enable-users-for-enterprise-voice.md)
    
- [<span data-ttu-id="b385f-121">ビジネス サーバー 2015 に Skype での高度なエンタープライズ VoIP 機能を展開します。</span><span class="sxs-lookup"><span data-stu-id="b385f-121">Deploy advanced Enterprise Voice features in Skype for Business Server 2015</span></span>](deploy-advanced-enterprise-voice-features.md)
    
- [<span data-ttu-id="b385f-122">ビジネス 2015年の Skype での通話管理機能を導入します。</span><span class="sxs-lookup"><span data-stu-id="b385f-122">Deploy call management features in Skype for Business 2015</span></span>](deploy-call-management-features.md)
    
## <a name="see-also"></a><span data-ttu-id="b385f-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b385f-123">See also</span></span>

#### 

[<span data-ttu-id="b385f-124">ビジネス サーバー 2015 の Skype でエンタープライズ VoIP の計画</span><span class="sxs-lookup"><span data-stu-id="b385f-124">Plan for Enterprise Voice in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

