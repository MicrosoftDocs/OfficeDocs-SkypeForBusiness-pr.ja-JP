---
title: 'Lync Server 2013: 集中ログサービス用のプロバイダーの構成'
description: 'Lync Server 2013: 集中ログサービス用のプロバイダーの構成。'
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
ms.openlocfilehash: 9146865b3856f7956c6ae393ef38614b0fea168e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547953"
---
# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="f3af2-103">Lync Server 2013 での集中ログサービスのプロバイダーの構成</span><span class="sxs-lookup"><span data-stu-id="f3af2-103">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3af2-104">_**トピックの最終更新日:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="f3af2-104">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="f3af2-105">集中ログサービスの *プロバイダー* の概念と構成は、把握しておくべき最も重要なものの1つです。</span><span class="sxs-lookup"><span data-stu-id="f3af2-105">The concepts and configuration of *providers* in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="f3af2-106">*プロバイダー*は、lync server トレースモデルの lync server サーバーロールコンポーネントに直接マップされます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-106">The *providers* map directly to Lync Server server role components in the Lync Server tracing model.</span></span> <span data-ttu-id="f3af2-107">プロバイダーは、追跡される Lync Server 2013 のコンポーネント、収集するメッセージの種類 (致命的、エラー、警告など)、およびフラグ (たとえば、TF \_ Connection または tf Diag) を定義し \_ ます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-107">The provider defines the components of a Lync Server 2013 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF\_Connection or TF\_Diag).</span></span> <span data-ttu-id="f3af2-108">プロバイダーは、各 Lync Server サーバーの役割で追跡可能なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="f3af2-108">Providers are the traceable components in each Lync Server server role.</span></span> <span data-ttu-id="f3af2-109">プロバイダーを使用して、コンポーネントに対するトレースのレベルと種類 (S4、SIPStack、IM、プレゼンスなど) を定義します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="f3af2-110">定義済みのプロバイダーは、シナリオの中で特定の問題状況に対応する特定の論理コレクション用のすべてのプロバイダーをグループ化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>

<span data-ttu-id="f3af2-111">Lync Server 管理シェルを使用して集中ログサービスの機能を実行するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、またはこれら2つのグループのどちらかを含むカスタムの RBAC の役割を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3af2-111">To run the Centralized Logging Service functions using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="f3af2-112">このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自分で作成したカスタムの RBAC の役割を含む) を戻すには、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="f3af2-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-113">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="f3af2-114">このトピックの以下の部分では、プロバイダーの定義方法、プロバイダーの変更方法、およびトラブルシューティングを最適化するためにプロバイダー定義に含まれるものに注目します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="f3af2-115">集中ログサービスのコマンドを発行するには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="f3af2-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="f3af2-116">既定では、ディレクトリ C: \\ Program Files \\ Common Files \\ Microsoft Lync Server 2013 clsagent にある CLSController.exe を使用でき \\ ます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-116">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="f3af2-117">または、Lync Server 管理シェルを使用して、Windows PowerShell コマンドを発行することもできます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-117">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="f3af2-118">この 2 つの方法の重要な相違点は、CLSController.exe をコマンド ラインで使用する場合は、使用できるシナリオに限りがあり (プロバイダーが既に定義されたシナリオから選択)、プロバイダーを変更することはできませんが、ログ レベルは定義できます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-118">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available in which the providers are already defined and are not changeable, but you can define the log level.</span></span> <span data-ttu-id="f3af2-119">Windows PowerShell を使用すると、ログセッションで使用するために新しいプロバイダーを定義し、作成、収集内容、データを収集するレベルなどを詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-119">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="f3af2-p104">前述したように、プロバイダーは非常に強力です。ただし、シナリオは、プロバイダーが表すコンポーネントに対するトレースの設定と実行を行うために必要な具体的な情報をすべて含んでいるため、プロバイダーよりも強力です。シナリオとプロバイダーのコレクションは、大まかに言うと、大量の情報を収集する多数のコマンドを含むバッチ ファイルを実行することと、多数のコマンドをコマンド ラインから一度に 1 つずつ発行することに相当します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span><BR><span data-ttu-id="f3af2-123">プロバイダーの詳細を深く掘り下げて把握する必要はありませんが、集中ログサービスでは、既に定義されているいくつかのシナリオが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f3af2-123">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="f3af2-124">用意されているシナリオを使用して、遭遇する可能性がある問題の大部分に対応できます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-124">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="f3af2-125">まれに、プロバイダーを定義してシナリオに割り当てなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3af2-125">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="f3af2-126">新しいプロバイダーとシナリオを作成する必要があるかどうかを考慮する前に、用意されているシナリオを十分に調べることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f3af2-126">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="f3af2-127">ここでは、シナリオでのプロバイダー要素の使用によるトレース情報の収集方法を理解するために、プロバイダーの作成に関する情報が提示されていますが、プロバイダーそのものの詳細については説明しません。</span><span class="sxs-lookup"><span data-stu-id="f3af2-127">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span>



