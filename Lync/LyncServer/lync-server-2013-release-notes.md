---
title: 'Lync Server 2013: リリース ノート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10961f0a8e59fe1d0dc0268b430f37fd294252b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="ab849-102">Lync Server 2013 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="ab849-102">Release notes for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab849-103">_**最終更新日:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="ab849-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="ab849-104">Lync Server 2013 のリリースノートへようこそ。</span><span class="sxs-lookup"><span data-stu-id="ab849-104">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="ab849-105">Lync Server 2013 に関する既知の問題については、このファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab849-105">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="ab849-106">このドキュメントについて</span><span class="sxs-lookup"><span data-stu-id="ab849-106">About this document</span></span>

<span data-ttu-id="ab849-107">このドキュメントには、Lync Server 2013 を展開して使用する前に知っておく必要がある重要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab849-107">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="ab849-108">Lync Server 2013 の詳細については、「 [Microsoft Lync server 2013](microsoft-lync-server-2013.md)のドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab849-108">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="ab849-109">このドキュメントには、次のセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab849-109">This document contains the following sections:</span></span>

  - <span data-ttu-id="ab849-110">Lync 2013 クライアント</span><span class="sxs-lookup"><span data-stu-id="ab849-110">Lync 2013 client</span></span>

  - <span data-ttu-id="ab849-111">Lync Server</span><span class="sxs-lookup"><span data-stu-id="ab849-111">Lync Server</span></span>

  - <span data-ttu-id="ab849-112">インストール</span><span class="sxs-lookup"><span data-stu-id="ab849-112">Installation</span></span>

  - <span data-ttu-id="ab849-113">モビリティ</span><span class="sxs-lookup"><span data-stu-id="ab849-113">Mobility</span></span>

  - <span data-ttu-id="ab849-114">会議</span><span class="sxs-lookup"><span data-stu-id="ab849-114">Conferencing</span></span>

  - <span data-ttu-id="ab849-115">エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="ab849-115">Enterprise Voice</span></span>

  - <span data-ttu-id="ab849-116">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="ab849-116">Presence</span></span>

  - <span data-ttu-id="ab849-117">応答グループ アプリケーションとコール パーク アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ab849-117">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="ab849-118">Lync Server コントロール パネル、トポロジ ビルダー、および計画ツール</span><span class="sxs-lookup"><span data-stu-id="ab849-118">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="ab849-119">版</span><span class="sxs-lookup"><span data-stu-id="ab849-119">Localization</span></span>

  - <span data-ttu-id="ab849-120">著作</span><span class="sxs-lookup"><span data-stu-id="ab849-120">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="ab849-121">Lync 2013 クライアント</span><span class="sxs-lookup"><span data-stu-id="ab849-121">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="ab849-122">他のアプリケーションでファイルを開いている場合、インスタントメッセージでファイルを転送できない</span><span class="sxs-lookup"><span data-stu-id="ab849-122">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="ab849-123">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-123">**Issue:**</span></span>

<span data-ttu-id="ab849-124">別の Lync ユーザーにインスタントメッセージを追加して、Word 文書などのファイルを転送しようとすると、転送は成功したように見えますが、実際にはファイルの転送に失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-124">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="ab849-125">ファイルの種類のアイコンは Lync クライアントに表示されますが、目的の受信者がファイルを開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="ab849-125">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="ab849-126">送信に失敗したことを通知するエラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="ab849-126">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="ab849-127">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-127">**Workaround:**</span></span>

<span data-ttu-id="ab849-128">この問題を回避するには、インスタントメッセージでファイルを転送する前に、開いている開いているファイルまたはアプリケーションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ab849-128">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="ab849-129">Lync Server</span><span class="sxs-lookup"><span data-stu-id="ab849-129">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="ab849-130">Lync Server ストレージサービスのデータレプリケーションに失敗した場合、管理者は、古いストレージサービスキューアイテムのパフォーマンスカウンターを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-130">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="ab849-131">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-131">**Issue:**</span></span>

<span data-ttu-id="ab849-132">Lync Server ストレージサービスは、Windows Fabric を使用してレプリケーションを行います。</span><span class="sxs-lookup"><span data-stu-id="ab849-132">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="ab849-133">プライマリフロントエンドサーバーでデータが削除されたが、セカンダリフロントエンドサーバーでの削除に失敗した場合 (たとえば、フロントエンドサーバーに予期しないシャットダウンまたはエラーが発生した場合)、データを残して、"切り離された" 状態にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-133">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="ab849-134">孤立したデータは、パフォーマンスが低下したり、ドライブの空き領域を浪費したりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-134">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="ab849-135">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-135">**Workaround:**</span></span>

<span data-ttu-id="ab849-136">この問題を回避するには、イベント (Id\_=\_32058\_)\_と\_\_"いいね!" の**よう**に、CRITICAL\_(\_id = 32059) が使用されていることがイベントログで生成される場合、管理者は、"指定した期間が**古いキュー項目の数を指定**した名前で、フロントエンドサーバーのパフォーマンスカウンターを確認してください</span><span class="sxs-lookup"><span data-stu-id="ab849-136">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="ab849-137">このパフォーマンスカウンターが大きい値 (たとえば、50,000 より大きい値) である場合、管理者は Lync Server 2013 リソースキットで CleanuUpStorageServiceData ツールを実行し、孤立したデータがプールからすべて削除されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-137">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="ab849-138">このツールの詳細については、「Lync Server 2013 リソースキットドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab849-138">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="ab849-139">サーバーまたはプールの IP アドレス構成が変更されるたびに、Lync Server サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-139">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="ab849-140">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-140">**Issue:**</span></span>

<span data-ttu-id="ab849-141">IPv4 からデュアルスタックへの変更、またはデュアルスタックから Ipv6 への変更など、Lync Server 2013 の展開用に IP アドレス構成が変更された場合、すべてのサーバーコンポーネントは、サービスが再起動されるまで構成の変更を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab849-141">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="ab849-142">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-142">**Workaround:**</span></span>

<span data-ttu-id="ab849-143">この問題を回避するには、展開の IP アドレス構成を変更した後で Lync Server サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ab849-143">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="ab849-144">そのためには、Lync Server 管理シェルで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab849-144">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="ab849-145">ダイヤルイン会議の代理トランザクションコマンドレットは、Lync Server 2013 管理パックでは利用できなくなりました</span><span class="sxs-lookup"><span data-stu-id="ab849-145">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="ab849-146">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-146">**Issue:**</span></span>

<span data-ttu-id="ab849-147">ダイヤルイン会議の統合トランザクションコマンドレット**テスト**用の会議は、Lync Server 2013 管理パックでは利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ab849-147">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="ab849-148">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-148">**Workaround:**</span></span>

<span data-ttu-id="ab849-149">ダイヤルイン会議の代理トランザクションコマンドレットの使用**テスト-Csdial In会議**は、社内でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ab849-149">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="ab849-150">トラブルシューティングのために、管理者は Lync Server 管理シェルのコマンドレットを引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-150">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="ab849-151">必要に応じて、社内でコマンドレットを実行するためのプライベート管理パックを開発することもできます。</span><span class="sxs-lookup"><span data-stu-id="ab849-151">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="ab849-152">ログファイルがネットワーク共有にコピーされているときに、ネットワークトラフィックが中断されると、一元管理サービスは停止します</span><span class="sxs-lookup"><span data-stu-id="ab849-152">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="ab849-153">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-153">**Issue:**</span></span>

<span data-ttu-id="ab849-154">中央集中ログサービスがネットワークパスを使用するよう**に構成さ**れている場合 (CacheFileNetworkFolder パラメーターの値は有効な UNC パスです)、キャッシュされたログファイルはネットワーク共有にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="ab849-154">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="ab849-155">ファイルのコピー中にネットワークトラフィックが中断する場合は、集中化されたログサービスが停止する例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="ab849-155">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="ab849-156">サービスが最大3回自動的に再起動するように構成されているため、サービスは最初の3つの例外から回復します。</span><span class="sxs-lookup"><span data-stu-id="ab849-156">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="ab849-157">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-157">**Workaround:**</span></span>

<span data-ttu-id="ab849-158">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-158">There is no workaround for this issue.</span></span> <span data-ttu-id="ab849-159">問題を特定するには、"Lync Server 集中ログサービスエージェント" サービスが予期せず終了したときにログに記録する "サービスコントロールマネージャー" からイベント7031ログを監視します。</span><span class="sxs-lookup"><span data-stu-id="ab849-159">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="ab849-160">この問題が3回以上発生する場合は、 **Start-CsWindowService**コマンドレットを使用してサービスを手動で再開します。</span><span class="sxs-lookup"><span data-stu-id="ab849-160">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="ab849-161">ストレージサービスキューアイテムを手動でインポートする必要がある</span><span class="sxs-lookup"><span data-stu-id="ab849-161">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="ab849-162">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-162">**Issue:**</span></span>

<span data-ttu-id="ab849-163">Lync Server 2013 は、アーカイブされたメッセージや通話の詳細記録 (CDR) など、各フロントエンドサーバー上のデータベース上の会議とインスタントメッセージに関するデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="ab849-163">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="ab849-164">指定された宛先に配信される前に、データはデータベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-164">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="ab849-165">Lync Server 2013 は、パフォーマンスを向上させるために、長期間に処理されていないローカルデータベースのキューアイテムを定期的にエクスポートし、ファイルストアに保存します。</span><span class="sxs-lookup"><span data-stu-id="ab849-165">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="ab849-166">ファイルストアを使用できない場合は、各フロントエンドサーバーにアイテムが格納されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-166">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="ab849-167">プールのフェールオーバー中にデータが失われないように、同じ操作が発生します。</span><span class="sxs-lookup"><span data-stu-id="ab849-167">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="ab849-168">エクスポート操作の実行中、Lync Server ストレージサービスは、イベント Id (完全なフラッシュ操作が開始されました)、32076 (完全なフラッシュが完了)、32082 (メンテナンスレベルのフラッシュが開始されました) 32075 の各ステージをイベントログに記録し32083ます。完了)、32089 (データベースの読み込みによってフラッシュが発生しました)。</span><span class="sxs-lookup"><span data-stu-id="ab849-168">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="ab849-169">このデータは、処理されて最終的な送信先 (SQL Server または Exchange Server) に配信されるように、システムに自動的にインポートされることはありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-169">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="ab849-170">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-170">**Workaround:**</span></span>

