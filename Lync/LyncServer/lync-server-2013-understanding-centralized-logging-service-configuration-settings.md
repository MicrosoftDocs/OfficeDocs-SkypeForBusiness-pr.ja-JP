---
title: 集中ログサービスの構成設定について
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a766756f082e6666d37dff793c457cb335736fe0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="0ff92-102">Lync Server 2013 の一元ログサービスの構成設定について</span><span class="sxs-lookup"><span data-stu-id="0ff92-102">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ff92-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0ff92-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0ff92-104">一元的なログサービスは、ログサービスの収集方法、収集方法、収集される場所、およびログ設定の内容を定義するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="0ff92-104">The Centralized Logging Service is configured to define what the logging service is intended to collect, how it collects, where it will collect from, and what the log settings are.</span></span> <span data-ttu-id="0ff92-105">これらの設定は、グローバル (展開全体) またはサイト (展開内で指定されたサイト) に対して定義します。</span><span class="sxs-lookup"><span data-stu-id="0ff92-105">You define these settings globally (that is, for the entire deployment) or for a site (that is, a named site in your deployment).</span></span> <span data-ttu-id="0ff92-106">定義するすべてのログで、ログを開始、停止、更新、および検索するコマンドに対して使用する ID に適した設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ff92-106">Any logging that you define will use the settings that are appropriate for the identity that you use for commands to start, stop, flush, and search logs.</span></span>

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="0ff92-107">現在の集中化ログサービスの構成を表示するには</span><span class="sxs-lookup"><span data-stu-id="0ff92-107">To display the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="0ff92-108">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ff92-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0ff92-109">コマンド ライン プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0ff92-109">Type the following at a command-line prompt:</span></span>
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > <span data-ttu-id="0ff92-110">定義<CODE>-Identity</CODE>によって返される構成設定の範囲を絞り込んだり、展開したりすることができます。たとえば、"Site: レドモンド" のように、サイトレドモンドの CsClsConfiguration のみを返すようにします。</span><span class="sxs-lookup"><span data-stu-id="0ff92-110">You can narrow or expand the scope of the configuration settings that are returned by defining <CODE>-Identity</CODE> and a scope, such as "Site:Redmond" to return only the CsClsConfiguration for the site Redmond.</span></span> <span data-ttu-id="0ff92-111">構成の特定の部分に関する詳細が必要な場合は、出力を別の Windows PowerShell コマンドレットにパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="0ff92-111">If you want details about a given portion of the configuration, you can pipe the output into another Windows PowerShell cmdlet.</span></span> <span data-ttu-id="0ff92-112">たとえば、サイト "Redmond" の構成で定義されているシナリオに関する詳細情報を取得するには、次のように入力します。<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span><span class="sxs-lookup"><span data-stu-id="0ff92-112">For example, to get details about the scenarios defined in the configuration for site "Redmond", type: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span></span>

    
    </div>
    
    <span data-ttu-id="0ff92-113">![Get-CsClsConfiguration からのサンプル出力](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration からのサンプル出力")</span><span class="sxs-lookup"><span data-stu-id="0ff92-113">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>
    
    <span data-ttu-id="0ff92-114">このコマンドレットの結果には、一元管理サービスの現在の構成が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ff92-114">The result from the cmdlet displays the current configuration of the Centralized Logging Service.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="0ff92-115">構成設定</span><span class="sxs-lookup"><span data-stu-id="0ff92-115">Configuration Setting</span></span></th>
    <th><span data-ttu-id="0ff92-116">説明</span><span class="sxs-lookup"><span data-stu-id="0ff92-116">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="0ff92-117"><strong>Identity</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-117"><strong>Identity</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-p103">この構成のスコープと名前を識別します。存在するグローバル構成は 1 つのみで、サイトごとに 1 つの構成があります。</span><span class="sxs-lookup"><span data-stu-id="0ff92-p103">Identifies the scope and name for this configuration. There is only one Global configuration, and one configuration per site.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="0ff92-120"><strong>Scenarios</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-120"><strong>Scenarios</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-121">この構成に対して定義されたシナリオの一覧。</span><span class="sxs-lookup"><span data-stu-id="0ff92-121">Listing of all scenarios that are defined for this configuration.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="0ff92-122"><strong>SearchTerms</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-122"><strong>SearchTerms</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-123">構成の定義済み検索用語。</span><span class="sxs-lookup"><span data-stu-id="0ff92-123">Defined search terms for the configuration.</span></span> <span data-ttu-id="0ff92-124">Office 365、オンプレミス展開ではありません。</span><span class="sxs-lookup"><span data-stu-id="0ff92-124">Office 365, not on-premises deployments.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="0ff92-125"><strong>SecurityGroups</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-125"><strong>SecurityGroups</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-126">コンピューターを確認できるユーザー (つまり、セキュリティ グループのメンバー) を、そのユーザーのサイトに基づいて制御する定義済みセキュリティ グループ。</span><span class="sxs-lookup"><span data-stu-id="0ff92-126">Defined security groups that control who (that is, members of the security groups) can see computers based on the site they are located in.</span></span> <span data-ttu-id="0ff92-127">このコンテキストのサイトは、トポロジビルダーで定義されているサイトです。</span><span class="sxs-lookup"><span data-stu-id="0ff92-127">Site, in this context, is the site as defined in Topology Builder.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="0ff92-128"><strong>Regions</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-128"><strong>Regions</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-129">SecurityGroups を地域にまとめる際に定義済み地域が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ff92-129">Defined regions are used to collect SecurityGroups into a region, for example EMEA.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="0ff92-130"><strong>EtlFileFolder</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-130"><strong>EtlFileFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-131">コンピューター上でログファイルが書き込まれる場所の定義パス。</span><span class="sxs-lookup"><span data-stu-id="0ff92-131">Defined path to the location where log files are written on computers.</span></span> <span data-ttu-id="0ff92-132">CLSAgent は、ログファイルを書き込み、ネットワークサービスのコンテキストで実行します。</span><span class="sxs-lookup"><span data-stu-id="0ff92-132">CLSAgent writes the log files and runs under the context of the Network Service.</span></span> <span data-ttu-id="0ff92-133">この場合、% TEMP% が%WINDIR%\ServiceProfiles\NetworkService\AppData\Local に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="0ff92-133">In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="0ff92-134"><strong>EtlFileRolloverSizeMB</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-134"><strong>EtlFileRolloverSizeMB</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-p107">パラメーターは、新しいイベント トレース ログ (.etl) ファイルが作成される前のログ ファイルの最大サイズを示します。定義したサイズに達すると、EtlFileRolloverMinutes で設定された最大時間に達していなくても、新しいログ ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0ff92-p107">The parameter indicates the maximum size of the log file before a new event trace log (.etl) file is created. A new log file is created when the defined size is reached even if the maximum time set in EtlFileRolloverMinutes has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="0ff92-137"><strong>EtlFileRolloverMinutes</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-137"><strong>EtlFileRolloverMinutes</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-p108">新しい .etl ファイルが作成されるまでのログの定義済み最大経過時間 (分単位)。指定した時間が過ぎると、EtlFileRolloverSizeMBE で設定された最大サイズに達していなくても、新しいログ ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0ff92-p108">Defined maximum amount of time, in minutes, that a log can elapse before a new .etl file is created. A new log file is created when the timer expires even if the maximum size set in EtlFileRolloverSizeMB has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="0ff92-140"><strong>TmfFileSearchPath</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-140"><strong>TmfFileSearchPath</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-141">トレース メッセージ形式のファイルを検索する場所。</span><span class="sxs-lookup"><span data-stu-id="0ff92-141">Location to search for the trace message format files.</span></span> <span data-ttu-id="0ff92-142">トレースメッセージ形式のファイルは、バイナリファイルを人間が読める形式に変換するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ff92-142">The trace message format files are used to convert the binary files into a human readable format.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="0ff92-143"><strong>CacheFileLocalFolders</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-143"><strong>CacheFileLocalFolders</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-p110">キャッシュ ファイルが書き込まれるコンピューター上の場所への定義済みパス。CLSAgent はキャッシュ ファイルを書き込み、ネットワーク サービスとの関連で実行されます。この場合は、%TEMP% が %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。既定では、キャッシュ ファイルとログ ファイルは同じディレクトリに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="0ff92-p110">Defined path to the location where cache files are written on computers. CLSAgent writes the cache files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. By default, cache files and log files are written to the same directory.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="0ff92-148"><strong>CacheFileNetworkFolder</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-148"><strong>CacheFileNetworkFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-149">汎用名前付け規則 (UNC) パスを定義すると、ログ操作中にキャッシュ ファイルを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="0ff92-149">You can define a universal naming convention (UNC) path to receive the cache files during logging operations.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="0ff92-150"><strong>CacheFileLocalRetentionPeriod</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-150"><strong>CacheFileLocalRetentionPeriod</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-151">キャッシュ ファイルが保持される最大時間 (日単位) として定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ff92-151">Defined as the maximum time, in days, that cache files are retained.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="0ff92-152"><strong>CacheFileMaxDiskUsage</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-152"><strong>CacheFileMaxDiskUsage</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-153">キャッシュ ファイルで使用できるディスク容量の割合として定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ff92-153">Defined as the percentage of disk space that can be used by the cache files.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="0ff92-154"><strong>ComponentThrottleLimit</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-154"><strong>ComponentThrottleLimit</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-155">自動調整制限がトリガーされるまでの、コンポーネントが生成できる秒あたりの最大トレース数として定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ff92-155">Defined as the maximum number of traces per second that a component can produce before the automatic throttle limiter is triggered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="0ff92-156"><strong>ComponentThrottleSample</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-156"><strong>ComponentThrottleSample</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-157">ComponentThrottleLimit を超えることができる 60 秒単位の回数。</span><span class="sxs-lookup"><span data-stu-id="0ff92-157">Number of times in 60 seconds that the ComponentThrottleLimit can be exceeded.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="0ff92-158"><strong>MinimumClsAgentServiceVersion</strong></span><span class="sxs-lookup"><span data-stu-id="0ff92-158"><strong>MinimumClsAgentServiceVersion</strong></span></span></p></td>
    <td><p><span data-ttu-id="0ff92-159">実行が許可されている CLSAgent の最小バージョン。</span><span class="sxs-lookup"><span data-stu-id="0ff92-159">The minimum version of the CLSAgent allowed to run.</span></span> <span data-ttu-id="0ff92-160">この要素は、Office 365 を対象としています。</span><span class="sxs-lookup"><span data-stu-id="0ff92-160">This element is intended for Office 365.</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0ff92-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ff92-161">See Also</span></span>


[<span data-ttu-id="0ff92-162">Lync Server 2013 の一元管理されたログサービスの概要</span><span class="sxs-lookup"><span data-stu-id="0ff92-162">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


<span data-ttu-id="0ff92-163">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ff92-163">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="0ff92-164">[CsClsConfiguration の削除](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ff92-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span></span>  
<span data-ttu-id="0ff92-165">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ff92-165">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="0ff92-166">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ff92-166">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

