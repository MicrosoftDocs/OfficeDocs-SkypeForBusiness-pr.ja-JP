---
title: Lync Server 2013 リリースノート
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
ms.openlocfilehash: f98a19e81ebf52d97b4c6807dbb97dc8110b0f34
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536564"
---
# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="97bea-102">Lync Server 2013 のリリースノート</span><span class="sxs-lookup"><span data-stu-id="97bea-102">Release notes for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97bea-103">_**トピックの最終更新日:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="97bea-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="97bea-104">Lync Server 2013 リリースノートへようこそ。</span><span class="sxs-lookup"><span data-stu-id="97bea-104">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="97bea-105">Lync Server 2013 の既知の問題に関する情報については、このファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="97bea-105">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="97bea-106">このドキュメントについて</span><span class="sxs-lookup"><span data-stu-id="97bea-106">About this document</span></span>

<span data-ttu-id="97bea-107">このドキュメントには、Lync Server 2013 を展開して使用する前に知っておく必要がある重要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="97bea-107">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="97bea-108">Lync Server 2013 の詳細については、「 [Microsoft Lync server 2013](microsoft-lync-server-2013.md) のドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97bea-108">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="97bea-109">このドキュメントは、以下のセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="97bea-109">This document contains the following sections:</span></span>

  - <span data-ttu-id="97bea-110">Lync 2013 クライアント</span><span class="sxs-lookup"><span data-stu-id="97bea-110">Lync 2013 client</span></span>

  - <span data-ttu-id="97bea-111">Lync Server</span><span class="sxs-lookup"><span data-stu-id="97bea-111">Lync Server</span></span>

  - <span data-ttu-id="97bea-112">インストール</span><span class="sxs-lookup"><span data-stu-id="97bea-112">Installation</span></span>

  - <span data-ttu-id="97bea-113">身体</span><span class="sxs-lookup"><span data-stu-id="97bea-113">Mobility</span></span>

  - <span data-ttu-id="97bea-114">会議</span><span class="sxs-lookup"><span data-stu-id="97bea-114">Conferencing</span></span>

  - <span data-ttu-id="97bea-115">用に構成します</span><span class="sxs-lookup"><span data-stu-id="97bea-115">Enterprise Voice</span></span>

  - <span data-ttu-id="97bea-116">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="97bea-116">Presence</span></span>

  - <span data-ttu-id="97bea-117">応答グループ アプリケーションおよびコール パーク アプリケーション</span><span class="sxs-lookup"><span data-stu-id="97bea-117">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="97bea-118">Lync Server コントロール パネル、トポロジ ビルダー、および計画ツール</span><span class="sxs-lookup"><span data-stu-id="97bea-118">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="97bea-119">ローカリゼーション</span><span class="sxs-lookup"><span data-stu-id="97bea-119">Localization</span></span>

  - <span data-ttu-id="97bea-120">著作権</span><span class="sxs-lookup"><span data-stu-id="97bea-120">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="97bea-121">Lync 2013 クライアント</span><span class="sxs-lookup"><span data-stu-id="97bea-121">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="97bea-122">他のアプリケーションでファイルが開かれている場合に、インスタントメッセージでファイルを転送できない</span><span class="sxs-lookup"><span data-stu-id="97bea-122">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="97bea-123">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-123">**Issue:**</span></span>

<span data-ttu-id="97bea-124">他の Lync ユーザーにインスタントメッセージでファイルを含めることによって、Word 文書などのファイルを転送しようとすると、転送は成功したように見えますが、実際にファイルの転送に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-124">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="97bea-125">ファイルの種類のアイコンは Lync クライアントに表示されますが、目的の受信者はそのファイルを開くことができません。</span><span class="sxs-lookup"><span data-stu-id="97bea-125">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="97bea-126">転送が成功しなかったことを通知するエラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="97bea-126">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="97bea-127">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-127">**Workaround:**</span></span>

<span data-ttu-id="97bea-128">この問題を回避するには、インスタントメッセージでファイルを転送する前に、開いているファイルまたはアプリケーションを閉じてください。</span><span class="sxs-lookup"><span data-stu-id="97bea-128">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="97bea-129">Lync Server</span><span class="sxs-lookup"><span data-stu-id="97bea-129">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="97bea-130">Lync Server ストレージサービスのデータレプリケーションが失敗した場合、管理者は古いストレージサービスキューアイテムのパフォーマンスカウンターをチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-130">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="97bea-131">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-131">**Issue:**</span></span>

<span data-ttu-id="97bea-132">Lync Server ストレージサービスは、レプリケーションに Windows Fabric を使用します。</span><span class="sxs-lookup"><span data-stu-id="97bea-132">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="97bea-133">プライマリフロントエンドサーバーでデータが削除されたが、セカンダリフロントエンドサーバーの削除が失敗した場合 (たとえば、フロントエンドサーバーに予期しないシャットダウンやエラーが発生した場合)、データは残され、"孤立" することがあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-133">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="97bea-134">孤立したデータを使用すると、パフォーマンスが低下し、ドライブ領域が浪費されることがあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-134">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="97bea-135">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-135">**Workaround:**</span></span>

<span data-ttu-id="97bea-136">この問題を回避するには、イベントログに "イベントを \_ \_ 指定してください" というイベント \_ \_ (id = 32058) と、その \_ 後に \_ \_ \_ 重大な (id = 32059) を使用していたデータベーススペースがイベントログに生成されている場合、管理者は、「 **LYSS - Current number of Storage Service stale queue items** **LS:** log service API」の下にあるフロントエンドサーバーのパフォーマンスカウンターを</span><span class="sxs-lookup"><span data-stu-id="97bea-136">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="97bea-137">このパフォーマンスカウンターに大きな値がある場合 (たとえば、50000より大きい場合)、管理者は Lync Server 2013 リソースキットの CleanuUpStorageServiceData.exe ツールを実行して、孤立したすべてのデータをプールから削除します。</span><span class="sxs-lookup"><span data-stu-id="97bea-137">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="97bea-138">このツールの詳細については、Lync Server 2013 リソースキットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="97bea-138">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="97bea-139">サーバーまたはプールの IP アドレス構成が変更された場合は、Lync Server サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-139">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="97bea-140">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-140">**Issue:**</span></span>

<span data-ttu-id="97bea-141">Lync Server 2013 の展開に対して IP アドレス構成が変更された場合 (IPv4 からデュアルスタックへの変更、デュアルスタックから Ipv6 への変更など)、すべてのサーバーコンポーネントは、サービスが再起動されるまで構成変更を選択しません。</span><span class="sxs-lookup"><span data-stu-id="97bea-141">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="97bea-142">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-142">**Workaround:**</span></span>

<span data-ttu-id="97bea-143">この問題を回避するには、展開の IP アドレス構成を変更した後に Lync Server サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="97bea-143">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="97bea-144">これを行うには、Lync Server 管理シェルで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="97bea-144">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="97bea-145">ダイヤルイン会議代理トランザクションコマンドレットは、Lync Server 2013 管理パックでは使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="97bea-145">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="97bea-146">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-146">**Issue:**</span></span>

<span data-ttu-id="97bea-147">ダイヤルイン会議代理トランザクションコマンドレット **Test-csdial In会議** は、Lync Server 2013 管理パックでは使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="97bea-147">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="97bea-148">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-148">**Workaround:**</span></span>

<span data-ttu-id="97bea-149">ダイヤルイン会議代理トランザクションコマンドレットの使用 **テスト-Csdial Inコンファレンス** は、社内のみでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="97bea-149">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="97bea-150">管理者は、トラブルシューティングの目的で、Lync Server 管理シェルのコマンドレットを引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="97bea-150">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="97bea-151">必要に応じて、エンタープライズは、コマンドレットを内部的に実行するためのプライベート管理パックを開発することもできます。</span><span class="sxs-lookup"><span data-stu-id="97bea-151">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="97bea-152">ログファイルがネットワーク共有にコピーされているときにネットワークトラフィックが中断された場合、集中ログサービスは停止します。</span><span class="sxs-lookup"><span data-stu-id="97bea-152">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="97bea-153">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-153">**Issue:**</span></span>

<span data-ttu-id="97bea-154">集中ログサービスがネットワークパスを使用するように構成さ **れている** 場合 (CacheFileNetworkFolder パラメーターの値が有効な UNC パスである)、キャッシュされたログファイルはネットワーク共有にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="97bea-154">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="97bea-155">ファイルのコピー中にネットワークトラフィックで中断が発生すると、集中ログサービスが停止する例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="97bea-155">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="97bea-156">サービスは、3回まで自動的に再起動するように構成されているため、最初の3つの例外から回復します。</span><span class="sxs-lookup"><span data-stu-id="97bea-156">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="97bea-157">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-157">**Workaround:**</span></span>

<span data-ttu-id="97bea-158">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-158">There is no workaround for this issue.</span></span> <span data-ttu-id="97bea-159">この問題を特定するには、"Lync Server 集中ログサービスエージェント" サービスが予期せず終了したときにログに記録されるイベント ID 7031 のイベントログを監視します。</span><span class="sxs-lookup"><span data-stu-id="97bea-159">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="97bea-160">これが3回を超えて発生する場合は、 **Start-CsWindowService** コマンドレットを使用して、サービスを手動で再起動します。</span><span class="sxs-lookup"><span data-stu-id="97bea-160">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="97bea-161">ストレージサービスキューアイテムを手動でインポートする必要がある</span><span class="sxs-lookup"><span data-stu-id="97bea-161">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="97bea-162">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-162">**Issue:**</span></span>