<span data-ttu-id="ab849-171">システムにデータをインポートするには、管理者は Lync Server リソースキットの ImportStorageServiceData ツールを使用する必要があります。これにより、システムにデータが追加され、最終的な送信先に配信されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-171">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="ab849-172">UseNormalizationRules の既定値が False に変更されている場合、アドレス帳の Web クエリの検索は失敗します。</span><span class="sxs-lookup"><span data-stu-id="ab849-172">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="ab849-173">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-173">**Issue:**</span></span>

<span data-ttu-id="ab849-174">UseNormalizationRules の既定値が False に変更されると、アドレス帳の Web クエリの検索は失敗します。</span><span class="sxs-lookup"><span data-stu-id="ab849-174">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail.</span></span> <span data-ttu-id="ab849-175">既定値が変更されると、Lync クライアントユーザーは Lync アドレス帳の web クエリを使ってユーザーを検索することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="ab849-175">After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="ab849-176">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-176">**Workaround:**</span></span>

<span data-ttu-id="ab849-177">UseNormalizationRules の既定値が False に設定されている場合に、ユーザーが Lync Server 2013 で定義されている電話番号を使用できるようにするには、次の操作を行ってこの問題を回避します。</span><span class="sxs-lookup"><span data-stu-id="ab849-177">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="ab849-178">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab849-178">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ab849-179">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab849-179">Do one of the following:</span></span>
    
      - <span data-ttu-id="ab849-180">展開に Lync Server 2013 サーバーしか含まれていない場合は、次のコマンドレットをグローバルレベルで実行して、UseNormalizationRules と IgnoreGenericRules の値を True に変更します。</span><span class="sxs-lookup"><span data-stu-id="ab849-180">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="ab849-181">展開に Lync Server 2013 および Lync Server 2010 または Office Communications Server 2007 R2 の組み合わせが含まれている場合は、次のコマンドレットを実行して、トポロジの各 Lync Server 2013 プールに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ab849-181">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="ab849-182">CMS のレプリケーションがすべてのプールで行われるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="ab849-182">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="ab849-183">展開の電話の正規化規則ファイルを変更して、コンテンツをクリアします。</span><span class="sxs-lookup"><span data-stu-id="ab849-183">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="ab849-184">ファイルは、各 Lync Server 2013 プールのファイル共有にあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-184">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="ab849-185">ファイルが表示されていない場合は、"\_会社電話\_番号\_の正規化\_ルール .txt" という名前の空のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab849-185">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="ab849-186">すべてのフロントエンドプールが新しいファイルを読み取るまで数分待ちます。</span><span class="sxs-lookup"><span data-stu-id="ab849-186">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="ab849-187">展開の各 Lync Server 2013 プールで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab849-187">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="ab849-188">アドレス帳サーバーエラーイベント21054が Lync 2013 プールごとに1回生成される</span><span class="sxs-lookup"><span data-stu-id="ab849-188">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="ab849-189">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-189">**Issue:**</span></span>

<span data-ttu-id="ab849-190">Lync Server 2013 アドレス帳サーバーでは、毎日のメンテナンス実行時に、毎日1回エラーイベント21054が生成されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-190">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="ab849-191">また、更新が成功した場合でも、管理者が**csAddressBook**コマンドレットを実行するたびにエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-191">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="ab849-192">ただし、更新が成功した場合は、このエラーイベントを無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-192">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="ab849-193">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-193">**Workaround:**</span></span>

<span data-ttu-id="ab849-194">このエラーイベントが発生した場合は、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab849-194">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="ab849-195">コマンドレットで、インデックスを作成しない、または破棄されたオブジェクトがないと報告された場合、エラーイベント21054は安全に無視できます。</span><span class="sxs-lookup"><span data-stu-id="ab849-195">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="ab849-196">さらに、System Center Operations Manager では、キー正常性インジケータ (KHI) のアドレス帳のユーザーが正しくインデックス処理されていることを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-196">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="ab849-197">エッジプールで IPv6 が構成されていると、要求が失敗することがある</span><span class="sxs-lookup"><span data-stu-id="ab849-197">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="ab849-198">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-198">**Issue:**</span></span>

<span data-ttu-id="ab849-199">エッジプールで IPv6 が構成されている場合、エッジプールへの要求が失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-199">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="ab849-200">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-200">**Workaround:**</span></span>

<span data-ttu-id="ab849-201">この問題を回避するには、IPv6 でエッジプールを構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="ab849-201">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="ab849-202">プールのフェイルバック中に csPoolFailback コマンドレットが失敗することがある</span><span class="sxs-lookup"><span data-stu-id="ab849-202">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="ab849-203">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-203">**Issue:**</span></span>

<span data-ttu-id="ab849-204">プールをフェイルバックしようとすると、 **csPoolFailback**コマンドレットが失敗することがあります。「再試行後に hydration プロセスを完了できませんでした」というエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-204">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="ab849-205">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-205">**Workaround:**</span></span>

<span data-ttu-id="ab849-206">この問題を回避するには、もう一度コマンドレットを実行し、コマンドレットが正常に完了するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="ab849-206">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds.</span></span> <span data-ttu-id="ab849-207">フェイルバックプロセスが完了するまで数分かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ab849-207">Note that the failback process can take several minutes to complete.</span></span> <span data-ttu-id="ab849-208">2万ユーザーがいるプールの場合、最大60分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-208">It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="ab849-209">フロントエンドサーバーを既に確立されているプール (ハイブリッド、Skype for Business Online) に追加すると、データが失われることがある</span><span class="sxs-lookup"><span data-stu-id="ab849-209">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="ab849-210">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-210">**Issue:**</span></span>

<span data-ttu-id="ab849-211">この問題は、プールに複数のフロントエンドサーバーがある環境で、フロントエンドサーバーの1つを再起動するか、またはプールの一部ではない新しいフロントエンドサーバーを追加することによって発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-211">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="ab849-212">データがアーカイブされているユーザーは、プールのデータアーカイブの安定した分布が確立されるまで、データの損失が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-212">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool.</span></span> <span data-ttu-id="ab849-213">このデータ損失の可能性がある期間は、人同士の会話で15分に制限され、会議に30分の通話が可能です。</span><span class="sxs-lookup"><span data-stu-id="ab849-213">This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="ab849-214">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-214">**Workaround:**</span></span>

<span data-ttu-id="ab849-215">プール内のフロントエンドサーバーを1つずつ開始する代わりに、管理を実行する場合は、プールを別のプールにフェールオーバーして、サーバーの保守タスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-215">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="ab849-216">メンテナンスタスクを実行する前にサービスを利用できないようにすることもできます。メンテナンスが完了したら、空き時間情報を復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="ab849-216">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="ab849-217">管理者は、取得-CsClientAccessLicense コマンドレットを使用してライセンシーの数を取得できません</span><span class="sxs-lookup"><span data-stu-id="ab849-217">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="ab849-218">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-218">**Issue:**</span></span>

<span data-ttu-id="ab849-219">管理者は、 **CsClientAccessLicense**コマンドレットを使用して、クライアントライセンスの正確な使用状況を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab849-219">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="ab849-220">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-220">**Workaround:**</span></span>

<span data-ttu-id="ab849-221">サーバーのライセンスの種類を確認するには、ユーザーの**取得サービス**コマンドレットを実行して、すべてのデータベースの完全修飾ドメイン名 (FDQNs) を取得します。</span><span class="sxs-lookup"><span data-stu-id="ab849-221">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="ab849-222">フロントエンドサーバーの FQDN がバックエンドデータベースの FQDN と同じである場合、ライセンスは標準エディションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="ab849-222">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="ab849-223">それ以外の場合は、ライセンスは Enterprise edition ライセンスです。</span><span class="sxs-lookup"><span data-stu-id="ab849-223">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="ab849-224">クライアントのライセンス数が正確に報告されていない</span><span class="sxs-lookup"><span data-stu-id="ab849-224">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="ab849-225">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-225">**Issue:**</span></span>