</div>

<span data-ttu-id="f3af2-128">[Lync Server 2013 の集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)では、シナリオで使用するプロバイダーを定義する主な要素として、次の要素を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="f3af2-128">Introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>

  - <span data-ttu-id="f3af2-129">**Providers**    OCSLogger を熟知している場合、プロバイダーは、トレースエンジンがログを収集する内容を OCSLogger に通知するために選択するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="f3af2-129">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="f3af2-130">プロバイダーは同じコンポーネントで、多くの場合、OCSLogger のコンポーネントと同じ名前になります。</span><span class="sxs-lookup"><span data-stu-id="f3af2-130">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="f3af2-131">OCSLogger を使い慣れていない場合、プロバイダーは、集中ログサービスがログを収集できる、サーバーロール固有のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="f3af2-131">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="f3af2-132">集中ログサービスの場合、CLSAgent は、プロバイダ構成で定義したコンポーネントのトレースを実行している、集中ログサービスのアーキテクチャ部分です。</span><span class="sxs-lookup"><span data-stu-id="f3af2-132">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>

  - <span data-ttu-id="f3af2-133">**ログ出力レベル**    OCSLogger では、収集されるデータの詳細レベルの数を選択するオプションが提供されています。</span><span class="sxs-lookup"><span data-stu-id="f3af2-133">**Logging levels**   OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="f3af2-134">この機能は、集中ログサービスとシナリオの重要な部分であり、 **Type** パラメーターで定義されています。</span><span class="sxs-lookup"><span data-stu-id="f3af2-134">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="f3af2-135">次のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-135">You can choose from the following:</span></span>
    
      - <span data-ttu-id="f3af2-136">**すべて**    指定されたプロバイダーについて、重大、エラー、警告、および情報の種類のトレースメッセージをログに収集します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-136">**All**   Collects trace messages of type fatal, error, warning, and info to the log for the defined provider.</span></span>
    
      - <span data-ttu-id="f3af2-137">**致命的**     な定義済みのプロバイダーのエラーを示すトレースメッセージのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-137">**Fatal**   Collects only the trace messages that indicate a failure for the defined provider.</span></span>
    
      - <span data-ttu-id="f3af2-138">**エラー**    定義済みのプロバイダーのエラー、および致命的なメッセージを示すトレースメッセージのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-138">**Error**   Collects only the trace messages that indicate an error for the defined provider, plus fatal messages.</span></span>
    
      - <span data-ttu-id="f3af2-139">**警告**    定義済みのプロバイダーについての警告、および致命的メッセージとエラーメッセージを示すトレースメッセージのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-139">**Warning**   Collects only the trace messages that indicate a warning for the defined provider, plus fatal and error messages.</span></span>
    
      - <span data-ttu-id="f3af2-140">**情報**    定義済みのプロバイダーの情報メッセージに加え、致命的、エラー、および警告メッセージを示すトレースメッセージのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-140">**Info**   Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
      - <span data-ttu-id="f3af2-141">**詳細**    定義済みのプロバイダーについて、種類が fatal、error、warning、info のすべてのトレースメッセージを収集します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-141">**Verbose**   Collects all trace messages of type fatal, error, warning and info for the defined provider.</span></span>

  - <span data-ttu-id="f3af2-142">**Flags**    OCSLogger では、トレースファイルから取得できる情報の種類を定義するプロバイダーごとにフラグを選択するオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f3af2-142">**Flags**   OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="f3af2-143">プロバイダーに基づいて、次のフラグを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-143">You can chose the following flags, based on the provider:</span></span>
    
      - <span data-ttu-id="f3af2-144">**TF \_接続**     接続に関連するログエントリを提供します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-144">**TF\_Connection**   Provides connection-related log entries.</span></span> <span data-ttu-id="f3af2-145">これらのログには、特定のコンポーネントとの間で確立された接続に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="f3af2-146">これには、ネットワークレベルの重要な情報 (接続の概念を持たないコンポーネント) が含まれることもあります。</span><span class="sxs-lookup"><span data-stu-id="f3af2-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
      - <span data-ttu-id="f3af2-147">**TF \_セキュリティ**     セキュリティに関連するすべてのイベント/ログエントリを提供します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-147">**TF\_Security**   Provides all events/log entries related to security.</span></span> <span data-ttu-id="f3af2-148">たとえば、SipStack の場合、これらはドメイン検証エラーなどのセキュリティイベント、およびクライアント認証/承認エラーです。</span><span class="sxs-lookup"><span data-stu-id="f3af2-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
      - <span data-ttu-id="f3af2-149">**TF \_Diag**     は、コンポーネントの診断またはトラブルシューティングに使用できる診断イベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-149">**TF\_Diag**   Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="f3af2-150">たとえば、SipStack の場合は、証明書が失敗したか、DNS の警告/エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
      - <span data-ttu-id="f3af2-151">**TF \_Protocol**     SIP、組み合わせたコミュニティコーデックパックメッセージなどのプロトコルメッセージを提供します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-151">**TF\_Protocol**   Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
      - <span data-ttu-id="f3af2-152">**TF \_コンポーネント**     は、プロバイダーの一部として指定されたコンポーネントのログ記録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f3af2-152">**TF\_Component**   Enables logging on the components specified as part of the providers.</span></span>
    
      - <span data-ttu-id="f3af2-153">**すべて**    プロバイダーで使用可能なすべての使用可能なフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-153">**All**   Sets all available flags available for the provider.</span></span>

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="f3af2-154">既存の集中ログサービスシナリオプロバイダーに関する情報を確認するには</span><span class="sxs-lookup"><span data-stu-id="f3af2-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1.  <span data-ttu-id="f3af2-155">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3af2-155">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f3af2-156">既存のプロバイダーの構成をレビューするには、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-156">To review the configuration of existing providers, type the following:</span></span>
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    <span data-ttu-id="f3af2-157">たとえば、グローバル会議アテンダントに関する情報をレビューするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA"
    
    <span data-ttu-id="f3af2-158">このコマンドは、関連するフラグ、設定、およびコンポーネントと共にプロバイダーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="f3af2-159">表示されている情報が不足している場合や、既定の Windows PowerShell リスト形式でリストが長すぎる場合は、別の出力メソッドを定義することで追加情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="f3af2-160">これを行うには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-160">To do this, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    <span data-ttu-id="f3af2-161">このコマンドの出力では、各プロバイダーを行分割形式で表示します。プロバイダー名、ログの種類、ログ レベル、フラグ、GUID、および役割が行ごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span>

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="f3af2-162">新しい集中ログサービスシナリオプロバイダーを定義するには</span><span class="sxs-lookup"><span data-stu-id="f3af2-162">To define a new Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="f3af2-163">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3af2-163">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f3af2-p113">シナリオ プロバイダーは、トレースするコンポーネント、使用するフラグ、および収集する詳細レベルで構成されます。これは実行するには次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    <span data-ttu-id="f3af2-166">たとえば、Lyss プロバイダーから収集する内容および詳細レベルを定義するトレース プロバイダー定義は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f3af2-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

