---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Skype ビジネス サーバー用のほとんどのサーバーの役割の主な高可用性スキームは、プールを使用してサーバーの冗長性に基づいています。 あるサーバーの役割を実行しているサーバーに障害が発生すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
ms.openlocfilehash: 38887d576a6e15135d9ea35c1dd286ee8c052063
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889361"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="3fd52-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="3fd52-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="3fd52-105">Skype ビジネス サーバー用のほとんどのサーバーの役割の主な高可用性スキームは、プールを使用してサーバーの冗長性に基づいています。</span><span class="sxs-lookup"><span data-stu-id="3fd52-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="3fd52-106">あるサーバーの役割を実行しているサーバーに障害が発生すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="3fd52-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="3fd52-107">ビジネス サーバーの Skype では、高可用性を実現するために少なくとも 2 台のフロント エンド サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="3fd52-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="3fd52-108">計画ツールでは、次の条件を使って、かどうかは、高可用性をサポートするために余分なサーバーが追加されますを決定します。</span><span class="sxs-lookup"><span data-stu-id="3fd52-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="3fd52-109">展開には、2 つまたは複数のフロント エンド サーバーが含まれています、計画ツールでは、予備のサーバーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="3fd52-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="3fd52-110">展開にエッジ サーバーが含まれている場合は、追加のサーバーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="3fd52-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="3fd52-111">展開には、永続的なチャットが含まれています、計画ツールは、余分なサーバーを追加するが、プールの数を増加しません。</span><span class="sxs-lookup"><span data-stu-id="3fd52-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="3fd52-112">など、既に展開には、4 つのサーバーが含まれている場合、計画ツール (合計 5 台のサーバー) に追加のサーバーを追加することが推奨されますが、1 つのプールが維持されます。</span><span class="sxs-lookup"><span data-stu-id="3fd52-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="3fd52-113">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3fd52-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="3fd52-114">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3fd52-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="3fd52-115">詳細については、[マイクロソフトのチームにビジネス用の Skype のアップグレード](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fd52-115">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="3fd52-116">永続的なチャットの使用が必要な場合、選択肢としてはチームにこの機能を必要とするユーザーを移行するか、ビジネス サーバー 2015 の Skype を使用し続けます。</span><span class="sxs-lookup"><span data-stu-id="3fd52-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="3fd52-117">計画ツールは、すべてのデータベースのミラーの SQL データベースにも追加されます。</span><span class="sxs-lookup"><span data-stu-id="3fd52-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="3fd52-118">などのフロント エンドの SQL Server データベースがある場合は、計画ツールはこの 1 つのミラー データベースとその他のデータベースを追加して名前を"フロント エンド ミラー SQL データベースとします。</span><span class="sxs-lookup"><span data-stu-id="3fd52-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="3fd52-119">高可用性環境を準備する方法の詳細については、[高可用性とビジネスのサーバー用の Skype での災害復旧の計画](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fd52-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