<span data-ttu-id="ab849-226">クライアントのライセンス数を確認するときに、次のような状況が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-226">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="ab849-227">**モバイルユーザーのライセンス数が正しくない**</span><span class="sxs-lookup"><span data-stu-id="ab849-227">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="ab849-228">ライセンス数は、デバイスベースのユーザーの一意の IP アドレスの数に基づいています。</span><span class="sxs-lookup"><span data-stu-id="ab849-228">The license count is based on the number of unique IP addresses for device-based users.</span></span> <span data-ttu-id="ab849-229">ライセンス数は、次のように制限されています。</span><span class="sxs-lookup"><span data-stu-id="ab849-229">The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="ab849-230">ユーザーの IP アドレスが Lync セッション中に変更されると、ライセンスは過大にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="ab849-230">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="ab849-231">この問題は、ユーザーがデスクトップクライアントで複数の場所から Lync Server に接続したときに発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-231">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="ab849-232">ユーザーがモバイルクライアントに接続すると、デバイスの IP アドレスを確認できないため、ライセンスはカウントされます。</span><span class="sxs-lookup"><span data-stu-id="ab849-232">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="ab849-233">**ライセンスは、公衆交換電話網 (PSTN) 通話、Lync クライアント、PSTN 回線への Lync クライアント通話、PSTN 回線に転送された Lync 通話に対して2回カウントされます。**</span><span class="sxs-lookup"><span data-stu-id="ab849-233">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="ab849-234">次のシナリオでは、電話番号と Lync ユーザーの両方がカウントされ、使用されているライセンス数が判断されるため、2つの追加ライセンスは1つではなくカウントされます。</span><span class="sxs-lookup"><span data-stu-id="ab849-234">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used.</span></span> <span data-ttu-id="ab849-235">正確なライセンスデータを取得するには、電話番号によって生成されたライセンスを手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="ab849-235">To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="ab849-236">Lync への PSTN 電話通話</span><span class="sxs-lookup"><span data-stu-id="ab849-236">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="ab849-237">PSTN 回線への Lync 通話</span><span class="sxs-lookup"><span data-stu-id="ab849-237">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="ab849-238">Lync への PSTN 通話。その後、Lync が着信を PSTN 回線に転送します。</span><span class="sxs-lookup"><span data-stu-id="ab849-238">A PSTN call to Lync, and then Lync forwards the call to a PSTN line.</span></span> <span data-ttu-id="ab849-239">いずれかの PSTN 線がカウントされます。</span><span class="sxs-lookup"><span data-stu-id="ab849-239">One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="ab849-240">**ログオンしている Lync 携帯電話のライセンスはカウントされません**</span><span class="sxs-lookup"><span data-stu-id="ab849-240">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="ab849-241">ユーザーが Lync 認定電話を使用している場合、電話のログイン後も接続されたままで、ログイン状態が維持されている場合は、ライセンスの照会が電話のログイン後に行われると、電話はライセンスを使用しているものとしてカウントされません。</span><span class="sxs-lookup"><span data-stu-id="ab849-241">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="ab849-242">**電話会議に参加している PSTN 電話にカウントされたライセンス**</span><span class="sxs-lookup"><span data-stu-id="ab849-242">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="ab849-243">ユーザーが PSTN 電話を使って会議に参加すると、会議に参加するためのライセンスが誤ってカウントされます。</span><span class="sxs-lookup"><span data-stu-id="ab849-243">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference.</span></span> <span data-ttu-id="ab849-244">ただし、PSTN 電話を使って会議に参加する場合はライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-244">However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="ab849-245">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-245">**Workaround:**</span></span>

1.  <span data-ttu-id="ab849-246">**モバイルユーザーのライセンス数が正しくない**</span><span class="sxs-lookup"><span data-stu-id="ab849-246">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="ab849-247">同じデバイスに属している IP アドレスを手動で特定して、ライセンス数のいずれかを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-247">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="ab849-248">この問題の回避策は、Lync クライアントで接続しているモバイルデバイスには対応していません。</span><span class="sxs-lookup"><span data-stu-id="ab849-248">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="ab849-249">**ライセンスは、Lync クライアントへの PSTN 通話、PSTN 回線への Lync クライアント通話、PSTN 回線への lync 通話の転送について2回カウントされます。**</span><span class="sxs-lookup"><span data-stu-id="ab849-249">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="ab849-250">PSTN 電話番号を手動で特定し、生成されたライセンス数を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-250">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="ab849-251">**ログインしている Lync 携帯電話のライセンスはカウントされません**</span><span class="sxs-lookup"><span data-stu-id="ab849-251">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="ab849-252">Lync 携帯電話を設定して、ログオフした後、3ヶ月ごとに定期的にログオンすることができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-252">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="ab849-253">**電話会議に参加している PSTN 電話にカウントされたライセンス**</span><span class="sxs-lookup"><span data-stu-id="ab849-253">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="ab849-254">電話会議に参加するために使用される PSTN 電話番号を手動で特定して、電話番号によって生成されたライセンスを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-254">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="ab849-255">Silverlight 5 にアップグレードした後、Lync Server コントロールパネルが VMware 環境で動作しなくなります。</span><span class="sxs-lookup"><span data-stu-id="ab849-255">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="ab849-256">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-256">**Issue:**</span></span>

<span data-ttu-id="ab849-257">VMware 環境で Lync Server コントロールパネルを使用すると、Microsoft Silverlight をバージョン5にアップグレードした後に Lync Server コントロールパネルが機能しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-257">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="ab849-258">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-258">**Workaround:**</span></span>

<span data-ttu-id="ab849-259">この問題を回避するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ab849-259">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="ab849-260">Silverlight 5 をアンインストールし、から[https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)silverlight 4 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ab849-260">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="ab849-261">Lync Server コントロールパネルに、VMware 仮想コンピューターではないコンピューターからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ab849-261">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="ab849-262">Lync server の管理ツールがコンピューターにインストールされている場合は、サーバーの Windows の [**スタート**] メニューから Lync Server コントロールパネルを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-262">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="ab849-263">Lync Server コントロールパネルには、web ブラウザーを使用してアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ab849-263">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="ab849-264">この URL\<は https://フロントエンド\_プール\_の fqdn\>に似ています/cscp.</span><span class="sxs-lookup"><span data-stu-id="ab849-264">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="ab849-265">ユーザーの識別名が Active Directory で変更された後、アドレス帳サービスのユーザー情報が更新されない</span><span class="sxs-lookup"><span data-stu-id="ab849-265">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="ab849-266">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-266">**Issue:**</span></span>

<span data-ttu-id="ab849-267">Active Directory ドメインサービスでユーザーの識別名 (DN とも呼ばれます) が変更された場合、アドレス帳サービス (ABS) では、追加の変更は更新されません。</span><span class="sxs-lookup"><span data-stu-id="ab849-267">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="ab849-268">この操作を行っても、ユーザーのサインインやプレゼンスには影響はありませんが、SIP アドレスが変更された場合、ユーザーは、古い SIP アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="ab849-268">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="ab849-269">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-269">**Workaround:**</span></span>

<span data-ttu-id="ab849-270">この問題を回避するには、ユーザーの DN を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="ab849-270">To work around this issue, do not change a user’s DN.</span></span> <span data-ttu-id="ab849-271">ユーザーの DN を以前の値に戻した場合、更新はアドレス帳サービスに反映されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-271">If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="ab849-272">インストール</span><span class="sxs-lookup"><span data-stu-id="ab849-272">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="ab849-273">ASCII 以外の文字を使用すると、Lync server が起動しない場合がある</span><span class="sxs-lookup"><span data-stu-id="ab849-273">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="ab849-274">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-274">**Issue:**</span></span>

<span data-ttu-id="ab849-275">エクスポート先のフォルダー名に ASCII 以外の文字 (UNICODE、2バイト文字セット (DBCS)、UTF-8、UTF-16 など) が含まれている場合、セットアップは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ab849-275">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="ab849-276">また、セットアップは成功しますが、ASCII 以外の文字が次のいずれかに含まれている場合は、サーバーが起動しません。</span><span class="sxs-lookup"><span data-stu-id="ab849-276">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="ab849-277">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="ab849-277">Computer name</span></span>

  - <span data-ttu-id="ab849-278">ドメイン名</span><span class="sxs-lookup"><span data-stu-id="ab849-278">Domain name</span></span>

  - <span data-ttu-id="ab849-279">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="ab849-279">User name</span></span>

  - <span data-ttu-id="ab849-280">ユーザー SIP URI</span><span class="sxs-lookup"><span data-stu-id="ab849-280">User SIP URI</span></span>

  - <span data-ttu-id="ab849-281">サービスアカウント名</span><span class="sxs-lookup"><span data-stu-id="ab849-281">Service account name</span></span>

<span data-ttu-id="ab849-282">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-282">**Workaround:**</span></span>

<span data-ttu-id="ab849-283">目的のフォルダー名、コンピューター名、ドメイン名、ユーザー名、ユーザー SIP URI、およびサービスアカウント名には ASCII 文字のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab849-283">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="ab849-284">"ヒープの破損" の修正プログラムは、Lync Server 2013 をインストールする前に、モジュールが IIS 7.5 の InsertEntityBody メソッドをインストールする必要がある場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="ab849-284">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="ab849-285">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-285">**Issue:**</span></span>

<span data-ttu-id="ab849-286">"ヒープの破損" の修正プログラムは、「モジュールが IIS 7.5 で InsertEntityBody メソッドを[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)呼び出すときに発生します。」 (264886[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)) は、Lync Server 2013 をインストールする前にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-286">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="ab849-287">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-287">**Workaround:**</span></span>

<span data-ttu-id="ab849-288">Microsoft ダウンロードセンターから修正プログラムをダウンロードしてインストール[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)します。</span><span class="sxs-lookup"><span data-stu-id="ab849-288">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="ab849-289">Lync Server 2013 が ITA Windows Server 2012 OS RTM バージョンでインストールできない</span><span class="sxs-lookup"><span data-stu-id="ab849-289">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="ab849-290">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-290">**Issue:**</span></span>

<span data-ttu-id="ab849-291">Windows Fabric のインストールに失敗したため、ITA Windows Server 2012 で Lync Server 2013 のインストールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="ab849-291">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="ab849-292">ファブリックトレースは、HH: MM: SS という時刻形式で作成されるため、Windows ファブリックインストールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="ab849-292">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS.</span></span> <span data-ttu-id="ab849-293">ただし、ITA Windows Server では、時刻の形式は HH です。MM.SS。</span><span class="sxs-lookup"><span data-stu-id="ab849-293">However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="ab849-294">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-294">**Workaround:**</span></span>

