---
title: 残りのユーザーの移動
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype for business server コントロールパネルまたは Skype for Business Server Management Shell を使用して、ユーザーを新しい Skype for Business Server 2019 の展開に移動することができます。 Skype for Business Server 2019 にスムーズに移行するためには、いくつかの要件を満たしている必要があります。 このトピックの手順を完了するための前提条件の詳細については、「移行のためにクライアントを構成する」を参照してください。 ユーザーの移動の詳細な手順については、「フェーズ 4: テストユーザーをパイロットプールに移動する」を参照してください。'
ms.openlocfilehash: 8c12ca52e162c4317dabc59d5de9b74082730882
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244566"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="2d04d-106">残りのユーザーを Skype for Business Server 2019 に移動する</span><span class="sxs-lookup"><span data-stu-id="2d04d-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="2d04d-107">Skype for business server コントロールパネルまたは Skype for Business Server Management Shell を使用して、ユーザーを新しい Skype for Business Server 2019 の展開に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="2d04d-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="2d04d-108">Skype for Business Server 2019 にスムーズに移行するためには、いくつかの要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d04d-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="2d04d-109">このトピックの手順を完了するための前提条件の詳細については、「[移行のためにクライアントを構成](configure-clients-for-migration.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d04d-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="2d04d-110">ユーザーの移動の詳細な手順については、「[フェーズ 4: テストユーザーをパイロットプールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d04d-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2d04d-111">Active Directory ユーザーとコンピューターのスナップインまたは従来の管理ツールを使用して、従来の環境から Skype for Business Server 2019 にユーザーを移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="2d04d-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="2d04d-112">ユーザーを Skype for Business Server 2019 プールに移動すると、そのユーザーのデータは、新しいプールに関連付けられているバックエンドデータベースに移動されます。</span><span class="sxs-lookup"><span data-stu-id="2d04d-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2d04d-113">これには、従来のユーザーによって作成されたアクティブな会議も含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d04d-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="2d04d-114">たとえば、従来のユーザーが**会議**用の会議を構成している場合は、ユーザーが移動された後も、新しい Skype For business Server 2019 プールでその会議を利用できます。</span><span class="sxs-lookup"><span data-stu-id="2d04d-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="2d04d-115">会議にアクセスするための詳細は、会議の**URL と会議 ID と**同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d04d-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="2d04d-116">唯一の違いは、会議が Skype for Business Server 2019 プールでホストされ、従来のプールではホストされていないことです。</span><span class="sxs-lookup"><span data-stu-id="2d04d-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2d04d-117">Skype for Business Server 2019 のホームユーザーは、アップグレードされたクライアントを展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2d04d-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="2d04d-118">新しい機能は、ユーザーが新しいクライアントソフトウェアにアップグレードした場合にのみ利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="2d04d-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="2d04d-119">移行後の作業</span><span class="sxs-lookup"><span data-stu-id="2d04d-119">Post migration task</span></span>

1. <span data-ttu-id="2d04d-120">ユーザーを移動した後、それらに割り当てられている会議ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d04d-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="2d04d-121">Skype for Business Server 2019 を使っているユーザーによって開催された会議が、レガシインストールのあるフェデレーションユーザーとシームレスに動作するようにするには、移行したユーザーに割り当てられている会議ポリシーを使用して、匿名の参加者を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d04d-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="2d04d-122">匿名の参加者が Skype for Business Server 2019 コントロールパネルで選択されている**匿名ユーザーを招待する**ことを許可する会議ポリシーを使用して、 **AllowAnonymousParticipantsInMeetings**が**True**に設定されているSkype for Business Server 管理シェルの**set-csconferencingpolicy**コマンドレットからの出力。</span><span class="sxs-lookup"><span data-stu-id="2d04d-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