<span data-ttu-id="97bea-163">Lync Server 2013 は、アーカイブされたメッセージ、通話詳細記録 (CDR) などの会議やインスタントメッセージングに関するデータを、各フロントエンドサーバー上のデータベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="97bea-163">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="97bea-164">データは、目的の宛先に配信される前に処理されている間、データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-164">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="97bea-165">パフォーマンスを向上させるために、Lync Server 2013 は定期的に処理されないローカルデータベースからキューアイテムをエクスポートし、それをファイルストアに保存します。</span><span class="sxs-lookup"><span data-stu-id="97bea-165">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="97bea-166">ファイルストアが使用できない場合、アイテムは各フロントエンドサーバーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-166">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="97bea-167">プールフェールオーバー中のデータ損失を防止するために同じ操作が発生します。</span><span class="sxs-lookup"><span data-stu-id="97bea-167">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="97bea-168">エクスポート操作の間に、Lync Server Storage サービスは、イベント Id 32075 のイベント Id (完全なフラッシュ操作が開始)、32076 (完全フラッシュ (完了))、32082 (メンテナンスレベルのフラッシュが開始)、32083 (メンテナンスレベルのフラッシュが完了 32089) の各ステージをイベントログに記録します。</span><span class="sxs-lookup"><span data-stu-id="97bea-168">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="97bea-169">このデータは、処理されて最終的な宛先 (SQL Server または Exchange Server) に配信されるように、システムに自動的にインポートされることはありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-169">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="97bea-170">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-170">**Workaround:**</span></span>

<span data-ttu-id="97bea-171">システムにデータをインポートするには、管理者は Lync Server リソースキットの ImportStorageServiceData ツールを使用する必要があります。これにより、データがシステムに追加され、処理されて最終的な送信先に配信されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-171">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="97bea-172">UseNormalizationRules の既定値を False に変更すると、アドレス帳 Web クエリの検索が失敗する</span><span class="sxs-lookup"><span data-stu-id="97bea-172">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="97bea-173">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-173">**Issue:**</span></span>

<span data-ttu-id="97bea-174">UseNormalizationRules の既定値を False に変更すると、アドレス帳の Web クエリ検索は失敗します。</span><span class="sxs-lookup"><span data-stu-id="97bea-174">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail.</span></span> <span data-ttu-id="97bea-175">既定値が変更されると、Lync クライアントユーザーは Lync アドレス帳 web クエリを使用してユーザーを検索することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="97bea-175">After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="97bea-176">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-176">**Workaround:**</span></span>

<span data-ttu-id="97bea-177">UseNormalizationRules の既定値が False に設定されている場合、ユーザーは、Active Directory ドメインサービスで定義されている電話番号を、Lync Server 2013 を使用せずに使用することができます。正規化ルールを適用するには、次の手順を実行してこの問題を回避します。</span><span class="sxs-lookup"><span data-stu-id="97bea-177">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="97bea-178">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="97bea-178">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="97bea-179">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="97bea-179">Do one of the following:</span></span>
    
      - <span data-ttu-id="97bea-180">展開に Lync Server 2013 サーバーのみが含まれている場合は、グローバルレベルで次のコマンドレットを実行して、UseNormalizationRules および IgnoreGenericRules の値を True に変更します。</span><span class="sxs-lookup"><span data-stu-id="97bea-180">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="97bea-181">展開に Lync Server 2013 と Lync Server 2010 または Office Communications Server 2007 R2 の組み合わせが含まれている場合は、次のコマンドレットを実行して、トポロジ内の各 Lync Server 2013 プールに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="97bea-181">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="97bea-182">すべてのプールで CMS レプリケーションが行われるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="97bea-182">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="97bea-183">展開用の電話正規化ルールファイルを変更して、コンテンツをクリアします。</span><span class="sxs-lookup"><span data-stu-id="97bea-183">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="97bea-184">ファイルは、各 Lync Server 2013 プールのファイル共有にあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-184">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="97bea-185">ファイルが存在しない場合は、"会社電話番号の正規化Rules.txt" という名前の空のファイルを作成し \_ \_ \_ \_ ます。</span><span class="sxs-lookup"><span data-stu-id="97bea-185">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="97bea-186">すべてのフロントエンドプールが新しいファイルを読み取るまで数分待機します。</span><span class="sxs-lookup"><span data-stu-id="97bea-186">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="97bea-187">展開内の各 Lync Server 2013 プールで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="97bea-187">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="97bea-188">Lync 2013 プールごとに1日1回アドレス帳サーバーエラーイベント21054が生成される</span><span class="sxs-lookup"><span data-stu-id="97bea-188">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="97bea-189">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-189">**Issue:**</span></span>

<span data-ttu-id="97bea-190">Lync Server 2013 アドレス帳サーバーでは、毎日のメンテナンスの実行時に、毎日1回エラーイベント21054が生成されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-190">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="97bea-191">また、更新が成功した場合でも、管理者が **update-csaddressbook** コマンドレットを実行するたびに、このエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-191">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="97bea-192">ただし、更新が成功した場合、このエラーイベントは無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-192">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="97bea-193">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-193">**Workaround:**</span></span>

<span data-ttu-id="97bea-194">このエラーイベントが発生した場合は、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="97bea-194">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="97bea-195">コマンドレットで、インデックスが設定されていないオブジェクトまたは破棄されたオブジェクトがないことを報告した場合は、エラーイベント21054を無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-195">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="97bea-196">また、System Center Operations Manager では、キー正常性インジケーター (KHI) "アドレス帳ユーザーが正しくインデックス処理されています" がオフになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-196">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="97bea-197">エッジプールで IPv6 が構成されていると、要求が失敗する場合がある</span><span class="sxs-lookup"><span data-stu-id="97bea-197">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="97bea-198">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-198">**Issue:**</span></span>

<span data-ttu-id="97bea-199">エッジプールで IPv6 が構成されている場合、エッジプールへの要求が失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-199">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="97bea-200">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-200">**Workaround:**</span></span>

<span data-ttu-id="97bea-201">この問題を回避するには、エッジプールを IPv6 で構成しないようにします。</span><span class="sxs-lookup"><span data-stu-id="97bea-201">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="97bea-202">プールのフェールバック時に Invoke-cspoolfailback コマンドレットが失敗する場合がある</span><span class="sxs-lookup"><span data-stu-id="97bea-202">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="97bea-203">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-203">**Issue:**</span></span>

<span data-ttu-id="97bea-204">プールのフェールバックを試行すると、 **invoke-cspoolfailback** コマンドレットがエラーで失敗することがあります。 "繰り返し試行が行われた後、ハイドロプロセスを完了できませんでした。"</span><span class="sxs-lookup"><span data-stu-id="97bea-204">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="97bea-205">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-205">**Workaround:**</span></span>

<span data-ttu-id="97bea-206">この問題を回避するには、もう一度コマンドレットを実行して、コマンドレットが正常に終了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="97bea-206">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds.</span></span> <span data-ttu-id="97bea-207">フェールバックプロセスが完了するまでに数分かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="97bea-207">Note that the failback process can take several minutes to complete.</span></span> <span data-ttu-id="97bea-208">プールが2万ユーザーの場合、最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-208">It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="97bea-209">既に確立されているプール (ハイブリッド、Skype for Business Online) にフロントエンドサーバーを追加するとデータが失われることがある</span><span class="sxs-lookup"><span data-stu-id="97bea-209">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="97bea-210">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-210">**Issue:**</span></span>

<span data-ttu-id="97bea-211">プールに複数のフロントエンドサーバーがある環境でこの問題が発生する場合があります。または、フロントエンドサーバーの1つを再起動するか、プールの一部ではない新しいフロントエンドサーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="97bea-211">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="97bea-212">データがアーカイブされているユーザーは、プールに対して安定したデータアーカイブの配布が確立されるまで、データの損失が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-212">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool.</span></span> <span data-ttu-id="97bea-213">このようなデータ損失が発生する可能性がある期間は、人間会話の場合は15分、電話会議の場合は30分に制限されています。</span><span class="sxs-lookup"><span data-stu-id="97bea-213">This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="97bea-214">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-214">**Workaround:**</span></span>

<span data-ttu-id="97bea-215">管理を実行するときは、プール内のフロントエンドサーバーを1つずつ開始するのではなく、プールを別のプールにフェールオーバーして、サーバー上でメンテナンスタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-215">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="97bea-216">メンテナンスタスクを実行する前にサービスを利用できないようにし、メンテナンスが完了したら可用性を復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="97bea-216">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="97bea-217">Get-CsClientAccessLicense コマンドレットを使用して、管理者がライセンス数を取得できない</span><span class="sxs-lookup"><span data-stu-id="97bea-217">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="97bea-218">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-218">**Issue:**</span></span>

<span data-ttu-id="97bea-219">管理者は、 **Get-help Clientaccesslicense** コマンドレットを使用して、クライアントライセンスの正確な使用状況を取得できません。</span><span class="sxs-lookup"><span data-stu-id="97bea-219">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="97bea-220">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-220">**Workaround:**</span></span>

<span data-ttu-id="97bea-221">サーバーライセンスの種類を確認するには、 **-CsService** コマンドレットを実行して、すべてのデータベースの完全修飾ドメイン名 (FDQNs) を取得します。</span><span class="sxs-lookup"><span data-stu-id="97bea-221">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="97bea-222">フロントエンドサーバーの FQDN がバックエンドデータベースの FQDN と同じである場合、ライセンスは Standard edition ライセンスです。</span><span class="sxs-lookup"><span data-stu-id="97bea-222">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="97bea-223">それ以外の場合、ライセンスは Enterprise edition ライセンスです。</span><span class="sxs-lookup"><span data-stu-id="97bea-223">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="97bea-224">クライアントライセンスの数が正確に報告されない</span><span class="sxs-lookup"><span data-stu-id="97bea-224">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="97bea-225">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-225">**Issue:**</span></span>