<span data-ttu-id="ab849-295">この問題を回避するには、Lync Server 2013 をインストールする前にシステムレジストリを更新します。</span><span class="sxs-lookup"><span data-stu-id="ab849-295">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="ab849-296">更新する必要があるレジストリキーは、HKEY\_ユーザー\\です。既定\\のコントロール\\パネル\\国際形式の書式。</span><span class="sxs-lookup"><span data-stu-id="ab849-296">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="ab849-297">次のように Windows PowerShell コマンドラインインターフェイスを使用して、"s" 形式の値を HH: mm: ss に変更します。</span><span class="sxs-lookup"><span data-stu-id="ab849-297">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="ab849-298">Windows PowerShell を起動し、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab849-298">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="ab849-299">現在の値を表示するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab849-299">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="ab849-300">インストールの完了後に復元できるように、現在の形式の値をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="ab849-300">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="ab849-301">新しい値に設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab849-301">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="ab849-302">Lync Server 2013 が正常にインストールされた後、次のコマンドレットを実行して、その形式の元の値を復元します。</span><span class="sxs-lookup"><span data-stu-id="ab849-302">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="ab849-303">Set-ItemProperty $a-Name という <の値について、手順3でメモした値を表示します。</span><span class="sxs-lookup"><span data-stu-id="ab849-303">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="ab849-304">上の> "</span><span class="sxs-lookup"><span data-stu-id="ab849-304">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="ab849-305">モビリティ</span><span class="sxs-lookup"><span data-stu-id="ab849-305">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="ab849-306">サーバーのフェールオーバープロセス中のモバイルクライアントの問題</span><span class="sxs-lookup"><span data-stu-id="ab849-306">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="ab849-307">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-307">**Issue:**</span></span>

<span data-ttu-id="ab849-308">Lync サーバーに障害が発生してフェールオーバープロセスが開始されると、次の問題がモバイルクライアントユーザーに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-308">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="ab849-309">フェールオーバーの開始後、最長10分間、Lync の着信またはシグナルがありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-309">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="ab849-310">着信チャット要求を受け入れることができません</span><span class="sxs-lookup"><span data-stu-id="ab849-310">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="ab849-311">障害が発生したサーバーがユーザーのホームサーバーである場合、会議に参加できない</span><span class="sxs-lookup"><span data-stu-id="ab849-311">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="ab849-312">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-312">**Workaround:**</span></span>

<span data-ttu-id="ab849-313">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-313">There is no workaround for this issue.</span></span> <span data-ttu-id="ab849-314">フェールオーバープロセスが完了すると、通常の機能が復元されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-314">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="ab849-315">モバイルユーザーが別の Lync エンドポイントからの着信を拒否した場合、その通話は Lync モバイルクライアントでの不在着信として表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-315">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="ab849-316">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-316">**Issue:**</span></span>

<span data-ttu-id="ab849-317">モバイルユーザーが着信を拒否した場合に、別の Lync エンドポイントから発信された通話は、デバイス呼び出しリストの電話ではなく、Lync モバイルクライアントで不在着信した会話として表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-317">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="ab849-318">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-318">**Workaround:**</span></span>

<span data-ttu-id="ab849-319">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-319">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="ab849-320">連絡先を検索するときに、モバイルクライアントでフェデレーション連絡先の表示名が表示されない場合がある</span><span class="sxs-lookup"><span data-stu-id="ab849-320">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="ab849-321">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-321">**Issue:**</span></span>

<span data-ttu-id="ab849-322">フェデレーションされた連絡先の表示名は、連絡先リストでフェデレーション連絡先を検索する場合など、一部のシナリオでは表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-322">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="ab849-323">この問題は、Lync モバイルクライアントからの連絡先に対してアクティブなプレゼンスサブスクリプションがない場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-323">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="ab849-324">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-324">**Workaround:**</span></span>

<span data-ttu-id="ab849-325">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-325">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="ab849-326">モバイルクライアントでは、会議に招待された不在着信した会話に出席者とタイムスタンプ情報が含まれていない</span><span class="sxs-lookup"><span data-stu-id="ab849-326">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="ab849-327">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-327">**Issue:**</span></span>

<span data-ttu-id="ab849-328">モバイルクライアントで、不在着信した会話が会議に招待された場合、不在着信した会話メッセージに出席者とタイムスタンプ情報が表示されません。</span><span class="sxs-lookup"><span data-stu-id="ab849-328">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="ab849-329">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-329">**Workaround:**</span></span>

<span data-ttu-id="ab849-330">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-330">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="ab849-331">VoIP を使用して電話をかけるモバイルクライアントユーザーが、Exchange 2010 以前のバージョンでボイスメールを構成しているユーザーのボイスメールを残すことができない</span><span class="sxs-lookup"><span data-stu-id="ab849-331">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="ab849-332">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-332">**Issue:**</span></span>

<span data-ttu-id="ab849-333">モバイルクライアントユーザーが VoIP を使用して通話を発信している場合、ユーザーは、Microsoft Exchange Server 2007 または Microsoft Exchange Server 2010 でボイスメールを使用するように構成されたユーザーのボイスメールメッセージを残すことはできません。</span><span class="sxs-lookup"><span data-stu-id="ab849-333">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="ab849-334">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-334">**Workaround:**</span></span>

<span data-ttu-id="ab849-335">この問題を回避するには、Exchange 2010 と SP1 以降のバージョンの Microsoft Exchange Server を使用します。</span><span class="sxs-lookup"><span data-stu-id="ab849-335">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="ab849-336">モバイルクライアントでクライアントのバージョン構成の URL がブロックされていると、誤ったエラーメッセージが表示されることがある</span><span class="sxs-lookup"><span data-stu-id="ab849-336">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="ab849-337">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-337">**Issue:**</span></span>

<span data-ttu-id="ab849-338">モバイルクライアントでクライアントバージョン構成の**URL をブロック**すると、クライアントバージョンがサポートされていない場合に誤ったエラーメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-338">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="ab849-339">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-339">**Workaround:**</span></span>

<span data-ttu-id="ab849-340">この問題を回避するには、 **URL を**指定して block の代わりに**block**を使うようにクライアントのバージョン構成を構成します。</span><span class="sxs-lookup"><span data-stu-id="ab849-340">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="ab849-341">会議</span><span class="sxs-lookup"><span data-stu-id="ab849-341">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="ab849-342">Lync Server 2013 フロントエンドサーバーで実行されているウイルス対策ソフトウェアが原因で、アプリケーションドメインのリサイクルが発生し、Lync Web App 2013、Lync Mobile 2010、Lync Mobile 2013 クライアントのサービスが一時的に停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-342">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="ab849-343">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-343">**Issue:**</span></span>

<span data-ttu-id="ab849-344">ウイルス対策ソフトウェアを使用すると、アプリケーションドメインを再起動することができます。これにより、Lync Mobility Service 2013 および統合通信 (UC) Web API クライアントアプリケーション (Lync Web App 2013、Lync Mobile 2010、Lync Mobile 2013) が状態を失います。</span><span class="sxs-lookup"><span data-stu-id="ab849-344">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="ab849-345">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-345">**Workaround:**</span></span>

<span data-ttu-id="ab849-346">この問題を回避するには、Web コンポーネントと .NET framework を含むフォルダーをウイルススキャンで除外します。</span><span class="sxs-lookup"><span data-stu-id="ab849-346">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="ab849-347">詳細については、「Microsoft サポート技術情報の記事 312592 "PRB: ASP.NET で" アプリケーションが再起動します "と[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)いうエラーが表示されています。</span><span class="sxs-lookup"><span data-stu-id="ab849-347">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="ab849-348">次のフォルダーを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-348">The following folders should be excluded:</span></span>

  - <span data-ttu-id="ab849-349">% ProgramFiles%\\Microsoft Lync Server 2013\\Web コンポーネント\\mcx\\Ext</span><span class="sxs-lookup"><span data-stu-id="ab849-349">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="ab849-350">% ProgramFiles%\\Microsoft Lync Server 2013\\Web コンポーネント\\mcx\\Int</span><span class="sxs-lookup"><span data-stu-id="ab849-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="ab849-351">% ProgramFiles%\\Microsoft Lync Server 2013\\Web コンポーネント\\ucwa\\Int</span><span class="sxs-lookup"><span data-stu-id="ab849-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="ab849-352">% ProgramFiles%\\Microsoft Lync Server 2013\\Web コンポーネント\\ucwa\\Ext</span><span class="sxs-lookup"><span data-stu-id="ab849-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="ab849-353">% Windir%\\Microsoft.NET\\Framework64\\v 4.0.30319\\Config</span><span class="sxs-lookup"><span data-stu-id="ab849-353">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="ab849-354">会議に参加するには、Windows Internet Explorer で ActiveX コントロールまたはネイティブ XMLHTTP のサポートが有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-354">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="ab849-355">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-355">**Issue:**</span></span>

<span data-ttu-id="ab849-356">Windows Internet Explorer の Internet browser 設定で、ユーザーが ActiveX コントロールとネイティブ XMLHTTP のサポートを無効にしている場合、Internet Explorer が既定のブラウザーとして選択されていると、ユーザーは会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="ab849-356">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="ab849-357">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-357">**Workaround:**</span></span>

<span data-ttu-id="ab849-358">Internet Explorer で ActiveX コントロールまたは "ネイティブ XMLHTTP サポート" を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ab849-358">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="ab849-359">Lync Server Web 会議サービスが、重要なモードから復元できない</span><span class="sxs-lookup"><span data-stu-id="ab849-359">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="ab849-360">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-360">**Issue:**</span></span>

<span data-ttu-id="ab849-361">システム障害が発生した場合に、クリティカルモードが有効になっていると、重要モードが開始され、会議が参加者に対して機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="ab849-361">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants.</span></span> <span data-ttu-id="ab849-362">管理者がシステムエラー (データベースの問題を修正するなど) を修正した後、データ会議サービスは自動的に回復しません。また、管理者は会議サービスを手動で再開して会議を再開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-362">After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="ab849-363">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-363">**Workaround:**</span></span>

<span data-ttu-id="ab849-364">システム障害が修正された後、管理者は会議サービスを手動で再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-364">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="ab849-365">外部の Office Web App サーバーの HTTP プロキシを無視する web 会議サービス</span><span class="sxs-lookup"><span data-stu-id="ab849-365">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="ab849-366">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-366">**Issue:**</span></span>

