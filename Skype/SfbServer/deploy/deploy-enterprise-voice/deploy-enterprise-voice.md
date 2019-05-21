---
title: Skype for Business Server でのエンタープライズボイスの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: '概要: Skype for Business Server のエンタープライズボイスをセントラルサイトに展開する方法について説明します。'
ms.openlocfilehash: c5995570d8d3cf775b2837bb6ddfc170860d57dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291243"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="079f3-103">Skype for Business Server でのエンタープライズボイスの展開</span><span class="sxs-lookup"><span data-stu-id="079f3-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="079f3-104">**概要:** 中央サイトで Skype for Business Server 用のエンタープライズボイスを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="079f3-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="079f3-105">このトピックを使用して、中央サイトにエンタープライズボイスを展開します。</span><span class="sxs-lookup"><span data-stu-id="079f3-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="079f3-106">ブランチサイトにエンタープライズボイスを展開するには、「[ブランチサイトの展開](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)」に進んでください。</span><span class="sxs-lookup"><span data-stu-id="079f3-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="079f3-107">このセクションでは、仲介サーバーが各フロントエンドサーバーまたは標準エディションサーバー (推奨) と、スタンドアロンの仲介サーバープールを使用して展開する場合の展開の手順について説明します。トポロジビルダーを使用して、各フロントエンドサーバーまたは Standard Edition サーバー上で仲介サーバーを見つけて配布するトポロジを定義して公開している場合は、次のコンテンツをスキップできます。フロントエンドサーバープールまたは Standard Edition サーバーにファイルをインストールした場合の仲介サーバー:</span><span class="sxs-lookup"><span data-stu-id="079f3-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="079f3-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="079f3-108">In this section</span></span>

- [<span data-ttu-id="079f3-109">Skype for Business Server でのエンタープライズ Voip のセキュリティと構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="079f3-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="079f3-110">Skype for Business Server でのトポロジビルダーへの仲介サーバーの展開</span><span class="sxs-lookup"><span data-stu-id="079f3-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="079f3-111">Skype for Business Server のトポロジビルダーでゲートウェイを定義する</span><span class="sxs-lookup"><span data-stu-id="079f3-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="079f3-112">Skype for Business Server の Topology Builder で追加の trunks を定義する</span><span class="sxs-lookup"><span data-stu-id="079f3-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="079f3-113">Skype for Business Server に仲介サーバー用のファイルをインストールする</span><span class="sxs-lookup"><span data-stu-id="079f3-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="079f3-114">Skype for Business Server で trunks を構成する</span><span class="sxs-lookup"><span data-stu-id="079f3-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="079f3-115">Skype for Business Server で発信者 ID のプレゼンテーションの翻訳ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="079f3-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="079f3-116">Skype for Business Server で呼び出された ID プレゼンテーションの翻訳ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="079f3-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="079f3-117">Skype for Business で正規化ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="079f3-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="079f3-118">Skype for Business Server でダイヤルプランを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="079f3-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="079f3-119">Skype for Business で音声ポリシー、PSTN 使用状況レコード、および音声ルートを構成する</span><span class="sxs-lookup"><span data-stu-id="079f3-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="079f3-120">Skype for Business Server でエンタープライズ Voip のユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="079f3-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="079f3-121">Skype for Business Server で高度なエンタープライズ Voip 機能を導入する</span><span class="sxs-lookup"><span data-stu-id="079f3-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="079f3-122">Skype for Business での通話管理機能の展開</span><span class="sxs-lookup"><span data-stu-id="079f3-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="079f3-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="079f3-123">See also</span></span>

[<span data-ttu-id="079f3-124">Skype for Business Server でのエンタープライズ Voip の計画</span><span class="sxs-lookup"><span data-stu-id="079f3-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