<span data-ttu-id="97bea-226">クライアントライセンスの数を決定するときには、次のような状況が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-226">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="97bea-227">**モバイルユーザーのライセンス数が正しくない**</span><span class="sxs-lookup"><span data-stu-id="97bea-227">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="97bea-228">ライセンス数は、デバイスベースのユーザーの一意の IP アドレスの数に基づいています。</span><span class="sxs-lookup"><span data-stu-id="97bea-228">The license count is based on the number of unique IP addresses for device-based users.</span></span> <span data-ttu-id="97bea-229">ライセンス数は、次の方法で制限されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-229">The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="97bea-230">ユーザーの IP アドレスが Lync セッション中に変更されると、ライセンスは過剰にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="97bea-230">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="97bea-231">これは、ユーザーがデスクトップクライアントを使用して複数の場所から Lync Server に接続している場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-231">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="97bea-232">ユーザーがモバイルクライアントを使用して接続する場合は、デバイスの IP アドレスを特定できないため、ライセンスが過小にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="97bea-232">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="97bea-233">**公衆交換電話網 (PSTN) から Lync クライアントへの通話、Lync クライアントから PSTN 回線への通話、および PSTN 回線に転送された Lync 通話でライセンスが2回カウントされる**</span><span class="sxs-lookup"><span data-stu-id="97bea-233">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="97bea-234">次のシナリオでは、電話番号と Lync ユーザーの両方がカウントされ、使用されているライセンスの数が判別されるため、2つの追加ライセンスは1つではなく、カウントされます。</span><span class="sxs-lookup"><span data-stu-id="97bea-234">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used.</span></span> <span data-ttu-id="97bea-235">正確なライセンスデータを取得するには、電話番号によって生成されたライセンスを手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="97bea-235">To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="97bea-236">Lync への PSTN 電話通話</span><span class="sxs-lookup"><span data-stu-id="97bea-236">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="97bea-237">PSTN 回線への Lync 通話</span><span class="sxs-lookup"><span data-stu-id="97bea-237">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="97bea-238">Lync への PSTN 通話。 Lync は、通話を PSTN 回線に転送します。</span><span class="sxs-lookup"><span data-stu-id="97bea-238">A PSTN call to Lync, and then Lync forwards the call to a PSTN line.</span></span> <span data-ttu-id="97bea-239">PSTN 回線の1つをカウントします。</span><span class="sxs-lookup"><span data-stu-id="97bea-239">One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="97bea-240">**ログオンしている Lync 電話のライセンスがカウントされない**</span><span class="sxs-lookup"><span data-stu-id="97bea-240">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="97bea-241">ユーザーが Lync 認定電話を使用している場合、電話がログインしていて、接続を維持すると、電話がログインした後にライセンスのクエリが発生した場合、その電話はライセンスを使用したものとしてカウントされません。</span><span class="sxs-lookup"><span data-stu-id="97bea-241">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="97bea-242">**電話会議に参加している PSTN 電話に対してカウントされたライセンス**</span><span class="sxs-lookup"><span data-stu-id="97bea-242">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="97bea-243">ユーザーが PSTN 電話機を使用して電話会議に参加すると、電話会議への参加のためのライセンスが不正確にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="97bea-243">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference.</span></span> <span data-ttu-id="97bea-244">ただし、PSTN 電話で会議に参加するためにライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-244">However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="97bea-245">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-245">**Workaround:**</span></span>

1.  <span data-ttu-id="97bea-246">**モバイルユーザーのライセンス数が正しくない**</span><span class="sxs-lookup"><span data-stu-id="97bea-246">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="97bea-247">同じデバイスに属する IP アドレスを手動で特定し、そのうちの1つをライセンス数で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="97bea-247">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="97bea-248">Lync クライアントを使用して接続するモバイルデバイスでこの問題を回避する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-248">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="97bea-249">**Lync クライアントへの PSTN 通話、Lync クライアントから PSTN 回線への通話、および PSTN 回線に転送された Lync 通話でライセンスが2回カウントされる**</span><span class="sxs-lookup"><span data-stu-id="97bea-249">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="97bea-250">PSTN 電話番号を手動で特定し、その番号に対して生成されたライセンス数を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-250">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="97bea-251">**ログインしている Lync 電話のライセンスがカウントされない**</span><span class="sxs-lookup"><span data-stu-id="97bea-251">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="97bea-252">ユーザーがログオフするように Lync phone を構成し、定期的に (3 か月ごとなど) ログオンし直すことができます。</span><span class="sxs-lookup"><span data-stu-id="97bea-252">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="97bea-253">**電話会議に参加している PSTN 電話に対してカウントされたライセンス**</span><span class="sxs-lookup"><span data-stu-id="97bea-253">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="97bea-254">電話会議への参加に使用される PSTN 電話番号を手動で特定し、その電話番号によって生成されたライセンスを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="97bea-254">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="97bea-255">Lync Server コントロールパネルは、Silverlight 5 へのアップグレード後の VMware 環境での動作を停止します。</span><span class="sxs-lookup"><span data-stu-id="97bea-255">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="97bea-256">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-256">**Issue:**</span></span>

<span data-ttu-id="97bea-257">VMware 環境で Lync Server コントロールパネルを使用すると、Microsoft Silverlight をバージョン5にアップグレードした後、Lync Server コントロールパネルが機能しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-257">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="97bea-258">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-258">**Workaround:**</span></span>

<span data-ttu-id="97bea-259">この問題を回避するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="97bea-259">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="97bea-260">Silverlight 5 をアンインストールし、から Silverlight 4 をインストール [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156) します。</span><span class="sxs-lookup"><span data-stu-id="97bea-260">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="97bea-261">VMware 仮想コンピューターではないコンピューターから Lync Server コントロールパネルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="97bea-261">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="97bea-262">そのためには、lync Server 管理ツールがコンピューターにインストールされている場合は、サーバーの Windows **スタート** メニューから Lync Server コントロールパネルを起動できます。</span><span class="sxs-lookup"><span data-stu-id="97bea-262">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="97bea-263">Web ブラウザーを使用して Lync Server コントロールパネルにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="97bea-263">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="97bea-264">URL は https:///cscp. に似ています。 \<frontend\_pool\_fqdn\></span><span class="sxs-lookup"><span data-stu-id="97bea-264">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="97bea-265">Active Directory でユーザーの識別名が変更されても、アドレス帳サービスのユーザー情報が更新されない</span><span class="sxs-lookup"><span data-stu-id="97bea-265">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="97bea-266">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-266">**Issue:**</span></span>

<span data-ttu-id="97bea-267">Active Directory ドメインサービスでユーザーの識別名 (DN とも言う) が変更された場合、アドレス帳サービス (ABS) 内の追加の変更は更新されません。</span><span class="sxs-lookup"><span data-stu-id="97bea-267">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="97bea-268">これは、ユーザーのサインインまたはプレゼンスには影響を与えませんが、検索によって古い SIP アドレスが返されるため、SIP アドレスも変更された場合にユーザーの通信ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="97bea-268">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="97bea-269">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-269">**Workaround:**</span></span>

<span data-ttu-id="97bea-270">この問題を回避するには、ユーザーの DN を変更しないようにします。</span><span class="sxs-lookup"><span data-stu-id="97bea-270">To work around this issue, do not change a user’s DN.</span></span> <span data-ttu-id="97bea-271">ユーザーの DN を以前の値に戻すと、アドレス帳サービスに更新が反映されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-271">If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="97bea-272">インストール</span><span class="sxs-lookup"><span data-stu-id="97bea-272">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="97bea-273">非 ASCII 文字を使用すると、Lync server の起動が失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-273">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="97bea-274">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-274">**Issue:**</span></span>

<span data-ttu-id="97bea-275">宛先フォルダーの名前に ASCII 以外の文字 (UNICODE、2バイト文字セット (DBCS)、UTF-8、UTF-16 を含む) が含まれている場合、セットアップは失敗します。</span><span class="sxs-lookup"><span data-stu-id="97bea-275">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="97bea-276">さらに、セットアップは成功する可能性がありますが、次のいずれかに ASCII 以外の文字が含まれていると、サーバーは起動しません。</span><span class="sxs-lookup"><span data-stu-id="97bea-276">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="97bea-277">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="97bea-277">Computer name</span></span>

  - <span data-ttu-id="97bea-278">ドメイン名</span><span class="sxs-lookup"><span data-stu-id="97bea-278">Domain name</span></span>

  - <span data-ttu-id="97bea-279">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="97bea-279">User name</span></span>

  - <span data-ttu-id="97bea-280">ユーザー SIP URI</span><span class="sxs-lookup"><span data-stu-id="97bea-280">User SIP URI</span></span>

  - <span data-ttu-id="97bea-281">サービスアカウント名</span><span class="sxs-lookup"><span data-stu-id="97bea-281">Service account name</span></span>

<span data-ttu-id="97bea-282">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-282">**Workaround:**</span></span>

<span data-ttu-id="97bea-283">移動先のフォルダー名、コンピューター名、ドメイン名、ユーザー名、ユーザーの SIP URI、およびサービスアカウント名には ASCII 文字のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="97bea-283">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="97bea-284">"ヒープの破損" という修正プログラムは、Lync Server 2013 をインストールする前に、モジュールが InsertEntityBody メソッドを IIS 7.5 で呼び出したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="97bea-284">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="97bea-285">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-285">**Issue:**</span></span>

<span data-ttu-id="97bea-286">「モジュールが IIS 7.5 で InsertEntityBody メソッドを呼び出すときに発生するヒープの破損」 () については、「 [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) Microsoft サポート技術情報の記事 264886 ()」を参照し [https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603) てください。 Lync Server 2013 をインストールする前に、をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-286">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="97bea-287">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-287">**Workaround:**</span></span>

<span data-ttu-id="97bea-288">「Microsoft ダウンロードセンター」から修正プログラムをダウンロードしてインストールし [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) ます。</span><span class="sxs-lookup"><span data-stu-id="97bea-288">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="97bea-289">Lync Server 2013 のインストールが ITA Windows Server 2012 OS RTM バージョンに失敗する</span><span class="sxs-lookup"><span data-stu-id="97bea-289">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="97bea-290">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-290">**Issue:**</span></span>

<span data-ttu-id="97bea-291">Windows Fabric のインストールに失敗したため、ITA Windows Server 2012 で Lync Server 2013 のインストールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="97bea-291">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="97bea-292">Fabric トレースは、時間形式 HH: MM: SS で作成されるため、Windows Fabric のインストールに失敗します。</span><span class="sxs-lookup"><span data-stu-id="97bea-292">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS.</span></span> <span data-ttu-id="97bea-293">ただし、ITA Windows Server では、時間の形式は HH です。MM.SS。</span><span class="sxs-lookup"><span data-stu-id="97bea-293">However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="97bea-294">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-294">**Workaround:**</span></span>