<span data-ttu-id="ab849-367">Web 会議サービスの外部に Office Web Apps サーバーを展開している場合 (つまり、社内ネットワークに接続されていないサーバーである)、インターネット、境界ネットワーク、Web 会議サービスに接続するには、次のような HTTP プロキシが必要です。Office Web Apps サーバーの検出は失敗します。</span><span class="sxs-lookup"><span data-stu-id="ab849-367">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="ab849-368">Web 会議サービスでは、[Office Web Apps サーバーセットアップ] の [トポロジビルダー] で定義されている HTTP プロキシ設定を無視します。</span><span class="sxs-lookup"><span data-stu-id="ab849-368">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="ab849-369">この結果、Lync クライアントは、会議の他の参加者と Microsoft PowerPoint 2010 共有を行うことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="ab849-369">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="ab849-370">オンプレミスの Lync Server をインストールしていて、内部ネットワークで Office Web Apps サーバーがオンプレミスにも構成されている場合、プロキシ構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-370">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="ab849-371">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-371">**Workaround:**</span></span>

<span data-ttu-id="ab849-372">唯一の回避策は、外部の Office Web Apps サーバーとの通信に HTTP プロキシを使用する必要がある展開構成を持たないことです。</span><span class="sxs-lookup"><span data-stu-id="ab849-372">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="ab849-373">電話会議プロバイダーの会議へのビデオの追加はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="ab849-373">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="ab849-374">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-374">**Issue:**</span></span>

<span data-ttu-id="ab849-375">ユーザーが音声会議プロバイダーの電話会議に参加している場合、ビデオの追加はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ab849-375">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="ab849-376">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-376">**Workaround:**</span></span>

<span data-ttu-id="ab849-377">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-377">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="ab849-378">IPv6 が有効になっているトポロジ lync Web App Silverlight プラグインを自動更新して、Lync Web App から画面共有機能を使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="ab849-378">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="ab849-379">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-379">**Issue:**</span></span>

<span data-ttu-id="ab849-380">IPv6 を有効にしてトポロジを構成すると、以前のバージョンの画面共有プラグインが既にインストールされている場合、ユーザーは Lync Web App クライアントから画面を共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab849-380">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="ab849-381">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-381">**Workaround:**</span></span>

<span data-ttu-id="ab849-382">Lync Web App を使って会議に参加するときに、画面共有プラグインの最新バージョンに更新するには、次の2つ**のファイル**で "4.0.7457.0" から "4.0.7577.380" に変更します。</span><span class="sxs-lookup"><span data-stu-id="ab849-382">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="ab849-383">% ProgramFiles%\\Microsoft Lync Server 15\\Web コンポーネント\\は\\、\\Int\\クライアント\\プラグイン ReachAppShPluginProperties にアクセスします</span><span class="sxs-lookup"><span data-stu-id="ab849-383">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="ab849-384">% ProgramFiles%\\Microsoft Lync Server 15\\Web コンポーネント\\は\\Ext\\クライアント\\プラグイン\\ReachAppShPluginProperties に到達します。</span><span class="sxs-lookup"><span data-stu-id="ab849-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="ab849-385">エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="ab849-385">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="ab849-386">場合によっては、IPv4 と IPv6 を使用するように構成されているコンピューターで実行されている Lync クライアントで、E911、メディアのバイパス、通話受付制御、位置ベースのルーティングなど、コンピューターの IP サブネットに依存する機能がサポートされていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-386">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="ab849-387">このセクションの情報は Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月に関係します。</span><span class="sxs-lookup"><span data-stu-id="ab849-387">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="ab849-388">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-388">**Issue:**</span></span>

<span data-ttu-id="ab849-389">使用しているコンピューターで、IPv4 および IPv6 デュアルスタックが有効になっていて、プロキシサーバーの DNS 解決に基づいている場合、クライアントはコンピューターの IPv6 アドレスを使ってサインインすることができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-389">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="ab849-390">この操作を行うと、Lync クライアントは IPv6 でサポートされている機能のみをサポートします。これにより、E911、メディアバイパス、通話受付制御、位置情報に基づくルーティングが除外されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-390">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="ab849-391">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-391">**Workaround:**</span></span>

<span data-ttu-id="ab849-392">この問題を回避するには、クライアントコンピューターで IPv6 サポートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ab849-392">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="ab849-393">エンタープライズ Voip がユーザーに対して構成されていない場合、ユーザーは [E164] 形式を使用して電話会議からダイヤルアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-393">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="ab849-394">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-394">**Issue:**</span></span>

<span data-ttu-id="ab849-395">エンタープライズボイスがユーザーに対して構成されていない場合は、ユーザーは [E164] 形式を使用して会議からのダイヤルアウトを成功させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-395">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="ab849-396">E164 形式が使用されていない場合、ユーザーは電話会議からダイヤルアウトすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ab849-396">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="ab849-397">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-397">**Workaround:**</span></span>

<span data-ttu-id="ab849-398">この問題を回避するために、エンタープライズボイスを有効にしていないユーザーは、E164 形式の数字を使って会議からダイヤルアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-398">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="ab849-399">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="ab849-399">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="ab849-400">ユーザーが [すべての招待と通信をブロックする] をオンにした場合、統合連絡先ストアが有効になっているときにプレゼンス状態が拒否されない</span><span class="sxs-lookup"><span data-stu-id="ab849-400">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="ab849-401">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-401">**Issue:**</span></span>

<span data-ttu-id="ab849-402">ユーザーが [すべての招待と通信をブロックする] をオンにした場合、統合連絡先ストアが有効になっている間、プレゼンス状態は拒否されません。</span><span class="sxs-lookup"><span data-stu-id="ab849-402">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="ab849-403">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-403">**Workaround:**</span></span>

<span data-ttu-id="ab849-404">この問題を回避するには、ユーザーに対してユニファイド連絡先ストアを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-404">To work around this issue, you can turn off the unified contact store for the user.</span></span> <span data-ttu-id="ab849-405">そのためには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab849-405">To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="ab849-406">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ab849-406">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="ab849-407">Office Communications Server 2007 R2 をオンプレミスで使用している場合、ハイブリッド展開での Skype for Business Online ユーザーのプレゼンス状態の表示はできません。ハイブリッド</span><span class="sxs-lookup"><span data-stu-id="ab849-407">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="ab849-408">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-408">**Issue:**</span></span>

<span data-ttu-id="ab849-409">この問題は、Lync Server 2013 ディレクターを使用している場合にハイブリッド展開で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-409">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="ab849-410">Skype for Business Online を使用しているユーザーのプレゼンス状態は、オンプレミスのユーザーに対して不明なプレゼンスとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-410">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="ab849-411">また、Skype for Business Online をホームとして使用しているユーザーは、Office Communications Server R2 オンプレミスユーザーのプレゼンス状態を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab849-411">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="ab849-412">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-412">**Workaround:**</span></span>

<span data-ttu-id="ab849-413">この問題を部分的に回避するには、Lync Server 2013 ディレクターではなく、Lync Server 2013 のオンプレミスプールをポイントするように、Skype for Business Online ユーザーのホームサーバー (msrtcsip-userenabled true presencehomeserver) を変更します。</span><span class="sxs-lookup"><span data-stu-id="ab849-413">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="ab849-414">オンプレミスフロントエンドサーバーでこの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ab849-414">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="ab849-415">この回避策では、Office Communications Server 2007 R2 に所属しているユーザーのプレゼンス状態が Skype for Business Online ユーザーに正しく表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-415">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="ab849-416">応答グループアプリケーション、コールパークアプリケーション、グループ通話のピックアップ</span><span class="sxs-lookup"><span data-stu-id="ab849-416">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="ab849-417">発信者は、相手を検索して通話を発信するときに、1秒間音楽の再生待ちを聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-417">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="ab849-418">このセクションの情報は Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月に関係します。</span><span class="sxs-lookup"><span data-stu-id="ab849-418">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="ab849-419">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-419">**Issue:**</span></span>

<span data-ttu-id="ab849-420">グループ通話の集配を使用して通話を取得すると、発信者は、取得側で通話を発信するときに、1秒間音楽を保留にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-420">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="ab849-421">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-421">**Workaround:**</span></span>

<span data-ttu-id="ab849-422">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-422">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="ab849-423">応答グループエージェントは、Lync Server 2010 エージェントコンソールを使用して、Lync Server 2010 の正式なエージェントグループのみにサインインしてサインアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-423">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="ab849-424">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-424">**Issue:**</span></span>

<span data-ttu-id="ab849-425">Lync server 2013 応答グループエージェントは、lync Server 2010 エージェントコンソールを使用して、lync server 2010 正式なエージェントグループに対してのみサインインし、サインアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-425">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="ab849-426">Lync Server 2010 エージェントコンソールでは、ユーザーが所属している Lync Server の2010応答グループのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="ab849-426">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="ab849-427">自分が属している Lync Server 2013 応答グループを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab849-427">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="ab849-428">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-428">**Workaround:**</span></span>

<span data-ttu-id="ab849-429">応答グループエージェントが Lync Server 2013 ユーザーであり、Lync Server 2013 の正式なエージェントグループの一部である場合、ユーザーはブラウザーの web リンクを通じて直接 Lync Server 2013 エージェントコンソールにアクセスし、Lync Server 2013 エージェントグループにサインインしてサインアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-429">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="ab849-430">Lync server 2010 応答グループエージェントは、Lync Server 2013 応答グループの代理として通話を発信することはできません</span><span class="sxs-lookup"><span data-stu-id="ab849-430">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="ab849-431">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-431">**Issue:**</span></span>

<span data-ttu-id="ab849-432">Lync server 2013 応答グループのエージェントである Lync Server 2010 ユーザーは、応答グループの代理として通話を発信できません。</span><span class="sxs-lookup"><span data-stu-id="ab849-432">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="ab849-433">Lync Server 2013 応答グループは、通話を発信するために Lync クライアントでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="ab849-433">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="ab849-434">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-434">**Workaround:**</span></span>

