---
title: 残りのユーザーを移動する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使用して、新しい Skype for business Server 2019 の展開にユーザーを移動することができます。 Skype for Business Server 2019 にスムーズに移行できるようにするには、いくつかの要件を満たす必要があります。 このトピックの手順を完了するための前提条件の詳細については、「Configure clients for migration」を参照してください。 ユーザーの移動の詳細な手順については、「フェーズ 4: テストユーザーをパイロットプールに移動する」を参照してください。'
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753715"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="77eb1-106">残りのユーザーの Skype for Business Server 2019 への移動</span><span class="sxs-lookup"><span data-stu-id="77eb1-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="77eb1-107">Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使用して、新しい Skype for business Server 2019 の展開にユーザーを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="77eb1-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="77eb1-108">Skype for Business Server 2019 にスムーズに移行できるようにするには、いくつかの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="77eb1-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="77eb1-109">このトピックの手順を完了するための前提条件の詳細については、「 [Configure clients for migration](configure-clients-for-migration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77eb1-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="77eb1-110">ユーザーの移動の詳細な手順については、「[フェーズ 4: テストユーザーをパイロットプールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77eb1-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="77eb1-111">Active Directory ユーザーとコンピュータースナップインまたは従来の管理ツールを使用して、レガシ環境から Skype for Business Server 2019 にユーザーを移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="77eb1-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="77eb1-112">ユーザーを Skype for Business Server 2019 プールに移動すると、そのユーザーのデータは、新しいプールに関連付けられたバックエンドデータベースに移動されます。</span><span class="sxs-lookup"><span data-stu-id="77eb1-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="77eb1-113">これには、レガシ ユーザーによって作成されたアクティブな会議が含まれます。</span><span class="sxs-lookup"><span data-stu-id="77eb1-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="77eb1-114">たとえば、従来のユーザーが**会議**の会議を構成している場合、ユーザーが移動された後も、新しい Skype For business Server 2019 プールでその会議を利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="77eb1-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="77eb1-115">会議へのアクセスに使用する**会議 URL と電話会議 ID** も同じです。</span><span class="sxs-lookup"><span data-stu-id="77eb1-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="77eb1-116">唯一の違いは、会議が従来のプールではなく、Skype for Business Server 2019 プールでホストされるようになったことです。</span><span class="sxs-lookup"><span data-stu-id="77eb1-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="77eb1-117">Skype for Business Server 2019 上のホームユーザーは、アップグレードされたクライアントを同時に展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="77eb1-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="77eb1-118">クライアントが新しいクライアント ソフトウェアにアップグレードされている場合に限り、ユーザーは新しい機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="77eb1-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="77eb1-119">移行後のタスク</span><span class="sxs-lookup"><span data-stu-id="77eb1-119">Post migration task</span></span>

1. <span data-ttu-id="77eb1-120">ユーザーを移動した後、ユーザーに割り当てられている会議ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="77eb1-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="77eb1-121">Skype for Business Server 2019 に所属するユーザーによって開催された会議が、従来のインストールに所属しているフェデレーションユーザーとシームレスに機能するようにするには、移行したユーザーに割り当てられている会議ポリシーで匿名の参加者を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77eb1-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="77eb1-122">匿名参加者に許可されている会議ポリシーにより、参加者は、Skype for business Server 2019 コントロールパネルで選択した**匿名ユーザーを招待でき**、Skype For Business Server 管理シェルの**get-csconferencingpolicy**コマンドレットからの出力で**AllowAnonymousParticipantsInMeetings**が**True**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="77eb1-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

