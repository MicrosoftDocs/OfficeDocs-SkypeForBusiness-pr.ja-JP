---
title: 'Lync Server 2013: 集中ログサービス用のプロバイダーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51dbb8c1a2e24290e4ab2805bed191e5f2dc86bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="5b214-102">Lync Server 2013 での集中ログサービスのプロバイダーの構成</span><span class="sxs-lookup"><span data-stu-id="5b214-102">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b214-103">_**トピックの最終更新日:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="5b214-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="5b214-104">集中ログサービスの*プロバイダー*の概念と構成は、把握しておくべき最も重要なものの1つです。</span><span class="sxs-lookup"><span data-stu-id="5b214-104">The concepts and configuration of *providers* in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="5b214-105">*プロバイダー*は、lync server トレースモデルの lync server サーバーロールコンポーネントに直接マップされます。</span><span class="sxs-lookup"><span data-stu-id="5b214-105">The *providers* map directly to Lync Server server role components in the Lync Server tracing model.</span></span> <span data-ttu-id="5b214-106">プロバイダーは、追跡される Lync Server 2013 のコンポーネント、収集するメッセージの種類 (致命的、エラー、警告など)、およびフラグ (たとえば、TF\_Connection または tf\_Diag) を定義します。</span><span class="sxs-lookup"><span data-stu-id="5b214-106">The provider defines the components of a Lync Server 2013 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF\_Connection or TF\_Diag).</span></span> <span data-ttu-id="5b214-107">プロバイダーは、各 Lync Server サーバーの役割で追跡可能なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="5b214-107">Providers are the traceable components in each Lync Server server role.</span></span> <span data-ttu-id="5b214-108">プロバイダーを使用して、コンポーネントに対するトレースのレベルと種類 (S4、SIPStack、IM、プレゼンスなど) を定義します。</span><span class="sxs-lookup"><span data-stu-id="5b214-108">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="5b214-109">定義済みのプロバイダーは、シナリオの中で特定の問題状況に対応する特定の論理コレクション用のすべてのプロバイダーをグループ化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5b214-109">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>

<span data-ttu-id="5b214-110">Lync Server 管理シェルを使用して集中ログサービスの機能を実行するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、またはのいずれかを含むカスタム RBAC の役割を持っている必要があります。これら2つのグループ。</span><span class="sxs-lookup"><span data-stu-id="5b214-110">To run the Centralized Logging Service functions using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="5b214-111">このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自分で作成したカスタムの RBAC の役割を含む) を戻すには、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b214-111">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="5b214-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5b214-112">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="5b214-113">このトピックの以下の部分では、プロバイダーの定義方法、プロバイダーの変更方法、およびトラブルシューティングを最適化するためにプロバイダー定義に含まれるものに注目します。</span><span class="sxs-lookup"><span data-stu-id="5b214-113">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="5b214-114">集中ログサービスのコマンドを発行するには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="5b214-114">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="5b214-115">既定で\\は、フォルダー C: Program Files\\Common Files\\Microsoft Lync Server 2013\\clscontroller にある clscontroller を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5b214-115">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="5b214-116">または、Lync Server 管理シェルを使用して、Windows PowerShell コマンドを発行することもできます。</span><span class="sxs-lookup"><span data-stu-id="5b214-116">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="5b214-117">この 2 つの方法の重要な相違点は、CLSController.exe をコマンド ラインで使用する場合は、使用できるシナリオに限りがあり (プロバイダーが既に定義されたシナリオから選択)、プロバイダーを変更することはできませんが、ログ レベルは定義できます。</span><span class="sxs-lookup"><span data-stu-id="5b214-117">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available in which the providers are already defined and are not changeable, but you can define the log level.</span></span> <span data-ttu-id="5b214-118">Windows PowerShell を使用すると、ログセッションで使用するために新しいプロバイダーを定義し、作成、収集内容、データを収集するレベルなどを詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="5b214-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="5b214-p104">前述したように、プロバイダーは非常に強力です。ただし、シナリオは、プロバイダーが表すコンポーネントに対するトレースの設定と実行を行うために必要な具体的な情報をすべて含んでいるため、プロバイダーよりも強力です。シナリオとプロバイダーのコレクションは、大まかに言うと、大量の情報を収集する多数のコマンドを含むバッチ ファイルを実行することと、多数のコマンドをコマンド ラインから一度に 1 つずつ発行することに相当します。</span><span class="sxs-lookup"><span data-stu-id="5b214-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span><BR><span data-ttu-id="5b214-122">プロバイダーの詳細を深く掘り下げて把握する必要はありませんが、集中ログサービスでは、既に定義されているいくつかのシナリオが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5b214-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="5b214-123">用意されているシナリオを使用して、遭遇する可能性がある問題の大部分に対応できます。</span><span class="sxs-lookup"><span data-stu-id="5b214-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="5b214-124">まれに、プロバイダーを定義してシナリオに割り当てなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5b214-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="5b214-125">新しいプロバイダーとシナリオを作成する必要があるかどうかを考慮する前に、用意されているシナリオを十分に調べることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5b214-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="5b214-126">ここでは、シナリオでのプロバイダー要素の使用によるトレース情報の収集方法を理解するために、プロバイダーの作成に関する情報が提示されていますが、プロバイダーそのものの詳細については説明しません。</span><span class="sxs-lookup"><span data-stu-id="5b214-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span>



