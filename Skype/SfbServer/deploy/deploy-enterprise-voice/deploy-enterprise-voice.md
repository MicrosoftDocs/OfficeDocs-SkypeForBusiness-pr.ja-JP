---
title: ビジネス サーバーの Skype でエンタープライズ VoIP を展開します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: '概要: は、Skype のビジネス サーバーをセントラル サイトでのエンタープライズ VoIP を展開する方法を説明します。'
ms.openlocfilehash: 8fb434a4fe02ec5755d78d549f870da9860b2910
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892714"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="3414a-103">ビジネス サーバーの Skype でエンタープライズ VoIP を展開します。</span><span class="sxs-lookup"><span data-stu-id="3414a-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="3414a-104">**の概要:** Skype のビジネス サーバーをセントラル サイトでのエンタープライズ VoIP を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3414a-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="3414a-105">セントラル サイトでエンタープライズ VoIP を展開するのにには、このトピックを使用します。</span><span class="sxs-lookup"><span data-stu-id="3414a-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="3414a-106">ブランチ サイトでエンタープライズ VoIP を展開するには、[ブランチ サイトの展開](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)をスキップします。</span><span class="sxs-lookup"><span data-stu-id="3414a-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="3414a-107">仲介サーバー併設されている各フロント エンド サーバーまたは Standard Edition サーバー上の指定どおり、および展開では、スタンドアロンの仲介サーバー プールには、展開の手順を説明します。定義し、展開ウィザードには既に自動的にファイルがインストールされているために、collocates の各フロント エンド サーバーまたは Standard Edition サーバー、仲介サーバーをトポロジを公開するのにはトポロジ ビルダーを使用する場合は、次の内容を省略できます。仲介サーバー、フロント エンド サーバー プールまたは Standard Edition サーバーのファイルをインストールしたとき。</span><span class="sxs-lookup"><span data-stu-id="3414a-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="3414a-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3414a-108">In this section</span></span>

- [<span data-ttu-id="3414a-109">Skype ビジネス サーバーでエンタープライズ VoIP のセキュリティおよび構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="3414a-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="3414a-110">ビジネス サーバーのトポロジ ビルダーで Skype に仲介サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="3414a-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="3414a-111">ビジネス サーバーの Skype でトポロジ ビルダーでゲートウェイを定義します。</span><span class="sxs-lookup"><span data-stu-id="3414a-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="3414a-112">Skype でトポロジ ビルダーでビジネスのサーバーの追加トランクを定義します。</span><span class="sxs-lookup"><span data-stu-id="3414a-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="3414a-113">ビジネス サーバーの Skype での仲介サーバーのファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3414a-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="3414a-114">ビジネス サーバー用の Skype でトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="3414a-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="3414a-115">作成または Skype のビジネス サーバーの呼び出し元の ID をプレゼンテーションの変換ルールを変更します。</span><span class="sxs-lookup"><span data-stu-id="3414a-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="3414a-116">作成またはビジネス サーバーの Skype で呼び出された ID プレゼンテーションの変換ルールを変更</span><span class="sxs-lookup"><span data-stu-id="3414a-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="3414a-117">作成するか、ビジネスの Skype の正規化ルールを変更</span><span class="sxs-lookup"><span data-stu-id="3414a-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="3414a-118">作成またはビジネス サーバーの Skype のダイヤル プランを変更します。</span><span class="sxs-lookup"><span data-stu-id="3414a-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="3414a-119">ビジネス用の Skype での音声ポリシー、PSTN 使用法レコード、およびボイス ルートを構成します。</span><span class="sxs-lookup"><span data-stu-id="3414a-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="3414a-120">ビジネス サーバーの Skype でエンタープライズ VoIP のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3414a-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="3414a-121">ビジネス サーバー用の Skype での高度なエンタープライズ VoIP 機能を導入します。</span><span class="sxs-lookup"><span data-stu-id="3414a-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="3414a-122">ビジネス用の Skype での通話管理機能を導入します。</span><span class="sxs-lookup"><span data-stu-id="3414a-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="3414a-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="3414a-123">See also</span></span>

[<span data-ttu-id="3414a-124">ビジネスのサーバーに、Skype でエンタープライズ VoIP を計画します。</span><span class="sxs-lookup"><span data-stu-id="3414a-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

