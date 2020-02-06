---
title: Skype for Business Server 2015 の集中ログ サービスの構成設定の管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server 2015 の中央集中ログサービスの構成設定を取得、更新、作成する方法について説明します。'
ms.openlocfilehash: 95aa05cfcd31acda8e78927d674f3a19dff7ef56
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816586"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="e815a-103">Skype for Business Server 2015 の集中ログ サービスの構成設定の管理</span><span class="sxs-lookup"><span data-stu-id="e815a-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="e815a-104">**概要:** Skype for Business Server 2015 の中央集中ログサービスの構成設定を取得、更新、作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e815a-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="e815a-105">一元化されたログサービスは、一元管理サービスコントローラー (CLSController) によって作成および使用される設定とパラメーターによって制御および構成され、個々のコンピューターの集中ログサービスエージェントにコマンドを送信します (CLSAgent)。</span><span class="sxs-lookup"><span data-stu-id="e815a-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="e815a-106">このエージェントは送信されたコマンドを処理し、(Start コマンドの場合は) シナリオ、プロバイダー、トレース期間、フラグの構成を使用して、提供された構成情報に従うトレース ログの収集を開始します。</span><span class="sxs-lookup"><span data-stu-id="e815a-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="e815a-107">一元管理のログサービス用に一覧表示されているすべての Windows PowerShell コマンドレットは、Skype for Business Server 2015 オンプレミスの展開で使用することを目的としていません。</span><span class="sxs-lookup"><span data-stu-id="e815a-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="e815a-108">機能しているように見えても、次のコマンドレットは、Skype for Business Server 2015 オンプレミスの展開で機能するように設計されていません。</span><span class="sxs-lookup"><span data-stu-id="e815a-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="e815a-109">**Csclsregion コマンドレット:** [Get-csclsregion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) 、[Set-csclsregion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)、 [New-](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)CsClsRegion、および削除された[csclsregion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="e815a-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="e815a-110">**Csclssearchterm コマンドレット:** [取得-csclssearchterm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps)と[Set-csclssearchterm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="e815a-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="e815a-111">**CsClsSecurityGroup コマンドレット:** [CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、 [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、 [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)、および[CsClsSecurityGroup を削除](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)します。</span><span class="sxs-lookup"><span data-stu-id="e815a-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="e815a-112">これらのコマンドレットで定義された設定により、悪影響を及ぼす可能性はありませんが、Microsoft Office 365 で使用するように設計されていますが、オンプレミスの展開で予期しない結果が返されることはありません。</span><span class="sxs-lookup"><span data-stu-id="e815a-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="e815a-113">これは、内部設置型展開ではこれらのコマンドレットが役に立たないという意味ではありませんが、その用途はより高度なトピックであるため、このドキュメントでは扱われません。</span><span class="sxs-lookup"><span data-stu-id="e815a-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="e815a-114">一元ログサービスは、1台のコンピューターまたはコンピューターのプールを含むスコープ (展開のコンピューターとプールのコレクションを含むサイトのレドモンドなどの定義されたサイト)、またはグローバルスコープで実行できます (つまり、配置内のコンピューターとプールのコレクションが含まれています)。[展開に含まれるすべてのコンピューターとプール] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e815a-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="e815a-115">Skype for Business Server 管理シェルを使用して一元的なログサービスのスコープを構成するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、または、次の2つのグループのいずれかが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e815a-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="e815a-116">このコマンドレットが割り当てられているすべての RBAC ロールの一覧 (自分自身で作成したカスタム RBAC ロールを含む) を返すには、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e815a-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="e815a-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e815a-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="e815a-118">Windows PowerShell または CLSController で実行できるコマンドラインコマンドには、基本的な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="e815a-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="e815a-119">Windows PowerShell には、シナリオを構成して定義するための豊富な方法が用意されています。また、トラブルシューティングシナリオには、わかりやすい方法でこれらのシナリオを再利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e815a-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="e815a-120">CLSController には、コマンドを発行して結果を取得するための高速で効率的な方法が用意されていますが、CLSController 用のコマンドセットは、コマンドラインから利用できる有限コマンドによって制限されます。</span><span class="sxs-lookup"><span data-stu-id="e815a-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="e815a-121">Windows PowerShell コマンドレットとは異なり、CLSController では、新しいシナリオを定義することはできません。サイトまたはグローバルレベルでスコープを管理することも、動的に構成できない有限コマンドセットに関するその他多くの制限事項もあります。</span><span class="sxs-lookup"><span data-stu-id="e815a-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="e815a-122">CLSController は、高速実行の手段を提供しますが、Windows PowerShell は、CLSController で可能な範囲を超えて一元的なログサービス機能を拡張するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="e815a-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="e815a-123">1つのコンピューターのスコープは、 [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)の実行時に定義することができます。この場合は、[コンピューター []](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)パラメーターを使用して、 [[csclslogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)]、[Sync-csclslogging []、[](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)[同期-](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) csclslogging] の[各コマンドを](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps)実行します。</span><span class="sxs-lookup"><span data-stu-id="e815a-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="e815a-124">-Computers パラメーターは、ターゲットコンピューターの完全修飾ドメイン名 (Fqdn) のコンマ区切りリストを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e815a-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="e815a-125">また、プールと、ログコマンドを実行するプールのコンマ区切りリストを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="e815a-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="e815a-126">サイトとグローバルスコープ**は、\*\*\*\*新しい\*\*\*\*集中化さ**れたログサービスコマンドレットで定義されます。</span><span class="sxs-lookup"><span data-stu-id="e815a-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="e815a-127">以下の例は、サイト スコープとグローバル スコープを設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e815a-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e815a-128">表示されるコマンドには、他のセクションで説明するパラメーターと概念が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="e815a-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="e815a-129">この例のコマンドは、スコープを定義するために **-Identity**パラメーターを使うことを示すことを目的としています。その他のパラメーターは完全に含まれており、スコープを指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e815a-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="e815a-130">**Set-csclsconfiguration**コマンドレットの詳細については、「操作のドキュメントでの[Set-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e815a-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="e815a-131">現在の集中化ログサービス構成を取得するには</span><span class="sxs-lookup"><span data-stu-id="e815a-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="e815a-132">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e815a-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e815a-133">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e815a-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="e815a-134">新規の構成を作成するか、既存の構成を更新するには、**新しい-csclsconfiguration**コマンドレットと**Set-csclsconfiguration**コマンドレットを使用します。" **CsClsConfiguration の設定**を実行すると、次のスクリーンショットのような情報が表示されます。ここでは、現在は既定のグローバル構成があり、サイト構成は定義されていません。</span><span class="sxs-lookup"><span data-stu-id="e815a-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Get-CsClsConfiguration からのサンプル出力](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="e815a-136">コンピューターのローカルストアから現在の集中化されたログサービス構成を取得するには</span><span class="sxs-lookup"><span data-stu-id="e815a-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="e815a-137">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e815a-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e815a-138">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e815a-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="e815a-139">最初の例の " **Get-CsClsConfiguration**でパラメーターが指定されていない" という最初の例を使用すると、コマンドはデータの中央管理ストアを参照します。</span><span class="sxs-lookup"><span data-stu-id="e815a-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="e815a-140">パラメーター-LocalStore を指定した場合、コマンドは中央管理ストアではなく、コンピューターの LocalStore を参照します。</span><span class="sxs-lookup"><span data-stu-id="e815a-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="e815a-141">現在定義されているシナリオの一覧を取得するには</span><span class="sxs-lookup"><span data-stu-id="e815a-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="e815a-142">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e815a-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e815a-143">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e815a-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="e815a-144">たとえば、グローバル スコープで定義されているシナリオを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e815a-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="e815a-145">コマンドレットの**取得の構成**では、常に、特定のスコープ構成の一部であるシナリオが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e815a-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="e815a-146">ほとんどの場合、シナリオがすべて表示されるのではなく、一部が切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="e815a-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="e815a-147">ここで使用するコマンドは、すべてのシナリオおよび使用されているプロバイダー、設定、およびフラグに関する一部の情報を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e815a-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="e815a-148">Windows PowerShell を使用して一元的なログサービスのグローバルスコープを更新するには</span><span class="sxs-lookup"><span data-stu-id="e815a-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="e815a-149">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e815a-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e815a-150">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e815a-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="e815a-151">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e815a-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="e815a-p111">このコマンドは、トレース ファイルのロールオーバーのサイズを 40 MB に設定するよう、展開内の各コンピューターおよびプールの CLSAgent に指示します。すべてのサイトのコンピューターとプールがこのコマンドの対象となり、コンピューターとプールの構成済みのトレース ログのロールオーバーの値が 40 MB に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e815a-p111">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="e815a-154">Windows PowerShell を使用して一元的なログサービスのサイト範囲を更新するには</span><span class="sxs-lookup"><span data-stu-id="e815a-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="e815a-155">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e815a-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e815a-156">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e815a-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="e815a-157">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e815a-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="e815a-p112">この例に示すように、ログ ファイルの既定の場所は %TEMP%\Tracing です。ただし、これは実際にはファイルを書き込む CLSAgent であり、CSLAgent はネットワーク サービスとして実行されるため、%TEMP% 変数は %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。</span><span class="sxs-lookup"><span data-stu-id="e815a-p112">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="e815a-p113">このコマンドは、トレース ファイルのロールオーバーのサイズを 40 MB に設定するよう、Redmond サイト内の各コンピューターおよびプールの CLSAgent に指示します。他のサイトのコンピューターとプールはこのコマンドの対象ではなく、現在構成されているトレース ログのロールオーバーの値 (既定値の 20 MB またはログ記録セッションの開始時に定義された値) が引き続き使用されます。</span><span class="sxs-lookup"><span data-stu-id="e815a-p113">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="e815a-162">新しい一元ログサービス構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="e815a-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="e815a-163">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e815a-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e815a-164">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e815a-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="e815a-165">New-CsClsConfiguration を使用すると、オプションの多数の構成設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e815a-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="e815a-166">構成オプションの詳細については、「 [CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) 」および「[一元ログサービスの構成設定につい](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e815a-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="e815a-167">たとえば、キャッシュ ファイル用のネットワーク フォルダー、ログ ファイルのロールオーバー時間、およびログ ファイルのロールオーバー サイズを定義する新しい構成を作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e815a-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="e815a-168">新しい構成の作成を慎重に計画し、一元管理サービスの新しいプロパティを定義する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="e815a-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="e815a-169">変更は慎重に行い、問題のシナリオのログを適切に記録する機能に及ぼす影響について理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="e815a-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="e815a-170">ログの管理機能を強化する、つまり発生した問題を解決するためのサイズおよびロールオーバー時間を定義できるように構成を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e815a-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="e815a-171">既存の一元ログサービス構成を削除するには</span><span class="sxs-lookup"><span data-stu-id="e815a-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="e815a-172">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e815a-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e815a-173">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e815a-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="e815a-174">たとえば、ログファイルのロールオーバー時間を増やすために作成した一元ログサービスの構成を削除するには、ロールオーバーログファイルのサイズを大きくして、次のようにログファイルキャッシュの場所をネットワーク共有に設定します。</span><span class="sxs-lookup"><span data-stu-id="e815a-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="e815a-175">これは、「新しい一元ログサービス構成を作成する」の手順で作成した新しい構成です。</span><span class="sxs-lookup"><span data-stu-id="e815a-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="e815a-176">サイト レベルの構成の削除を選択すると、そのサイトではグローバル設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e815a-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="e815a-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="e815a-177">See also</span></span>

[<span data-ttu-id="e815a-178">Skype for Business Server 2015 での集中ログ サービス プロバイダーの構成</span><span class="sxs-lookup"><span data-stu-id="e815a-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="e815a-179">Skype for Business Server 2015 での集中ログ サービスのシナリオの構成</span><span class="sxs-lookup"><span data-stu-id="e815a-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="e815a-180">Centralized Logging Service in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="e815a-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="e815a-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="e815a-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="e815a-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="e815a-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="e815a-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="e815a-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="e815a-184">CsClsConfiguration の削除</span><span class="sxs-lookup"><span data-stu-id="e815a-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