</div>

<span data-ttu-id="5b214-127">[Lync Server 2013 の集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)では、シナリオで使用するプロバイダーを定義する主な要素として、次の要素を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="5b214-127">Introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>

  - <span data-ttu-id="5b214-128">**プロバイダー**   ocslogger を熟知している場合、プロバイダーは、トレースエンジンがログを収集する内容を ocslogger に通知するために選択するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="5b214-128">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="5b214-129">プロバイダーは同じコンポーネントで、多くの場合、OCSLogger のコンポーネントと同じ名前になります。</span><span class="sxs-lookup"><span data-stu-id="5b214-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="5b214-130">OCSLogger を使い慣れていない場合、プロバイダーは、集中ログサービスがログを収集できる、サーバーロール固有のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="5b214-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="5b214-131">集中ログサービスの場合、CLSAgent は、プロバイダ構成で定義したコンポーネントのトレースを実行している、集中ログサービスのアーキテクチャ部分です。</span><span class="sxs-lookup"><span data-stu-id="5b214-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>

  - <span data-ttu-id="5b214-132">**Logging levels**   ocslogger では、収集されるデータの詳細レベルの数を選択するオプションが提供されています。</span><span class="sxs-lookup"><span data-stu-id="5b214-132">**Logging levels**   OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="5b214-133">この機能は、集中ログサービスとシナリオの重要な部分であり、 **Type**パラメーターで定義されています。</span><span class="sxs-lookup"><span data-stu-id="5b214-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="5b214-134">次のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5b214-134">You can choose from the following:</span></span>
    
      - <span data-ttu-id="5b214-135">**All**   は、指定されたプロバイダーのログに、致命的、エラー、警告、および情報の種類のトレースメッセージを収集します。</span><span class="sxs-lookup"><span data-stu-id="5b214-135">**All**   Collects trace messages of type fatal, error, warning, and info to the log for the defined provider.</span></span>
    
      - <span data-ttu-id="5b214-136">**Fatal**   定義されたプロバイダーの障害を示すトレースメッセージのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="5b214-136">**Fatal**   Collects only the trace messages that indicate a failure for the defined provider.</span></span>
    
      - <span data-ttu-id="5b214-137">**エラー**   は、定義されたプロバイダーのエラーと致命的なメッセージを示すトレースメッセージのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="5b214-137">**Error**   Collects only the trace messages that indicate an error for the defined provider, plus fatal messages.</span></span>
    
      - <span data-ttu-id="5b214-138">**Warning**   定義済みのプロバイダーについての警告に加えて、致命的なメッセージとエラーメッセージを示すトレースメッセージのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="5b214-138">**Warning**   Collects only the trace messages that indicate a warning for the defined provider, plus fatal and error messages.</span></span>
    
      - <span data-ttu-id="5b214-139">**Info**   : 定義済みのプロバイダーの情報メッセージに加え、致命的、エラー、および警告メッセージを示すトレースメッセージのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="5b214-139">**Info**   Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
      - <span data-ttu-id="5b214-140">**Verbose**   : 定義済みのプロバイダーについて、種類が fatal、error、warning、info のすべてのトレースメッセージを収集します。</span><span class="sxs-lookup"><span data-stu-id="5b214-140">**Verbose**   Collects all trace messages of type fatal, error, warning and info for the defined provider.</span></span>

  - <span data-ttu-id="5b214-141">**Flags**   ocslogger では、トレースファイルから取得できる情報の種類を定義した各プロバイダーのフラグを選択するオプションが提供されていました。</span><span class="sxs-lookup"><span data-stu-id="5b214-141">**Flags**   OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="5b214-142">プロバイダーに基づいて、次のフラグを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5b214-142">You can chose the following flags, based on the provider:</span></span>
    
      - <span data-ttu-id="5b214-143">**TF\_connection**   は、接続に関連するログエントリを提供します。</span><span class="sxs-lookup"><span data-stu-id="5b214-143">**TF\_Connection**   Provides connection-related log entries.</span></span> <span data-ttu-id="5b214-144">これらのログには、特定のコンポーネントとの間で確立された接続に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5b214-144">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="5b214-145">これには、ネットワークレベルの重要な情報 (接続の概念を持たないコンポーネント) が含まれることもあります。</span><span class="sxs-lookup"><span data-stu-id="5b214-145">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
      - <span data-ttu-id="5b214-146">**TF\_security**   には、セキュリティに関連するすべてのイベント/ログエントリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5b214-146">**TF\_Security**   Provides all events/log entries related to security.</span></span> <span data-ttu-id="5b214-147">たとえば、SipStack の場合、これらはドメイン検証エラーなどのセキュリティイベント、およびクライアント認証/承認エラーです。</span><span class="sxs-lookup"><span data-stu-id="5b214-147">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
      - <span data-ttu-id="5b214-148">**TF\_Diag**   には、コンポーネントの診断またはトラブルシューティングに使用できる診断イベントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5b214-148">**TF\_Diag**   Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="5b214-149">たとえば、SipStack の場合は、証明書が失敗したか、DNS の警告/エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5b214-149">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
      - <span data-ttu-id="5b214-150">**TF\_プロトコル**   は、SIP、組み合わせたコミュニティコーデックパックメッセージなどのプロトコルメッセージを提供します。</span><span class="sxs-lookup"><span data-stu-id="5b214-150">**TF\_Protocol**   Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
      - <span data-ttu-id="5b214-151">**TF\_コンポーネント**   は、プロバイダーの一部として指定されたコンポーネントのログ記録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5b214-151">**TF\_Component**   Enables logging on the components specified as part of the providers.</span></span>
    
      - <span data-ttu-id="5b214-152">**すべて**   の使用可能なフラグをプロバイダーが使用できるように設定します。</span><span class="sxs-lookup"><span data-stu-id="5b214-152">**All**   Sets all available flags available for the provider.</span></span>

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="5b214-153">既存の集中ログサービスシナリオプロバイダーに関する情報を確認するには</span><span class="sxs-lookup"><span data-stu-id="5b214-153">To review information about existing Centralized Logging Service scenario providers</span></span>