<span data-ttu-id="97bea-295">この問題を回避するには、Lync Server 2013 をインストールする前に、システムレジストリを更新します。</span><span class="sxs-lookup"><span data-stu-id="97bea-295">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="97bea-296">更新する必要のあるレジストリキーは次のとおりです。 HKEY \_ ユーザー \\ 。既定 \\ のコントロールパネル \\ インターナショナル \\ の形式。</span><span class="sxs-lookup"><span data-stu-id="97bea-296">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="97bea-297">Windows PowerShell コマンドラインインターフェイスを使用して、次に示すように、[形式] の値を HH: mm: ss に変更します。</span><span class="sxs-lookup"><span data-stu-id="97bea-297">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="97bea-298">Windows PowerShell を起動し、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="97bea-298">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="97bea-299">現在の値を表示するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="97bea-299">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="97bea-300">インストールの完了後に復元できるように、このプロパティの現在の値をメモしておいてください。</span><span class="sxs-lookup"><span data-stu-id="97bea-300">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="97bea-301">新しい値を設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="97bea-301">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="97bea-302">Lync Server 2013 が正常にインストールされた後、次のコマンドレットを実行して、この形式の元の値を復元します。</span><span class="sxs-lookup"><span data-stu-id="97bea-302">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="97bea-303">Set-ItemProperty $a、手順3でメモした <値の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="97bea-303">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="97bea-304">上記の> "</span><span class="sxs-lookup"><span data-stu-id="97bea-304">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="97bea-305">身体</span><span class="sxs-lookup"><span data-stu-id="97bea-305">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="97bea-306">サーバーフェールオーバープロセス中のモバイルクライアントの問題</span><span class="sxs-lookup"><span data-stu-id="97bea-306">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="97bea-307">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-307">**Issue:**</span></span>

<span data-ttu-id="97bea-308">Lync Server に障害が発生し、フェールオーバープロセスが開始されると、次の問題がモバイルクライアントユーザーに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-308">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="97bea-309">フェールオーバーの開始から最大10分間、Lync 通話または着信通知がありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-309">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="97bea-310">着信チャット要求を受け入れることができない</span><span class="sxs-lookup"><span data-stu-id="97bea-310">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="97bea-311">障害が発生したサーバーがユーザーのホームサーバーの場合、会議に参加できない</span><span class="sxs-lookup"><span data-stu-id="97bea-311">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="97bea-312">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-312">**Workaround:**</span></span>

<span data-ttu-id="97bea-313">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-313">There is no workaround for this issue.</span></span> <span data-ttu-id="97bea-314">フェールオーバープロセスが完了すると、通常の機能が復元されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-314">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="97bea-315">モバイルユーザーが別の Lync エンドポイントからの着信呼び出しを拒否した場合、その通話は Lync Mobile クライアントに不在時の変換として表示されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-315">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="97bea-316">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-316">**Issue:**</span></span>

<span data-ttu-id="97bea-317">モバイルユーザーが着信呼び出しを拒否し、別の Lync エンドポイントから発信された通話は、デバイス呼び出しリストの呼び出しではなく、Lync Mobile クライアントで不在着信として表示されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-317">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="97bea-318">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-318">**Workaround:**</span></span>

<span data-ttu-id="97bea-319">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-319">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="97bea-320">モバイルクライアントが連絡先を検索するときに、フェデレーションの連絡先の表示名が表示されない場合がある</span><span class="sxs-lookup"><span data-stu-id="97bea-320">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="97bea-321">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-321">**Issue:**</span></span>

<span data-ttu-id="97bea-322">フェデレーション連絡先の表示名は、連絡先リストでフェデレーション連絡先を検索する場合など、一部のシナリオでは表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-322">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="97bea-323">これは、Lync mobile クライアントからの連絡先に対してアクティブなプレゼンスサブスクリプションが存在しない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-323">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="97bea-324">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-324">**Workaround:**</span></span>

<span data-ttu-id="97bea-325">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-325">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="97bea-326">モバイルクライアントでは、会議への招待である不在着信した会話から招待者とタイムスタンプ情報が欠落しています。</span><span class="sxs-lookup"><span data-stu-id="97bea-326">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="97bea-327">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-327">**Issue:**</span></span>

<span data-ttu-id="97bea-328">モバイルクライアントでは、不在着信した会話が会議への招待である場合、不在着信した会話メッセージに招待者とタイムスタンプ情報が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="97bea-328">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="97bea-329">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-329">**Workaround:**</span></span>

<span data-ttu-id="97bea-330">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-330">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="97bea-331">VoIP を使用して通話を行うモバイルクライアントユーザーは、Exchange 2010 またはそれ以前のバージョンでボイスメールが構成されているユーザーにボイスメールを残すことができません。</span><span class="sxs-lookup"><span data-stu-id="97bea-331">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="97bea-332">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-332">**Issue:**</span></span>

<span data-ttu-id="97bea-333">モバイルクライアントユーザーが VoIP を使用して通話を発信している場合、ユーザーは、Microsoft Exchange Server 2007 または Microsoft Exchange Server 2010 でボイスメールを使用するように構成されたユーザーにボイスメールメッセージを残すことはできません。</span><span class="sxs-lookup"><span data-stu-id="97bea-333">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="97bea-334">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-334">**Workaround:**</span></span>

<span data-ttu-id="97bea-335">この問題を回避するには、Exchange 2010 SP1 以降のバージョンの Microsoft Exchange Server を使用します。</span><span class="sxs-lookup"><span data-stu-id="97bea-335">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="97bea-336">モバイルクライアントでクライアントバージョン構成に URL を指定して Block を使用すると、正しくないエラーメッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-336">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="97bea-337">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-337">**Issue:**</span></span>

<span data-ttu-id="97bea-338">モバイルクライアントでクライアントバージョン構成に **URL を** 指定したブロックを使用する場合、クライアントバージョンがサポートされていないと、正しくないエラーメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-338">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="97bea-339">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-339">**Workaround:**</span></span>

<span data-ttu-id="97bea-340">この問題を回避するには、 **URL を使用して block**ではなく**ブロック**を使用するようにクライアントバージョン構成を構成します。</span><span class="sxs-lookup"><span data-stu-id="97bea-340">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="97bea-341">会議</span><span class="sxs-lookup"><span data-stu-id="97bea-341">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="97bea-342">Lync Server 2013 のフロントエンドサーバー上で実行されているウイルス対策ソフトウェアは、アプリケーションドメインのリサイクルを発生させることがあります。これにより、Lync Web App 2013、Lync Mobile 2010、Lync Mobile 2013 クライアントのサービスが一時的に中断されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-342">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="97bea-343">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-343">**Issue:**</span></span>

<span data-ttu-id="97bea-344">ウイルス対策ソフトウェアは、アプリケーションドメインの再起動をトリガーすることができます。これにより、Lync Mobility Service 2013 および統合コミュニケーション (UC) Web API クライアントアプリケーション (Lync Web App 2013、Lync Mobile 2010、および Lync Mobile 2013) の状態が失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-344">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="97bea-345">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-345">**Workaround:**</span></span>

<span data-ttu-id="97bea-346">この問題を回避するには、Web コンポーネントと .NET framework を含むフォルダーをウイルス対策スキャン対象から除外します。</span><span class="sxs-lookup"><span data-stu-id="97bea-346">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="97bea-347">詳細については、「Microsoft サポート技術情報の記事312592、「PRB: ASP.NET で、アプリケーションが再起動しています」というエラーを参照してください [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592) 。</span><span class="sxs-lookup"><span data-stu-id="97bea-347">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="97bea-348">次のフォルダーを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-348">The following folders should be excluded:</span></span>

  - <span data-ttu-id="97bea-349">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web コンポーネント \\ mcx \\ Ext</span><span class="sxs-lookup"><span data-stu-id="97bea-349">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="97bea-350">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web コンポーネント \\ mcx \\ Int</span><span class="sxs-lookup"><span data-stu-id="97bea-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="97bea-351">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web コンポーネント \\ ucwa \\ Int</span><span class="sxs-lookup"><span data-stu-id="97bea-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="97bea-352">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web コンポーネント \\ ucwa \\ Ext</span><span class="sxs-lookup"><span data-stu-id="97bea-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="97bea-353">% Windir% \\ Microsoft.NET \\ Framework64 \\ v v4.0.30319 \\ Config</span><span class="sxs-lookup"><span data-stu-id="97bea-353">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="97bea-354">会議に参加するには、Windows Internet Explorer で ActiveX コントロールまたはネイティブ XMLHTTP サポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-354">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="97bea-355">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-355">**Issue:**</span></span>

<span data-ttu-id="97bea-356">ユーザーが Windows Internet Explorer のインターネットブラウザー設定で ActiveX コントロールとネイティブ XMLHTTP サポートの両方を無効にしている場合、Internet Explorer が既定のブラウザーとして選択されていると、ユーザーは会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="97bea-356">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="97bea-357">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-357">**Workaround:**</span></span>

<span data-ttu-id="97bea-358">Internet Explorer で、ActiveX コントロールまたは "ネイティブ XMLHTTP サポート" を有効にします。</span><span class="sxs-lookup"><span data-stu-id="97bea-358">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="97bea-359">Lync Server Web 会議サービスが重要なモードから回復できない</span><span class="sxs-lookup"><span data-stu-id="97bea-359">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="97bea-360">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-360">**Issue:**</span></span>

<span data-ttu-id="97bea-361">重要モードでアーカイブが有効になっている場合、システム障害が発生すると、重要モードが開始され、会議は参加者に対して機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="97bea-361">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants.</span></span> <span data-ttu-id="97bea-362">管理者がシステム障害 (データベース問題の修正など) を修正した後、データ会議サービスは自動的には回復しないため、管理者は会議サービスを再開するために手動で再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-362">After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="97bea-363">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-363">**Workaround:**</span></span>