<span data-ttu-id="f3af2-167">–Level は、重大、エラー、警告、および情報メッセージを収集します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-167">The –Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="f3af2-168">使用されるフラグは、一からの Ss プロバイダーに対して定義されているもので、TF \_ Connection、tf \_ DIAG、tf プロトコルが含まれてい \_ ます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-168">The flags used are all of those defined for the Lyss provider, and include TF\_Connection, TF\_Diag and TF\_Protocol.</span></span>

<span data-ttu-id="f3af2-169">変数 $LyssProvider を定義した後、**New-CsClsScenario** コマンドレットでその変数を使用して Lyss プロバイダーからトレースを収集できます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-169">After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="f3af2-170">このプロバイダーの作成と新しいシナリオへの割り当てを完了するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-170">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="f3af2-171">$LyssProvider は、**New-CsClsProvider** で作成された定義済みのシナリオを含む変数です。</span><span class="sxs-lookup"><span data-stu-id="f3af2-171">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="f3af2-172">既存の集中ログサービスシナリオプロバイダーを変更するには</span><span class="sxs-lookup"><span data-stu-id="f3af2-172">To change an existing Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="f3af2-173">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3af2-173">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f3af2-174">既存のプロバイダーの構成を更新または変更するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-174">To update or change the configuration of an existing provider, type:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    <span data-ttu-id="f3af2-175">次のように入力することで、プロバイダーを割り当てるシナリオを更新します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-175">You then update the scenario to assign the provider by typing the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="f3af2-176">コマンドを実行すると、最終的にシナリオ site:Redmond/RedmondLyssInfo のフラグと割り当てられるプロバイダーのレベルが更新されます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-176">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="f3af2-177">Get-CsClsScenario を使用して、新しいシナリオを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-177">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="f3af2-178">詳細については、「[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3af2-178">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span></span>

<div class="">


> [!WARNING]  
> <span data-ttu-id="f3af2-179"><STRONG>New-ClsCsProvider</STRONG> は、フラグが有効かどうかを確認しません。</span><span class="sxs-lookup"><span data-stu-id="f3af2-179"><STRONG>New-ClsCsProvider</STRONG> does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="f3af2-180">フラグのスペル (TF_DIAG や TF_CONNECTION など) が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f3af2-180">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="f3af2-181">フラグのスペルが正しくない場合、プロバイダーは期待されるログ情報を返すことができません。</span><span class="sxs-lookup"><span data-stu-id="f3af2-181">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>



</div>

<span data-ttu-id="f3af2-182">このシナリオに対してプロバイダーを追加するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-182">If you want to add additional providers to this scenario, type the following:</span></span>

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

<span data-ttu-id="f3af2-183">Add ディレクティブで定義される各プロバイダーは、**New-CsClsProvider** プロセスで既に定義されています。</span><span class="sxs-lookup"><span data-stu-id="f3af2-183">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="f3af2-184">シナリオ プロバイダーを削除するには</span><span class="sxs-lookup"><span data-stu-id="f3af2-184">To remove a scenario provider</span></span>

1.  <span data-ttu-id="f3af2-185">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3af2-185">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f3af2-186">用意されているコマンドレットを使用して、既存のプロバイダーの更新と新しいプロバイダーの作成を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-186">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="f3af2-187">プロバイダーを削除するには、**Set-CsClsScenario** に対して Provider パラメーター用の Replace ディレクティブを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3af2-187">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="f3af2-188">プロバイダーを完全に削除する唯一の方法は、Update ディレクティブを使用して、削除するプロバイダーを、再定義した同じ名前のプロバイダーに置き換えることです。</span><span class="sxs-lookup"><span data-stu-id="f3af2-188">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="f3af2-189">たとえば、プロバイダー LyssProvider は、ログの種類、デバッグのレベルセット、flags セットが TF CONNECTION および TF DIAG として、WPP で定義されてい \_ \_ ます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-189">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF\_CONNECTION and TF\_DIAG.</span></span> <span data-ttu-id="f3af2-190">このフラグを "All" に変更する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="f3af2-190">You need to change the flags to “All”.</span></span> <span data-ttu-id="f3af2-191">このプロバイダーを変更するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-191">To change the provider, type the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  <span data-ttu-id="f3af2-192">シナリオとそれに関連付けられているプロバイダーを完全に削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-192">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    <span data-ttu-id="f3af2-193">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f3af2-193">For example:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="f3af2-194"><STRONG>Remove-CsClsScenario</STRONG> コマンドレットは、確認のプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="f3af2-194">The cmdlet <STRONG>Remove-CsClsScenario</STRONG> does not prompt you for confirmation.</span></span> <span data-ttu-id="f3af2-195">シナリオは、それに関連付けられているプロバイダーと共に削除されます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-195">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="f3af2-196">シナリオを初めて作成したときに使用したコマンドを再実行することで、シナリオを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-196">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="f3af2-197">削除したシナリオまたはプロバイダーを回復するための手順はありません。</span><span class="sxs-lookup"><span data-stu-id="f3af2-197">There is no procedure to recover removed scenarios or providers.</span></span>

    
    </div>

<span data-ttu-id="f3af2-198">**Remove-CsClsScenario** コマンドレットを使用してシナリオを削除すると、シナリオはスコープから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-198">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="f3af2-199">作成したシナリオとシナリオの一部であったプロバイダーを使用するには、新しいプロバイダーを作成し、それらを新しいシナリオに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f3af2-199">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f3af2-200">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3af2-200">See Also</span></span>


[<span data-ttu-id="f3af2-201">取得-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="f3af2-201">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[<span data-ttu-id="f3af2-202">新しい-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="f3af2-202">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[<span data-ttu-id="f3af2-203">削除-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="f3af2-203">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[<span data-ttu-id="f3af2-204">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="f3af2-204">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[<span data-ttu-id="f3af2-205">新しい-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="f3af2-205">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