<span data-ttu-id="ab849-435">この問題を回避するには、Lync Server 2010 ユーザーを Lync Server 2013 に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-435">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="ab849-436">Lync server 2013 に移行された後に、Lync Server 2010 から応答グループを削除すると、応答グループが着信を受け付けることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="ab849-436">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="ab849-437">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-437">**Issue:**</span></span>

<span data-ttu-id="ab849-438">Lync server 2010 から Lync server 2013 に移行された応答グループが lync server の [コントロールパネル] または [Lync Server 管理シェル] から2010削除された場合、Lync Server 2013 の応答グループは、着信の受信を停止します。</span><span class="sxs-lookup"><span data-stu-id="ab849-438">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="ab849-439">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-439">**Workaround:**</span></span>

<span data-ttu-id="ab849-440">この問題を回避するには、Lync Server 2010 から Lync Server 2013 に移行された返信グループを Lync server 2010 から削除しないようにします。</span><span class="sxs-lookup"><span data-stu-id="ab849-440">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="ab849-441">応答グループが既に削除されている場合は、Lync Server 2013 で再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-441">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="ab849-442">作成時に新しいマネージワークフローが非アクティブに設定されると、ワークフローの展開に失敗します。</span><span class="sxs-lookup"><span data-stu-id="ab849-442">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="ab849-443">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-443">**Issue:**</span></span>

<span data-ttu-id="ab849-444">作成時に新しいマネージワークフローが非アクティブに設定されると、ワークフローの展開が失敗します。</span><span class="sxs-lookup"><span data-stu-id="ab849-444">When a new managed workflow is set to inactive when created, deployment of the workflow will fail.</span></span> <span data-ttu-id="ab849-445">この問題は、作成時にワークフローが [非アクティブ] に設定されているときに発生しますが、展開された後に [非アクティブ] に設定するように編集されたワークフローには影響しません。</span><span class="sxs-lookup"><span data-stu-id="ab849-445">This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="ab849-446">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-446">**Workaround:**</span></span>

<span data-ttu-id="ab849-447">ワークフローを作成して展開するときに、ワークフローをアクティブとして設定し、展開します。</span><span class="sxs-lookup"><span data-stu-id="ab849-447">When creating and deploying a workflow, set the workflow as active and then deploy it.</span></span> <span data-ttu-id="ab849-448">ワークフローが正常に展開されると、ワークフローが編集可能になり、[非アクティブ] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-448">After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="ab849-449">所有者プールから応答グループを削除すると、バックアッププールの応答グループがバックアッププールにインポートされた場合に、フェールオーバー中に着信を受け付けることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="ab849-449">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="ab849-450">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-450">**Issue:**</span></span>

<span data-ttu-id="ab849-451">所有者を上書きせずに、プライマリプールによって所有されている応答グループがバックアッププールにインポートされていて、所有者プールから応答グループが削除された場合、バックアッププール内の応答グループは、フェールオーバー中に着信通話を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="ab849-451">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="ab849-452">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-452">**Workaround:**</span></span>

<span data-ttu-id="ab849-453">プライマリプールで応答グループを再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-453">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="ab849-454">次に、プライマリプールから応答グループの構成をエクスポートして、もう一度バックアッププールにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-454">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="ab849-455">バックアッププールで応答グループを再作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ab849-455">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="ab849-456">この場合、バックアッププールは応答グループの所有者プールになります。</span><span class="sxs-lookup"><span data-stu-id="ab849-456">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="ab849-457">受信要求が応答グループの代理として実行されている場合は、保留中の通話をコールパークアプリケーションから取得できない</span><span class="sxs-lookup"><span data-stu-id="ab849-457">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="ab849-458">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-458">**Issue:**</span></span>

<span data-ttu-id="ab849-459">次の条件が満たされている場合は、保留中の通話の取得要求が失敗します。</span><span class="sxs-lookup"><span data-stu-id="ab849-459">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="ab849-460">エージェントが匿名応答グループの一部である</span><span class="sxs-lookup"><span data-stu-id="ab849-460">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="ab849-461">エージェントは、匿名応答グループを通じて、コールパークアプリケーションから保留中の通話を取得しようとします。</span><span class="sxs-lookup"><span data-stu-id="ab849-461">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="ab849-462">エージェントは、[代理人として呼び出し] オプションを通じて、または Lync アテンダントクライアントで同じオプションを使用して、軌道番号にダイヤルすることで、通話を取得しようとします。</span><span class="sxs-lookup"><span data-stu-id="ab849-462">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="ab849-463">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-463">**Workaround:**</span></span>

<span data-ttu-id="ab849-464">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-464">There are no workarounds for this issue.</span></span> <span data-ttu-id="ab849-465">保留中の呼び出しは、応答グループに代わって取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-465">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="ab849-466">Lync Server コントロール パネル、トポロジ ビルダー、および計画ツール</span><span class="sxs-lookup"><span data-stu-id="ab849-466">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="ab849-467">計画ツールの制限</span><span class="sxs-lookup"><span data-stu-id="ab849-467">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="ab849-468">このセクションの情報は Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月に関係します。</span><span class="sxs-lookup"><span data-stu-id="ab849-468">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="ab849-469">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-469">**Issue:**</span></span>

<span data-ttu-id="ab849-470">展開を計画する場合、計画ツールには次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-470">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="ab849-471">サポートされる最大10個のセントラルサイトがあります</span><span class="sxs-lookup"><span data-stu-id="ab849-471">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="ab849-472">各セントラルサイトは、最大で14個のブランチサイトを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-472">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="ab849-473">各セントラルサイトには、最大24万ユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-473">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="ab849-474">また、推奨されるトポロジを計算するときに、計画ツールには次の値は含まれません。</span><span class="sxs-lookup"><span data-stu-id="ab849-474">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="ab849-475">オンラインになっているユーザーの数</span><span class="sxs-lookup"><span data-stu-id="ab849-475">The number of users that are homed online</span></span>

  - <span data-ttu-id="ab849-476">XMPP フェデレーションが有効になっているユーザーのパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="ab849-476">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="ab849-477">Lync Web App を使用しているユーザーのパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="ab849-477">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="ab849-478">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-478">**Workaround:**</span></span>

<span data-ttu-id="ab849-479">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-479">There is no workaround for these issues.</span></span> <span data-ttu-id="ab849-480">計画ツールの詳細については、「[計画ツールを使用して Lync Server 2013 のトポロジを設計](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab849-480">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="ab849-481">オプションを更新するときに、計画ツールで、エッジネットワークに事前に定義された IP アドレスを使用できない場合がある</span><span class="sxs-lookup"><span data-stu-id="ab849-481">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="ab849-482">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-482">**Issue:**</span></span>

<span data-ttu-id="ab849-483">計画ツールを使用して設計を完了した後、エッジネットワークのオプションを変更すると、既存の IP アドレスを更新する代わりに、追加の IP アドレスを設計に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-483">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="ab849-484">この問題は、Edge ネットワーク図の詳細を表示しているときに、[**ここをクリックしてオプションを更新する**] を選択し、[構成オプション] ダイアログで、[edge ネットワーク] を選択します。 [**同じ fqdn と IP アドレスを使用しますが、エッジサーバー上のエッジサービスには異なるポートを使用**します] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ab849-484">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="ab849-485">変更を適用すると、新しい IP アドレスとエッジサーバーがデザインに追加されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-485">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="ab849-486">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-486">**Workaround:**</span></span>

<span data-ttu-id="ab849-487">現時点では、この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-487">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="ab849-488">Lync Server コントロールパネルの [すべてのユーザーをプールに移動] が期待どおりに動作しない場合がある</span><span class="sxs-lookup"><span data-stu-id="ab849-488">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="ab849-489">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-489">**Issue:**</span></span>

<span data-ttu-id="ab849-490">Lync Server コントロールパネルを使用して、1つのプールから、複数のドメインコントローラーと親/子ドメインを含む複雑な Active Directory 環境内の別のプールにすべてのユーザーを移動する場合、エラーメッセージが表示されることがあります。 "指定されたユーザーはレガシユーザーではありません。"</span><span class="sxs-lookup"><span data-stu-id="ab849-490">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="ab849-491">これは、複雑な Active Directory 環境でのレプリケーション時間が長くなったためです。</span><span class="sxs-lookup"><span data-stu-id="ab849-491">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="ab849-492">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-492">**Workaround:**</span></span>

<span data-ttu-id="ab849-493">この問題を回避するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ab849-493">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="ab849-494">Lync Server コントロールパネルで [フィルター] を使用して、従来のユーザーを検索し、それらのユーザーを選択して、[**すべてのユーザーをプールに**移動] ではなく、[**選択したユーザーをプールに移動] コマンド**を使用します。</span><span class="sxs-lookup"><span data-stu-id="ab849-494">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="ab849-495">Lync server 管理シェルを使用して、Lync Server コマンドレットを使用して、従来のユーザーをまとめて移動します。</span><span class="sxs-lookup"><span data-stu-id="ab849-495">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="ab849-496">Microsoft Silverlight ブラウザープラグインをバージョン5に更新した後に、Lync Server コントロールパネルが VMware 環境で動作を停止する</span><span class="sxs-lookup"><span data-stu-id="ab849-496">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="ab849-497">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-497">**Issue:**</span></span>

<span data-ttu-id="ab849-498">VMware 環境で Lync Server コントロールパネルを使用すると、Silverlight をバージョン5にアップグレードした後に Lync Server コントロールパネルが機能しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-498">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="ab849-499">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-499">**Workaround:**</span></span>

