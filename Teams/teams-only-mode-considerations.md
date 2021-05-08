---
title: Teams Only モードの考慮事項
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 管理者は、管理センターで [Microsoft Teamsのみ] モードへのアップグレードを準備Microsoft Teams確認できます。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b2232d4774a31f3b081b2410371a5903debe9123
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239014"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="d6baa-103">Teams Only モードの考慮事項</span><span class="sxs-lookup"><span data-stu-id="d6baa-103">Teams Only mode considerations</span></span>

<span data-ttu-id="d6baa-104">組織のMicrosoft 365またはOffice 365管理者は、個々のユーザーまたはテナント全体を [のみ] Teamsアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="d6baa-104">Administrators of Microsoft 365 or Office 365 organizations can upgrade either individual users or the entire tenant to Teams Only mode.</span></span>  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="d6baa-105">Teams のみモードにアップグレードすると、Microsoft 365 または Office 365 のチームワークのハブである Microsoft Teams の完全な利点を、1 つのクライアント エクスペリエンスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="d6baa-105">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Microsoft 365 or Office 365, via a single client experience.</span></span> <span data-ttu-id="d6baa-106">Teams のみモードのユーザーは、送信者が Skype for Business または Teams を使用しているかどうかに関係なく、Teams ですべての通話とチャットを受信し、相互運用とフェデレーションのサポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="d6baa-106">Users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="d6baa-107">何千もの顧客が Microsoft Teams に正常にアップグレードされましたが、組織のアップグレード タイムラインとユーザー エクスペリエンスに影響を与える可能性がある考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="d6baa-107">Although thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="d6baa-108">最高のユーザー エクスペリエンスを得るために、Teams が自分たちの共同作業や通信の要件に適合してることを確認し、確実にお使いのネットワークが Teams をサポートする状態を整えて、ユーザーの準備状態計画を実施してから Teams へのユーザーのアップグレードを実行してください。</span><span class="sxs-lookup"><span data-stu-id="d6baa-108">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d6baa-109">アップグレード計画を開始し始めたばかりの場合は、アップグレードの開始に関するガイドをMicrosoft Teams[してください](upgrade-start-here.md)。</span><span class="sxs-lookup"><span data-stu-id="d6baa-109">If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md) guide.</span></span> 

<span data-ttu-id="d6baa-110">**共存に関** する考慮事項: Skype for Business Online や Skype for Business Server を既に使用している組織は、Teams をニーズに合ったペースで環境に導入できます。</span><span class="sxs-lookup"><span data-stu-id="d6baa-110">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="d6baa-111">組織は必要に応じて Teams を目的のユーザー セットに段階的にロールアウトでき、Teams を使用するユーザーは Skype for Business を使用するユーザーと通信できます。その逆も可能です。</span><span class="sxs-lookup"><span data-stu-id="d6baa-111">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="d6baa-112">このエクスペリエンスを管理するために、管理者は共存モードを使用して、エンド ユーザーのクライアント エクスペリエンス、着信チャットと通話のルーティング動作、および新しい会議が Teams または Skype for Business でスケジュールされるかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="d6baa-112">To manage this experience, administrators use coexistence modes, which define the end-user client experience, the routing behavior of incoming chats and calls, and whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="d6baa-113">ユーザーが [のみ] にアップグレードされている場合、ユーザーは他の組織の **Teamsできます**。ただし、両方のユーザーがアプリを使用する場合に最適なTeams。</span><span class="sxs-lookup"><span data-stu-id="d6baa-113">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="d6baa-114">[会議のみ] にアップグレードTeamsユーザーは、引き続き会議Skype for Businessできます。</span><span class="sxs-lookup"><span data-stu-id="d6baa-114">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d6baa-115">共存の詳細については、「共存と相互運用性[Microsoft Teams Skype for Businessを参照してください](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="d6baa-115">For more detailed information about coexistence, please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> <span data-ttu-id="d6baa-116">Teams と Skype (Consumer) の詳細については、「TeamsとSkype[参照してください](teams-skype-interop.md)。</span><span class="sxs-lookup"><span data-stu-id="d6baa-116">For more information about Teams and Skype (Consumer), see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>


<span data-ttu-id="d6baa-117">**ユーザー固有の** 考慮事項: 一部のユーザー シナリオはまだ進化しており、管理者は組織内の他のユーザーをアップグレードする際に、特定のユーザーのアップグレードを一時的に延期する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d6baa-117">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="d6baa-118">特に、プライマリ デバイスが VDI ベースのユーザーのシナリオへの対応に引き続き取り組み中です。</span><span class="sxs-lookup"><span data-stu-id="d6baa-118">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="d6baa-119">サイトのお知らせについては、「ロードマップ[」をMicrosoft 365してください](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="d6baa-119">For site announcements, monitor the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

> [!NOTE]
> <span data-ttu-id="d6baa-120">[移行のみ] Teamsする前に、アプリケーションをサポートしないデバイスを交換または更新する必要Teams。</span><span class="sxs-lookup"><span data-stu-id="d6baa-120">Before you move to Teams Only mode you need to replace or update devices that don't support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d6baa-121">**注意**: この移行へのTeamsは、技術的な移行以上の作業です。</span><span class="sxs-lookup"><span data-stu-id="d6baa-121">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="d6baa-122">アップグレードが成功すると、技術的な準備とエンドユーザーの準備の両方が評価されます。</span><span class="sxs-lookup"><span data-stu-id="d6baa-122">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="d6baa-123">アップグレードへのSkype for Businessの[Teams計画の](upgrade-framework.md)詳細については、アップグレードガイダンスを参照Teams。</span><span class="sxs-lookup"><span data-stu-id="d6baa-123">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
