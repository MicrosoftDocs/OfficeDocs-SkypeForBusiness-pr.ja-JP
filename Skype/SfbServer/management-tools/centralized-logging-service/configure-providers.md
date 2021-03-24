---
title: Skype for Business Server 2015 で集中ログ サービスのプロバイダーを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: '概要: Skype for Business Server 2015 の集中ログ サービスのシナリオ プロバイダーを構成する方法について説明します。'
ms.openlocfilehash: cd0364d6497aa53d258b5346090d6cdd7c338cc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098853"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="4632d-103">Skype for Business Server 2015 で集中ログ サービスのプロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="4632d-103">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4632d-104">**概要:** Skype for Business Server 2015 の集中ログ サービスのシナリオ プロバイダーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4632d-104">**Summary:** Learn how to configure scenario providers for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4632d-105">集中ログ サービスのプロバイダーの概念と構成は、把握する最も重要な点の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="4632d-105">The concepts and configuration of providers in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="4632d-106">Theproviders は、Skype for Business Server トレース モデルの Skype for Business Server サーバーの役割コンポーネントに直接マップされます。</span><span class="sxs-lookup"><span data-stu-id="4632d-106">Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model.</span></span> <span data-ttu-id="4632d-107">プロバイダーは、追跡される Skype for Business Server 2015 のコンポーネント、収集するメッセージの種類 (致命的、エラー、警告など)、フラグ (TF_Connection や TF_Diag など) を定義します。</span><span class="sxs-lookup"><span data-stu-id="4632d-107">The provider defines the components of a Skype for Business Server 2015 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF_Connection or TF_Diag).</span></span> <span data-ttu-id="4632d-108">プロバイダーは、Skype for Business Server サーバーの各役割の追跡可能なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="4632d-108">Providers are the traceable components in each Skype for Business Server server role.</span></span> <span data-ttu-id="4632d-109">プロバイダーを使用して、コンポーネントに対するトレースのレベルと種類 (S4、SIPStack、IM、プレゼンスなど) を定義します。</span><span class="sxs-lookup"><span data-stu-id="4632d-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="4632d-110">定義済みのプロバイダーは、シナリオの中で特定の問題状況に対応する特定の論理コレクション用のすべてのプロバイダーをグループ化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4632d-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>
  
<span data-ttu-id="4632d-111">Skype for Business Server 管理シェルを使用して集中ログ サービス機能を実行するには、CsAdministrator または CsServerAdministrator 役割ベースのアクセス制御 (RBAC) セキュリティ グループのメンバーか、これら 2 つのグループのいずれかを含むカスタム RBAC 役割である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4632d-111">To run the Centralized Logging Service functions using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="4632d-112">このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割 (自分で作成したカスタム RBAC の役割を含む) の一覧を取得するには、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4632d-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="4632d-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4632d-113">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="4632d-114">このトピックの以下の部分では、プロバイダーの定義方法、プロバイダーの変更方法、およびトラブルシューティングを最適化するためにプロバイダー定義に含まれるものに注目します。</span><span class="sxs-lookup"><span data-stu-id="4632d-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="4632d-115">集中ログ サービス コマンドを発行するには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="4632d-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="4632d-116">既定では、ディレクトリ C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent にある CLSController.exeを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4632d-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span></span> <span data-ttu-id="4632d-117">または、Skype for Business Server 管理シェルを使用して、複数のコマンドWindows PowerShellすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4632d-117">Or, you can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="4632d-118">このWindows PowerShellを使用すると、ログ セッションで使用する新しいプロバイダーを定義し、作成、収集する情報、およびデータを収集するレベルを完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="4632d-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4632d-p104">前述したように、プロバイダーは非常に強力です。ただし、シナリオは、プロバイダーが表すコンポーネントに対するトレースの設定と実行を行うために必要な具体的な情報をすべて含んでいるため、プロバイダーよりも強力です。シナリオとプロバイダーのコレクションは、大まかに言うと、大量の情報を収集する多数のコマンドを含むバッチ ファイルを実行することと、多数のコマンドをコマンド ラインから一度に 1 つずつ発行することに相当します。</span><span class="sxs-lookup"><span data-stu-id="4632d-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span> 
  
<span data-ttu-id="4632d-122">プロバイダーの詳細を深く掘り下げる必要が生じなくても、集中ログ サービスには、既に定義されている多数のシナリオが提供されます。</span><span class="sxs-lookup"><span data-stu-id="4632d-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="4632d-123">用意されているシナリオを使用して、遭遇する可能性がある問題の大部分に対応できます。</span><span class="sxs-lookup"><span data-stu-id="4632d-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="4632d-124">まれに、プロバイダーを定義してシナリオに割り当てなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="4632d-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="4632d-125">新しいプロバイダーとシナリオを作成する必要があるかどうかを考慮する前に、用意されているシナリオを十分に調べることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4632d-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="4632d-126">ここでは、シナリオでのプロバイダー要素の使用によるトレース情報の収集方法を理解するために、プロバイダーの作成に関する情報が提示されていますが、プロバイダーそのものの詳細については説明しません。</span><span class="sxs-lookup"><span data-stu-id="4632d-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span> 
  
