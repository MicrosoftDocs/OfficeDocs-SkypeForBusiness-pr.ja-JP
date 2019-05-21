---
title: Skype for Business Server 2015 での集中ログ サービスのシナリオの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: '概要: Skype for Business Server 2015 の中央集中ログサービスのシナリオを作成、変更、削除する方法について説明します。'
ms.openlocfilehash: 89aa0c37dfb13f7614067b64e37ee9c9fb376331
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274437"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="2a3c0-103">Skype for Business Server 2015 での集中ログ サービスのシナリオの構成</span><span class="sxs-lookup"><span data-stu-id="2a3c0-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2a3c0-104">**概要:** Skype for Business Server 2015 の中央集中ログサービスのシナリオを作成、変更、削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2a3c0-105">シナリオでは、スコープ (つまり、グローバル、サイト、プール、またはコンピューター) と、一元管理サービスで使用するプロバイダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="2a3c0-106">シナリオを使用して、プロバイダー (S4、SIPStack、IM、プレゼンスなど) のトレースを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="2a3c0-107">シナリオを構成することで、特定の問題の条件に対応する特定の論理コレクションのすべてのプロバイダーをグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="2a3c0-108">トラブルシューティングとログのニーズに合わせてシナリオを変更する必要があることがわかった場合は、Skype for Business Server 2015 デバッグツールでは、ClsScenarioEdit という名前の Windows PowerShell モジュールが提供されます。これには、dlmigrationmodule.psm1 という名前の namedEdit が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="2a3c0-109">このモジュールの目的は、指定したシナリオのプロパティを編集することです。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="2a3c0-110">このトピックでは、このモジュールの使用方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="2a3c0-111">さらに先に進む前に、Skype for Business Server 2015[デバッグツール](https://go.microsoft.com/fwlink/p/?LinkId=285257)をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2a3c0-112">どのスコープ (サイト、グローバル、プール、またはコンピューター) でも、一度に最大で 2 つのシナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="2a3c0-113">現在実行されているシナリオを特定するには、Windows PowerShell と[Get CsClsScenario シナリオ](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="2a3c0-114">Windows PowerShell と[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)を使用すると、実行されているシナリオを動的に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-114">By using Windows PowerShell and [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="2a3c0-115">ログ セッション中に実行するシナリオを変更して、収集するデータや収集元のプロバイダーを変更または微調整することができます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="2a3c0-116">Skype for Business Server 管理シェルを使用して一元的なログサービス機能を実行するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、または、次の2つのグループのいずれかが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="2a3c0-117">自分で作成したすべての RBAC ロールの一覧を返すには、Skype for Business Server 管理シェルまたは Windows PowerShell のプロンプトから次のコマンドを実行します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="2a3c0-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-118">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="2a3c0-119">このトピックの以降の部分では、トラブルシューティングを最適化するためのシナリオの定義、シナリオの変更、実行中のシナリオの取得、シナリオの削除、シナリオ内容の指定の方法を中心に説明します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="2a3c0-120">Skype for Business Server 管理シェルを使用して、Windows PowerShell コマンドを発行することができます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="2a3c0-121">Windows PowerShell を使用する場合は、ログセッションで使用する新しいシナリオを定義できます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="2a3c0-122">[Skype For business 2015 の中央集中ログサービス](centralized-logging-service.md)で導入されたように、シナリオの要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="2a3c0-123">**Providers**OCSLogger に精通している場合、プロバイダーは、トレースエンジンがログを収集する必要があることを OCSLogger に伝えるために選ぶコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="2a3c0-124">プロバイダーは同じコンポーネントであり、多くの場合、OCSLogger のコンポーネントと同じ名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="2a3c0-125">OCSLogger に精通していない場合は、中央のログサービスがログを収集できるサーバーの役割固有のコンポーネントはプロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="2a3c0-126">プロバイダーの構成の詳細については、「 [Skype For Business Server 2015 で中央集中ログサービスのプロバイダーを構成する](configure-providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="2a3c0-127">**Id**パラメーター-Identity は、シナリオのスコープと名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="2a3c0-128">たとえば、"グローバル" のスコープを設定し、"LyssServiceScenario" を使ってシナリオを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="2a3c0-129">この2つを組み合わせると、Id (たとえば、"global/LyssServiceScenario") が定義されます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="2a3c0-130">必要に応じて、-Name と-Parent パラメーターを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="2a3c0-131">Name パラメーターは、シナリオを一意に識別するために定義します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="2a3c0-132">Name を使用する場合は、Parent も使用して、グローバルまたはサイトにシナリオを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="2a3c0-133">Name パラメーターと Parent パラメーターを使用する場合は、 **-Identity**パラメーターを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="2a3c0-134">New-CsClsScenario コマンドレットを使用して新しいシナリオを作成するには</span><span class="sxs-lookup"><span data-stu-id="2a3c0-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="2a3c0-135">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2a3c0-p108">ログ セッションのための新しいシナリオを作成するには、[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) を使用し、シナリオの名前 (シナリオを一意に識別する方法) を定義します。ログ形式の種類を、WPP (Windows ソフトウェア トレース プリプロセッサ。これが既定値です)、EventLog (Windows イベント ログ形式)、または IISLog (IIS ログ ファイル形式に基づく ASCII 形式ファイル) から選択します。次に、レベル (このトピックのログ レベルの説明で定義されています) とフラグ (このトピックのフラグの説明で定義されています) を定義します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-p108">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified). Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format). Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="2a3c0-139">このシナリオ例では、プロバイダー変数の例として LyssProvider を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="2a3c0-140">定義されたオプションを使用してシナリオを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-140">To create a scenario using the options defined, type:</span></span>
    
   ```
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    <span data-ttu-id="2a3c0-141">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-141">For example:</span></span>
    
   ```
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    <span data-ttu-id="2a3c0-142">-Name と-Parent を使った代替形式:</span><span class="sxs-lookup"><span data-stu-id="2a3c0-142">The alternate format using -Name and -Parent:</span></span>
    
   ```
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="2a3c0-143">複数のプロバイダーを指定した新しいシナリオを New-CsClsScenario コマンドレットを使用して作成するには</span><span class="sxs-lookup"><span data-stu-id="2a3c0-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="2a3c0-144">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2a3c0-145">スコープごとのシナリオ数は 2 つまでに制限されています。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="2a3c0-146">しかし、設定するプロバイダーの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="2a3c0-147">この例では、3 つのプロバイダーを作成済みで、定義するシナリオに 3 つのプロバイダーをすべて割り当てる必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="2a3c0-148">プロバイダー変数の名前は LyssProvider、ABServerProvider、および SIPStackProvider です。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="2a3c0-149">1つのシナリオに複数のプロバイダーを定義して割り当てるには、Skype for Business Server 管理シェルまたは Windows PowerShell コマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
   ```
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > <span data-ttu-id="2a3c0-150">Windows PowerShell でわかっているように、using `@{<variable>=<value1>, <value2>, <value>…}`という値のハッシュテーブルを作成するための規則は既知の assplatting です。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="2a3c0-151">Windows PowerShell での splatting の詳細につい[https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)ては、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="2a3c0-152">Set-CsClsScenario コマンドレットを使用して既存のシナリオを変更するには</span><span class="sxs-lookup"><span data-stu-id="2a3c0-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="2a3c0-153">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2a3c0-154">スコープごとのシナリオ数は 2 つまでに制限されています。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="2a3c0-155">実行するシナリオは、ログ キャプチャ セッションの実行中を含め、いつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="2a3c0-156">実行するシナリオを再定義すると、現在のログ セッションは削除されたシナリオの使用を停止し、新しいシナリオの使用を開始します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="2a3c0-157">ただし、削除されたシナリオでキャプチャされたログ情報はキャプチャされたログに残ります。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="2a3c0-158">新しいシナリオを定義するには、次の操作を行います (つまり、"S4Provider" という名前の定義済みプロバイダーが追加されていることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    <span data-ttu-id="2a3c0-159">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-159">For example:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    <span data-ttu-id="2a3c0-p112">プロバイダーを置き換える場合は、現在のセットと置き換える単一のプロバイダーか、プロバイダーのコンマ区切りリストを定義します。多数のプロバイダーのうち 1 つだけを置き換える場合は、現在のプロバイダーに新しいプロバイダーを追加して、新しいプロバイダーと既存のプロバイダーの両方を含む新しいプロバイダーのセットを作成します。すべてのプロバイダーを新しいセットで置き換える場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    <span data-ttu-id="2a3c0-163">たとえば、現在の $LyssProvider、$ABServerProvider、および $SIPStackProvider のセットを $LyssServiceProvider に置き換えるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    <span data-ttu-id="2a3c0-164">現在の $LyssProvider、$ABServerProvider、および $SIPStackProvider のセットのうち、$LyssProvider プロバイダーだけを $LyssServiceProvider に置き換えるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="2a3c0-165">Remove-CsClsScenario コマンドレットを使用して既存のシナリオを削除するには</span><span class="sxs-lookup"><span data-stu-id="2a3c0-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="2a3c0-166">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2a3c0-167">定義済みのシナリオを削除する場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
   ```
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    <span data-ttu-id="2a3c0-168">たとえば、定義済みのシナリオ site:Redmond/LyssServiceScenario を削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

<span data-ttu-id="2a3c0-169">**Remove-CsClsScenario** コマンドレットでは指定したシナリオが削除されますが、キャプチャ済みのトレースはログに残り、検索に利用できます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="2a3c0-170">ClsScenarioEdit.psm1 モジュールを使用して Edit-CsClsScenario コマンドレットをロードおよびアンロードするには</span><span class="sxs-lookup"><span data-stu-id="2a3c0-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="2a3c0-171">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2a3c0-172">ClsScenarioEdit.psm1 モジュールは個別の Web ダウンロードとして提供されます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="2a3c0-173">このモジュールは、Skype for Business Server 2015 デバッグツールの一部です。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="2a3c0-174">既定では、デバッグ ツールは C:\Program Files\Skype for Business Server 2015\Debugging Tools ディレクトリにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="2a3c0-175">Windows PowerShell で次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-175">From the Windows PowerShell, type:</span></span>
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="2a3c0-176">モジュールの読み込みが成功すると、Windows PowerShell コマンドプロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="2a3c0-177">モジュールが読み込まれていること、および編集-CsClsScenario が利用可能`Get-Help Edit-CsClsScenario`であることを確認するには、「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="2a3c0-178">すると、EditCsClsScenario の構文の基本的な概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="2a3c0-179">モジュールをアンロードするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-179">To unload the modules, type:</span></span>
    
   ```
   Remove-Module ClsController
   ```

    > [!TIP]
    > <span data-ttu-id="2a3c0-180">モジュールを正常にアンロードすると、Windows PowerShell コマンドプロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="2a3c0-181">モジュールがアンロードされたことを確認`Get-Help Edit-CsClsScenario`するには、「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="2a3c0-182">Windows PowerShell は、コマンドレットのヘルプを検索して失敗します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="2a3c0-183">Edit-ClsController モジュールを使用してシナリオから既存のプロバイダーを削除するには</span><span class="sxs-lookup"><span data-stu-id="2a3c0-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="2a3c0-184">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2a3c0-185">Windows PowerShell で次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-185">From the Windows PowerShell, type:</span></span>
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="2a3c0-186">モジュールの読み込みが成功すると、Windows PowerShell コマンドプロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="2a3c0-187">モジュールが読み込まれていること、および編集-CsClsScenario が利用可能`Get-Help Edit-CsClsScenario`であることを確認するには、「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="2a3c0-188">すると、EditCsClsScenario の構文の基本的な概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="2a3c0-189">AlwaysOn シナリオからプロバイダーを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   <span data-ttu-id="2a3c0-190">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-190">For Example:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   <span data-ttu-id="2a3c0-p117">パラメーター ScenarioName および ProviderName は、位置指定 (コマンド ライン内の指定された位置に定義する必要がある) パラメーターです。コマンドレット名を位置 1 として、シナリオ名が位置 2、プロバイダーが位置 3 にある場合は、パラメーター名を明示的に定義する必要はありません。この情報を使用すると、上記のコマンドは次のように入力できます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-p117">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   <span data-ttu-id="2a3c0-194">パラメーター値の位置の配置は、シナリオとプロバイダーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="2a3c0-195">他のすべてのパラメーターは明示的に定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="2a3c0-196">Edit-ClsController モジュールを使用してシナリオにプロバイダーを追加するには</span><span class="sxs-lookup"><span data-stu-id="2a3c0-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="2a3c0-197">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2a3c0-198">AlwaysOn シナリオにプロバイダーを追加するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    <span data-ttu-id="2a3c0-199">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-199">For Example:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    <span data-ttu-id="2a3c0-200">-Loglevel には、Fatal、Error、Warning、Info、Verbose、Debug、または All を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="2a3c0-201">-Flag は、TF_COMPONENT、TF_DIAG など、プロバイダーがサポートしているフラグのいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="2a3c0-202">-フラグはすべての値にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-202">-Flags can also be of value ALL</span></span>
    
   <span data-ttu-id="2a3c0-p120">上記の例を、コマンドレットの位置指定機能を使用して入力することもできます。たとえば、プロバイダー ChatServer を AlwaysOn シナリオに追加するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2a3c0-p120">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