<span data-ttu-id="ab849-500">この問題を回避するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ab849-500">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="ab849-501">Silverlight 5 をアンインストールしてから、Silverlight 4 [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)をからインストールします。</span><span class="sxs-lookup"><span data-stu-id="ab849-501">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="ab849-502">Lync Server コントロールパネルを、VMware 仮想コンピューターではないコンピューターから開きます。</span><span class="sxs-lookup"><span data-stu-id="ab849-502">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="ab849-503">リモートコンピューターから Lync Server コントロールパネルを開くには、コンピューターに Lync Server 管理ツールをインストールして、Windows の [**スタート**] メニューから Lync Server コントロールパネルを起動します。</span><span class="sxs-lookup"><span data-stu-id="ab849-503">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="ab849-504">Web ブラウザーで URL を入力して、Lync Server コントロールパネルを開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="ab849-504">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="ab849-505">この URL\<は https://フロントエンド\_プール\_の fqdn\>に似ています/cscp.</span><span class="sxs-lookup"><span data-stu-id="ab849-505">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="ab849-506">トポロジビルダーでミラーリングデータベースを削除した後に、管理者がアンインストール-csMirrorDB コマンドレットを実行できない</span><span class="sxs-lookup"><span data-stu-id="ab849-506">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="ab849-507">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-507">**Issue:**</span></span>

<span data-ttu-id="ab849-508">管理者がトポロジビルダーでミラーリングデータベースを無効にして、トポロジビルダーでミラーリングデータベースを削除すると、管理者が**csMirrorDatabase**コマンドレットを実行して SQL Server からミラーリングを削除するようにメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-508">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="ab849-509">管理者がコマンドレットを実行しようとすると、失敗します。</span><span class="sxs-lookup"><span data-stu-id="ab849-509">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="ab849-510">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-510">**Workaround:**</span></span>

<span data-ttu-id="ab849-511">トポロジビルダーでプールの SQL ミラーリングを削除するには、最初にコマンドレットを使用して、SQL Server のミラーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-511">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="ab849-512">次に、トポロジ ビルダーを使用して、トポロジからミラーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="ab849-512">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="ab849-513">SQL Server でミラーを削除するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab849-513">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="ab849-514">たとえば、ミラーリングを削除してユーザーデータベースのデータベースをドロップするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ab849-514">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="ab849-515">*Dropexistingdatabases Onmirror*パラメーターを使うと、影響を受けたデータベースがミラーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-515">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="ab849-516">その後、トポロジからミラーを削除するために次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ab849-516">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="ab849-517">トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab849-517">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="ab849-518">[ **SQL ストアミラーリングを有効にする**] をオフにし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab849-518">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="ab849-519">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="ab849-519">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="ab849-520">バックエンドデータベースミラーリングの関係を変更する場合は、必ずプール内のすべてのフロントエンドサーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-520">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="ab849-521">管理者が、関連付けられている監視ストアを持つフロントエンドプールを使用して展開を削除しようとすると、検証エラーがトポロジビルダーで返される</span><span class="sxs-lookup"><span data-stu-id="ab849-521">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="ab849-522">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-522">**Issue:**</span></span>

<span data-ttu-id="ab849-523">管理者が、関連付けられている監視ストアでフロントエンドプールを含む展開を削除するために、管理者がトポロジビルダーで [**展開の削除**] を使用しようとした場合、トポロジビルダーに検証エラーが表示され、操作は続行されません。</span><span class="sxs-lookup"><span data-stu-id="ab849-523">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="ab849-524">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-524">**Workaround:**</span></span>

<span data-ttu-id="ab849-525">この問題を回避するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ab849-525">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="ab849-526">展開を削除する前に、監視ストアを削除します。</span><span class="sxs-lookup"><span data-stu-id="ab849-526">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="ab849-527">フロントエンドプールの監視ストアを追加してから、削除します。</span><span class="sxs-lookup"><span data-stu-id="ab849-527">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="ab849-528">計画ツールとトポロジビルダーとの間の常設チャットサーバーの展開情報に一貫性がない</span><span class="sxs-lookup"><span data-stu-id="ab849-528">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="ab849-529">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-529">**Issue:**</span></span>

<span data-ttu-id="ab849-530">Lync Server 2013 の計画ツールで、障害回復が有効になっている常設チャットサーバーの展開用のサイトトポロジ図を出力すると、サイトトポロジ図には複数の (物理) サイトが含まれており、それぞれに常設チャットサーバーが均等に割り当てられています。サービス.</span><span class="sxs-lookup"><span data-stu-id="ab849-530">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="ab849-531">Topology Builder では、すべての常設チャットサーバーは1つの (論理) サイトに属しているものとして表され、同じ常設チャットサーバープールノードの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-531">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="ab849-532">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-532">**Workaround:**</span></span>

<span data-ttu-id="ab849-533">現時点では、この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-533">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="ab849-534">ユーザーは、常設チャットサーバー展開の計画ツールの出力を分析し、特定のニーズに合わせてプランを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-534">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="ab849-535">版</span><span class="sxs-lookup"><span data-stu-id="ab849-535">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="ab849-536">監視</span><span class="sxs-lookup"><span data-stu-id="ab849-536">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="ab849-537">東アジアバージョンの Lync Server を使用すると、監視レポートの展開ウィザードで特定の状況で誤った文字が表示される</span><span class="sxs-lookup"><span data-stu-id="ab849-537">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="ab849-538">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-538">**Issue:**</span></span>

<span data-ttu-id="ab849-539">東アジアバージョンの Lync Server 2013 (中国語 (簡体字)、中国語 (繁体字)、日本語、韓国語など) を使用している場合、システムロケールが東アジア言語に設定されていないオペレーティングシステムでは、[監視レポートの展開] ウィザードが表示されます。ローカライズされたメッセージではなく、疑問符などの文字を表示します。</span><span class="sxs-lookup"><span data-stu-id="ab849-539">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="ab849-540">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-540">**Workaround:**</span></span>

<span data-ttu-id="ab849-541">この問題を解決するには、オペレーティングシステムと Lync Server 2013 のロケールを同じ言語に設定します。これにより、すべてのメッセージが正しく表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-541">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="ab849-542">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="ab849-542">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="ab849-543">特定の状況では、トップナビゲーションバーの最後のアイテムがクリックされると、Lync Server コントロールパネルのページ上のトップナビゲーションバーの最初のアイテムが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="ab849-543">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="ab849-544">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-544">**Issue:**</span></span>

<span data-ttu-id="ab849-545">Lync Server コントロールパネルのページの上部にあるナビゲーションバーで最後のアイテムをクリックすると、トップナビゲーションバーの最初のアイテムが非表示になるという3つの既知の場合があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-545">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="ab849-546">フランス語版のページ "Féderation et accès externe" で、"Partenaires d'accès XMPP" がクリックされると、"項目" Stratégie externe fédérés "が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="ab849-546">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="ab849-547">ドイツ語版の [クライアント] ページで、"Pushbenachrichtigungskonfiguration" がクリックされると、"Clientversionskonfiguration" 項目が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="ab849-547">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="ab849-548">ロシア語版の "Конфигурациясети" ページでは、"Маршрутрегиона" がクリックされると、項目 "Глобально" が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="ab849-548">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="ab849-549">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-549">**Workaround:**</span></span>

<span data-ttu-id="ab849-550">この問題を回避するには、ブラウザーで Lync Server コントロールパネルのページを更新します。</span><span class="sxs-lookup"><span data-stu-id="ab849-550">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="ab849-551">ページは、上部のナビゲーションバーに表示されているすべてのアイテムと共にブラウザーに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="ab849-551">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="ab849-552">アドレス帳</span><span class="sxs-lookup"><span data-stu-id="ab849-552">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="ab849-553">一部の言語で、アドレス帳のインデックス処理が予期したとおりに機能しない</span><span class="sxs-lookup"><span data-stu-id="ab849-553">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="ab849-554">このセクションの情報は Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月に関係します。</span><span class="sxs-lookup"><span data-stu-id="ab849-554">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="ab849-555">ユーザーのプロパティにインデックス付きフィールドが含まれており、そのフィールドにインデックスを作成できない文字しか含まれていない場合、そのユーザーはアドレス帳で実行された検索には表示されません。</span><span class="sxs-lookup"><span data-stu-id="ab849-555">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="ab849-556">次の文字とロケールのインデックスを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab849-556">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="ab849-557">大文字のキリル文字、ギリシャ文字、およびアルメニア文字</span><span class="sxs-lookup"><span data-stu-id="ab849-557">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="ab849-558">大文字アクセント記号付き文字</span><span class="sxs-lookup"><span data-stu-id="ab849-558">Upper-case accented characters</span></span>

  - <span data-ttu-id="ab849-559">タイ語</span><span class="sxs-lookup"><span data-stu-id="ab849-559">Thai</span></span>

  - <span data-ttu-id="ab849-560">ラオス</span><span class="sxs-lookup"><span data-stu-id="ab849-560">Lao</span></span>

  - <span data-ttu-id="ab849-561">ビルマ</span><span class="sxs-lookup"><span data-stu-id="ab849-561">Myanmar</span></span>

  - <span data-ttu-id="ab849-562">バナー</span><span class="sxs-lookup"><span data-stu-id="ab849-562">Devanagari</span></span>

  - <span data-ttu-id="ab849-563">語</span><span class="sxs-lookup"><span data-stu-id="ab849-563">Ethiopic</span></span>

  - <span data-ttu-id="ab849-564">語</span><span class="sxs-lookup"><span data-stu-id="ab849-564">Tibetan</span></span>

  - <span data-ttu-id="ab849-565">ベンガル語</span><span class="sxs-lookup"><span data-stu-id="ab849-565">Bengali</span></span>

  - <span data-ttu-id="ab849-566">グジャラート語</span><span class="sxs-lookup"><span data-stu-id="ab849-566">Gujarati</span></span>

  - <span data-ttu-id="ab849-567">テルグ語</span><span class="sxs-lookup"><span data-stu-id="ab849-567">Telugu</span></span>

  - <span data-ttu-id="ab849-568">その他のすべてのインド系言語スクリプト</span><span class="sxs-lookup"><span data-stu-id="ab849-568">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="ab849-569">Lync Web App、Web Scheduler、Web コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ab849-569">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="ab849-570">Lync Web Scheduler、ダイヤルイン、参加起動ツール、常設チャットルーム管理、および OCTab の一部の言語の言語のフォールバックは、期待どおりに動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-570">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="ab849-571">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-571">**Issue:**</span></span>

