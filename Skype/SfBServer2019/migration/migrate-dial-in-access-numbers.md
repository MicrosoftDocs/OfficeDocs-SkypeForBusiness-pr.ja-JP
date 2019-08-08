---
title: ダイヤルイン アクセス番号の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 にダイヤルインアクセス番号を移行するには、Move-CsApplicationEndpoint コマンドレットを実行して、連絡先オブジェクトを移行する必要があります。 従来のインストールと Skype for Business Server 2019 の共存期間の間、Skype for Business Server 2019 で作成したダイヤルインアクセス番号は、この後で説明するように、従来のインストールで作成したダイヤルインアクセス番号と同じように動作します。ここ.
ms.openlocfilehash: 81f100979d009f4f9b48cf9a538ec92095a67ad8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238047"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="b21b7-104">ダイヤルイン アクセス番号の移行</span><span class="sxs-lookup"><span data-stu-id="b21b7-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="b21b7-105">Skype for Business Server 2019 にダイヤルインアクセス番号を移行するには、 **Move-CsApplicationEndpoint**コマンドレットを実行して、連絡先オブジェクトを移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b21b7-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="b21b7-106">従来のインストールと Skype for Business Server 2019 の共存期間の間、Skype for Business Server 2019 で作成したダイヤルインアクセス番号は、この後で説明するように、従来のインストールで作成したダイヤルインアクセス番号と同じように動作します。ここ.</span><span class="sxs-lookup"><span data-stu-id="b21b7-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="b21b7-107">従来のインストールで作成したが、Skype for Business Server 2019 に移動したか、移行中、または移行後に Skype for Business Server 2019 で作成したダイヤルインアクセス番号には、次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="b21b7-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="b21b7-108">Office Communications Server 2007 R2 会議の出席依頼とダイヤルインアクセス番号のページには表示されません。</span><span class="sxs-lookup"><span data-stu-id="b21b7-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="b21b7-109">従来の [会議出席依頼のインストールとダイヤルインアクセス番号] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b21b7-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="b21b7-110">Skype for Business Server 2019 の会議出席依頼とダイヤルインアクセス番号のページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b21b7-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="b21b7-111">Office Communications Server 2007 R2 管理ツールでは、表示または変更できません。</span><span class="sxs-lookup"><span data-stu-id="b21b7-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="b21b7-112">従来の [コントロールパネル] の [レガシーインストールの管理] シェルで、表示と変更ができます。</span><span class="sxs-lookup"><span data-stu-id="b21b7-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="b21b7-113">Skype for Business Server 2019 コントロールパネルと Skype for Business Server 2019 Management Shell で表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="b21b7-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="b21b7-114">Priority パラメーターを指定して CsDialinConferencingAccessNumber コマンドレットを使用して、地域内で再シーケンスできます。</span><span class="sxs-lookup"><span data-stu-id="b21b7-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="b21b7-115">レガシインストールプールを廃止する前に、以前のインストールプールを参照するダイヤルインアクセス番号の移行を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b21b7-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="b21b7-116">次の手順で説明するように、ダイヤルインアクセス番号の移行が完了していない場合は、アクセス番号への着信通話が失敗します。</span><span class="sxs-lookup"><span data-stu-id="b21b7-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b21b7-117">レガシインストールプールを廃止する前に、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b21b7-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="b21b7-118">短時間のサービス停止が発生した場合に備えて、ネットワーク使用量が少ない場合は、ダイヤルインアクセス番号を移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b21b7-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="b21b7-119">ダイヤルインアクセス番号を特定して移動するには</span><span class="sxs-lookup"><span data-stu-id="b21b7-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="b21b7-120">Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b21b7-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b21b7-121">Skype for Business Server 2019 でホストされているプールにダイヤルインアクセス番号を移動するには、コマンドラインで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b21b7-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="b21b7-122">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b21b7-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="b21b7-123">左側のナビゲーション バーで [**会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b21b7-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="b21b7-124">[**ダイヤルインアクセス番号**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b21b7-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="b21b7-125">移行元のレガシーインストールプールのダイヤルインアクセス番号が残っていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b21b7-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b21b7-126">すべてのダイヤルインアクセス番号が Skype for Business Server 2019 プールをポイントしている場合、レガシインストールプールを廃止することができます。</span><span class="sxs-lookup"><span data-stu-id="b21b7-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b21b7-127">Skype for Business Server コントロールパネルを使用して、ダイヤルインアクセス番号の移行を確認する</span><span class="sxs-lookup"><span data-stu-id="b21b7-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b21b7-128">**Csuseradministrator**ロールまたは**csadministrator**ロールに割り当てられているユーザーアカウントから、社内展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b21b7-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="b21b7-129">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b21b7-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="b21b7-130">左側のナビゲーション バーで [**会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b21b7-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="b21b7-131">[**ダイヤルインアクセス番号**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b21b7-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="b21b7-132">すべてのダイヤルインアクセス番号が、Skype for Business Server 2019 でホストされているプールに移行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b21b7-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b21b7-133">Skype for Business Server 管理シェルを使用したダイヤルインアクセス番号の移行を確認する</span><span class="sxs-lookup"><span data-stu-id="b21b7-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="b21b7-134">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b21b7-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="b21b7-135">移行されたダイヤルイン会議アクセス番号をすべて返すには、コマンドラインで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b21b7-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="b21b7-136">すべてのダイヤルインアクセス番号が、Skype for Business Server 2019 でホストされているプールに移行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b21b7-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