1.  <span data-ttu-id="5b214-154">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b214-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5b214-155">既存のプロバイダーの構成をレビューするには、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="5b214-155">To review the configuration of existing providers, type the following:</span></span>
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    <span data-ttu-id="5b214-156">たとえば、グローバル会議アテンダントに関する情報をレビューするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5b214-156">For example, to review information about the global conferencing attendant, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA"
    
    <span data-ttu-id="5b214-157">このコマンドは、関連するフラグ、設定、およびコンポーネントと共にプロバイダーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="5b214-157">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="5b214-158">表示されている情報が不足している場合や、既定の Windows PowerShell リスト形式でリストが長すぎる場合は、別の出力メソッドを定義することで追加情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5b214-158">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="5b214-159">これを行うには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5b214-159">To do this, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    <span data-ttu-id="5b214-160">このコマンドの出力では、各プロバイダーを行分割形式で表示します。プロバイダー名、ログの種類、ログ レベル、フラグ、GUID、および役割が行ごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b214-160">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span>

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="5b214-161">新しい集中ログサービスシナリオプロバイダーを定義するには</span><span class="sxs-lookup"><span data-stu-id="5b214-161">To define a new Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="5b214-162">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b214-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5b214-p113">シナリオ プロバイダーは、トレースするコンポーネント、使用するフラグ、および収集する詳細レベルで構成されます。これは実行するには次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5b214-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    <span data-ttu-id="5b214-165">たとえば、Lyss プロバイダーから収集する内容および詳細レベルを定義するトレース プロバイダー定義は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5b214-165">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

<span data-ttu-id="5b214-166">–Level は、重大、エラー、警告、および情報メッセージを収集します。</span><span class="sxs-lookup"><span data-stu-id="5b214-166">The –Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="5b214-167">使用されるフラグは、一からの Ss プロバイダーに対して定義され\_ているもの\_で、tf\_Connection、tf Diag、tf プロトコルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b214-167">The flags used are all of those defined for the Lyss provider, and include TF\_Connection, TF\_Diag and TF\_Protocol.</span></span>