<span data-ttu-id="97bea-364">システム障害が修正された後、管理者は、会議サービスを手動で再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-364">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="97bea-365">Web 会議サービスが外部の Office Web App サーバーの HTTP プロキシを無視する</span><span class="sxs-lookup"><span data-stu-id="97bea-365">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="97bea-366">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-366">**Issue:**</span></span>

<span data-ttu-id="97bea-367">Web 会議サービスの外部にある Office Web Apps サーバーを展開している (つまり、内部の企業ネットワークにないサーバー) インターネット、境界ネットワーク、および Web 会議サービスに接続するために HTTP プロキシが必要な場合、Office Web Apps サーバーの検出は失敗します。</span><span class="sxs-lookup"><span data-stu-id="97bea-367">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="97bea-368">Web 会議サービスは、「Office Web Apps Server セットアップのトポロジビルダー」で定義されているように、HTTP プロキシ設定を無視します。</span><span class="sxs-lookup"><span data-stu-id="97bea-368">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="97bea-369">その結果、Lync クライアントは、会議の他の参加者と Microsoft PowerPoint 2010 の共有を行うことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="97bea-369">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="97bea-370">内部ネットワークで Lync Server をオンプレミスでインストールし、オンプレミスの Office Web Apps サーバーを構成する場合、プロキシ構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-370">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="97bea-371">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-371">**Workaround:**</span></span>

<span data-ttu-id="97bea-372">唯一の回避策は、外部の Office Web Apps サーバーとの通信に HTTP プロキシを使用する必要がある展開構成を行わないことです。</span><span class="sxs-lookup"><span data-stu-id="97bea-372">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="97bea-373">電話会議プロバイダーの会議へのビデオの追加はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="97bea-373">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="97bea-374">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-374">**Issue:**</span></span>

<span data-ttu-id="97bea-375">ユーザーが音声会議プロバイダーの電話会議に参加している場合、ビデオの追加はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97bea-375">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="97bea-376">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-376">**Workaround:**</span></span>

<span data-ttu-id="97bea-377">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-377">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="97bea-378">IPv6 が有効になっているトポロジ lync web App Silverlight プラグイン自動更新を強制して、画面共有機能が Lync Web App から機能できるようにします。</span><span class="sxs-lookup"><span data-stu-id="97bea-378">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="97bea-379">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-379">**Issue:**</span></span>

<span data-ttu-id="97bea-380">IPv6 が有効な状態でトポロジを構成すると、以前のバージョンの画面共有プラグインが既にインストールされている場合、ユーザーは Lync Web App クライアントから画面を共有できません。</span><span class="sxs-lookup"><span data-stu-id="97bea-380">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="97bea-381">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-381">**Workaround:**</span></span>

<span data-ttu-id="97bea-382">Lync Web App を使用して会議に参加するときに、最新バージョンの画面共有プラグインを強制的に更新するには、次の両方のファイルで **Minsupportedbuildversion** の値を "4.0.7457.0" から "4.0.7577.380" に変更します。</span><span class="sxs-lookup"><span data-stu-id="97bea-382">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="97bea-383">% ProgramFiles% \\ Microsoft Lync Server 15 \\ Web コンポーネント \\ が \\ Int \\ クライアント \\ プラグインに到達 \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="97bea-383">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="97bea-384">% ProgramFiles% \\ Microsoft Lync Server 15 \\ Web コンポーネント \\ は \\ Ext \\ クライアント \\ プラグインに到達 \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="97bea-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="97bea-385">用に構成します</span><span class="sxs-lookup"><span data-stu-id="97bea-385">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="97bea-386">場合によっては、IPv4 と IPv6 デュアルスタックを使用するように構成されたコンピューター上で実行されている Lync クライアントが、E911、メディアバイパス、通話受付管理、場所ベースのルーティングなどのコンピューターの IP サブネットに依存する機能をサポートしていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-386">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="97bea-387">このセクションの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。</span><span class="sxs-lookup"><span data-stu-id="97bea-387">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="97bea-388">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-388">**Issue:**</span></span>

<span data-ttu-id="97bea-389">Lync クライアントが、IPv4 と IPv6 のデュアルスタックが有効になっていて、プロキシサーバーの DNS 解決に基づいてコンピューター上で実行されている場合、クライアントはコンピューターの IPv6 アドレスを使用してサインインすることができます。</span><span class="sxs-lookup"><span data-stu-id="97bea-389">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="97bea-390">その後、Lync クライアントは IPv6 に対してサポートされている機能のみをサポートします。これにより、E911、メディアバイパス、通話受付管理、および場所ベースのルーティングが除外されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-390">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="97bea-391">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-391">**Workaround:**</span></span>

<span data-ttu-id="97bea-392">この問題を回避するには、クライアントコンピューター上で IPv6 サポートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="97bea-392">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="97bea-393">エンタープライズ Voip がユーザーに対して構成されていない場合、ユーザーは、電話会議からダイヤルアウトするために E164 形式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-393">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="97bea-394">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-394">**Issue:**</span></span>

<span data-ttu-id="97bea-395">エンタープライズ Voip がユーザーに対して構成されていない場合、そのユーザーは、E164 形式を使用して会議からのダイヤルアウトを成功させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-395">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="97bea-396">E164 形式が使用されていない場合、ユーザーは会議からダイヤルアウトできません。</span><span class="sxs-lookup"><span data-stu-id="97bea-396">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="97bea-397">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-397">**Workaround:**</span></span>

<span data-ttu-id="97bea-398">この問題を回避するには、エンタープライズ Voip が有効になっていないユーザーは、E164 形式の番号を使用して電話会議からダイヤルアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-398">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="97bea-399">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="97bea-399">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="97bea-400">統合連絡先ストアがユーザーに対して有効になっているときに、ユーザーが "招待と通信をすべてブロックする" を選択している場合、プレゼンス状態が拒否されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-400">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="97bea-401">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-401">**Issue:**</span></span>

<span data-ttu-id="97bea-402">統合連絡先ストアがユーザーに対して有効になっているときに、ユーザーが "招待と通信をすべてブロックする" を選択した場合、プレゼンス状態が拒否されないはずです。</span><span class="sxs-lookup"><span data-stu-id="97bea-402">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="97bea-403">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-403">**Workaround:**</span></span>

<span data-ttu-id="97bea-404">この問題を回避するには、ユーザーの統合連絡先ストアを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="97bea-404">To work around this issue, you can turn off the unified contact store for the user.</span></span> <span data-ttu-id="97bea-405">これを行うには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="97bea-405">To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="97bea-406">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="97bea-406">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="97bea-407">Office Communications Server 2007 R2 オンプレミスのユーザーが、ハイブリッド展開で Skype for Business Online ユーザーのプレゼンス状態を表示できない-ハイブリッド</span><span class="sxs-lookup"><span data-stu-id="97bea-407">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="97bea-408">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-408">**Issue:**</span></span>

<span data-ttu-id="97bea-409">この問題は、Lync Server 2013 ディレクターを使用している場合に、ハイブリッド展開で発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-409">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="97bea-410">Skype for Business Online に所属するユーザーのプレゼンス状態は、オンプレミスユーザーのプレゼンス不明として表示されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-410">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="97bea-411">また、Skype for Business Online に所属しているユーザーは、Office Communications Server R2 オンプレミスユーザーのプレゼンス状態を表示できません。</span><span class="sxs-lookup"><span data-stu-id="97bea-411">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="97bea-412">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-412">**Workaround:**</span></span>

<span data-ttu-id="97bea-413">この問題を部分的に回避するには、Skype for Business Online ユーザーのホームサーバー (msrtcsip) を、Lync Server 2013 ディレクターではなく、Lync Server 2013 社内プールを指すように変更します。</span><span class="sxs-lookup"><span data-stu-id="97bea-413">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="97bea-414">この設定は、オンプレミスのフロントエンドサーバーで変更できます。</span><span class="sxs-lookup"><span data-stu-id="97bea-414">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="97bea-415">この回避策では、Office Communications Server 2007 R2 に所属するユーザーのプレゼンス状態が Skype for Business Online ユーザーに正しく表示されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-415">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="97bea-416">応答グループアプリケーション、コールパークアプリケーション、グループ通話ピックアップ</span><span class="sxs-lookup"><span data-stu-id="97bea-416">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="97bea-417">発信者は、取得側で通話を発信している間、保留音の1秒間を聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="97bea-417">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="97bea-418">このセクションの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。</span><span class="sxs-lookup"><span data-stu-id="97bea-418">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="97bea-419">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-419">**Issue:**</span></span>

<span data-ttu-id="97bea-420">グループ通話ピックアップを使用して通話を取得した場合、発信者は取得側で通話を確立している間、保留音の1秒間を聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="97bea-420">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="97bea-421">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-421">**Workaround:**</span></span>

<span data-ttu-id="97bea-422">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-422">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="97bea-423">応答グループエージェントは、Lync Server 2010 エージェントコンソールを使用して Lync server 2010 の正式なエージェントグループのみにサインインしてサインアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="97bea-423">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="97bea-424">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-424">**Issue:**</span></span>

<span data-ttu-id="97bea-425">Lync Server 2013 応答グループエージェントは、lync server 2010 エージェントコンソールを使用して、lync server 2010 の正式なエージェントグループのみにサインインしてサインアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="97bea-425">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="97bea-426">Lync Server 2010 エージェントコンソールでは、ユーザーは自分が属している Lync Server 2010 応答グループのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="97bea-426">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="97bea-427">自分が属している Lync Server 2013 応答グループを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="97bea-427">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="97bea-428">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-428">**Workaround:**</span></span>

<span data-ttu-id="97bea-429">応答グループエージェントが Lync Server 2013 ユーザーであり、Lync Server 2013 の正式なエージェントグループの一部である場合、ユーザーは、ブラウザーの web リンクを介して直接 Lync Server 2013 エージェントコンソールにアクセスし、Lync Server の2013エージェントグループにサインインしてサインアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-429">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="97bea-430">Lync Server 2010 応答グループエージェントは、Lync Server 2013 応答グループの代理として通話を行うことができません</span><span class="sxs-lookup"><span data-stu-id="97bea-430">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="97bea-431">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-431">**Issue:**</span></span>

