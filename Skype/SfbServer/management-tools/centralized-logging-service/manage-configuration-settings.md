---
title: Skype for Business Server 2015 での集中ログ サービス構成設定の管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: '概要: Skype for Business Server 2015 の集中ログ サービスの構成設定を取得、更新、および作成する方法について説明します。'
ms.openlocfilehash: fb2d66e6ff72bc5fb5a4c8c987713f3ca7030ab5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098863"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="b7ad4-103">Skype for Business Server 2015 での集中ログ サービス構成設定の管理</span><span class="sxs-lookup"><span data-stu-id="b7ad4-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="b7ad4-104">**概要:** Skype for Business Server 2015 の集中ログ サービスの構成設定を取得、更新、および作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="b7ad4-105">集中ログ サービスは、個別のコンピューターの集中ログ サービス エージェント (CLSAgent) にコマンドを送信するために、集中ログ サービス コントローラー (CLSController) によって作成および使用される設定とパラメーターによって制御および構成されます。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="b7ad4-106">エージェントは、送信されるコマンドを処理し(Start コマンドの場合)、シナリオ、プロバイダー、トレース期間、フラグの構成を使用して、提供された構成情報に従ってトレース ログの収集を開始します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="b7ad4-107">集中ログ Windows PowerShell一覧にあるすべてのコマンドレットが、Skype for Business Server 2015 のオンプレミス展開で使用することを目的としているのではありません。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="b7ad4-108">動作するように見える場合でも、次のコマンドレットは Skype for Business Server 2015 オンプレミス展開では機能するようには設計されません。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="b7ad4-109">**CsClsRegion** コマンドレット: [Get-CsClsRegion](/powershell/module/skype/get-csclsregion?view=skype-ps) [、Set-CsClsRegion](/powershell/module/skype/set-csclsregion?view=skype-ps) [、New-CsClsRegion、Remove-CsClsRegion](/powershell/module/skype/new-csclsregion?view=skype-ps)。 [](/powershell/module/skype/remove-csclsregion?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="b7ad4-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="b7ad4-110">**CsClsSearchTerm コマンドレット:** [Get-CsClsSearchTerm](/powershell/module/skype/get-csclssearchterm?view=skype-ps) および [Set-CsClsSearchTerm](/powershell/module/skype/set-csclssearchterm?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="b7ad4-111">**CsClsSecurityGroup** コマンドレット: [Get-CsClsSecurityGroup](/powershell/module/skype/get-csclssecuritygroup?view=skype-ps) [、Set-CsClsSecurityGroup、New-CsClsSecurityGroup、](/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)[および Remove-CsClsSecurityGroup](/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。 [](/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="b7ad4-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="b7ad4-112">これらのコマンドレットで定義されている設定は、悪影響を及ぼしたり、悪影響を及ぼしたりしませんが、Microsoft 365 または Office 365 で使用するように設計され、オンプレミス展開では予期した結果を得る必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 or Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="b7ad4-113">これは、内部設置型展開ではこれらのコマンドレットが役に立たないという意味ではありませんが、その用途はより高度なトピックであるため、このドキュメントでは扱われません。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="b7ad4-114">集中ログ サービスは、1 台のコンピューターまたはコンピューターのプールを含むスコープ (展開内のコンピューターとプールのコレクションを含むサイト Redmond などの定義されたサイト) またはグローバル スコープ (展開内のすべてのコンピューターとプール) で実行できます。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="b7ad4-115">Skype for Business Server 管理シェルを使用して集中ログ サービス スコープを構成するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティ グループ、またはこれら 2 つのグループのいずれかを含むカスタム RBAC 役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="b7ad4-116">このコマンドレットが割り当てられているすべての RBAC 役割 (自分で作成したカスタム RBAC の役割を含む) の一覧を取得するには、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="b7ad4-117">例:</span><span class="sxs-lookup"><span data-stu-id="b7ad4-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="b7ad4-118">コマンド ライン コマンドと CLSController で実行できる基本的なWindows PowerShellがあります。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="b7ad4-119">Windows PowerShellシナリオを構成および定義し、それらのシナリオをトラブルシューティング シナリオに対して有意義な方法で再利用するための豊富な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="b7ad4-120">CLSController はコマンドを発行して結果を得る迅速かつ効率的な方法を提供しますが、CLSController のコマンド セットは、コマンド ラインから使用できる有限のコマンドによって制限されます。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="b7ad4-121">Windows PowerShell コマンドレットとは異なり、CLSController は新しいシナリオを定義したり、サイトまたはグローバル レベルでスコープを管理したり、動的に構成できない有限コマンド セットのその他の多くの制限を定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="b7ad4-122">CLSController は高速実行のための手段を提供しますが、Windows PowerShell は CLSController で可能な機能を超えて集中ログ サービス機能を拡張する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="b7ad4-123">[Search-CsClsLogging](/powershell/module/skype/search-csclslogging?view=skype-ps)、 [Show-CsClsLogging](/powershell/module/skype/show-csclslogging?view=skype-ps)、 [Start-CsClsLogging](/powershell/module/skype/start-csclslogging?view=skype-ps)、 Stop-CsClsLogging 、 [Sync-CsClsLogging](/powershell/module/skype/sync-csclslogging?view=skype-ps)および[](/powershell/module/skype/stop-csclslogging?view=skype-ps)[Update-CsClsLogging](/powershell/module/skype/update-csclslogging?view=skype-ps)コマンドの実行中に、-Computers パラメーターを使用して単一のコンピューター スコープを定義できます。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="b7ad4-124">-Computers パラメーターは、ターゲット コンピューターの完全修飾ドメイン名 (FQDN) のコンマ区切りリストを受け入れる。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="b7ad4-125">ログ コマンドを実行する -Pools とコンマ区切りのプールの一覧を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="b7ad4-126">サイトスコープとグローバル スコープは **、New-、Set-、Remove-** の集中ログ サービスコマンドレットで定義されます。  </span><span class="sxs-lookup"><span data-stu-id="b7ad4-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="b7ad4-127">次の例では、サイトとグローバル スコープを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7ad4-128">表示されるコマンドには、他のセクションで説明されているパラメーターと概念が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="b7ad4-129">この例のコマンドは、スコープを定義するために **-Identity** パラメーターを使用することを示す目的で使用され、その他のパラメーターは完全性とスコープを指定するために含まれています。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="b7ad4-130">**Set-CsClsConfiguration** コマンドレットの詳細については、「操作」のドキュメントの [「Set-CsClsConfiguration」](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="b7ad4-131">現在の集中ログ サービス構成を取得するには</span><span class="sxs-lookup"><span data-stu-id="b7ad4-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="b7ad4-132">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b7ad4-133">コマンド ライン プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="b7ad4-134">**New-CsClsConfiguration** コマンドレットと **Set-CsClsConfiguration** コマンドレットを使用して、新しい構成を作成するか、既存の構成を更新します。**Get-CsClsConfiguration** を実行すると、展開に現在既定のグローバル構成がありますが、サイト構成が定義されていない次のスクリーン ショットのような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Get-CsClsConfiguration からの出力例。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="b7ad4-136">コンピューターのローカル ストアから現在の集中ログ サービス構成を取得するには</span><span class="sxs-lookup"><span data-stu-id="b7ad4-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="b7ad4-137">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b7ad4-138">コマンド ライン プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="b7ad4-139">**Get-CsClsConfiguration** でパラメーターを指定しない最初の例を使用すると、このコマンドはデータの中央管理ストアを参照します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="b7ad4-140">パラメーター -LocalStore を指定すると、サーバーの全体管理ストアではなく、コンピューターの LocalStore が参照されます。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="b7ad4-141">現在定義されているシナリオの一覧を取得するには</span><span class="sxs-lookup"><span data-stu-id="b7ad4-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="b7ad4-142">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b7ad4-143">コマンド ライン プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="b7ad4-144">たとえば、グローバル スコープで定義されているシナリオを取得するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="b7ad4-145">コマンドレット **Get-CsClsConfiguration は** 、常に特定のスコープの構成の一部であるシナリオを表示します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="b7ad4-146">ほとんどの場合、すべてのシナリオが表示されないので、切り捨てられて表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="b7ad4-147">ここで使用するコマンドは、すべてのシナリオと、使用するプロバイダー、設定、およびフラグに関する部分的な情報を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="b7ad4-148">サーバーを使用して集中ログ サービスのグローバル スコープを更新Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7ad4-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="b7ad4-149">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b7ad4-150">コマンド ライン プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="b7ad4-151">例:</span><span class="sxs-lookup"><span data-stu-id="b7ad4-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="b7ad4-152">このコマンドは、展開内の各コンピューターとプールの CLSAgent に対して、トレース ファイルのロールオーバー値のサイズを 40 メガバイトに設定します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-152">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="b7ad4-153">すべてのサイトのコンピューターとプールはコマンドの影響を受け、構成済みのトレース ログのロールオーバー値を 40 メガバイトに設定します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-153">Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="b7ad4-154">サーバーを使用して集中ログ サービスのサイト スコープを更新するにはWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7ad4-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="b7ad4-155">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b7ad4-156">コマンド ライン プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="b7ad4-157">例:</span><span class="sxs-lookup"><span data-stu-id="b7ad4-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="b7ad4-158">例で説明した通り、ログ ファイルの既定の場所は %TEMP%\Tracing です。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-158">As noted in the example, the default location of the log files is %TEMP%\Tracing.</span></span> <span data-ttu-id="b7ad4-159">ただし、ファイルを書き込むのは実際には CLSAgent であり、CSLAgent はネットワーク サービスとして実行されます。%TEMP% 変数は %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-159">However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="b7ad4-160">このコマンドは、サイト Redmond の各コンピューターとプールの CLSAgent に対して、トレース ファイルのロールオーバー値のサイズを 40 メガバイトに設定します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-160">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="b7ad4-161">他のサイトのコンピューターとプールはコマンドの影響を受け、既定で定義されている現在構成されているトレース ログロールオーバー値 (20 メガバイト) またはログ 記録セッションの開始時に引き続き使用されます。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-161">Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="b7ad4-162">新しい集中ログ サービス構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="b7ad4-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="b7ad4-163">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b7ad4-164">コマンド ライン プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="b7ad4-165">New-CsClsConfiguration多数のオプション構成設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="b7ad4-166">構成オプションの詳細については [、「Get-CsClsConfiguration」](/powershell/module/skype/get-csclsconfiguration?view=skype-ps) および「集中ログ サービス構成設定について [」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-understanding-centralized-logging-service-configuration-settings)。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-166">For details about the configuration options, see [Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-understanding-centralized-logging-service-configuration-settings).</span></span>

<span data-ttu-id="b7ad4-167">たとえば、キャッシュ ファイルのネットワーク フォルダー、ログ ファイルのロールオーバー期間、ログ ファイルのロールオーバー サイズを定義する新しい構成を作成するには、次の入力を行います。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="b7ad4-168">新しい構成の作成と、集中ログ サービスの新しいプロパティの定義方法を慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="b7ad4-169">変更は慎重に行い、問題のシナリオを適切にログに記録する能力への影響を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="b7ad4-170">ログをサイズとロールオーバー期間に管理する機能を強化し、問題が発生した場合に問題解決を可能にする構成を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="b7ad4-171">既存の集中ログ サービス構成を削除するには</span><span class="sxs-lookup"><span data-stu-id="b7ad4-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="b7ad4-172">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b7ad4-173">コマンド ライン プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="b7ad4-174">たとえば、ログ ファイルのロールオーバー時間を増やして作成した集中ログ サービス構成を削除するには、ロールオーバー ログ ファイルのサイズを大きくし、ログ ファイルのキャッシュの場所を次のようにネットワーク共有に設定します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="b7ad4-175">これは、「新しい集中ログ サービス構成を作成するには」の手順で作成された新しい構成です。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="b7ad4-176">サイト レベルの構成を削除する場合、サイトはグローバル設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7ad4-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="b7ad4-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7ad4-177">See also</span></span>

[<span data-ttu-id="b7ad4-178">Skype for Business Server 2015 で集中ログ サービスのプロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="b7ad4-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="b7ad4-179">Skype for Business Server 2015 で集中ログ サービスのシナリオを構成する</span><span class="sxs-lookup"><span data-stu-id="b7ad4-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="b7ad4-180">Skype for Business 2015 の集中ログ サービス</span><span class="sxs-lookup"><span data-stu-id="b7ad4-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="b7ad4-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b7ad4-181">Set-CsClsConfiguration</span></span>](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="b7ad4-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b7ad4-182">Get-CsClsConfiguration</span></span>](/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="b7ad4-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b7ad4-183">New-CsClsConfiguration</span></span>](/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="b7ad4-184">Remove-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b7ad4-184">Remove-CsClsConfiguration</span></span>](/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)