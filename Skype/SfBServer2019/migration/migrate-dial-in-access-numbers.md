---
title: ダイヤルイン アクセス番号の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバー 2019 の Skype に移行するダイヤルイン アクセス番号は、連絡先オブジェクトを移行するのには移動 CsApplicationEndpoint コマンドレットを実行する必要があります。 従来のインストールと Skype ビジネス サーバー 2019 共存の期間には、ビジネス サーバー 2019 の Skype で作成したダイヤルイン アクセス番号と同様に動作では、従来のインストールでは、作成するダイヤルイン アクセス番号これで説明するようセクションです。
ms.openlocfilehash: 7f7aef113018a27e70b88e166d365195c07dce9c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32239584"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="82237-104">ダイヤルイン アクセス番号の移行</span><span class="sxs-lookup"><span data-stu-id="82237-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="82237-105">ビジネス サーバー 2019 の Skype に移行するダイヤルイン アクセス番号は、連絡先オブジェクトを移行するのには**移動 CsApplicationEndpoint**コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82237-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="82237-106">従来のインストールと Skype ビジネス サーバー 2019 共存の期間には、ビジネス サーバー 2019 の Skype で作成したダイヤルイン アクセス番号と同様に動作では、従来のインストールでは、作成するダイヤルイン アクセス番号これで説明するようセクションです。</span><span class="sxs-lookup"><span data-stu-id="82237-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="82237-107">従来で作成したダイヤルイン アクセス番号は、インストールがビジネス サーバー 2019、またはの前に、ビジネスのサーバー 2019、Skype で作成した Skype を移動中、または移行後に、次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="82237-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="82237-108">Office 通信 Server 2007 の R2 の会議出席依頼とダイヤルイン アクセス番号のページには表示されません。</span><span class="sxs-lookup"><span data-stu-id="82237-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="82237-109">レガシー インストールの会議出席依頼とダイヤルイン アクセス番号のページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="82237-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="82237-110">Skype のビジネス サーバー 2019 会議出席依頼とダイヤルイン アクセス番号のページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82237-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="82237-111">表示したり、Office 通信 Server 2007 の R2 の管理ツールで変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="82237-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="82237-112">表示およびレガシー インストールのコントロール パネルと従来のインストール管理シェルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="82237-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="82237-113">表示およびビジネス サーバー 2019 のコントロール パネルの Skype と Skype ビジネス サーバー 2019 の管理シェルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="82237-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="82237-114">再シーケンス処理できる領域内にある優先順位のパラメーターを使用してセット CsDialinConferencingAccessNumber コマンドレットを使用しています。</span><span class="sxs-lookup"><span data-stu-id="82237-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="82237-115">移行を完了する必要がありますポイントには、従来のダイヤルイン アクセス番号がレガシー インストールのプールの使用を停止する前に、プールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="82237-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="82237-116">次の手順に従って、ダイヤルイン アクセス番号の移行を完了しないと、アクセス番号への着信呼び出しが失敗します。</span><span class="sxs-lookup"><span data-stu-id="82237-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82237-117">レガシー インストールのプールの使用を停止する前にこの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82237-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="82237-118">サービスの停止の期間が短い場合に、ネットワーク使用率が軽いときは、ダイヤルイン アクセス番号を移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="82237-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="82237-119">番号を特定しをダイヤルイン アクセスを移動するには</span><span class="sxs-lookup"><span data-stu-id="82237-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="82237-120">ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネス サーバー 2019 の Skype をマイクロソフト**をクリック**ビジネス サーバー管理シェルの Skype**です。</span><span class="sxs-lookup"><span data-stu-id="82237-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="82237-121">各ダイヤルイン アクセス番号をビジネス サーバー 2019 の Skype 上でホストされているプールに移動すると、コマンド ・ ラインから実行します。</span><span class="sxs-lookup"><span data-stu-id="82237-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="82237-122">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="82237-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="82237-123">左側のナビゲーション バーで [**会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82237-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="82237-124">**ダイヤルイン アクセス番号**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="82237-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="82237-125">ないダイヤルイン アクセス番号のまま移行しているレガシー インストールのプールのことを確認します。</span><span class="sxs-lookup"><span data-stu-id="82237-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="82237-126">すべてのダイヤルイン アクセス番号は、ビジネス サーバー 2019 プールの Skype をポイントして、レガシー インストールのプールをし、解除できます。</span><span class="sxs-lookup"><span data-stu-id="82237-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="82237-127">ビジネス サーバーのコントロール パネルの Skype を使用してダイヤルイン アクセス番号の移行を検証します。</span><span class="sxs-lookup"><span data-stu-id="82237-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="82237-128">**CsUserAdministrator**または**CsAdministrator**の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="82237-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="82237-129">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="82237-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="82237-130">左側のナビゲーション バーで [**会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82237-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="82237-131">**ダイヤルイン アクセス番号**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="82237-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="82237-132">ビジネス サーバー 2019 の Skype 上でホストされているプールに、すべてのダイヤルイン アクセス番号が移行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="82237-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="82237-133">ビジネス サーバー管理シェルの Skype を使用してダイヤルイン アクセス番号の移行を検証します。</span><span class="sxs-lookup"><span data-stu-id="82237-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="82237-134">Skype をビジネス サーバー管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="82237-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="82237-135">すべてを取得するのには、ダイヤルイン会議アクセス番号移行、実行コマンド ・ ラインから。</span><span class="sxs-lookup"><span data-stu-id="82237-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="82237-136">ビジネス サーバー 2019 の Skype 上でホストされているプールに、すべてのダイヤルイン アクセス番号が移行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="82237-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