<span data-ttu-id="97bea-432">Lync Server 2010 Lync Server 2013 応答グループのエージェントであるユーザーは、応答グループの代わりに通話を行うことができません。</span><span class="sxs-lookup"><span data-stu-id="97bea-432">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="97bea-433">Lync Server 2013 応答グループは、通話を行うために Lync クライアントで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="97bea-433">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="97bea-434">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-434">**Workaround:**</span></span>

<span data-ttu-id="97bea-435">この問題を回避するには、Lync Server 2010 ユーザーを Lync Server 2013 に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-435">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="97bea-436">Lync server 2013 に移行された後で Lync Server 2010 から応答グループを削除すると、応答グループは着信呼び出しを受け付けなくなります。</span><span class="sxs-lookup"><span data-stu-id="97bea-436">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="97bea-437">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-437">**Issue:**</span></span>

<span data-ttu-id="97bea-438">Lync server 2010 から Lync Server 2013 に移行された応答グループが lync server の [コントロールパネル] または [Lync Server 管理シェル] から2010削除された場合、Lync Server 2013 の応答グループは着信呼び出しの受信を停止します。</span><span class="sxs-lookup"><span data-stu-id="97bea-438">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="97bea-439">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-439">**Workaround:**</span></span>

<span data-ttu-id="97bea-440">この問題を回避するには、lync server 2010 から Lync Server 2013 に移行された Lync Server 2010 から応答グループを削除しないようにします。</span><span class="sxs-lookup"><span data-stu-id="97bea-440">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="97bea-441">応答グループが既に削除されている場合は、Lync Server 2013 に再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-441">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="97bea-442">新しい管理ワークフローを作成時に非アクティブに設定すると、ワークフローの展開に失敗します。</span><span class="sxs-lookup"><span data-stu-id="97bea-442">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="97bea-443">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-443">**Issue:**</span></span>

<span data-ttu-id="97bea-444">新しい管理ワークフローを作成時に非アクティブに設定すると、ワークフローの展開は失敗します。</span><span class="sxs-lookup"><span data-stu-id="97bea-444">When a new managed workflow is set to inactive when created, deployment of the workflow will fail.</span></span> <span data-ttu-id="97bea-445">この問題は、作成時にワークフローが非アクティブに設定されている場合に発生しますが、が展開された後に非アクティブに設定するように編集されたワークフローには影響しません。</span><span class="sxs-lookup"><span data-stu-id="97bea-445">This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="97bea-446">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-446">**Workaround:**</span></span>

<span data-ttu-id="97bea-447">ワークフローを作成して展開するときは、ワークフローをアクティブに設定して展開します。</span><span class="sxs-lookup"><span data-stu-id="97bea-447">When creating and deploying a workflow, set the workflow as active and then deploy it.</span></span> <span data-ttu-id="97bea-448">ワークフローが正常に展開された後、ワークフローを編集して非アクティブに設定できます。</span><span class="sxs-lookup"><span data-stu-id="97bea-448">After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="97bea-449">応答グループがバックアッププールにインポートされている場合、所有者プールから応答グループを削除すると、フェールオーバー中のすべての着信呼び出しがバックアッププールの応答グループによって受け付けられなくなります。</span><span class="sxs-lookup"><span data-stu-id="97bea-449">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="97bea-450">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-450">**Issue:**</span></span>

<span data-ttu-id="97bea-451">プライマリプールに所有されている応答グループが所有者を上書きせずにバックアッププールにインポートされ、所有者プールから応答グループが削除された場合、バックアッププールの応答グループは、フェールオーバー中に着信呼び出しを受け付けません。</span><span class="sxs-lookup"><span data-stu-id="97bea-451">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="97bea-452">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-452">**Workaround:**</span></span>

<span data-ttu-id="97bea-453">プライマリプールに応答グループを再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-453">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="97bea-454">その後、プライマリプールから応答グループの構成をエクスポートして、もう一度バックアッププールにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-454">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="97bea-455">バックアッププールで応答グループを再作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="97bea-455">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="97bea-456">この場合、バックアッププールは応答グループの所有者プールになります。</span><span class="sxs-lookup"><span data-stu-id="97bea-456">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="97bea-457">応答グループの代理として取得要求が行われた場合、コールパークアプリケーションから保留中の通話を取得することはできません</span><span class="sxs-lookup"><span data-stu-id="97bea-457">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="97bea-458">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-458">**Issue:**</span></span>

<span data-ttu-id="97bea-459">次の条件に該当する場合、保留中の通話の取得要求は失敗します。</span><span class="sxs-lookup"><span data-stu-id="97bea-459">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="97bea-460">エージェントが匿名応答グループに含まれている</span><span class="sxs-lookup"><span data-stu-id="97bea-460">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="97bea-461">エージェントは、呼び出しパークアプリケーションからの保留中の呼び出しを匿名応答グループを介して取得しようとします。</span><span class="sxs-lookup"><span data-stu-id="97bea-461">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="97bea-462">エージェントは、[代理人として呼び出し] オプションまたは Lync アテンダントクライアントの同じオプションを使用して、オービット番号をダイヤルして通話を取得しようとしています。</span><span class="sxs-lookup"><span data-stu-id="97bea-462">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="97bea-463">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-463">**Workaround:**</span></span>

<span data-ttu-id="97bea-464">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-464">There are no workarounds for this issue.</span></span> <span data-ttu-id="97bea-465">保留中の呼び出しは、応答グループの代理としてではなく、取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-465">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="97bea-466">Lync Server コントロール パネル、トポロジ ビルダー、および計画ツール</span><span class="sxs-lookup"><span data-stu-id="97bea-466">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="97bea-467">計画ツールの制限事項</span><span class="sxs-lookup"><span data-stu-id="97bea-467">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="97bea-468">このセクションの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。</span><span class="sxs-lookup"><span data-stu-id="97bea-468">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="97bea-469">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-469">**Issue:**</span></span>

<span data-ttu-id="97bea-470">展開を計画する場合、計画ツールには次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-470">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="97bea-471">最大10個の中央サイトがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="97bea-471">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="97bea-472">各中央サイトには、最大14個のブランチサイトを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="97bea-472">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="97bea-473">各中央サイトには、最大24万ユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="97bea-473">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="97bea-474">また、計画ツールでは、推奨されるトポロジを計算する際に、次の値は含まれません。</span><span class="sxs-lookup"><span data-stu-id="97bea-474">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="97bea-475">オンラインに所属しているユーザーの数</span><span class="sxs-lookup"><span data-stu-id="97bea-475">The number of users that are homed online</span></span>

  - <span data-ttu-id="97bea-476">XMPP フェデレーションが有効になっているユーザーの割合</span><span class="sxs-lookup"><span data-stu-id="97bea-476">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="97bea-477">Lync Web App を使用しているユーザーの割合</span><span class="sxs-lookup"><span data-stu-id="97bea-477">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="97bea-478">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-478">**Workaround:**</span></span>

<span data-ttu-id="97bea-479">これらの問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-479">There is no workaround for these issues.</span></span> <span data-ttu-id="97bea-480">計画ツールの詳細については、「 [計画ツールを使用して Lync Server 2013 のトポロジを設計](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97bea-480">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="97bea-481">計画ツールでオプションを更新するときに、エッジネットワークに対して定義済みの IP アドレスが使用されないことがある</span><span class="sxs-lookup"><span data-stu-id="97bea-481">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="97bea-482">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-482">**Issue:**</span></span>

<span data-ttu-id="97bea-483">計画ツールを使用して設計を完了した後、エッジネットワークオプションを変更すると、既存の IP アドレスを更新するのではなく、追加の IP アドレスが設計に追加されることがあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-483">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="97bea-484">これは、エッジネットワークダイアグラムの詳細を表示しているときに、 **[ここをクリックしてオプションを更新**します] を選択し、[構成オプション] ダイアログボックスの [エッジネットワーク] を選択します。 [ **同じ fqdn および IP アドレスを使用するが、エッジサーバー上のエッジサービスに異なるポートを使用**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97bea-484">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="97bea-485">変更を適用すると、新しい IP アドレスとエッジサーバーが設計に追加されることがあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-485">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="97bea-486">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-486">**Workaround:**</span></span>

<span data-ttu-id="97bea-487">現時点では、この問題を回避する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-487">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="97bea-488">Lync Server コントロールパネルで、[すべてのユーザーをプールに移動] が期待どおりに機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-488">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="97bea-489">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-489">**Issue:**</span></span>

<span data-ttu-id="97bea-490">Lync Server コントロールパネルを使用して、複数のドメインコントローラーや親/子ドメインなど、複雑な Active Directory 環境にあるプールから別のプールにすべてのユーザーを移動する場合、エラーメッセージが返されることがあります。 "指定されたユーザーはレガシユーザーではないため、代わりに Move-CsUser コマンドレットを使用してください。</span><span class="sxs-lookup"><span data-stu-id="97bea-490">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="97bea-491">複雑な Active Directory 環境では、レプリケーション時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="97bea-491">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="97bea-492">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-492">**Workaround:**</span></span>

<span data-ttu-id="97bea-493">この問題を回避するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="97bea-493">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="97bea-494">Lync Server コントロールパネルのフィルターを使用して、レガシユーザーを検索し、それらのユーザーを選択してから、[ **選択したユーザーをプールに移動] コマンド** を使用して、 **すべてのユーザーをプールに移動**します。</span><span class="sxs-lookup"><span data-stu-id="97bea-494">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="97bea-495">Lync server のコマンドレットを使用して、バッチで従来のユーザーを移動するには、Lync Server 管理シェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="97bea-495">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="97bea-496">Microsoft Silverlight ブラウザープラグインがバージョン5に更新された後、Lync Server コントロールパネルが VMware 環境で機能しなくなる</span><span class="sxs-lookup"><span data-stu-id="97bea-496">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="97bea-497">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-497">**Issue:**</span></span>

