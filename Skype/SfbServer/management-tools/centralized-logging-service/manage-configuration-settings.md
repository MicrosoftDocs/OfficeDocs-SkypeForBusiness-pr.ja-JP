---
title: Skype for Business Server 2015 での集中ログサービスの構成設定の管理
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
description: '概要: Skype for Business Server 2015 で集中ログサービスの構成設定を取得、更新、および作成する方法について説明します。'
ms.openlocfilehash: ed75aab211f2d2abbf0a2007fd83e5be8bb70404
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221177"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="7a0da-103">Skype for Business Server 2015 での集中ログサービスの構成設定の管理</span><span class="sxs-lookup"><span data-stu-id="7a0da-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="7a0da-104">**概要:** Skype for Business Server 2015 で集中ログサービスの構成設定を取得、更新、および作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="7a0da-105">集中ログサービスは、個々のコンピューターの集中ログサービスエージェント (CLSController) にコマンドを送信するために、集中ログサービスコントローラー (CLSController) によって作成および使用される設定とパラメーターによって制御および構成されます。</span><span class="sxs-lookup"><span data-stu-id="7a0da-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="7a0da-106">エージェントは、エージェントに送信されたコマンドを処理し (開始コマンドの場合)、シナリオ、プロバイダ、トレース期間、フラグの構成を使用して、提供された構成情報に従ってトレースログの収集を開始します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="7a0da-107">集中ログサービス用に一覧表示されているすべての Windows PowerShell コマンドレットは、Skype for Business Server 2015 社内展開で使用することを目的としたものではありません。</span><span class="sxs-lookup"><span data-stu-id="7a0da-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="7a0da-108">次のコマンドレットは、機能しているように見えても、Skype for Business Server 2015 の社内展開で機能するようには設計されていません。</span><span class="sxs-lookup"><span data-stu-id="7a0da-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="7a0da-109">**Csclsregion コマンドレット:** [取得-csclsregion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) 、[Set-csclsregion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)、 [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)、および[Remove-csclsregion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="7a0da-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="7a0da-110">**CsClsSearchTerm コマンドレット:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) および [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="7a0da-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="7a0da-111">**New-csclssecuritygroup コマンドレット:** [new-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、 [new-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、 [New-new-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)、および[Remove-new-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="7a0da-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="7a0da-112">これらのコマンドレットで定義されている設定は、悪影響を及ぼすことはありませんが、Microsoft 365 または Office 365 で使用するように設計されており、オンプレミスの展開で予期した結果をもたらすことはありません。</span><span class="sxs-lookup"><span data-stu-id="7a0da-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 or Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="7a0da-113">これは、内部設置型展開ではこれらのコマンドレットが役に立たないという意味ではありませんが、その用途はより高度なトピックであるため、このドキュメントでは扱われません。</span><span class="sxs-lookup"><span data-stu-id="7a0da-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="7a0da-114">集中ログサービスは、1台のコンピューターまたはコンピューターのプール、サイトスコープ (展開内のコンピューターとプールのコレクションが含まれているサイト Redmond などの定義済みサイト)、またはグローバルスコープ (展開内のすべてのコンピューターとプール) に対して実行できます。</span><span class="sxs-lookup"><span data-stu-id="7a0da-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="7a0da-115">Skype for Business Server 管理シェルを使用して集中ログサービススコープを構成するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、またはこれら2つのグループのどちらかを含むカスタムの RBAC の役割を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a0da-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="7a0da-116">このコマンドレットが割り当てられているすべての RBAC の役割の一覧 (自分で作成したカスタムの RBAC の役割を含む) を取得するには、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="7a0da-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="7a0da-118">Windows PowerShell または CLSController で実行できるコマンドラインコマンドには、基本的な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="7a0da-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="7a0da-119">Windows PowerShell には、シナリオを構成して定義するための豊富な方法が用意されています。また、これらのシナリオをトラブルシューティングのシナリオに合わせてわかりやすく再利用できます。</span><span class="sxs-lookup"><span data-stu-id="7a0da-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="7a0da-120">CLSController では、コマンドを発行して結果を取得する高速で効率的な方法が提供されていますが、CLSController のコマンドセットは、コマンドラインから使用可能な有限コマンドによって制限されます。</span><span class="sxs-lookup"><span data-stu-id="7a0da-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="7a0da-121">Windows PowerShell コマンドレットとは異なり、CLSController では新しいシナリオを定義したり、サイトまたはグローバルレベルでスコープを管理したり、動的に構成することができない制限されたコマンドセットに関するその他の多くの制限を設けたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7a0da-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="7a0da-122">CLSController は高速実行の手段を提供しますが、Windows PowerShell では、集中化されたログサービス機能を、CLSController で可能な範囲を超えて拡張する手段が提供されています。</span><span class="sxs-lookup"><span data-stu-id="7a0da-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="7a0da-123">[検索-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)、 [Show-csclslogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)、 [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)、 [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)、 [Sync-csclslogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) 、および-Computers パラメーターを使用した[更新-](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) csclslogging コマンドの実行中に、単一のコンピュータースコープを定義できます。</span><span class="sxs-lookup"><span data-stu-id="7a0da-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="7a0da-124">-Computers パラメーターには、ターゲットコンピューターの完全修飾ドメイン名 (Fqdn) をコンマで区切った一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="7a0da-125">また、ログコマンドを実行するプールとコンマで区切られた一覧を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="7a0da-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="7a0da-126">サイトとグローバルスコープは、**新しい-**、 **Set-** および**Remove-** 集中ログサービスのコマンドレットで定義されています。</span><span class="sxs-lookup"><span data-stu-id="7a0da-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="7a0da-127">次の例は、サイトとグローバルスコープを設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7a0da-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a0da-128">表示されているコマンドには、他のセクションで説明しているパラメーターと概念が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="7a0da-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="7a0da-129">この例では、 **-Identity**パラメーターを使用してスコープを定義することを示し、他のパラメーターは完全に、そのスコープを指定することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="7a0da-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="7a0da-130">**設定-csclsconfiguration**コマンドレットの詳細については、「操作」のドキュメントの「 [Set-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a0da-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="7a0da-131">現在の集中ログサービスの構成を取得するには</span><span class="sxs-lookup"><span data-stu-id="7a0da-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="7a0da-132">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a0da-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7a0da-133">コマンドラインプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="7a0da-134">新しい構成を作成したり、既存の構成を更新したりするには、**新しい-csclsconfiguration**および**Set-csclsconfiguration**コマンドレットを使用します。**取得-CsClsConfiguration**を実行すると、次のスクリーンショットに示すような情報が表示されます。現在、展開には既定のグローバル構成がありますが、サイト構成は定義されていません。</span><span class="sxs-lookup"><span data-stu-id="7a0da-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Get-CsClsConfiguration からの出力例。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="7a0da-136">コンピューターのローカルストアから現在の集中ログサービスの構成を取得するには</span><span class="sxs-lookup"><span data-stu-id="7a0da-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="7a0da-137">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a0da-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7a0da-138">コマンドラインプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="7a0da-139">**Get-CsClsConfiguration**でパラメーターが指定されていない最初の例を使用すると、コマンドはデータの中央管理ストアを参照します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="7a0da-140">パラメーター-LocalStore を指定すると、コマンドは中央管理ストアの代わりにコンピューターの LocalStore を参照します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="7a0da-141">現在定義されているシナリオの一覧を取得するには</span><span class="sxs-lookup"><span data-stu-id="7a0da-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="7a0da-142">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a0da-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7a0da-143">コマンドラインプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="7a0da-144">たとえば、グローバルスコープで定義されているシナリオを取得するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="7a0da-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="7a0da-145">コマンドレットを**取得**すると、指定したスコープの構成の一部であるシナリオが常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a0da-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="7a0da-146">ほとんどの場合、すべてのシナリオは表示されず、切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="7a0da-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="7a0da-147">ここで使用しているコマンドは、すべてのシナリオと、プロバイダー、設定、およびフラグを使用することに関する情報の一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="7a0da-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="7a0da-148">Windows PowerShell を使用して集中ログサービスのグローバルスコープを更新するには</span><span class="sxs-lookup"><span data-stu-id="7a0da-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="7a0da-149">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a0da-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7a0da-150">コマンドラインプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="7a0da-151">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="7a0da-152">このコマンドは、展開内の各コンピューターおよびプールの CLSAgent に対して、トレースファイルのロールオーバー値のサイズを 40 mb に設定するように指示します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-152">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="7a0da-153">すべてのサイトのコンピューターとプールはコマンドの影響を受け、構成済みのトレースログのロールオーバー値は40メガバイトに設定されます。</span><span class="sxs-lookup"><span data-stu-id="7a0da-153">Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="7a0da-154">Windows PowerShell を使用して集中ログサービスのサイトスコープを更新するには</span><span class="sxs-lookup"><span data-stu-id="7a0da-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="7a0da-155">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a0da-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7a0da-156">コマンドラインプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="7a0da-157">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="7a0da-158">例に示されているように、ログファイルの既定の場所は%TEMP%\Tracing. です。</span><span class="sxs-lookup"><span data-stu-id="7a0da-158">As noted in the example, the default location of the log files is %TEMP%\Tracing.</span></span> <span data-ttu-id="7a0da-159">ただし、実際には、ファイルを書き込み中で、CSLAgent はネットワークサービスとして実行されるので、このような場合、%Windir%\serviceprofiles\networkservice\appdata\local には% TEMP% 変数が展開されます。</span><span class="sxs-lookup"><span data-stu-id="7a0da-159">However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="7a0da-160">このコマンドは、サイト Redmond の各コンピューターおよびプールの CLSAgent に対して、トレースファイルのロールオーバー値のサイズを 40 mb に設定します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-160">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="7a0da-161">他のサイト内のコンピューターとプールはコマンドの影響を受けず、現在構成されているトレースログのロールオーバー値 (既定値 (20 mb) またはログセッションの開始時) を引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-161">Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="7a0da-162">新しい集中ログサービスの構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="7a0da-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="7a0da-163">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a0da-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7a0da-164">コマンドラインプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="7a0da-165">新しい-CsClsConfiguration を使用すると、多数のオプションの構成設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7a0da-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="7a0da-166">構成オプションの詳細については、「[取得-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) 」と「[集中ログサービスの構成設定](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a0da-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="7a0da-167">たとえば、キャッシュファイル用のネットワークフォルダー、ログファイルのロールオーバー期間、およびログファイルのロールオーバーサイズを定義する新しい構成を作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="7a0da-168">新しい構成の作成を慎重に計画し、集中ログサービスの新しいプロパティを定義する方法を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a0da-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="7a0da-169">変更を行って、問題のシナリオを適切にログに記録する機能への影響を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a0da-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="7a0da-170">ログの管理能力を向上させるように構成を変更する必要があります。これにより、問題が発生したときに問題を解決するためのサイズとロールオーバー期間が向上します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="7a0da-171">既存の集中ログサービスの構成を削除するには</span><span class="sxs-lookup"><span data-stu-id="7a0da-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="7a0da-172">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a0da-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7a0da-173">コマンドラインプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="7a0da-174">たとえば、ログファイルのロールオーバー時間を長くするために作成した集中ログサービスの構成を削除するには、次のように、ロールオーバーログファイルのサイズを大きくして、ログファイルのキャッシュの場所をネットワーク共有に設定します。</span><span class="sxs-lookup"><span data-stu-id="7a0da-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="7a0da-175">これは、「新しい集中ログサービスの構成を作成するには」の手順で作成した新しい構成です。</span><span class="sxs-lookup"><span data-stu-id="7a0da-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="7a0da-176">サイトレベルの構成の削除を選択すると、サイトではグローバル設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a0da-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="7a0da-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a0da-177">See also</span></span>

[<span data-ttu-id="7a0da-178">Skype for Business Server 2015 で集中ログサービスのプロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="7a0da-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="7a0da-179">Skype for Business Server 2015 での集中ログサービスのシナリオの構成</span><span class="sxs-lookup"><span data-stu-id="7a0da-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="7a0da-180">Skype for Business 2015 の集中ログサービス</span><span class="sxs-lookup"><span data-stu-id="7a0da-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="7a0da-181">設定-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7a0da-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="7a0da-182">取得-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7a0da-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="7a0da-183">新しい-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7a0da-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="7a0da-184">削除-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7a0da-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
