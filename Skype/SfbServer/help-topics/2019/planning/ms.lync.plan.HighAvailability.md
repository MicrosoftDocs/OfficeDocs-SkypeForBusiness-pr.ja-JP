---
title: 高可用性 (計画ツール)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server のほとんどのサーバーの役割の主な高可用性スキームは、プールによるサーバーの冗長性に基づいて行います。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
ms.openlocfilehash: 36b2d9fad34e16daf11fb7539f73c815264a55a6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093315"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="aa0c6-104">高可用性 (計画ツール)</span><span class="sxs-lookup"><span data-stu-id="aa0c6-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="aa0c6-105">Skype for Business Server のほとんどのサーバーの役割の主な高可用性スキームは、プールによるサーバーの冗長性に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="aa0c6-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="aa0c6-106">あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="aa0c6-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="aa0c6-107">Skype for Business Server では、高可用性を有効にするには、少なくとも 2 つのフロント エンド サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="aa0c6-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="aa0c6-108">計画ツールは、次の条件を使用して、高可用性をサポートするために追加のサーバーを追加するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="aa0c6-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="aa0c6-109">展開に 2 つ以上のフロント エンド サーバーが含まれている場合、計画ツールは追加のサーバーを追加しません。</span><span class="sxs-lookup"><span data-stu-id="aa0c6-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="aa0c6-110">展開にエッジ サーバーが含まれている場合は、追加のサーバーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="aa0c6-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="aa0c6-111">展開に常設チャットが含まれている場合、計画ツールは追加のサーバーを追加しますが、プール番号は増やしません。</span><span class="sxs-lookup"><span data-stu-id="aa0c6-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="aa0c6-112">たとえば、展開に既に 4 台のサーバーが含まれている場合、計画ツールは追加のサーバー (合計 5 台のサーバー) の追加を提案しますが、1 つのプールを維持します。</span><span class="sxs-lookup"><span data-stu-id="aa0c6-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="aa0c6-113">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="aa0c6-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="aa0c6-114">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="aa0c6-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="aa0c6-115">詳細については [、「Skype for Business to Microsoft Teams のアップグレード」を参照してください](/MicrosoftTeams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="aa0c6-115">For more information, see [Skype for Business to Microsoft Teams upgrade](/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="aa0c6-116">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="aa0c6-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="aa0c6-117">また、計画ツールは、すべてのデータベースSQLミラー データベースを追加します。</span><span class="sxs-lookup"><span data-stu-id="aa0c6-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="aa0c6-118">たとえば、フロントエンド SQL Server データベースがある場合、計画ツールはもう一方のデータベースをミラー データベースとして追加し、それを "フロントエンド ミラー SQL データベース" と名付けします。</span><span class="sxs-lookup"><span data-stu-id="aa0c6-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="aa0c6-119">高可用性のために環境を準備する方法の詳細については、「Skype for Business Server で高可用性と障害復旧を計画する [」を参照してください](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="aa0c6-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
