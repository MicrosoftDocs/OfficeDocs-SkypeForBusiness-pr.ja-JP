---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server のほとんどのサーバーの役割に関する高可用性の主要なスキームは、プールによるサーバーの冗長性に基づいています。 あるサーバーの役割を実行しているサーバーに障害が発生すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
ms.openlocfilehash: 328d269e6d6694dc26be66bd3894094770562726
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797178"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="a95dd-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="a95dd-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="a95dd-105">Skype for Business Server のほとんどのサーバーの役割に関する高可用性の主要なスキームは、プールによるサーバーの冗長性に基づいています。</span><span class="sxs-lookup"><span data-stu-id="a95dd-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="a95dd-106">あるサーバーの役割を実行しているサーバーに障害が発生すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="a95dd-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="a95dd-107">高可用性を有効にするには、Skype for Business Server で少なくとも2台のフロントエンドサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="a95dd-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="a95dd-108">計画ツールでは、高可用性をサポートするために追加のサーバーが追加されるかどうかを判断するために、次の条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="a95dd-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="a95dd-109">展開に2台以上のフロントエンドサーバーが含まれている場合、計画ツールでは追加のサーバーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="a95dd-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="a95dd-110">展開にエッジサーバーが含まれている場合は、追加のサーバーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="a95dd-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="a95dd-111">展開に永続的なチャットが含まれている場合、計画ツールでは、余分なサーバーが追加されますが、プール番号は増えません。</span><span class="sxs-lookup"><span data-stu-id="a95dd-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="a95dd-112">たとえば、展開に既に4台のサーバーが含まれている場合、計画ツールでは、(合計5台の) サーバーを追加することが推奨されますが、1つのプールを維持します。</span><span class="sxs-lookup"><span data-stu-id="a95dd-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="a95dd-113">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a95dd-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a95dd-114">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a95dd-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="a95dd-115">詳細については、「 [Skype For business から Microsoft Teams へのアップグレード](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a95dd-115">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="a95dd-116">常設チャットを使用する必要がある場合は、この機能が必要なユーザーを Teams に移行するか、Skype for Business Server 2015 を使い続けるかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a95dd-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="a95dd-117">計画ツールでは、すべてのデータベースのミラー SQL データベースも追加されます。</span><span class="sxs-lookup"><span data-stu-id="a95dd-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="a95dd-118">たとえば、フロントエンドの SQL Server データベースがある場合は、計画ツールによって、そのデータベースがこのデータベースのミラーデータベースとして追加され、"フロントエンドミラー SQL データベース" という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="a95dd-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="a95dd-119">高可用性を実現するための環境の準備について詳しくは、「 [Skype For Business Server で高可用性と障害回復を計画する](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a95dd-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