<span data-ttu-id="97bea-498">VMware 環境で Lync Server コントロールパネルを使用すると、Silverlight をバージョン5にアップグレードした後、Lync Server コントロールパネルが機能しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-498">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="97bea-499">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-499">**Workaround:**</span></span>

<span data-ttu-id="97bea-500">この問題を回避するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="97bea-500">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="97bea-501">Silverlight 5 をアンインストールし、から Silverlight 4 をインストールし [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0) ます。</span><span class="sxs-lookup"><span data-stu-id="97bea-501">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="97bea-502">VMware 仮想コンピューターではないコンピューターから Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="97bea-502">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="97bea-503">リモートコンピューターから Lync server コントロールパネルを開くには、コンピューターに Lync Server 管理ツールをインストールしてから、Windows の [ **スタート** ] メニューから Lync Server コントロールパネルを起動します。</span><span class="sxs-lookup"><span data-stu-id="97bea-503">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="97bea-504">Web ブラウザーに URL を入力して、Lync Server コントロールパネルを開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="97bea-504">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="97bea-505">URL は https:///cscp. に似ています。 \<frontend\_pool\_fqdn\></span><span class="sxs-lookup"><span data-stu-id="97bea-505">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="97bea-506">トポロジビルダーでミラーリングデータベースを削除した後、管理者がアンインストール-csMirrorDB コマンドレットを実行できない</span><span class="sxs-lookup"><span data-stu-id="97bea-506">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="97bea-507">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-507">**Issue:**</span></span>

<span data-ttu-id="97bea-508">管理者がトポロジビルダーでミラーリングデータベースを無効にした後、トポロジビルダーでミラーリングデータベースを削除すると、管理者が **install-csmirrordatabase** コマンドレットを実行して SQL Server からミラーリングを削除するように、メッセージが [タスク] 一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-508">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="97bea-509">管理者がコマンドレットを実行しようとすると、失敗します。</span><span class="sxs-lookup"><span data-stu-id="97bea-509">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="97bea-510">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-510">**Workaround:**</span></span>

<span data-ttu-id="97bea-511">トポロジビルダーでプールの SQL ミラーリングを削除するには、最初にコマンドレットを使用して、SQL Server でミラーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-511">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="97bea-512">次に、トポロジ ビルダーを使用して、トポロジからミラーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="97bea-512">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="97bea-513">SQL Server でミラーを削除するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="97bea-513">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="97bea-514">たとえば、ミラーリングを削除してユーザーデータベースのデータベースをドロップするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="97bea-514">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="97bea-515">*Dropexistingdatabases Onmirror*パラメーターを指定すると、影響を受けるデータベースがミラーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-515">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="97bea-516">次に、トポロジからミラーを削除するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="97bea-516">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="97bea-517">トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97bea-517">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="97bea-518">[ **SQL ストアミラーリングの有効化** ] をオフにして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97bea-518">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="97bea-519">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="97bea-519">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="97bea-520">バックエンドデータベースミラーリング関係を変更するたびに、プール内のすべてのフロントエンドサーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-520">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="97bea-521">管理者が関連付けられた監視ストアを持つフロントエンドプールを使用して展開を削除しようとすると、トポロジビルダーで検証エラーが返される</span><span class="sxs-lookup"><span data-stu-id="97bea-521">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="97bea-522">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-522">**Issue:**</span></span>

<span data-ttu-id="97bea-523">管理者がトポロジビルダーの [ **展開の削除** ] コマンドを使用して、関連付けられた監視ストアを持つフロントエンドプールを含む展開を削除しようとすると、検証エラーがトポロジビルダーに表示され、操作は続行されません。</span><span class="sxs-lookup"><span data-stu-id="97bea-523">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="97bea-524">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-524">**Workaround:**</span></span>

<span data-ttu-id="97bea-525">この問題を回避するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="97bea-525">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="97bea-526">展開を削除する前に、ミラーリング監視ストアを削除します。</span><span class="sxs-lookup"><span data-stu-id="97bea-526">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="97bea-527">フロントエンドプールのミラーリング監視ストアを追加し、削除します。</span><span class="sxs-lookup"><span data-stu-id="97bea-527">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="97bea-528">計画ツールとトポロジビルダーの間で常設チャットサーバーの展開情報が矛盾している</span><span class="sxs-lookup"><span data-stu-id="97bea-528">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="97bea-529">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-529">**Issue:**</span></span>

<span data-ttu-id="97bea-530">Lync Server 2013 の計画ツールが、障害復旧を有効にした常設チャットサーバーの展開のためのサイトトポロジ図を出力すると、サイトトポロジの図には複数の (物理的な) サイトが含まれ、各サイトで常設チャットサーバーが均等に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="97bea-530">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="97bea-531">トポロジビルダーでは、すべての常設チャットサーバーは、1つの (論理的な) サイトに属するものとして表され、同じ常設チャットサーバープールノードの下に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-531">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="97bea-532">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-532">**Workaround:**</span></span>

<span data-ttu-id="97bea-533">現時点では、この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-533">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="97bea-534">常設チャットサーバーの展開の計画ツールの出力を分析し、特定のニーズに合わせて計画を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-534">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="97bea-535">ローカリゼーション</span><span class="sxs-lookup"><span data-stu-id="97bea-535">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="97bea-536">監視</span><span class="sxs-lookup"><span data-stu-id="97bea-536">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="97bea-537">日本語版の Lync Server を使用している場合、監視レポートの展開ウィザードで、特定の状況で誤った文字が表示される</span><span class="sxs-lookup"><span data-stu-id="97bea-537">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="97bea-538">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-538">**Issue:**</span></span>

