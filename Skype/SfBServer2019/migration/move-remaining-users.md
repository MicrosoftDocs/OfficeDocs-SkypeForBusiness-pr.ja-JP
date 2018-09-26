---
title: 残りのユーザーを移動します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'ビジネス サーバー 2019 展開新しい Skype にユーザーを移動するには、ビジネス サーバーのコントロール パネルまたは Skype のビジネス サーバー管理シェルのいずれかの Skype を使用します。 ビジネス サーバー 2019 の Skype へのスムーズな移行を確実にいくつかの要件を満たす必要があります。 このトピックの手順を完了するための前提条件についての詳細は、移行のためのクライアントを構成するを参照してください。 ユーザーの移動に関する詳細な手順については、フェーズ 4 を参照してください: パイロット プールにテスト ユーザーを移動します。'
ms.openlocfilehash: 7bc5d942ddcf30cad84ceb5badf8817de2b254a0
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030498"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="52947-106">Skype をビジネス サーバー 2019 の残りのユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="52947-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="52947-107">ビジネス サーバー 2019 展開新しい Skype にユーザーを移動するには、ビジネス サーバーのコントロール パネルまたは Skype のビジネス サーバー管理シェルのいずれかの Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="52947-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="52947-108">ビジネス サーバー 2019 の Skype へのスムーズな移行を確実にいくつかの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="52947-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="52947-109">このトピックの手順を完了するための前提条件についての詳細は、[移行のためのクライアントを構成する](configure-clients-for-migration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52947-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="52947-110">ユーザーの移動に関する詳細な手順についてを参照してください[フェーズ 4: パイロット プールにテスト ユーザーの移動](phase-4-move-test-users-to-the-pilot-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="52947-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="52947-111">ビジネス サーバー 2019 の Skype を従来の環境からユーザーを移動する、Active Directory ユーザーとコンピューター スナップインまたは従来の管理ツールを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="52947-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="52947-112">Skype のビジネス サーバー 2019 プールにユーザーを移動すると、ユーザーのデータは、新しいプールに関連付けられているバックエンド ・ データベースに移動されます。</span><span class="sxs-lookup"><span data-stu-id="52947-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="52947-113">これには、従来のユーザーによって作成されたアクティブな会議が含まれます。</span><span class="sxs-lookup"><span data-stu-id="52947-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="52947-114">などの従来のユーザーが**自分の会議**の会議を設定している場合その会議、できるビジネス サーバー 2019 プールの新しい Skype のユーザーを移動した後。</span><span class="sxs-lookup"><span data-stu-id="52947-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="52947-115">その会議にアクセスするための詳細では、同じ**会議 URL および会議 ID**は使用できます。</span><span class="sxs-lookup"><span data-stu-id="52947-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="52947-116">唯一の違いは、ビジネス サーバー 2019 プールの場合は、Skype では、従来のプールではなく、会議がここでホストされています。</span><span class="sxs-lookup"><span data-stu-id="52947-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="52947-117">ビジネス サーバー 2019 は同時にアップグレードされたクライアントを展開するは、Skype のユーザーを格納します。</span><span class="sxs-lookup"><span data-stu-id="52947-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="52947-118">新機能は、新しいクライアント ソフトウェアにアップグレードする場合にのみユーザーが利用されます。</span><span class="sxs-lookup"><span data-stu-id="52947-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="52947-119">ポスト移行タスク</span><span class="sxs-lookup"><span data-stu-id="52947-119">Post migration task</span></span>

1. <span data-ttu-id="52947-120">ユーザーを移動した後は、それらに割り当てられている会議ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="52947-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="52947-121">によってユーザーが開催する会議が置かれている Skype レガシー インストールのホームは、フェデレーション ユーザーとシームレスにビジネス サーバー 2019 作業のためには、移行したユーザーに割り当てられている会議ポリシーは、匿名の参加者を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52947-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="52947-122">匿名の参加者**に匿名ユーザーを招待する参加者を許可する**ビジネス サーバー 2019 のコントロール パネルの Skype で選択されているし、 **AllowAnonymousParticipantsInMeetings**を許可する会議ポリシーの設定を**True**にしますビジネス サーバー管理シェルには、Skype で**Get CsConferencingPolicy**コマンドレットから出力します。</span><span class="sxs-lookup"><span data-stu-id="52947-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