<span data-ttu-id="5b214-168">変数 $LyssProvider を定義した後、**New-CsClsScenario** コマンドレットでその変数を使用して Lyss プロバイダーからトレースを収集できます。</span><span class="sxs-lookup"><span data-stu-id="5b214-168">After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="5b214-169">このプロバイダーの作成と新しいシナリオへの割り当てを完了するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5b214-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="5b214-170">$LyssProvider は、**New-CsClsProvider** で作成された定義済みのシナリオを含む変数です。</span><span class="sxs-lookup"><span data-stu-id="5b214-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="5b214-171">既存の集中ログサービスシナリオプロバイダーを変更するには</span><span class="sxs-lookup"><span data-stu-id="5b214-171">To change an existing Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="5b214-172">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b214-172">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5b214-173">既存のプロバイダーの構成を更新または変更するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5b214-173">To update or change the configuration of an existing provider, type:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    <span data-ttu-id="5b214-174">次のように入力することで、プロバイダーを割り当てるシナリオを更新します。</span><span class="sxs-lookup"><span data-stu-id="5b214-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="5b214-175">コマンドを実行すると、最終的にシナリオ site:Redmond/RedmondLyssInfo のフラグと割り当てられるプロバイダーのレベルが更新されます。</span><span class="sxs-lookup"><span data-stu-id="5b214-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="5b214-176">Get-CsClsScenario を使用して、新しいシナリオを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5b214-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="5b214-177">詳細については、「[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b214-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span></span>

<div class="">


> [!WARNING]  
> <span data-ttu-id="5b214-178"><STRONG>New-ClsCsProvider</STRONG> は、フラグが有効かどうかを確認しません。</span><span class="sxs-lookup"><span data-stu-id="5b214-178"><STRONG>New-ClsCsProvider</STRONG> does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="5b214-179">フラグのスペル (TF_DIAG や TF_CONNECTION など) が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5b214-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="5b214-180">フラグのスペルが正しくない場合、プロバイダーは期待されるログ情報を返すことができません。</span><span class="sxs-lookup"><span data-stu-id="5b214-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>



</div>

<span data-ttu-id="5b214-181">このシナリオに対してプロバイダーを追加するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5b214-181">If you want to add additional providers to this scenario, type the following:</span></span>

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

<span data-ttu-id="5b214-182">Add ディレクティブで定義される各プロバイダーは、**New-CsClsProvider** プロセスで既に定義されています。</span><span class="sxs-lookup"><span data-stu-id="5b214-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="5b214-183">シナリオ プロバイダーを削除するには</span><span class="sxs-lookup"><span data-stu-id="5b214-183">To remove a scenario provider</span></span>

1.  <span data-ttu-id="5b214-184">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b214-184">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5b214-185">用意されているコマンドレットを使用して、既存のプロバイダーの更新と新しいプロバイダーの作成を実行できます。</span><span class="sxs-lookup"><span data-stu-id="5b214-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="5b214-186">プロバイダーを削除するには、**Set-CsClsScenario** に対して Provider パラメーター用の Replace ディレクティブを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b214-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="5b214-187">プロバイダーを完全に削除する唯一の方法は、Update ディレクティブを使用して、削除するプロバイダーを、再定義した同じ名前のプロバイダーに置き換えることです。</span><span class="sxs-lookup"><span data-stu-id="5b214-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="5b214-188">たとえば、プロバイダー LyssProvider は、ログの種類、デバッグのレベルセット、flags セットが TF\_CONNECTION および tf\_DIAG として、WPP で定義されています。</span><span class="sxs-lookup"><span data-stu-id="5b214-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF\_CONNECTION and TF\_DIAG.</span></span> <span data-ttu-id="5b214-189">このフラグを "All" に変更する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="5b214-189">You need to change the flags to “All”.</span></span> <span data-ttu-id="5b214-190">このプロバイダーを変更するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5b214-190">To change the provider, type the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  <span data-ttu-id="5b214-191">シナリオとそれに関連付けられているプロバイダーを完全に削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5b214-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    <span data-ttu-id="5b214-192">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5b214-192">For example:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="5b214-193"><STRONG>Remove-CsClsScenario</STRONG> コマンドレットは、確認のプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="5b214-193">The cmdlet <STRONG>Remove-CsClsScenario</STRONG> does not prompt you for confirmation.</span></span> <span data-ttu-id="5b214-194">シナリオは、それに関連付けられているプロバイダーと共に削除されます。</span><span class="sxs-lookup"><span data-stu-id="5b214-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="5b214-195">シナリオを初めて作成したときに使用したコマンドを再実行することで、シナリオを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="5b214-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="5b214-196">削除したシナリオまたはプロバイダーを回復するための手順はありません。</span><span class="sxs-lookup"><span data-stu-id="5b214-196">There is no procedure to recover removed scenarios or providers.</span></span>

    
    </div>

<span data-ttu-id="5b214-197">**Remove-CsClsScenario** コマンドレットを使用してシナリオを削除すると、シナリオはスコープから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="5b214-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="5b214-198">作成したシナリオとシナリオの一部であったプロバイダーを使用するには、新しいプロバイダーを作成し、それらを新しいシナリオに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5b214-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5b214-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b214-199">See Also</span></span>


[<span data-ttu-id="5b214-200">取得-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="5b214-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[<span data-ttu-id="5b214-201">新しい-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="5b214-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[<span data-ttu-id="5b214-202">削除-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="5b214-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[<span data-ttu-id="5b214-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="5b214-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[<span data-ttu-id="5b214-204">新しい-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="5b214-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

