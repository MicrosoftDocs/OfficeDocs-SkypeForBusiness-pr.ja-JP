---
title: Skype for Business Server 2015 の集中ログ サービスの構成設定の管理
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 概要では、取得、更新、およびビジネス サーバー 2015 の Skype で集中ログ サービスの構成設定を作成する方法について説明します。
ms.openlocfilehash: 1aab363f88b7639e2eb61f9101864bac20cc0aa0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896932"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="03dd5-103">Skype for Business Server 2015 の集中ログ サービスの構成設定の管理</span><span class="sxs-lookup"><span data-stu-id="03dd5-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="03dd5-104">**の概要:** 取得、更新、およびビジネス サーバー 2015 の Skype で集中ログ サービスの構成設定を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="03dd5-105">集中ログ サービスを制御し、設定と作成され、個々 のコンピューターのログ サービス エージェントを集中型の (コマンドを送信するため、一元的なログ記録サービス コント ローラー (CLSController) 使用されているパラメーターによって構成されています。CLSAgent)。</span><span class="sxs-lookup"><span data-stu-id="03dd5-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="03dd5-106">このエージェントは送信されたコマンドを処理し、(Start コマンドの場合は) シナリオ、プロバイダー、トレース期間、フラグの構成を使用して、提供された構成情報に従うトレース ログの収集を開始します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="03dd5-107">集中ログ サービスの一覧にないすべての Windows PowerShell コマンドレットは、使用する Skype でビジネス サーバー 2015 設置型展開では。</span><span class="sxs-lookup"><span data-stu-id="03dd5-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="03dd5-108">作業に見えるかもしれませんが、次のコマンドレットがビジネス サーバー 2015 設置型展開では、Skype で機能するために設計されていません。</span><span class="sxs-lookup"><span data-stu-id="03dd5-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="03dd5-109">**CsClsRegion コマンドレット:**[Get CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) [セット CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)、 [CsClsRegion では新しい](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)、し、[削除 CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="03dd5-110">**CsClsSearchTerm コマンドレット:**[Get CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) [セット CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="03dd5-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="03dd5-111">**CsClsSecurityGroup コマンドレット:**[Get CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)[セット CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、 [CsClsSecurityGroup では新しい](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)、し、[削除 CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="03dd5-112">これらのコマンドレットで定義された設定されないを低下させるか、任意の有害な動作が発生するが、Microsoft Office 365 で使用するために設計されていますが、設置型展開で期待どおりの結果には意味がありません。</span><span class="sxs-lookup"><span data-stu-id="03dd5-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="03dd5-113">これは、内部設置型展開ではこれらのコマンドレットが役に立たないという意味ではありませんが、その用途はより高度なトピックであるため、このドキュメントでは扱われません。</span><span class="sxs-lookup"><span data-stu-id="03dd5-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="03dd5-114">1 台のコンピューターまたはコンピューターのプールを含むスコープ、サイト スコープ (つまり、定義したサイトのコンピューターと、展開内のプールのコレクションを含む Redmond サイトなど)、またはグローバル スコープ (つまり、集中ログ サービスを実行することができます。、すべてのコンピューターと、展開内のプール)。</span><span class="sxs-lookup"><span data-stu-id="03dd5-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="03dd5-115">ビジネス サーバー管理シェルには、Skype を使用して、ログ サービスの一元的なスコープを構成するのには、CsAdministrator または CsServerAdministrator の役割に基づくアクセス制御 (RBAC) セキュリティ グループ、またはカスタムの RBAC の役割のいずれかのメンバーが必要ですこれら 2 つのグループのいずれかが含まれています。</span><span class="sxs-lookup"><span data-stu-id="03dd5-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="03dd5-116">(自分で作成したカスタムの RBAC の役割を含む) には、このコマンドレットが割り当てられているすべての RBAC の役割の一覧を返すするには、ビジネスのサーバー管理シェルまたは Windows PowerShell プロンプトに、Skype から次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="03dd5-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-117">For example:</span></span>

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="03dd5-118">Windows PowerShell または CLSController で実行できるコマンド ライン コマンドの基本的な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="03dd5-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="03dd5-119">Windows PowerShell を構成し、シナリオを定義して、トラブルシューティングのシナリオでは、意味のある方法でこれらのシナリオを再利用するのには、豊富なメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="03dd5-120">CLSController は、高速および効率のよいコマンドを発行し、結果を得るまで、CLSController は、有限で制限を設定するコマンド コマンドの中に、コマンドラインから使用可能ながあります。</span><span class="sxs-lookup"><span data-stu-id="03dd5-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="03dd5-121">Windows PowerShell コマンドレットとは異なり、CLSController は新しいシナリオを定義は可能で、サイトまたはグローバル レベル、および動的に構成することはできませんが、有限のコマンド セットの他の多くの制限の範囲を管理できません。</span><span class="sxs-lookup"><span data-stu-id="03dd5-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="03dd5-122">CLSController には、高速に実行の手段が用意されています、Windows PowerShell は CLSController で使用可能な対象外ログ サービスの集中管理機能を拡張するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="03dd5-123">[検索 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)、[ショー CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)、[開始 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)、 [Stop CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)、[同期 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) [更新プログラム CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps)の実行中に 1 台のコンピューターのスコープを定義することができます。コマンドを使用してコンピューターのパラメーターをします。</span><span class="sxs-lookup"><span data-stu-id="03dd5-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="03dd5-124">コンピューターのパラメーターは、ターゲット コンピューターの完全修飾ドメイン名 (Fqdn) のコンマ区切りのリストを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="03dd5-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="03dd5-125">定義することも・ プールとコマンドのログを実行するプールのコンマ区切りのリストです。</span><span class="sxs-lookup"><span data-stu-id="03dd5-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="03dd5-126">**新規**、**セットを**および**削除の**一元的なログ記録サービスのコマンドレットでは、サイトおよびグローバル スコープが定義されています。</span><span class="sxs-lookup"><span data-stu-id="03dd5-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="03dd5-127">以下の例は、サイト スコープとグローバル スコープを設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="03dd5-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03dd5-128">表示されるコマンドには、パラメーターとその他のセクションで説明する概念が含まれます。</span><span class="sxs-lookup"><span data-stu-id="03dd5-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="03dd5-129">コマンドの例の使用法を紹介するものでは、 **-の Id**のスコープを定義するパラメーターとその他のパラメーターは、完全を期すのため、スコープを指定するのには含まれています。</span><span class="sxs-lookup"><span data-stu-id="03dd5-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="03dd5-130">**セット CsClsConfiguration**コマンドレットの詳細については、操作マニュアルの[セットの CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03dd5-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="03dd5-131">現在のログ サービスの一元的な構成を取得するには</span><span class="sxs-lookup"><span data-stu-id="03dd5-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="03dd5-132">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="03dd5-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="03dd5-133">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-133">Type the following at the command-line prompt:</span></span>

   ```
   Get-CsClsConfiguration
   ```

<span data-ttu-id="03dd5-134">新しい構成を作成または既存の構成を更新するのには、**新規 CsClsConfiguration**と**セット CsClsConfiguration**コマンドレットを使用します。**Get CsClsConfiguration**を実行すると、次のスクリーン ショット、展開されているデフォルトのグローバル設定ですが定義されているサイト構成はありませんのような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="03dd5-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Get-CsClsConfiguration からのサンプル出力](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="03dd5-136">コンピューターのローカル ストアから現在のログ サービスの一元的な構成を取得するには</span><span class="sxs-lookup"><span data-stu-id="03dd5-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="03dd5-137">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="03dd5-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="03dd5-138">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-138">Type the following at the command-line prompt:</span></span>

   ```
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="03dd5-139">使用する場合最初の例では、 **Get CsClsConfiguration**がすべてのパラメーター、コマンドの参照先を指定しない、中央管理ストアのデータです。</span><span class="sxs-lookup"><span data-stu-id="03dd5-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="03dd5-140">パラメーターを指定する場合、-LocalStore、コマンドは、中央管理ストアではなくコンピューターの LocalStore を参照します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="03dd5-141">現在定義されているシナリオの一覧を取得するには</span><span class="sxs-lookup"><span data-stu-id="03dd5-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="03dd5-142">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="03dd5-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="03dd5-143">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-143">Type the following at the command-line prompt:</span></span>

   ```
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="03dd5-144">たとえば、グローバル スコープで定義されているシナリオを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="03dd5-145">**Get CsClsConfiguration**コマンドレットは、常に特定のスコープの構成の一部になっているシナリオを表示します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="03dd5-146">ほとんどの場合、シナリオがすべて表示されるのではなく、一部が切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="03dd5-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="03dd5-147">ここで使用するコマンドは、すべてのシナリオおよび使用されているプロバイダー、設定、およびフラグに関する一部の情報を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="03dd5-148">Windows PowerShell を使用して集中ログ サービスのグローバル スコープを更新するには</span><span class="sxs-lookup"><span data-stu-id="03dd5-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="03dd5-149">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="03dd5-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="03dd5-150">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-150">Type the following at the command-line prompt:</span></span>

   ```
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="03dd5-151">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-151">For example:</span></span>

   ```
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="03dd5-p111">このコマンドは、トレース ファイルのロールオーバーのサイズを 40 MB に設定するよう、展開内の各コンピューターおよびプールの CLSAgent に指示します。すべてのサイトのコンピューターとプールがこのコマンドの対象となり、コンピューターとプールの構成済みのトレース ログのロールオーバーの値が 40 MB に設定されます。</span><span class="sxs-lookup"><span data-stu-id="03dd5-p111">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="03dd5-154">Windows PowerShell を使用して集中ログ サービスのサイトの範囲を更新するには</span><span class="sxs-lookup"><span data-stu-id="03dd5-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="03dd5-155">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="03dd5-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="03dd5-156">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-156">Type the following at the command-line prompt:</span></span>

   ```
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="03dd5-157">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-157">For example:</span></span>

   ```
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="03dd5-p112">この例に示すように、ログ ファイルの既定の場所は %TEMP%\Tracing です。ただし、これは実際にはファイルを書き込む CLSAgent であり、CSLAgent はネットワーク サービスとして実行されるため、%TEMP% 変数は %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。</span><span class="sxs-lookup"><span data-stu-id="03dd5-p112">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="03dd5-p113">このコマンドは、トレース ファイルのロールオーバーのサイズを 40 MB に設定するよう、Redmond サイト内の各コンピューターおよびプールの CLSAgent に指示します。他のサイトのコンピューターとプールはこのコマンドの対象ではなく、現在構成されているトレース ログのロールオーバーの値 (既定値の 20 MB またはログ記録セッションの開始時に定義された値) が引き続き使用されます。</span><span class="sxs-lookup"><span data-stu-id="03dd5-p113">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="03dd5-162">新しいログ サービスの一元的な構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="03dd5-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="03dd5-163">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="03dd5-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="03dd5-164">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-164">Type the following at the command-line prompt:</span></span>

   ```
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="03dd5-165">New-CsClsConfiguration を使用すると、オプションの多数の構成設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="03dd5-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="03dd5-166">詳細構成オプションについては、 [Get CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)と[理解する一元的なログ記録サービス構成の設定](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03dd5-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="03dd5-167">たとえば、キャッシュ ファイル用のネットワーク フォルダー、ログ ファイルのロールオーバー時間、およびログ ファイルのロールオーバー サイズを定義する新しい構成を作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="03dd5-168">新しい構成および集中ログ サービスの新しいプロパティを定義する方法の作成を慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03dd5-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="03dd5-169">変更は慎重に行い、問題のシナリオのログを適切に記録する機能に及ぼす影響について理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="03dd5-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="03dd5-170">ログの管理機能を強化する、つまり発生した問題を解決するためのサイズおよびロールオーバー時間を定義できるように構成を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03dd5-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="03dd5-171">既存のログ サービスの一元的な構成を削除するのには</span><span class="sxs-lookup"><span data-stu-id="03dd5-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="03dd5-172">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="03dd5-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="03dd5-173">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="03dd5-173">Type the following at the command-line prompt:</span></span>

   ```
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="03dd5-174">などのログ ファイルのロール オーバーの時間を増加するために作成するログ サービスの一元的な構成を削除するには、ロール オーバーのログ ファイル サイズを増やすし、ネットワーク共有にログ ファイルのキャッシュの場所を次のように設定。</span><span class="sxs-lookup"><span data-stu-id="03dd5-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="03dd5-175">これは、新しい構成を作成する新しい集中ログ サービス構成します」の手順で作成されました。</span><span class="sxs-lookup"><span data-stu-id="03dd5-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="03dd5-176">サイト レベルの構成の削除を選択すると、そのサイトではグローバル設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="03dd5-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="03dd5-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="03dd5-177">See also</span></span>

[<span data-ttu-id="03dd5-178">Skype for Business Server 2015 での集中ログ サービス プロバイダーの構成</span><span class="sxs-lookup"><span data-stu-id="03dd5-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="03dd5-179">Skype for Business Server 2015 での集中ログ サービスのシナリオの構成</span><span class="sxs-lookup"><span data-stu-id="03dd5-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="03dd5-180">Centralized Logging Service in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="03dd5-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="03dd5-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="03dd5-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="03dd5-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="03dd5-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="03dd5-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="03dd5-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="03dd5-184">削除 CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="03dd5-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
