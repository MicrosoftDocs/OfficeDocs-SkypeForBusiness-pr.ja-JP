---
title: Skype for Business Server 2015 での集中ログ サービスのシナリオの構成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: '概要: は、作成、変更、およびビジネス サーバー 2015 の Skype で集中ログ サービスのシナリオを削除する方法を説明します。'
ms.openlocfilehash: e80324d4228aec503c887927459e42188741837f
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373931"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="d2929-103">Skype for Business Server 2015 での集中ログ サービスのシナリオの構成</span><span class="sxs-lookup"><span data-stu-id="d2929-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d2929-104">**の概要:** 作成、変更、およびビジネス サーバー 2015 の Skype で集中ログ サービスのシナリオを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d2929-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d2929-105">シナリオが (つまり、グローバル、サイト、プール、またはコンピューター) のスコープを定義し、一元的なログ サービスで使用するには、どのようなプロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="d2929-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="d2929-106">シナリオを使用して、プロバイダー (S4、SIPStack、IM、プレゼンスなど) のトレースを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="d2929-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="d2929-107">シナリオを構成することで、特定の問題の条件に対応する特定の論理コレクションのすべてのプロバイダーをグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="d2929-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="d2929-108">シナリオのトラブルシューティングとログのニーズを満たすために変更する必要がある場合は、ビジネスのサーバー 2015 のデバッグ ツールの Skype に関数の namedEdit CsClsScenario を含む ClsScenarioEdit.psm1 をという名前の Windows PowerShell モジュールが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d2929-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="d2929-109">このモジュールの目的は、指定したシナリオのプロパティを編集することです。</span><span class="sxs-lookup"><span data-stu-id="d2929-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="d2929-110">このトピックでは、このモジュールの使用方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="d2929-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="d2929-111">ビジネス サーバー 2015[のデバッグ ツール](https://go.microsoft.com/fwlink/p/?LinkId=285257)のいずれかに入る前に、Skype をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d2929-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d2929-112">どのスコープ (サイト、グローバル、プール、またはコンピューター) でも、一度に最大で 2 つのシナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d2929-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="d2929-113">シナリオで実行されているを確認するのには、Windows PowerShell と[Get CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)を使用します。</span><span class="sxs-lookup"><span data-stu-id="d2929-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="d2929-114">Windows PowerShell と[セット CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)を使用すると、どのシナリオを実行している動的に変更できます。</span><span class="sxs-lookup"><span data-stu-id="d2929-114">By using Windows PowerShell and [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="d2929-115">ログ セッション中に実行するシナリオを変更して、収集するデータや収集元のプロバイダーを変更または微調整することができます。</span><span class="sxs-lookup"><span data-stu-id="d2929-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="d2929-116">ビジネス サーバー管理シェルには、Skype を使用して、ログ サービスの集中管理機能を実行するには、CsAdministrator または CsServerAdministrator の役割に基づくアクセス制御 (RBAC) セキュリティ グループ、またはカスタムの RBAC の役割のいずれかのメンバーをする必要がありますがこれら 2 つのグループのいずれかが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d2929-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="d2929-117">すべての RBAC のリストを返すため、このコマンドレットに割り当てられているなど、自分で作成したカスタムの RBAC の役割の役割がビジネス サーバー管理シェルまたは Windows PowerShell プロンプトの Skype から次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d2929-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="d2929-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d2929-118">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="d2929-119">このトピックの以降の部分では、トラブルシューティングを最適化するためのシナリオの定義、シナリオの変更、実行中のシナリオの取得、シナリオの削除、シナリオ内容の指定の方法を中心に説明します。</span><span class="sxs-lookup"><span data-stu-id="d2929-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="d2929-120">ビジネス サーバー管理シェルの Skype を使用するには Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d2929-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="d2929-121">Windows PowerShell を使用する場合は、ログ ・ セッションで使用するための新しいシナリオを定義できます。</span><span class="sxs-lookup"><span data-stu-id="d2929-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="d2929-122">、[ビジネス 2015年の Skype のログ サービスの一元管理](centralized-logging-service.md)の導入シナリオの要素は。</span><span class="sxs-lookup"><span data-stu-id="d2929-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="d2929-123">**プロバイダー**OCSLogger を理解する場合は、プロバイダーはトレース エンジンからのログを収集する必要があります OCSLogger を確認する選択したコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="d2929-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="d2929-124">プロバイダーは、同じコンポーネントし、多くの場合 OCSLogger で、コンポーネントと同じ名前があります。</span><span class="sxs-lookup"><span data-stu-id="d2929-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="d2929-125">プロバイダー サーバーの役割の特定のコンポーネントは、OCSLogger に慣れていない場合は、集中ログ サービスを収集できますからログに記録します。</span><span class="sxs-lookup"><span data-stu-id="d2929-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="d2929-126">プロバイダーの構成に関する詳細については、[集中ログ サービスの Skype ビジネス サーバー 2015 の構成プロバイダー](configure-providers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2929-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="d2929-127">**識別情報**パラメーターの識別情報は、シナリオの名前とスコープを設定します。</span><span class="sxs-lookup"><span data-stu-id="d2929-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="d2929-128">などでした「グローバル」のスコープを設定して"LyssServiceScenario"を使用してシナリオを識別します。</span><span class="sxs-lookup"><span data-stu-id="d2929-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="d2929-129">Id を定義する 2 つを組み合わせると、(たとえば、「LyssServiceScenario/グローバル」)。</span><span class="sxs-lookup"><span data-stu-id="d2929-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="d2929-130">必要に応じて、使用することができます-名前と親のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="d2929-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="d2929-131">Name パラメーターは、シナリオを一意に識別するために定義します。</span><span class="sxs-lookup"><span data-stu-id="d2929-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="d2929-132">Name を使用する場合は、Parent も使用して、グローバルまたはサイトにシナリオを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2929-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="d2929-133">名前と親のパラメーターを使用する場合は使用できません、 **・ アイデンティティ**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="d2929-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="d2929-134">New-CsClsScenario コマンドレットを使用して新しいシナリオを作成するには</span><span class="sxs-lookup"><span data-stu-id="d2929-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="d2929-135">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2929-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d2929-136">ログ セッションの新しいシナリオを作成するに[新規 CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)を使用し、(は、どのようにそれは一意に識別される) のシナリオの名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="d2929-136">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="d2929-137">WPP (つまり、Windows のソフトウェア トレース プリプロセッサは、既定値)、イベント ログ (つまり、Windows イベント ログの形式で) または IISLog のログ出力形式の種類を選択 (つまり、ASCII 形式のファイルに基づいて、IIS ログ ファイル形式)。</span><span class="sxs-lookup"><span data-stu-id="d2929-137">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="d2929-138">次に、定義、定義されているログ出力レベル] の下の「)、レベルとフラグ (このトピックでは、フラグ下で定義されている)。</span><span class="sxs-lookup"><span data-stu-id="d2929-138">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="d2929-139">このシナリオ例では、プロバイダー変数の例として LyssProvider を使用します。</span><span class="sxs-lookup"><span data-stu-id="d2929-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="d2929-140">定義されたオプションを使用してシナリオを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2929-140">To create a scenario using the options defined, type:</span></span>
    
   ```
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    <span data-ttu-id="d2929-141">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d2929-141">For example:</span></span>
    
   ```
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    <span data-ttu-id="d2929-142">他の形式名と親の使用します。</span><span class="sxs-lookup"><span data-stu-id="d2929-142">The alternate format using -Name and -Parent:</span></span>
    
   ```
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="d2929-143">複数のプロバイダーを指定した新しいシナリオを New-CsClsScenario コマンドレットを使用して作成するには</span><span class="sxs-lookup"><span data-stu-id="d2929-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="d2929-144">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2929-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d2929-145">スコープごとのシナリオ数は 2 つまでに制限されています。</span><span class="sxs-lookup"><span data-stu-id="d2929-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="d2929-146">しかし、設定するプロバイダーの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="d2929-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="d2929-147">この例では、3 つのプロバイダーを作成済みで、定義するシナリオに 3 つのプロバイダーをすべて割り当てる必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="d2929-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="d2929-148">プロバイダー変数の名前は LyssProvider、ABServerProvider、および SIPStackProvider です。</span><span class="sxs-lookup"><span data-stu-id="d2929-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="d2929-149">定義し、シナリオに複数のプロバイダーを割り当てるするには、ビジネスのサーバー管理シェルまたは Windows PowerShell コマンド プロンプトで、Skype で次を入力します。</span><span class="sxs-lookup"><span data-stu-id="d2929-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
   ```
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > <span data-ttu-id="d2929-150">Windows PowerShell を使用して値のハッシュ テーブルを作成するための規則で認識されている`@{<variable>=<value1>, <value2>, <value>…}`assplatting と呼びます。</span><span class="sxs-lookup"><span data-stu-id="d2929-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="d2929-151">Windows PowerShell のスプラッティング技法に関する詳細についてを参照してください[https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)。</span><span class="sxs-lookup"><span data-stu-id="d2929-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="d2929-152">Set-CsClsScenario コマンドレットを使用して既存のシナリオを変更するには</span><span class="sxs-lookup"><span data-stu-id="d2929-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="d2929-153">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2929-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d2929-154">スコープごとのシナリオ数は 2 つまでに制限されています。</span><span class="sxs-lookup"><span data-stu-id="d2929-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="d2929-155">実行するシナリオは、ログ キャプチャ セッションの実行中を含め、いつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="d2929-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="d2929-156">実行するシナリオを再定義すると、現在のログ セッションは削除されたシナリオの使用を停止し、新しいシナリオの使用を開始します。</span><span class="sxs-lookup"><span data-stu-id="d2929-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="d2929-157">ただし、削除されたシナリオでキャプチャされたログ情報はキャプチャされたログに残ります。</span><span class="sxs-lookup"><span data-stu-id="d2929-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="d2929-158">新しいシナリオを定義する (つまり、"S4Provider"という名前の定義済みのプロバイダーの追加を想定して)、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d2929-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    <span data-ttu-id="d2929-159">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d2929-159">For example:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    <span data-ttu-id="d2929-p112">プロバイダーを置き換える場合は、現在のセットと置き換える単一のプロバイダーか、プロバイダーのコンマ区切りリストを定義します。多数のプロバイダーのうち 1 つだけを置き換える場合は、現在のプロバイダーに新しいプロバイダーを追加して、新しいプロバイダーと既存のプロバイダーの両方を含む新しいプロバイダーのセットを作成します。すべてのプロバイダーを新しいセットで置き換える場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2929-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    <span data-ttu-id="d2929-163">たとえば、現在の $LyssProvider、$ABServerProvider、および $SIPStackProvider のセットを $LyssServiceProvider に置き換えるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2929-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    <span data-ttu-id="d2929-164">現在の $LyssProvider、$ABServerProvider、および $SIPStackProvider のセットのうち、$LyssProvider プロバイダーだけを $LyssServiceProvider に置き換えるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2929-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="d2929-165">Remove-CsClsScenario コマンドレットを使用して既存のシナリオを削除するには</span><span class="sxs-lookup"><span data-stu-id="d2929-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="d2929-166">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2929-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d2929-167">定義済みのシナリオを削除する場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2929-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
   ```
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    <span data-ttu-id="d2929-168">たとえば、定義済みのシナリオ site:Redmond/LyssServiceScenario を削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d2929-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

<span data-ttu-id="d2929-169">**削除 CsClsScenario**コマンドレットには、指定したシナリオが削除されますが、ログを検索するには、キャプチャされたトレースが利用できます。</span><span class="sxs-lookup"><span data-stu-id="d2929-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="d2929-170">ClsScenarioEdit.psm1 モジュールを使用して Edit-CsClsScenario コマンドレットをロードおよびアンロードするには</span><span class="sxs-lookup"><span data-stu-id="d2929-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="d2929-171">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2929-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d2929-172">ClsScenarioEdit.psm1 モジュールは個別の Web ダウンロードとして提供されます。</span><span class="sxs-lookup"><span data-stu-id="d2929-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="d2929-173">モジュールは、ビジネス サーバー 2015 のデバッグ ツールの Skype の一部です。</span><span class="sxs-lookup"><span data-stu-id="d2929-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="d2929-174">既定では、デバッグ ツールは C:\Program Files\Skype for Business Server 2015\Debugging Tools ディレクトリにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d2929-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="d2929-175">Windows PowerShell で、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2929-175">From the Windows PowerShell, type:</span></span>
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="d2929-176">モジュールの読み込みが成功では、Windows PowerShell コマンド プロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="d2929-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="d2929-177">モジュールが読み込まれ、編集 CsClsScenario が利用できることを確認するには、次のように入力します。 `Get-Help Edit-CsClsScenario`。</span><span class="sxs-lookup"><span data-stu-id="d2929-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="d2929-178">すると、EditCsClsScenario の構文の基本的な概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2929-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="d2929-179">モジュールをアンロードするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2929-179">To unload the modules, type:</span></span>
    
   ```
   Remove-Module ClsController
   ```

    > [!TIP]
    > <span data-ttu-id="d2929-180">成功のアンロード モジュールを返しますする Windows PowerShell コマンド プロンプトにします。</span><span class="sxs-lookup"><span data-stu-id="d2929-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="d2929-181">モジュールが読み込まれていることを確認するには、次のように入力します。 `Get-Help Edit-CsClsScenario`。</span><span class="sxs-lookup"><span data-stu-id="d2929-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="d2929-182">Windows PowerShell コマンドレットのヘルプを検索し、失敗を試みます。</span><span class="sxs-lookup"><span data-stu-id="d2929-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="d2929-183">Edit-ClsController モジュールを使用してシナリオから既存のプロバイダーを削除するには</span><span class="sxs-lookup"><span data-stu-id="d2929-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="d2929-184">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2929-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d2929-185">Windows PowerShell で、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2929-185">From the Windows PowerShell, type:</span></span>
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="d2929-186">モジュールの読み込みが成功では、Windows PowerShell コマンド プロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="d2929-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="d2929-187">モジュールが読み込まれ、編集 CsClsScenario が利用できることを確認するには、次のように入力します。 `Get-Help Edit-CsClsScenario`。</span><span class="sxs-lookup"><span data-stu-id="d2929-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="d2929-188">すると、EditCsClsScenario の構文の基本的な概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2929-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="d2929-189">AlwaysOn シナリオからプロバイダーを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2929-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   <span data-ttu-id="d2929-190">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d2929-190">For Example:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   <span data-ttu-id="d2929-p117">パラメーター ScenarioName および ProviderName は、位置指定 (コマンド ライン内の指定された位置に定義する必要がある) パラメーターです。コマンドレット名を位置 1 として、シナリオ名が位置 2、プロバイダーが位置 3 にある場合は、パラメーター名を明示的に定義する必要はありません。この情報を使用すると、上記のコマンドは次のように入力できます。</span><span class="sxs-lookup"><span data-stu-id="d2929-p117">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   <span data-ttu-id="d2929-194">パラメーターの値の位置で配置することにのみ適用されます - シナリオとプロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="d2929-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="d2929-195">他のすべてのパラメーターは明示的に定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2929-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="d2929-196">Edit-ClsController モジュールを使用してシナリオにプロバイダーを追加するには</span><span class="sxs-lookup"><span data-stu-id="d2929-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="d2929-197">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2929-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d2929-198">AlwaysOn シナリオにプロバイダーを追加するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2929-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    <span data-ttu-id="d2929-199">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d2929-199">For Example:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    <span data-ttu-id="d2929-200">-Loglevel には、Fatal、Error、Warning、Info、Verbose、Debug、または All を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d2929-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="d2929-201">フラグには、TF_COMPONENT、TF_DIAG など、プロバイダーがサポートするためのフラグのいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d2929-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="d2929-202">フラグことができますのすべての値</span><span class="sxs-lookup"><span data-stu-id="d2929-202">-Flags can also be of value ALL</span></span>
    
   <span data-ttu-id="d2929-p120">上記の例を、コマンドレットの位置指定機能を使用して入力することもできます。たとえば、プロバイダー ChatServer を AlwaysOn シナリオに追加するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2929-p120">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```