<span data-ttu-id="4632d-127">[Skype for Business 2015](centralized-logging-service.md)の集中ログ サービスで導入された、シナリオで使用するプロバイダーを定義する重要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4632d-127">Introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>
  
- <span data-ttu-id="4632d-128">**プロバイダー** OCSLogger に精通している場合、プロバイダーは、トレース エンジンがログを収集する必要がある情報を OCSLogger に伝えるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="4632d-128">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="4632d-129">プロバイダーは同じコンポーネントであり、多くの場合、OCSLogger のコンポーネントと同じ名前を持っています。</span><span class="sxs-lookup"><span data-stu-id="4632d-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="4632d-130">OCSLogger に精通していないプロバイダーは、集中ログ サービスがログを収集できるサーバー役割固有のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="4632d-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="4632d-131">集中ログ サービスの場合、CLSAgent は、プロバイダー構成で定義したコンポーネントのトレースを行う集中ログ サービスのアーキテクチャ部分です。</span><span class="sxs-lookup"><span data-stu-id="4632d-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>
    
- <span data-ttu-id="4632d-132">**ログ レベル** OCSLogger には、収集されたデータの詳細レベルの数を選択するオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4632d-132">**Logging levels** OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="4632d-133">この機能は、集中ログ サービスとシナリオの不可欠な部分であり **、Type** パラメーターによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="4632d-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="4632d-134">次の中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="4632d-134">You can choose from the following:</span></span>
    
  - <span data-ttu-id="4632d-135">**All** 致命的、エラー、警告、詳細、デバッグの種類のトレース メッセージを、定義されたプロバイダーのログに収集します。</span><span class="sxs-lookup"><span data-stu-id="4632d-135">**All** Collects trace messages of type fatal, error, warning, verbose, and debug info to the log for the defined provider.</span></span>
    
  - <span data-ttu-id="4632d-136">**致命的** "Fatal" として定義されたトレース メッセージのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="4632d-136">**Fatal** Collects only the trace messages defined as "Fatal."</span></span>
    
  - <span data-ttu-id="4632d-137">**エラー** "Error" または "Fatal" として定義されたトレース メッセージのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="4632d-137">**Error** Collects only the trace messages defined as "Error" or "Fatal."</span></span>
    
  - <span data-ttu-id="4632d-138">**警告** "Warning"、"Error"、"Fatal" の種類のトレース メッセージのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="4632d-138">**Warning** Collects only the trace messages of type "Warning," "Error" and "Fatal."</span></span>
    
  - <span data-ttu-id="4632d-139">**Info** 定義されたプロバイダーの情報メッセージに加えて、致命的なメッセージ、エラー メッセージ、および警告メッセージを示すトレース メッセージのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="4632d-139">**Info** Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
  - <span data-ttu-id="4632d-140">**Verbose** 定義されたプロバイダーの致命的、エラー、警告、詳細型のすべてのトレース メッセージを収集します。</span><span class="sxs-lookup"><span data-stu-id="4632d-140">**Verbose** Collects all trace messages of type fatal, error, warning and verbose for the defined provider.</span></span>
    
  - <span data-ttu-id="4632d-141">**デバッグ** は、基本的には 'All' と同等です。定義されたプロバイダーの型 Fatal、Error、Warning、Info、Verbose、Debug のトレースを収集します。</span><span class="sxs-lookup"><span data-stu-id="4632d-141">**Debug** this is essentially an equivalent of 'All' - collects traces of type Fatal, Error, Warning, Info, Verbose and Debug for the defined provider.</span></span>
    
