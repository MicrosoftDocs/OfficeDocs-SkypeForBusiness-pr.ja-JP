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
ms.openlocfilehash: 1bda4fe432841cd005671b18a163df57bd6e0bb7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="fb7bb-102">Lync Server 2013 での集中ログサービスの構成設定について</span><span class="sxs-lookup"><span data-stu-id="fb7bb-102">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb7bb-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="fb7bb-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fb7bb-104">集中ログサービスは、ログサービスが収集する目的、収集方法、収集される場所、およびログ設定について定義するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-104">The Centralized Logging Service is configured to define what the logging service is intended to collect, how it collects, where it will collect from, and what the log settings are.</span></span> <span data-ttu-id="fb7bb-105">これらの設定は、グローバルに (つまり、展開全体で)、またはサイト (展開内の名前付きサイト) で定義します。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-105">You define these settings globally (that is, for the entire deployment) or for a site (that is, a named site in your deployment).</span></span> <span data-ttu-id="fb7bb-106">定義するすべてのログで、ログを開始、停止、更新、および検索するコマンドに対して使用する ID に適した設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-106">Any logging that you define will use the settings that are appropriate for the identity that you use for commands to start, stop, flush, and search logs.</span></span>

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="fb7bb-107">現在の集中ログサービスの構成を表示するには</span><span class="sxs-lookup"><span data-stu-id="fb7bb-107">To display the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="fb7bb-108">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="fb7bb-109">コマンド ライン プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-109">Type the following at a command-line prompt:</span></span>
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > <span data-ttu-id="fb7bb-110">定義<CODE>-Identity</CODE>によって返される構成設定の範囲を絞り込んだり展開したり、"Site: redmond" のようにスコープを展開して、サイト Redmond の CsClsConfiguration のみを取得したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-110">You can narrow or expand the scope of the configuration settings that are returned by defining <CODE>-Identity</CODE> and a scope, such as "Site:Redmond" to return only the CsClsConfiguration for the site Redmond.</span></span> <span data-ttu-id="fb7bb-111">構成の特定の部分に関する詳細が必要な場合は、出力を別の Windows PowerShell コマンドレットにパイプ処理できます。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-111">If you want details about a given portion of the configuration, you can pipe the output into another Windows PowerShell cmdlet.</span></span> <span data-ttu-id="fb7bb-112">たとえば、"Redmond" サイトの構成で定義されているシナリオの詳細を取得するには、次のように入力します。<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span><span class="sxs-lookup"><span data-stu-id="fb7bb-112">For example, to get details about the scenarios defined in the configuration for site "Redmond", type: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span></span>

    
    </div>
    
    <span data-ttu-id="fb7bb-113">![Get-CsClsConfiguration からの出力例。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration からの出力例。")</span><span class="sxs-lookup"><span data-stu-id="fb7bb-113">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>
    
    <span data-ttu-id="fb7bb-114">コマンドレットの結果によって、集中ログサービスの現在の構成が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-114">The result from the cmdlet displays the current configuration of the Centralized Logging Service.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="fb7bb-115">構成設定</span><span class="sxs-lookup"><span data-stu-id="fb7bb-115">Configuration Setting</span></span></th>
    <th><span data-ttu-id="fb7bb-116">説明</span><span class="sxs-lookup"><span data-stu-id="fb7bb-116">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="fb7bb-117"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-117"><strong>Identity</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-p103">この構成のスコープと名前を識別します。存在するグローバル構成は 1 つのみで、サイトごとに 1 つの構成があります。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-p103">Identifies the scope and name for this configuration. There is only one Global configuration, and one configuration per site.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fb7bb-120"><strong>Scenarios</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-120"><strong>Scenarios</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-121">この構成に対して定義されたシナリオの一覧。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-121">Listing of all scenarios that are defined for this configuration.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="fb7bb-122"><strong>SearchTerms</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-122"><strong>SearchTerms</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-123">構成の定義済み検索用語。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-123">Defined search terms for the configuration.</span></span> <span data-ttu-id="fb7bb-124">Office 365。オンプレミス展開ではありません。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-124">Office 365, not on-premises deployments.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fb7bb-125"><strong>Securitygroups まとめる</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-125"><strong>SecurityGroups</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-126">コンピューターを確認できるユーザー (つまり、セキュリティ グループのメンバー) を、そのユーザーのサイトに基づいて制御する定義済みセキュリティ グループ。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-126">Defined security groups that control who (that is, members of the security groups) can see computers based on the site they are located in.</span></span> <span data-ttu-id="fb7bb-127">このコンテキストのサイトは、トポロジビルダーで定義されているサイトです。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-127">Site, in this context, is the site as defined in Topology Builder.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="fb7bb-128"><strong>地域</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-128"><strong>Regions</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-129">SecurityGroups を地域にまとめる際に定義済み地域が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-129">Defined regions are used to collect SecurityGroups into a region, for example EMEA.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fb7bb-130"><strong>EtlFileFolder</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-130"><strong>EtlFileFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-p106">ログ ファイルが書き込まれるコンピューター上の場所への定義済みパス。CLSAgent はログ ファイルを書き込み、ネットワーク サービスとの関連で実行されます。この場合は、%TEMP% が %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-p106">Defined path to the location where log files are written on computers. CLSAgent writes the log files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="fb7bb-134"><strong>Etlfilerolloversizembe</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-134"><strong>EtlFileRolloverSizeMB</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-p107">パラメーターは、新しいイベント トレース ログ (.etl) ファイルが作成される前のログ ファイルの最大サイズを示します。定義したサイズに達すると、EtlFileRolloverMinutes で設定された最大時間に達していなくても、新しいログ ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-p107">The parameter indicates the maximum size of the log file before a new event trace log (.etl) file is created. A new log file is created when the defined size is reached even if the maximum time set in EtlFileRolloverMinutes has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fb7bb-137"><strong>EtlFileRolloverMinutes</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-137"><strong>EtlFileRolloverMinutes</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-p108">新しい .etl ファイルが作成されるまでのログの定義済み最大経過時間 (分単位)。指定した時間が過ぎると、EtlFileRolloverSizeMBE で設定された最大サイズに達していなくても、新しいログ ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-p108">Defined maximum amount of time, in minutes, that a log can elapse before a new .etl file is created. A new log file is created when the timer expires even if the maximum size set in EtlFileRolloverSizeMB has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="fb7bb-140"><strong>TmfFileSearchPath</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-140"><strong>TmfFileSearchPath</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-p109">トレース メッセージ形式のファイルを検索する場所。トレース メッセージ形式のファイルは、バイナリ ファイルを人が読み取れる形式に変換するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-p109">Location to search for the trace message format files. The trace message format files are used to convert the binary files into a human readable format.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fb7bb-143"><strong>よる cachefilelocalfolders</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-143"><strong>CacheFileLocalFolders</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-p110">キャッシュ ファイルが書き込まれるコンピューター上の場所への定義済みパス。CLSAgent はキャッシュ ファイルを書き込み、ネットワーク サービスとの関連で実行されます。この場合は、%TEMP% が %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。既定では、キャッシュ ファイルとログ ファイルは同じディレクトリに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-p110">Defined path to the location where cache files are written on computers. CLSAgent writes the cache files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. By default, cache files and log files are written to the same directory.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="fb7bb-148"><strong>CacheFileNetworkFolder</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-148"><strong>CacheFileNetworkFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-149">汎用名前付け規則 (UNC) パスを定義すると、ログ操作中にキャッシュ ファイルを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-149">You can define a universal naming convention (UNC) path to receive the cache files during logging operations.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fb7bb-150"><strong>CacheFileLocalRetentionPeriod</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-150"><strong>CacheFileLocalRetentionPeriod</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-151">キャッシュ ファイルが保持される最大時間 (日単位) として定義されます。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-151">Defined as the maximum time, in days, that cache files are retained.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="fb7bb-152"><strong>CacheFileMaxDiskUsage</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-152"><strong>CacheFileMaxDiskUsage</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-153">キャッシュ ファイルで使用できるディスク容量の割合として定義されます。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-153">Defined as the percentage of disk space that can be used by the cache files.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fb7bb-154"><strong>ComponentThrottleLimit</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-154"><strong>ComponentThrottleLimit</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-155">自動調整制限がトリガーされるまでの、コンポーネントが生成できる秒あたりの最大トレース数として定義されます。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-155">Defined as the maximum number of traces per second that a component can produce before the automatic throttle limiter is triggered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="fb7bb-156"><strong>ComponentThrottleSample</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-156"><strong>ComponentThrottleSample</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-157">ComponentThrottleLimit を超えることができる 60 秒単位の回数。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-157">Number of times in 60 seconds that the ComponentThrottleLimit can be exceeded.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fb7bb-158"><strong>MinimumClsAgentServiceVersion</strong></span><span class="sxs-lookup"><span data-stu-id="fb7bb-158"><strong>MinimumClsAgentServiceVersion</strong></span></span></p></td>
    <td><p><span data-ttu-id="fb7bb-159">実行が許可されている CLSAgent の最小バージョン。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-159">The minimum version of the CLSAgent allowed to run.</span></span> <span data-ttu-id="fb7bb-160">この要素は、Office 365 を対象としています。</span><span class="sxs-lookup"><span data-stu-id="fb7bb-160">This element is intended for Office 365.</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb7bb-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb7bb-161">See Also</span></span>


[<span data-ttu-id="fb7bb-162">Lync Server 2013 の集中ログサービスの概要</span><span class="sxs-lookup"><span data-stu-id="fb7bb-162">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


<span data-ttu-id="fb7bb-163">[設定-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb7bb-163">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="fb7bb-164">[削除-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb7bb-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
<span data-ttu-id="fb7bb-165">[新しい-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb7bb-165">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="fb7bb-166">[取得-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb7bb-166">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

