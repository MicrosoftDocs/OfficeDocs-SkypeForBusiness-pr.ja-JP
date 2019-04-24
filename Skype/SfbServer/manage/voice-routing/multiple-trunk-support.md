---
title: Skype のビジネス サーバー用の複数のトランク サポート
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバーの機能のための Skype では、ゲートウェイと仲介サーバーの間で複数のアソシエーションをサポートします。 これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コント ローラー (SBC)、または IP PBX との間の論理的な関連付けには、トランクを定義することによって行われます。 ゲートウェイを仲介サーバー (つまり、トランクなど) に関連付けるには、トポロジ ビルダーを使用します。
ms.openlocfilehash: 5d093bee56597474f0cefcf1053536774f2eb795
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214643"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="15425-105">Skype のビジネス サーバー用の複数のトランク サポート</span><span class="sxs-lookup"><span data-stu-id="15425-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="15425-106">ビジネス サーバーの機能のための Skype では、ゲートウェイと仲介サーバーの間で複数のアソシエーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="15425-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="15425-107">これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コント ローラー (SBC)、または IP PBX との間の論理的な関連付けには、トランクを定義することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="15425-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="15425-108">ゲートウェイを仲介サーバー (つまり、トランクなど) に関連付けるには、トポロジ ビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="15425-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="15425-109">割り当てまたはトランクを Skype のビジネス サーバーの削除、最初にトポロジ ビルダーでトランクを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15425-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="15425-110">トランクは、次の関連で構成されています: ドメイン名 (FQDN)、仲介サーバーのリッスン ポート、ゲートウェイの FQDN、およびゲートウェイ リッスン ポートを仲介サーバーの完全修飾します。</span><span class="sxs-lookup"><span data-stu-id="15425-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="15425-111">複数のトランクを構成するには、同じゲートウェイと仲介サーバーとの間の複数の関連付けを作成できます。</span><span class="sxs-lookup"><span data-stu-id="15425-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="15425-112">これは、構内交換 (機 PBX) の interoperational のシナリオで特に便利ですが、エンタープライズ VoIP インフラストラクチャに追加の復元機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="15425-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="15425-113">トランクを定義するときは、工順に関連付けられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="15425-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="15425-114">ルートにトランクを関連付けるには、トポロジ ビルダーでは、トランクの簡易名を定義します。</span><span class="sxs-lookup"><span data-stu-id="15425-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="15425-115">この単純な名前は、ビジネス サーバーのコントロール パネル]、トランクできるルートに関連付けられているに、Skype でトランクの名前として使用されます。</span><span class="sxs-lookup"><span data-stu-id="15425-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="15425-116">トランクの単純な名前は、サーバー管理シェルのビジネスに、Skype からゲートウェイの名前として使用されます。</span><span class="sxs-lookup"><span data-stu-id="15425-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="15425-117">管理者は、仲介サーバーに関連付けられている既定のトランクを選択してください。</span><span class="sxs-lookup"><span data-stu-id="15425-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="15425-118">トポロジ ビルダーでは、関連付けられている仲介サーバーを右クリックし、し、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15425-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="15425-119">仲介サーバーのデフォルト ゲートウェイを指定します。</span><span class="sxs-lookup"><span data-stu-id="15425-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="15425-120">次の図は、仲介サーバーとゲートウェイごとに定義されている複数のトランクを示しています。</span><span class="sxs-lookup"><span data-stu-id="15425-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![トランクの複数の割り当て](../../media/multiple-trunk-assignments.jpg)