<span data-ttu-id="97bea-539">日本語版の Lync Server 2013 (中国語 (簡体字)、中国語 (繁体字)、日本語、韓国語を使用している場合、システムロケールが東アジア言語に設定されていないオペレーティングシステムで、[監視レポートの展開] ウィザードには、ローカライズされたメッセージではなく、疑問符または他の文字が表示されます</span><span class="sxs-lookup"><span data-stu-id="97bea-539">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="97bea-540">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-540">**Workaround:**</span></span>

<span data-ttu-id="97bea-541">この問題を解決するには、オペレーティングシステムと Lync Server 2013 のロケールを同じ言語に設定して、すべてのメッセージが正しく表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="97bea-541">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="97bea-542">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="97bea-542">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="97bea-543">場合によっては、トップナビゲーションバーのページ上のトップナビゲーションバーの最初の項目が表示されなくなると、トップナビゲーションバーの最後の項目がクリックされます。</span><span class="sxs-lookup"><span data-stu-id="97bea-543">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="97bea-544">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-544">**Issue:**</span></span>

<span data-ttu-id="97bea-545">次の3つの既知のケースでは、Lync Server コントロールパネルのページにあるトップナビゲーションバーの最後の項目をクリックすると、トップナビゲーションバーの最初の項目が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="97bea-545">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="97bea-546">フランス語版のページ "Féderation et accès externe" では、"Partenaires d'accès XMPP" がクリックされたときに "Stratégie externe fédérés" という項目が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="97bea-546">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="97bea-547">ドイツ語版の "Clients" ページで "クリックすると" がクリックされると、アイテム "Clientversionskonfiguration" が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="97bea-547">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="97bea-548">ロシア語版の "Конфигурациясети" ページで "Маршрутрегиона" をクリックすると、"Глобально" という項目が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="97bea-548">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="97bea-549">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-549">**Workaround:**</span></span>

<span data-ttu-id="97bea-550">この問題を回避するには、ブラウザーで Lync Server コントロールパネルのページを更新します。</span><span class="sxs-lookup"><span data-stu-id="97bea-550">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="97bea-551">トップナビゲーションバーに表示されるすべてのアイテムと共に、ページがブラウザーに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="97bea-551">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="97bea-552">アドレス帳</span><span class="sxs-lookup"><span data-stu-id="97bea-552">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="97bea-553">一部の言語で、アドレス帳のインデックス処理が期待どおりに機能しない</span><span class="sxs-lookup"><span data-stu-id="97bea-553">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="97bea-554">このセクションの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。</span><span class="sxs-lookup"><span data-stu-id="97bea-554">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="97bea-555">ユーザーのプロパティにインデックスフィールドが含まれており、そのフィールドにインデックスを作成できない文字のみが含まれている場合、そのユーザーはアドレス帳で実行される検索には表示されません。</span><span class="sxs-lookup"><span data-stu-id="97bea-555">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="97bea-556">次の文字とロケールのインデックスを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="97bea-556">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="97bea-557">大文字のキリル文字、ギリシャ文字、およびアルメニア文字</span><span class="sxs-lookup"><span data-stu-id="97bea-557">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="97bea-558">大文字のアクセント記号付き文字</span><span class="sxs-lookup"><span data-stu-id="97bea-558">Upper-case accented characters</span></span>

  - <span data-ttu-id="97bea-559">タイ語</span><span class="sxs-lookup"><span data-stu-id="97bea-559">Thai</span></span>

  - <span data-ttu-id="97bea-560">ラオス語</span><span class="sxs-lookup"><span data-stu-id="97bea-560">Lao</span></span>

  - <span data-ttu-id="97bea-561">ミャンマー</span><span class="sxs-lookup"><span data-stu-id="97bea-561">Myanmar</span></span>

  - <span data-ttu-id="97bea-562">デバナガリ</span><span class="sxs-lookup"><span data-stu-id="97bea-562">Devanagari</span></span>

  - <span data-ttu-id="97bea-563">エチオピア</span><span class="sxs-lookup"><span data-stu-id="97bea-563">Ethiopic</span></span>

  - <span data-ttu-id="97bea-564">チベット語</span><span class="sxs-lookup"><span data-stu-id="97bea-564">Tibetan</span></span>

  - <span data-ttu-id="97bea-565">ベンガル語</span><span class="sxs-lookup"><span data-stu-id="97bea-565">Bengali</span></span>

  - <span data-ttu-id="97bea-566">グジャラート語</span><span class="sxs-lookup"><span data-stu-id="97bea-566">Gujarati</span></span>

  - <span data-ttu-id="97bea-567">テルグ語</span><span class="sxs-lookup"><span data-stu-id="97bea-567">Telugu</span></span>

  - <span data-ttu-id="97bea-568">他のすべてのインド諸語スクリプト</span><span class="sxs-lookup"><span data-stu-id="97bea-568">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="97bea-569">Lync Web App、Web Scheduler、および Web コンポーネント</span><span class="sxs-lookup"><span data-stu-id="97bea-569">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="97bea-570">Lync Web Scheduler、ダイヤルイン、参加起動ツール、常設チャットルーム管理、および OCTab の特定の言語の言語フォールバックが期待どおりに機能しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-570">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="97bea-571">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-571">**Issue:**</span></span>

<span data-ttu-id="97bea-572">Web ブラウザーでニュートラルロケールを選択する (Internet Explorer の場合) たとえば、 \[ \] 言語、スクリプト、およびロケール ("ノルウェー語、ブークモール (ノルウェー) NB-いいえ" など) を指定するロケールの代わりに、"ノルウェー no" のような仕様のない言語名は、 \[ \] Lync web Scheduler、ダイヤルイン、参加起動ツール、常設チャットルーム管理、および [octab] タブの特定の言語に対して予期しない表示動作を</span><span class="sxs-lookup"><span data-stu-id="97bea-572">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="97bea-573">たとえば、次の言語のいずれかが選択されている場合、ユーザーには英語のページが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-573">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="97bea-574">ノルウェー語</span><span class="sxs-lookup"><span data-stu-id="97bea-574">Norwegian</span></span>

  - <span data-ttu-id="97bea-575">ポルトガル語</span><span class="sxs-lookup"><span data-stu-id="97bea-575">Portuguese</span></span>

  - <span data-ttu-id="97bea-576">セルビア語</span><span class="sxs-lookup"><span data-stu-id="97bea-576">Serbian</span></span>

<span data-ttu-id="97bea-577">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-577">**Workaround:**</span></span>

<span data-ttu-id="97bea-578">ニュートラルロケールの言語を選択する場合は、ブラウザーの言語設定一覧で、特定のロケール (スクリプトや国コードを含む) が追加言語として追加されていることを必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="97bea-578">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="97bea-579">一部の web ブラウザーでは、Lync Web Scheduler、ダイヤルイン、参加起動ツール、常設チャットルーム管理、および OCTab を使用する場合に、アゼルバイジャンおよびウズベク語のサポートが制限されています。</span><span class="sxs-lookup"><span data-stu-id="97bea-579">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="97bea-580">このセクションの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。</span><span class="sxs-lookup"><span data-stu-id="97bea-580">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="97bea-581">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-581">**Issue:**</span></span>

<span data-ttu-id="97bea-582">Internet Explorer 8 または Internet Explorer 9 を使用していて、ブラウザーの言語をアゼルバイジャン語 (ラテン) またはウズベク語 (ラテン) に設定すると、ダイヤルインページと参加起動ツールページが英語で表示されるか、ブラウザーで優先言語セットとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-582">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="97bea-583">Firefox または Chrome ブラウザーを使用している場合、ブラウザーの言語をアゼルバイジャン語 (ラテン) またはウズベク語 (ラテン) に設定すると、Lync Web App、Lync Web Scheduler、および RGS OCTab が英語で表示されるか、ブラウザーの優先言語セットとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-583">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="97bea-584">Safari ブラウザーでは、ウズベク語 (ラテン) ロケールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97bea-584">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="97bea-585">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-585">**Workaround:**</span></span>

<span data-ttu-id="97bea-586">これらの問題を回避する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-586">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="97bea-587">ルーマニア語版の Lync Web App の [会議に参加] リストにドロップダウン矢印が表示されない</span><span class="sxs-lookup"><span data-stu-id="97bea-587">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="97bea-588">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-588">**Issue:**</span></span>

<span data-ttu-id="97bea-589">ルーマニア語版の Lync Web App を使用しているユーザーが次の手順を実行すると、[ **会議に参加** ] ドロップダウンリストにドロップダウン矢印が表示されません。</span><span class="sxs-lookup"><span data-stu-id="97bea-589">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="97bea-590">[**全般**] タブの [**このコンピューターにあるメールを記憶**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97bea-590">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="97bea-591">[ **電話** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="97bea-591">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="97bea-592">[ **会議に参加**する] のドロップダウンリストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="97bea-592">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="97bea-593">ユーザーには、既定の **Lync Web App**より多くのオプションがあることを示す矢印は表示されません。これには、[ **オーディオに参加しない** ] (ルーマニア語、"ニュー se asociaža la componenta audio")、および [ **新しい番号**] (ルーマニア語、"Număr nou") が含まれます。</span><span class="sxs-lookup"><span data-stu-id="97bea-593">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="97bea-594">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-594">**Workaround:**</span></span>

<span data-ttu-id="97bea-595">このドロップダウンリストの矢印は表示されませんが、ユーザーは既定値をクリックして、リスト内の追加の設定を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="97bea-595">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="97bea-596">トルコ語版の Lync Web Scheduler を使用している場合、[発表者となるユーザー] の [選択したユーザー] オプションを使用すると、会議を保存できません。</span><span class="sxs-lookup"><span data-stu-id="97bea-596">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="97bea-597">**問題**</span><span class="sxs-lookup"><span data-stu-id="97bea-597">**Issue:**</span></span>

<span data-ttu-id="97bea-598">トルコ語版の Lync Web Scheduler で会議を作成または編集する場合、[発表者となるユーザー] の [選択したユーザー] オプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97bea-598">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported.</span></span> <span data-ttu-id="97bea-599">このオプションを選択すると、会議を保存できません。</span><span class="sxs-lookup"><span data-stu-id="97bea-599">When this option is selected, the meeting can't be saved.</span></span> <span data-ttu-id="97bea-600">代わりに、1人以上のユーザーがプレゼンターを作成できないことを示すエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-600">Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="97bea-601">**回避策**</span><span class="sxs-lookup"><span data-stu-id="97bea-601">**Workaround:**</span></span>

<span data-ttu-id="97bea-602">この問題を回避するには、ユーザーは "会社のユーザーからの人"、または "会社外の人を含むすべての人を含むすべてのユーザー" の既定のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="97bea-602">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company."</span></span> <span data-ttu-id="97bea-603">開催者は後で会議に参加した後で、ユーザーを適切な役割に降格または昇格させることができます。</span><span class="sxs-lookup"><span data-stu-id="97bea-603">The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="97bea-604">別の言語を理解しているユーザーは、ブラウザーでの言語の選択を他の43でサポートされている言語のいずれかに変更し、"ユーザーが選択した" オプションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="97bea-604">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="97bea-605">著作権</span><span class="sxs-lookup"><span data-stu-id="97bea-605">Copyright</span></span>

<span data-ttu-id="97bea-606">このドキュメントでは、最終的な商用リリースの前に実質的に変更される可能性があるソフトウェア製品の予備リリースがサポートされています。また、Microsoft Corporation の機密情報でもあります。</span><span class="sxs-lookup"><span data-stu-id="97bea-606">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation.</span></span> <span data-ttu-id="97bea-607">これは、受信者と Microsoft との間の機密保持契約に基づいて開示されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-607">It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft.</span></span> <span data-ttu-id="97bea-608">このドキュメントは情報提供のみを目的として提供されており、このドキュメントでは明示的にも黙示的にもいかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="97bea-608">This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document.</span></span> <span data-ttu-id="97bea-609">このドキュメントに記載されている情報 (URL やその他のインターネット web サイトへの参照を含む) は、将来予告なしに変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97bea-609">Information in this document, including URL and other Internet website references, is subject to change without notice.</span></span> <span data-ttu-id="97bea-610">このドキュメントを使用した場合のリスク全体またはその結果は、ユーザーによって保持されます。</span><span class="sxs-lookup"><span data-stu-id="97bea-610">The entire risk of the use or the results from the use of this document remains with the user.</span></span> <span data-ttu-id="97bea-611">別途記載されていない限り、このドキュメントで使用している会社、組織、製品、ドメイン名、電子メールアドレス、ロゴ、人物、場所、およびイベントは架空のものです。</span><span class="sxs-lookup"><span data-stu-id="97bea-611">Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="97bea-612">実在する会社、組織、製品、ドメイン名、電子メールアドレス、ロゴ、人物、場所、またはイベントには、意図されていないか、または推論する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-612">No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="97bea-613">該当するすべての著作権法の順守は、ユーザー側の責任となります。</span><span class="sxs-lookup"><span data-stu-id="97bea-613">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="97bea-614">著作権法の範囲に限定されることなく、米国 Microsoft Corporation の書面による明示的な許諾なしに、このドキュメントのいかなる部分も、いかなる形式または手段 (電子的、機械的、コピー複写、記録、またはその他の方法) で、またはいかなる目的でも、複製、保存、検索システム導入、または転送することはできません。</span><span class="sxs-lookup"><span data-stu-id="97bea-614">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="97bea-p162">マイクロソフトは、このドキュメントに記載されている内容に関し、特許、特許申請、商標、著作権、またはその他の無体財産権を有する場合があります。別途マイクロソフトのライセンス契約上に明示の規定のない限り、このドキュメントはこれらの特許、商標、著作権、またはその他の無体財産権に関する権利をお客様に許諾するものではありません。</span><span class="sxs-lookup"><span data-stu-id="97bea-p162">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="97bea-617">c 2012 Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="97bea-617">© 2012 Microsoft Corporation.</span></span> <span data-ttu-id="97bea-618">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="97bea-618">All rights reserved.</span></span>

<span data-ttu-id="97bea-619">Microsoft、Windows、Windows Live、Active Directory、Internet Explorer、MSN、Outlook、および SQL Server は、米国 Microsoft Corporation の米国およびその他の国/地域における登録商標または商標です。</span><span class="sxs-lookup"><span data-stu-id="97bea-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="97bea-620">その他すべての商標は各社が所有しています。</span><span class="sxs-lookup"><span data-stu-id="97bea-620">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