<span data-ttu-id="ab849-572">Web ブラウザーでニュートラルロケールを選択する場合 (Internet Explorer の場合) たとえば、言語、スクリプト、ロケール ("ノルウェー語、 \[ブークモール\](ノルウェー語) \[nb-いいえ\]" など) を指定しない言語名は、Lync Web Scheduler、ダイヤルイン、参加起動ツール、常設チャットルーム管理、および octab の特定の言語に対して予期しない表示動作を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-572">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="ab849-573">たとえば、次のいずれかの言語が選択されている場合、ユーザーに英語のページが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-573">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="ab849-574">ノルウェー語</span><span class="sxs-lookup"><span data-stu-id="ab849-574">Norwegian</span></span>

  - <span data-ttu-id="ab849-575">ポルトガル語</span><span class="sxs-lookup"><span data-stu-id="ab849-575">Portuguese</span></span>

  - <span data-ttu-id="ab849-576">セルビア語</span><span class="sxs-lookup"><span data-stu-id="ab849-576">Serbian</span></span>

<span data-ttu-id="ab849-577">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-577">**Workaround:**</span></span>

<span data-ttu-id="ab849-578">ニュートラルロケールの言語を選択する場合は、ブラウザーの [言語設定] ボックスの一覧で、特定のロケール (スクリプトおよび国コードを含む) の言語も追加であることを必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="ab849-578">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="ab849-579">Lync Web Scheduler、ダイヤルイン、参加起動ツール、常設チャットルーム管理、および一部の Web ブラウザーでの OCTab を使用している場合、アゼルバイジャン語とウズベク語のサポートは制限されています。</span><span class="sxs-lookup"><span data-stu-id="ab849-579">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="ab849-580">このセクションの情報は Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月に関係します。</span><span class="sxs-lookup"><span data-stu-id="ab849-580">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="ab849-581">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-581">**Issue:**</span></span>

<span data-ttu-id="ab849-582">Internet Explorer 8 または Internet Explorer 9 を使用して、ブラウザーの言語をアゼルバイジャン語 (ラテン) またはウズベク語 (ラテン) に設定すると、ダイヤルインと参加起動ツールのページは、英語またはブラウザーで設定した言語で表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-582">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="ab849-583">Firefox または Chrome ブラウザーを使用しているときに、ブラウザーの言語を [アゼルバイジャン (ラテン)] または [ウズベク語 (ラテン)] に設定すると、Lync Web App、Lync Web Scheduler、および RGS OCTab が、英語で表示されるか、ブラウザーの優先言語セットとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-583">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="ab849-584">Safari ブラウザーでは、ウズベク語 (ラテン) ロケールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ab849-584">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="ab849-585">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-585">**Workaround:**</span></span>

<span data-ttu-id="ab849-586">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-586">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="ab849-587">ルーマニア語版の Lync Web App の [会議に参加する] リストのドロップダウン矢印が表示されない</span><span class="sxs-lookup"><span data-stu-id="ab849-587">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="ab849-588">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-588">**Issue:**</span></span>

<span data-ttu-id="ab849-589">ルーマニア語版の Lync Web App を使用しているユーザーが次の手順を実行すると、ドロップダウンリストに**会議に参加**するためのドロップダウン矢印が表示されません。</span><span class="sxs-lookup"><span data-stu-id="ab849-589">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="ab849-590">[**全般**] タブの [**このコンピューター上でパスワードを記憶**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab849-590">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="ab849-591">[**電話**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab849-591">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="ab849-592">[**会議に参加**する] のドロップダウンリストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab849-592">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="ab849-593">ユーザーには、既定の**Lync Web App**よりも多くのオプションが含まれていることを示す矢印が表示されません。これには、**オーディオに参加しない**(ルーマニア語、"ニュー se asociaža la componenta Audio") と**新しい番号**"(ルーマニア語で" Număr nou ") が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ab849-593">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="ab849-594">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-594">**Workaround:**</span></span>

<span data-ttu-id="ab849-595">このドロップダウンリストの矢印が表示されていない場合でも、ユーザーは既定値をクリックして、リスト内の追加の設定を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-595">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="ab849-596">トルコ語版の Lync Web Scheduler を使用している場合、[発表者になる人] の下にある [選択したユーザー] オプションを使用すると、会議を保存できません。</span><span class="sxs-lookup"><span data-stu-id="ab849-596">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="ab849-597">**点**</span><span class="sxs-lookup"><span data-stu-id="ab849-597">**Issue:**</span></span>

<span data-ttu-id="ab849-598">トルコ語版の Lync Web Scheduler で会議を作成または編集している場合、[発表者になるユーザー] の下の [選択したユーザー] オプションはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ab849-598">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported.</span></span> <span data-ttu-id="ab849-599">このオプションが選択されている場合、会議を保存することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab849-599">When this option is selected, the meeting can't be saved.</span></span> <span data-ttu-id="ab849-600">代わりに、1人以上のユーザーが発表者を作成できないことを示すエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-600">Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="ab849-601">**ところ**</span><span class="sxs-lookup"><span data-stu-id="ab849-601">**Workaround:**</span></span>

<span data-ttu-id="ab849-602">この問題を回避するために、ユーザーは、"社内のユーザー" の既定のオプション、または [開催者のみ] や [社外のユーザーを含むすべてのユーザー] などの任意の選択肢を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ab849-602">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company."</span></span> <span data-ttu-id="ab849-603">開催者は、会議に参加した後で、後でユーザーを適切なロールに降格または昇格させることができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-603">The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="ab849-604">または、別の言語を理解しているユーザーは、ブラウザーでの言語の選択を、サポートされている他の43言語のいずれかに変更して、[選択したユーザー] オプションを使用しようとすることができます。</span><span class="sxs-lookup"><span data-stu-id="ab849-604">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="ab849-605">著作</span><span class="sxs-lookup"><span data-stu-id="ab849-605">Copyright</span></span>

<span data-ttu-id="ab849-606">このドキュメントでは、最終的な商用リリースの前に実質的に変更される可能性があるソフトウェア製品の暫定的なリリースをサポートしています。また、Microsoft Corporation の機密情報でもあります。</span><span class="sxs-lookup"><span data-stu-id="ab849-606">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation.</span></span> <span data-ttu-id="ab849-607">この情報は、受信者と Microsoft との間の非開示契約に基づいて公開されます。</span><span class="sxs-lookup"><span data-stu-id="ab849-607">It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft.</span></span> <span data-ttu-id="ab849-608">このドキュメントは、情報提供のみを目的として提供されています。このドキュメントでは、Microsoft は明示または黙示のいずれの保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="ab849-608">This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document.</span></span> <span data-ttu-id="ab849-609">このドキュメントに記載されている情報 (URL などのインターネット web サイトへの参照を含む) は、予告なしに変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-609">Information in this document, including URL and other Internet website references, is subject to change without notice.</span></span> <span data-ttu-id="ab849-610">このドキュメントの使用、またはこのドキュメントの使用による結果のすべてのリスクは、ユーザーに残ります。</span><span class="sxs-lookup"><span data-stu-id="ab849-610">The entire risk of the use or the results from the use of this document remains with the user.</span></span> <span data-ttu-id="ab849-611">特に記載がない限り、ここに記載されている会社、組織、製品、ドメイン名、メールアドレス、ロゴ、人物、場所、およびイベントは架空のものです。</span><span class="sxs-lookup"><span data-stu-id="ab849-611">Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="ab849-612">実際の会社、組織、製品、ドメイン名、メールアドレス、ロゴ、人物、場所、またはイベントに関連するものではありません。</span><span class="sxs-lookup"><span data-stu-id="ab849-612">No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="ab849-613">すべての該当する著作権法を遵守することは、ユーザーにとっての責任となります。</span><span class="sxs-lookup"><span data-stu-id="ab849-613">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="ab849-614">著作権の下にある権利を制限することなく、このドキュメントの一部は、どの形式または任意の形態 (電子的、機械的、複写、レコーディングなど) またはその他の手段 (電子的、機械、複写、記録など) でも、または送信される可能性があります。Microsoft Corporation の書面による明示的な許可がない場合。</span><span class="sxs-lookup"><span data-stu-id="ab849-614">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="ab849-615">Microsoft には、このドキュメントの内容について、特許、特許申請、商標、著作権、またはその他の知的財産権が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="ab849-615">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document.</span></span> <span data-ttu-id="ab849-616">Microsoft の書面によるライセンス契約で明示的に記載されている場合を除き、このドキュメントの提供により、これらの特許、商標、著作権、またはその他の知的財産権の許諾を得ることはできません。</span><span class="sxs-lookup"><span data-stu-id="ab849-616">Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="ab849-617">© 2012 Microsoft Corporation。</span><span class="sxs-lookup"><span data-stu-id="ab849-617">© 2012 Microsoft Corporation.</span></span> <span data-ttu-id="ab849-618">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="ab849-618">All rights reserved.</span></span>

<span data-ttu-id="ab849-619">Microsoft、Windows、Windows Live、Active Directory、Internet Explorer、MSN、Outlook、および SQL Server は、米国およびその他の国/地域で、Microsoft Corporation の登録商標または商標です。</span><span class="sxs-lookup"><span data-stu-id="ab849-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="ab849-620">その他のすべての商標は、各所有者の財産権を持っています。</span><span class="sxs-lookup"><span data-stu-id="ab849-620">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

