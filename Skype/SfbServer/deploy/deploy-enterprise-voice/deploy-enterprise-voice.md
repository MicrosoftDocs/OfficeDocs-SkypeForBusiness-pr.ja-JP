---
title: Skype for Business Server エンタープライズ VoIP展開する
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
description: '概要: 中央サイトで skype for Business Server エンタープライズ VoIPを展開する方法について学習します。'
ms.openlocfilehash: 246c1e5c03401b885b297ada08677fb40faad60d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812497"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="96563-103">Skype for Business Server エンタープライズ VoIP展開する</span><span class="sxs-lookup"><span data-stu-id="96563-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="96563-104">**概要:** 中央サイトで Skype for Business Server エンタープライズ VoIPを展開する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="96563-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="96563-105">このトピックを使用して、エンタープライズ VoIPサイトに展開します。</span><span class="sxs-lookup"><span data-stu-id="96563-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="96563-106">ブランチ サイトエンタープライズ VoIP展開するには、「ブランチ サイトの [展開」にスキップします](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)。</span><span class="sxs-lookup"><span data-stu-id="96563-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="96563-107">このセクションでは、仲介サーバーを各フロントエンド サーバーまたは Standard Edition サーバーに配置する展開の手順 (推奨)、およびスタンドアロンの仲介サーバー プールを使用した展開の手順について説明します。トポロジ ビルダーを使用して、各フロントエンド サーバーまたは Standard Edition サーバーに仲介サーバーを配置するトポロジを定義および公開した場合は、以下のコンテンツをスキップできます。これは、展開ウィザードは、フロントエンド サーバー プールまたは Standard Edition サーバーのファイルをインストールすると、仲介サーバーのファイルを既に自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="96563-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="96563-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="96563-108">In this section</span></span>

- [<span data-ttu-id="96563-109">Skype for Business Server での エンタープライズ VoIPのセキュリティと構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="96563-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="96563-110">Skype for Business Server のトポロジ ビルダーで仲介サーバーを展開する</span><span class="sxs-lookup"><span data-stu-id="96563-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="96563-111">Skype for Business Server のトポロジ ビルダーでゲートウェイを定義する</span><span class="sxs-lookup"><span data-stu-id="96563-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="96563-112">Skype for Business Server のトポロジ ビルダーで追加のトランクを定義する</span><span class="sxs-lookup"><span data-stu-id="96563-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="96563-113">Skype for Business Server に仲介サーバーのファイルをインストールする</span><span class="sxs-lookup"><span data-stu-id="96563-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="96563-114">Skype for Business Server でトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="96563-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="96563-115">Skype for Business Server で発信者番号のプレゼンテーションの変換ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="96563-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="96563-116">Skype for Business Server で呼び出し ID プレゼンテーションの変換ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="96563-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="96563-117">Skype for Business で正規化ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="96563-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="96563-118">Skype for Business Server でダイヤル プランを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="96563-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="96563-119">Skype for Business で音声ポリシー、PSTN 使用法レコード、およびボイス ルートを構成する</span><span class="sxs-lookup"><span data-stu-id="96563-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="96563-120">Skype for Business Server でエンタープライズ VoIPを有効にする</span><span class="sxs-lookup"><span data-stu-id="96563-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="96563-121">Skype for Business Server エンタープライズ VoIP高度な機能を展開する</span><span class="sxs-lookup"><span data-stu-id="96563-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="96563-122">Skype for Business での通話管理機能の展開</span><span class="sxs-lookup"><span data-stu-id="96563-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="96563-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="96563-123">See also</span></span>

[<span data-ttu-id="96563-124">Skype for Business Server エンタープライズ VoIPの計画</span><span class="sxs-lookup"><span data-stu-id="96563-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