- <span data-ttu-id="4632d-142">**フラグ** OCSLogger には、トレース ファイルから取得できる情報の種類を定義した各プロバイダーのフラグを選択するオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4632d-142">**Flags** OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="4632d-143">プロバイダーに基づいて、次のフラグを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4632d-143">You can chose the following flags, based on the provider:</span></span>
    
  - <span data-ttu-id="4632d-144">**TF_Connection** 接続関連のログ エントリを提供します。</span><span class="sxs-lookup"><span data-stu-id="4632d-144">**TF_Connection** Provides connection-related log entries.</span></span> <span data-ttu-id="4632d-145">これらのログには、特定のコンポーネントとの間で確立された接続に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4632d-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="4632d-146">これには、ネットワーク レベルの重要な情報 (つまり、接続の概念のないコンポーネント) も含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4632d-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
  - <span data-ttu-id="4632d-147">**TF_Security** セキュリティに関連するイベント/ログ エントリを提供します。</span><span class="sxs-lookup"><span data-stu-id="4632d-147">**TF_Security** Provides all events/log entries related to security.</span></span> <span data-ttu-id="4632d-148">たとえば、SipStack の場合、これらはドメイン検証エラー、クライアント認証/承認エラーなどのセキュリティ イベントです。</span><span class="sxs-lookup"><span data-stu-id="4632d-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
  - <span data-ttu-id="4632d-149">**TF_Diag** コンポーネントの診断またはトラブルシューティングに使用できる診断イベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="4632d-149">**TF_Diag** Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="4632d-150">たとえば、SipStack の場合、これらは証明書の障害、または DNS の警告/エラーです。</span><span class="sxs-lookup"><span data-stu-id="4632d-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
  - <span data-ttu-id="4632d-151">**TF_Protocol** SIP メッセージや複合コミュニティ コーデック パック メッセージなどのプロトコル メッセージを提供します。</span><span class="sxs-lookup"><span data-stu-id="4632d-151">**TF_Protocol** Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
  - <span data-ttu-id="4632d-152">**TF_Component** プロバイダーの一部として指定されたコンポーネントのログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4632d-152">**TF_Component** Enables logging on the components specified as part of the providers.</span></span>
    
  - <span data-ttu-id="4632d-153">**All** プロバイダーで使用可能なすべてのフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="4632d-153">**All** Sets all available flags available for the provider.</span></span>
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="4632d-154">既存の集中ログ サービス シナリオ プロバイダーに関する情報を確認するには</span><span class="sxs-lookup"><span data-stu-id="4632d-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1. <span data-ttu-id="4632d-155">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4632d-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4632d-156">既存のプロバイダーの構成をレビューするには、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="4632d-156">To review the configuration of existing providers, type the following:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    <span data-ttu-id="4632d-157">たとえば、グローバル会議アテンダントに関する情報をレビューするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4632d-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    <span data-ttu-id="4632d-158">このコマンドは、関連するフラグ、設定、およびコンポーネントと共にプロバイダーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="4632d-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="4632d-159">表示される情報 Windows PowerShellが足りない場合や、既定のリスト形式でリストが長すぎる場合は、別の出力方法を定義して追加情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4632d-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="4632d-160">これを行うには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4632d-160">To do this, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    <span data-ttu-id="4632d-161">このコマンドの出力では、各プロバイダーを行分割形式で表示します。プロバイダー名、ログの種類、ログ レベル、フラグ、GUID、および役割が行ごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4632d-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span> 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="4632d-162">新しい集中ログ サービス シナリオ プロバイダーを定義するには</span><span class="sxs-lookup"><span data-stu-id="4632d-162">To define a new Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="4632d-163">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4632d-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4632d-p113">シナリオ プロバイダーは、トレースするコンポーネント、使用するフラグ、および収集する詳細レベルで構成されます。これは実行するには次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4632d-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    <span data-ttu-id="4632d-166">たとえば、Lyss プロバイダーから収集する内容および詳細レベルを定義するトレース プロバイダー定義は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4632d-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

<span data-ttu-id="4632d-167">-Level は、致命的、エラー、警告、および情報メッセージを収集します。</span><span class="sxs-lookup"><span data-stu-id="4632d-167">The -Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="4632d-168">使用されるフラグは、Lyss プロバイダー用に定義されたフラグのすべてであり、TF_Connection、TF_Diag、TF_Protocol が含まれます。変数 $LyssProvider を定義した後 **、New-CsClsScenario** コマンドレットと一緒に使用して、Lyss プロバイダーからトレースを収集できます。</span><span class="sxs-lookup"><span data-stu-id="4632d-168">The flags used are all of those defined for the Lyss provider, and include TF_Connection, TF_Diag and TF_Protocol.After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="4632d-169">このプロバイダーの作成と新しいシナリオへの割り当てを完了するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4632d-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

<span data-ttu-id="4632d-170">$LyssProvider は、**New-CsClsProvider** で作成された定義済みのシナリオを含む変数です。</span><span class="sxs-lookup"><span data-stu-id="4632d-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="4632d-171">既存の集中ログ サービス シナリオ プロバイダーを変更するには</span><span class="sxs-lookup"><span data-stu-id="4632d-171">To change an existing Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="4632d-172">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4632d-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4632d-173">既存のプロバイダーの構成を更新または変更するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4632d-173">To update or change the configuration of an existing provider, type:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    <span data-ttu-id="4632d-174">次のように入力することで、プロバイダーを割り当てるシナリオを更新します。</span><span class="sxs-lookup"><span data-stu-id="4632d-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

