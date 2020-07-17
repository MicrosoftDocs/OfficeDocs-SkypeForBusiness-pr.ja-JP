---
title: ダイヤルイン アクセス番号を移行する
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
description: ダイヤルインアクセス番号を Skype for Business Server 2019 に移行するには、連絡先オブジェクトを移行するために、Move-CsApplicationEndpoint コマンドレットを実行する必要があります。 従来のインストールと Skype for business Server 2019 の共存期間の間、このセクションで説明するように、Skype for Business Server 2019 で作成したダイヤルインアクセス番号は、従来のインストールで作成したダイヤルインアクセス番号と同じように動作します。
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752699"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="a21de-104">ダイヤルイン アクセス番号を移行する</span><span class="sxs-lookup"><span data-stu-id="a21de-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="a21de-105">ダイヤルインアクセス番号を Skype for Business Server 2019 に移行するには、連絡先オブジェクトを移行するために、 **Move-CsApplicationEndpoint**コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21de-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="a21de-106">従来のインストールと Skype for business Server 2019 の共存期間の間、このセクションで説明するように、Skype for Business Server 2019 で作成したダイヤルインアクセス番号は、従来のインストールで作成したダイヤルインアクセス番号と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="a21de-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="a21de-107">従来のインストールで作成したが Skype for business Server 2019 に移動したダイヤルインアクセス番号、または移行前、移行中、または移行後に Skype for Business Server 2019 で作成したダイヤルインアクセス番号には、次のような特徴があります。</span><span class="sxs-lookup"><span data-stu-id="a21de-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="a21de-108">Office Communications Server 2007 R2 の会議への招待およびダイヤルインアクセス番号ページには表示されません。</span><span class="sxs-lookup"><span data-stu-id="a21de-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="a21de-109">[従来の会議出席依頼のインストールとダイヤルインアクセス番号] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21de-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="a21de-110">Skype for Business Server 2019 の会議への招待およびダイヤルインアクセス番号ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21de-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="a21de-111">Office Communications Server 2007 R2 管理ツールで表示または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a21de-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="a21de-112">レガシーインストールコントロールパネルと従来のインストール管理シェルで表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="a21de-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="a21de-113">Skype for Business Server 2019 コントロールパネルおよび Skype for Business Server 2019 管理シェルで表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="a21de-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="a21de-114">Set-CsDialinConferencingAccessNumber コマンドレットで Priority パラメーターを指定して、地域内で並べ直すことができます。</span><span class="sxs-lookup"><span data-stu-id="a21de-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="a21de-115">従来のインストールプールを使用停止にする前に、従来のインストールプールをポイントするダイヤルインアクセス番号の移行を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21de-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="a21de-116">記載されている以下の手順でダイヤルイン アクセス番号の移行を完了しないと、そのアクセス番号への着信通話が失敗します。</span><span class="sxs-lookup"><span data-stu-id="a21de-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a21de-117">従来のインストールプールを使用停止にする前に、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21de-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="a21de-118">サービスが短時間停止される場合に備えて、ネットワークの使用率が低いときに、ダイヤルイン アクセス番号を移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a21de-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="a21de-119">ダイヤルイン アクセス番号を識別し、移動するには</span><span class="sxs-lookup"><span data-stu-id="a21de-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="a21de-120">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21de-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a21de-121">各ダイヤルインアクセス番号を Skype for Business Server 2019 でホストされているプールに移動するには、コマンドラインで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a21de-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="a21de-122">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a21de-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="a21de-123">左側のナビゲーション バーで **[会議]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21de-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="a21de-124">[**ダイヤルインアクセス番号**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21de-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="a21de-125">移行元の従来のインストールプールに対して、ダイヤルインアクセス番号が残っていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a21de-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a21de-126">すべてのダイヤルインアクセス番号が Skype for Business Server 2019 プールをポイントしている場合は、従来のインストールプールを使用停止にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a21de-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a21de-127">Skype for Business Server コントロールパネルを使用してダイヤルインアクセス番号の移行を確認する</span><span class="sxs-lookup"><span data-stu-id="a21de-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a21de-128">**Csuseradministrator**または**csadministrator**の役割に割り当てられているユーザーアカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a21de-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="a21de-129">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a21de-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="a21de-130">左側のナビゲーション バーで **[会議]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21de-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="a21de-131">[**ダイヤルインアクセス番号**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21de-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="a21de-132">すべてのダイヤルインアクセス番号が Skype for Business Server 2019 でホストされているプールに移行されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a21de-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a21de-133">Skype for Business Server 管理シェルを使用してダイヤルインアクセス番号の移行を確認する</span><span class="sxs-lookup"><span data-stu-id="a21de-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="a21de-134">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a21de-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="a21de-135">移行されたすべてのダイヤルイン会議アクセス番号を戻すには、コマンドラインで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a21de-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="a21de-136">すべてのダイヤルインアクセス番号が Skype for Business Server 2019 でホストされているプールに移行されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a21de-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


