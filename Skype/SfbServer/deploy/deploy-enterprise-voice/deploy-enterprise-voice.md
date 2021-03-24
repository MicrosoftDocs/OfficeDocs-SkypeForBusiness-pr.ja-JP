---
title: Skype for business server エンタープライズ VoIPに展開する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: '概要: Skype for Business Server のエンタープライズ VoIPを中央サイトに展開する方法について学習します。'
ms.openlocfilehash: c2aead4d42a02acce6b0db9f92866dba3a6e956d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104973"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="699cd-103">Skype for business server エンタープライズ VoIPに展開する</span><span class="sxs-lookup"><span data-stu-id="699cd-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="699cd-104">**概要:** 中央サイトで Skype for Business Server エンタープライズ VoIPを展開する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="699cd-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="699cd-105">このトピックを使用して、エンタープライズ VoIPサイトに展開します。</span><span class="sxs-lookup"><span data-stu-id="699cd-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="699cd-106">ブランチ サイトエンタープライズ VoIP展開するには、[ブランチ サイトの [展開] にスキップします](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-branch-sites)。</span><span class="sxs-lookup"><span data-stu-id="699cd-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-branch-sites).</span></span>

<span data-ttu-id="699cd-107">このセクションでは、仲介サーバーを各フロント エンド サーバーまたは Standard Edition サーバーに配置する展開の手順と、推奨される手順、およびスタンドアロンの仲介サーバー プールを使用した展開の手順について説明します。展開ウィザードは、フロントエンド サーバー プールまたは Standard Edition サーバー用のファイルをインストールするときに仲介サーバー用のファイルを自動的にインストール済みなので、トポロジ ビルダーを使用して各フロントエンド サーバーまたは Standard Edition サーバー上の仲介サーバーを照合するトポロジを定義および発行する場合は、次のコンテンツをスキップできます。</span><span class="sxs-lookup"><span data-stu-id="699cd-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="699cd-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="699cd-108">In this section</span></span>

- [<span data-ttu-id="699cd-109">Skype for Business Server エンタープライズ VoIPのセキュリティと構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="699cd-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="699cd-110">Skype for Business Server のトポロジ ビルダーに仲介サーバーを展開する</span><span class="sxs-lookup"><span data-stu-id="699cd-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="699cd-111">Skype for Business Server のトポロジ ビルダーでゲートウェイを定義する</span><span class="sxs-lookup"><span data-stu-id="699cd-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="699cd-112">Skype for Business Server のトポロジ ビルダーで追加のトランクを定義する</span><span class="sxs-lookup"><span data-stu-id="699cd-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="699cd-113">Skype for Business Server に仲介サーバー用のファイルをインストールする</span><span class="sxs-lookup"><span data-stu-id="699cd-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="699cd-114">Skype for Business Server でトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="699cd-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="699cd-115">Skype for Business Server で発信者 ID プレゼンテーションの翻訳ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="699cd-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="699cd-116">Skype for Business Server で呼び出された ID プレゼンテーションの変換ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="699cd-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="699cd-117">Skype for Business で正規化ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="699cd-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="699cd-118">Skype for Business Server でダイヤル プランを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="699cd-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="699cd-119">Skype for Business で音声ポリシー、PSTN 使用法レコード、および音声ルートを構成する</span><span class="sxs-lookup"><span data-stu-id="699cd-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="699cd-120">Skype for Business Server でエンタープライズ VoIPユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="699cd-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="699cd-121">Skype for Business Server エンタープライズ VoIP高度な機能を展開する</span><span class="sxs-lookup"><span data-stu-id="699cd-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="699cd-122">Skype for Business での通話管理機能の展開</span><span class="sxs-lookup"><span data-stu-id="699cd-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="699cd-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="699cd-123">See also</span></span>

[<span data-ttu-id="699cd-124">Skype for Business Server エンタープライズ VoIPの計画を立て</span><span class="sxs-lookup"><span data-stu-id="699cd-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)