<span data-ttu-id="4632d-175">コマンドを実行すると、最終的にシナリオ site:Redmond/RedmondLyssInfo のフラグと割り当てられるプロバイダーのレベルが更新されます。</span><span class="sxs-lookup"><span data-stu-id="4632d-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="4632d-176">Get-CsClsScenario を使用して、新しいシナリオを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4632d-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="4632d-177">詳細については、「[Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4632d-177">For details, see [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span>
> [!CAUTION]
> <span data-ttu-id="4632d-178">**New-ClsCsProvider** は、フラグが有効かどうかを確認しません。</span><span class="sxs-lookup"><span data-stu-id="4632d-178">**New-ClsCsProvider** does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="4632d-179">フラグのスペル (TF_DIAG や TF_CONNECTION など) が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4632d-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="4632d-180">フラグのスペルが正しくない場合、プロバイダーは期待されるログ情報を返すことができません。</span><span class="sxs-lookup"><span data-stu-id="4632d-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>
  
<span data-ttu-id="4632d-181">このシナリオに対してプロバイダーを追加するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4632d-181">If you want to add additional providers to this scenario, type the following:</span></span>

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

<span data-ttu-id="4632d-182">Add ディレクティブで定義される各プロバイダーは、**New-CsClsProvider** プロセスで既に定義されています。</span><span class="sxs-lookup"><span data-stu-id="4632d-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>
### <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="4632d-183">シナリオ プロバイダーを削除するには</span><span class="sxs-lookup"><span data-stu-id="4632d-183">To remove a scenario provider</span></span>

1. <span data-ttu-id="4632d-184">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4632d-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4632d-185">用意されているコマンドレットを使用して、既存のプロバイダーの更新と新しいプロバイダーの作成を実行できます。</span><span class="sxs-lookup"><span data-stu-id="4632d-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="4632d-186">プロバイダーを削除するには、**Set-CsClsScenario** に対して Provider パラメーター用の Replace ディレクティブを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4632d-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="4632d-187">プロバイダーを完全に削除する唯一の方法は、Update ディレクティブを使用して、削除するプロバイダーを、再定義した同じ名前のプロバイダーに置き換えることです。</span><span class="sxs-lookup"><span data-stu-id="4632d-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="4632d-188">たとえば、プロバイダー LyssProvider は、ログの種類として WPP、レベルとして Debug、およびフラグとして TF_CONNECTION と TF_DIAG が定義されています。</span><span class="sxs-lookup"><span data-stu-id="4632d-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF_CONNECTION and TF_DIAG.</span></span> <span data-ttu-id="4632d-189">フラグを "All" に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4632d-189">You need to change the flags to "All".</span></span> <span data-ttu-id="4632d-190">このプロバイダーを変更するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4632d-190">To change the provider, type the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. <span data-ttu-id="4632d-191">シナリオとそれに関連付けられているプロバイダーを完全に削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4632d-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    <span data-ttu-id="4632d-192">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4632d-192">For example:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > <span data-ttu-id="4632d-193">**Remove-CsClsScenario** コマンドレットは、確認のプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="4632d-193">The cmdlet **Remove-CsClsScenario** does not prompt you for confirmation.</span></span> <span data-ttu-id="4632d-194">シナリオは、それに関連付けられているプロバイダーと共に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4632d-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="4632d-195">シナリオを初めて作成したときに使用したコマンドを再実行することで、シナリオを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="4632d-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="4632d-196">削除したシナリオまたはプロバイダーを回復するための手順はありません。</span><span class="sxs-lookup"><span data-stu-id="4632d-196">There is no procedure to recover removed scenarios or providers.</span></span>
  
<span data-ttu-id="4632d-197">**Remove-CsClsScenario** コマンドレットを使用してシナリオを削除すると、シナリオはスコープから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4632d-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="4632d-198">作成したシナリオとシナリオの一部であったプロバイダーを使用するには、新しいプロバイダーを作成し、それらを新しいシナリオに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4632d-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>
## <a name="see-also"></a><span data-ttu-id="4632d-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="4632d-199">See also</span></span>

[<span data-ttu-id="4632d-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="4632d-200">Get-CsClsScenario</span></span>](/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="4632d-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="4632d-201">New-CsClsScenario</span></span>](/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="4632d-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="4632d-202">Remove-CsClsScenario</span></span>](/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="4632d-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="4632d-203">Set-CsClsScenario</span></span>](/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="4632d-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="4632d-204">New-CsClsProvider</span></span>](/powershell/module/skype/new-csclsprovider?view=skype-ps)