---
title: Lync Server 2013 リリースノート
description: Lync Server 2013 リリースノート。
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
ms.openlocfilehash: 33fabb0912d7ea3defd91014df732368eced909e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555873"
---
# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="1c83f-103">Lync Server 2013 のリリースノート</span><span class="sxs-lookup"><span data-stu-id="1c83f-103">Release notes for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c83f-104">_**トピックの最終更新日:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="1c83f-104">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="1c83f-105">Lync Server 2013 リリースノートへようこそ。</span><span class="sxs-lookup"><span data-stu-id="1c83f-105">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="1c83f-106">Lync Server 2013 の既知の問題に関する情報については、このファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c83f-106">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="1c83f-107">このドキュメントについて</span><span class="sxs-lookup"><span data-stu-id="1c83f-107">About this document</span></span>

<span data-ttu-id="1c83f-108">このドキュメントには、Lync Server 2013 を展開して使用する前に知っておく必要がある重要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1c83f-108">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="1c83f-109">Lync Server 2013 の詳細については、「 [Microsoft Lync server 2013](microsoft-lync-server-2013.md) のドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c83f-109">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="1c83f-110">このドキュメントは、以下のセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="1c83f-110">This document contains the following sections:</span></span>

  - <span data-ttu-id="1c83f-111">Lync 2013 クライアント</span><span class="sxs-lookup"><span data-stu-id="1c83f-111">Lync 2013 client</span></span>

  - <span data-ttu-id="1c83f-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="1c83f-112">Lync Server</span></span>

  - <span data-ttu-id="1c83f-113">インストール</span><span class="sxs-lookup"><span data-stu-id="1c83f-113">Installation</span></span>

  - <span data-ttu-id="1c83f-114">身体</span><span class="sxs-lookup"><span data-stu-id="1c83f-114">Mobility</span></span>

  - <span data-ttu-id="1c83f-115">会議</span><span class="sxs-lookup"><span data-stu-id="1c83f-115">Conferencing</span></span>

  - <span data-ttu-id="1c83f-116">用に構成します</span><span class="sxs-lookup"><span data-stu-id="1c83f-116">Enterprise Voice</span></span>

  - <span data-ttu-id="1c83f-117">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="1c83f-117">Presence</span></span>

  - <span data-ttu-id="1c83f-118">応答グループ アプリケーションおよびコール パーク アプリケーション</span><span class="sxs-lookup"><span data-stu-id="1c83f-118">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="1c83f-119">Lync Server コントロール パネル、トポロジ ビルダー、および計画ツール</span><span class="sxs-lookup"><span data-stu-id="1c83f-119">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="1c83f-120">ローカリゼーション</span><span class="sxs-lookup"><span data-stu-id="1c83f-120">Localization</span></span>

  - <span data-ttu-id="1c83f-121">著作権</span><span class="sxs-lookup"><span data-stu-id="1c83f-121">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="1c83f-122">Lync 2013 クライアント</span><span class="sxs-lookup"><span data-stu-id="1c83f-122">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="1c83f-123">他のアプリケーションでファイルが開かれている場合に、インスタントメッセージでファイルを転送できない</span><span class="sxs-lookup"><span data-stu-id="1c83f-123">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="1c83f-124">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-124">**Issue:**</span></span>

<span data-ttu-id="1c83f-125">他の Lync ユーザーにインスタントメッセージでファイルを含めることによって、Word 文書などのファイルを転送しようとすると、転送は成功したように見えますが、実際にファイルの転送に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-125">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="1c83f-126">ファイルの種類のアイコンは Lync クライアントに表示されますが、目的の受信者はそのファイルを開くことができません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-126">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="1c83f-127">転送が成功しなかったことを通知するエラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-127">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="1c83f-128">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-128">**Workaround:**</span></span>

<span data-ttu-id="1c83f-129">この問題を回避するには、インスタントメッセージでファイルを転送する前に、開いているファイルまたはアプリケーションを閉じてください。</span><span class="sxs-lookup"><span data-stu-id="1c83f-129">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="1c83f-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="1c83f-130">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="1c83f-131">Lync Server ストレージサービスのデータレプリケーションが失敗した場合、管理者は古いストレージサービスキューアイテムのパフォーマンスカウンターをチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-131">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="1c83f-132">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-132">**Issue:**</span></span>

<span data-ttu-id="1c83f-133">Lync Server ストレージサービスは、レプリケーションに Windows Fabric を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-133">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="1c83f-134">プライマリフロントエンドサーバーでデータが削除されたが、セカンダリフロントエンドサーバーの削除が失敗した場合 (たとえば、フロントエンドサーバーに予期しないシャットダウンやエラーが発生した場合)、データは残され、"孤立" することがあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-134">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="1c83f-135">孤立したデータを使用すると、パフォーマンスが低下し、ドライブ領域が浪費されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-135">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="1c83f-136">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-136">**Workaround:**</span></span>

<span data-ttu-id="1c83f-137">この問題を回避するには、イベントログに "イベントを \_ \_ 指定してください" というイベント \_ \_ (id = 32058) と、その \_ 後に \_ \_ \_ 重大な (id = 32059) を使用していたデータベーススペースがイベントログに生成されている場合、管理者は、「 **LYSS - Current number of Storage Service stale queue items** **LS:** log service API」の下にあるフロントエンドサーバーのパフォーマンスカウンターを</span><span class="sxs-lookup"><span data-stu-id="1c83f-137">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="1c83f-138">このパフォーマンスカウンターに大きな値がある場合 (たとえば、50000より大きい場合)、管理者は Lync Server 2013 リソースキットの CleanuUpStorageServiceData.exe ツールを実行して、孤立したすべてのデータをプールから削除します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-138">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="1c83f-139">このツールの詳細については、Lync Server 2013 リソースキットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c83f-139">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="1c83f-140">サーバーまたはプールの IP アドレス構成が変更された場合は、Lync Server サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-140">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="1c83f-141">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-141">**Issue:**</span></span>

<span data-ttu-id="1c83f-142">Lync Server 2013 の展開に対して IP アドレス構成が変更された場合 (IPv4 からデュアルスタックへの変更、デュアルスタックから Ipv6 への変更など)、すべてのサーバーコンポーネントは、サービスが再起動されるまで構成変更を選択しません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-142">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="1c83f-143">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-143">**Workaround:**</span></span>

<span data-ttu-id="1c83f-144">この問題を回避するには、展開の IP アドレス構成を変更した後に Lync Server サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-144">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="1c83f-145">これを行うには、Lync Server 管理シェルで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-145">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="1c83f-146">ダイヤルイン会議代理トランザクションコマンドレットは、Lync Server 2013 管理パックでは使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1c83f-146">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="1c83f-147">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-147">**Issue:**</span></span>

<span data-ttu-id="1c83f-148">ダイヤルイン会議代理トランザクションコマンドレット **Test-csdial In会議** は、Lync Server 2013 管理パックでは使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1c83f-148">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="1c83f-149">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-149">**Workaround:**</span></span>

<span data-ttu-id="1c83f-150">ダイヤルイン会議代理トランザクションコマンドレットの使用 **テスト-Csdial Inコンファレンス** は、社内のみでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1c83f-150">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="1c83f-151">管理者は、トラブルシューティングの目的で、Lync Server 管理シェルのコマンドレットを引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-151">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="1c83f-152">必要に応じて、エンタープライズは、コマンドレットを内部的に実行するためのプライベート管理パックを開発することもできます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-152">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="1c83f-153">ログファイルがネットワーク共有にコピーされているときにネットワークトラフィックが中断された場合、集中ログサービスは停止します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-153">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="1c83f-154">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-154">**Issue:**</span></span>

<span data-ttu-id="1c83f-155">集中ログサービスがネットワークパスを使用するように構成さ **れている** 場合 (CacheFileNetworkFolder パラメーターの値が有効な UNC パスである)、キャッシュされたログファイルはネットワーク共有にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-155">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="1c83f-156">ファイルのコピー中にネットワークトラフィックで中断が発生すると、集中ログサービスが停止する例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-156">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="1c83f-157">サービスは、3回まで自動的に再起動するように構成されているため、最初の3つの例外から回復します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-157">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="1c83f-158">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-158">**Workaround:**</span></span>

<span data-ttu-id="1c83f-159">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-159">There is no workaround for this issue.</span></span> <span data-ttu-id="1c83f-160">この問題を特定するには、"Lync Server 集中ログサービスエージェント" サービスが予期せず終了したときにログに記録されるイベント ID 7031 のイベントログを監視します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-160">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="1c83f-161">これが3回を超えて発生する場合は、 **Start-CsWindowService** コマンドレットを使用して、サービスを手動で再起動します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-161">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="1c83f-162">ストレージサービスキューアイテムを手動でインポートする必要がある</span><span class="sxs-lookup"><span data-stu-id="1c83f-162">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="1c83f-163">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-163">**Issue:**</span></span>

<span data-ttu-id="1c83f-164">Lync Server 2013 は、アーカイブされたメッセージ、通話詳細記録 (CDR) などの会議やインスタントメッセージングに関するデータを、各フロントエンドサーバー上のデータベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-164">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="1c83f-165">データは、目的の宛先に配信される前に処理されている間、データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-165">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="1c83f-166">パフォーマンスを向上させるために、Lync Server 2013 は定期的に処理されないローカルデータベースからキューアイテムをエクスポートし、それをファイルストアに保存します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-166">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="1c83f-167">ファイルストアが使用できない場合、アイテムは各フロントエンドサーバーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-167">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="1c83f-168">プールフェールオーバー中のデータ損失を防止するために同じ操作が発生します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-168">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="1c83f-169">エクスポート操作の間に、Lync Server Storage サービスは、イベント Id 32075 のイベント Id (完全なフラッシュ操作が開始)、32076 (完全フラッシュ (完了))、32082 (メンテナンスレベルのフラッシュが開始)、32083 (メンテナンスレベルのフラッシュが完了 32089) の各ステージをイベントログに記録します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-169">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="1c83f-170">このデータは、処理されて最終的な宛先 (SQL Server または Exchange Server) に配信されるように、システムに自動的にインポートされることはありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-170">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="1c83f-171">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-171">**Workaround:**</span></span>

<span data-ttu-id="1c83f-172">システムにデータをインポートするには、管理者は Lync Server リソースキットの ImportStorageServiceData ツールを使用する必要があります。これにより、データがシステムに追加され、処理されて最終的な送信先に配信されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-172">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="1c83f-173">UseNormalizationRules の既定値を False に変更すると、アドレス帳 Web クエリの検索が失敗する</span><span class="sxs-lookup"><span data-stu-id="1c83f-173">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="1c83f-174">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-174">**Issue:**</span></span>

<span data-ttu-id="1c83f-175">UseNormalizationRules の既定値を False に変更すると、アドレス帳の Web クエリ検索は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-175">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail.</span></span> <span data-ttu-id="1c83f-176">既定値が変更されると、Lync クライアントユーザーは Lync アドレス帳 web クエリを使用してユーザーを検索することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-176">After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="1c83f-177">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-177">**Workaround:**</span></span>

<span data-ttu-id="1c83f-178">UseNormalizationRules の既定値が False に設定されている場合、ユーザーは、Active Directory ドメインサービスで定義されている電話番号を、Lync Server 2013 を使用せずに使用することができます。正規化ルールを適用するには、次の手順を実行してこの問題を回避します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-178">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="1c83f-179">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c83f-179">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1c83f-180">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1c83f-180">Do one of the following:</span></span>
    
      - <span data-ttu-id="1c83f-181">展開に Lync Server 2013 サーバーのみが含まれている場合は、グローバルレベルで次のコマンドレットを実行して、UseNormalizationRules および IgnoreGenericRules の値を True に変更します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-181">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="1c83f-182">展開に Lync Server 2013 と Lync Server 2010 または Office Communications Server 2007 R2 の組み合わせが含まれている場合は、次のコマンドレットを実行して、トポロジ内の各 Lync Server 2013 プールに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-182">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="1c83f-183">すべてのプールで CMS レプリケーションが行われるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-183">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="1c83f-184">展開用の電話正規化ルールファイルを変更して、コンテンツをクリアします。</span><span class="sxs-lookup"><span data-stu-id="1c83f-184">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="1c83f-185">ファイルは、各 Lync Server 2013 プールのファイル共有にあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-185">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="1c83f-186">ファイルが存在しない場合は、"会社電話番号の正規化Rules.txt" という名前の空のファイルを作成し \_ \_ \_ \_ ます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-186">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="1c83f-187">すべてのフロントエンドプールが新しいファイルを読み取るまで数分待機します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-187">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="1c83f-188">展開内の各 Lync Server 2013 プールで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-188">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="1c83f-189">Lync 2013 プールごとに1日1回アドレス帳サーバーエラーイベント21054が生成される</span><span class="sxs-lookup"><span data-stu-id="1c83f-189">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="1c83f-190">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-190">**Issue:**</span></span>

<span data-ttu-id="1c83f-191">Lync Server 2013 アドレス帳サーバーでは、毎日のメンテナンスの実行時に、毎日1回エラーイベント21054が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-191">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="1c83f-192">また、更新が成功した場合でも、管理者が **update-csaddressbook** コマンドレットを実行するたびに、このエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-192">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="1c83f-193">ただし、更新が成功した場合、このエラーイベントは無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-193">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="1c83f-194">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-194">**Workaround:**</span></span>

<span data-ttu-id="1c83f-195">このエラーイベントが発生した場合は、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-195">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="1c83f-196">コマンドレットで、インデックスが設定されていないオブジェクトまたは破棄されたオブジェクトがないことを報告した場合は、エラーイベント21054を無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-196">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="1c83f-197">また、System Center Operations Manager では、キー正常性インジケーター (KHI) "アドレス帳ユーザーが正しくインデックス処理されています" がオフになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-197">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="1c83f-198">エッジプールで IPv6 が構成されていると、要求が失敗する場合がある</span><span class="sxs-lookup"><span data-stu-id="1c83f-198">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="1c83f-199">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-199">**Issue:**</span></span>

<span data-ttu-id="1c83f-200">エッジプールで IPv6 が構成されている場合、エッジプールへの要求が失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-200">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="1c83f-201">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-201">**Workaround:**</span></span>

<span data-ttu-id="1c83f-202">この問題を回避するには、エッジプールを IPv6 で構成しないようにします。</span><span class="sxs-lookup"><span data-stu-id="1c83f-202">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="1c83f-203">プールのフェールバック時に Invoke-cspoolfailback コマンドレットが失敗する場合がある</span><span class="sxs-lookup"><span data-stu-id="1c83f-203">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="1c83f-204">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-204">**Issue:**</span></span>

<span data-ttu-id="1c83f-205">プールのフェールバックを試行すると、 **invoke-cspoolfailback** コマンドレットがエラーで失敗することがあります。 "繰り返し試行が行われた後、ハイドロプロセスを完了できませんでした。"</span><span class="sxs-lookup"><span data-stu-id="1c83f-205">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="1c83f-206">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-206">**Workaround:**</span></span>

<span data-ttu-id="1c83f-207">この問題を回避するには、もう一度コマンドレットを実行して、コマンドレットが正常に終了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-207">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds.</span></span> <span data-ttu-id="1c83f-208">フェールバックプロセスが完了するまでに数分かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1c83f-208">Note that the failback process can take several minutes to complete.</span></span> <span data-ttu-id="1c83f-209">プールが2万ユーザーの場合、最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-209">It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="1c83f-210">既に確立されているプール (ハイブリッド、Skype for Business Online) にフロントエンドサーバーを追加するとデータが失われることがある</span><span class="sxs-lookup"><span data-stu-id="1c83f-210">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="1c83f-211">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-211">**Issue:**</span></span>

<span data-ttu-id="1c83f-212">プールに複数のフロントエンドサーバーがある環境でこの問題が発生する場合があります。または、フロントエンドサーバーの1つを再起動するか、プールの一部ではない新しいフロントエンドサーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-212">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="1c83f-213">データがアーカイブされているユーザーは、プールに対して安定したデータアーカイブの配布が確立されるまで、データの損失が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-213">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool.</span></span> <span data-ttu-id="1c83f-214">このようなデータ損失が発生する可能性がある期間は、人間会話の場合は15分、電話会議の場合は30分に制限されています。</span><span class="sxs-lookup"><span data-stu-id="1c83f-214">This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="1c83f-215">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-215">**Workaround:**</span></span>

<span data-ttu-id="1c83f-216">管理を実行するときは、プール内のフロントエンドサーバーを1つずつ開始するのではなく、プールを別のプールにフェールオーバーして、サーバー上でメンテナンスタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-216">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="1c83f-217">メンテナンスタスクを実行する前にサービスを利用できないようにし、メンテナンスが完了したら可用性を復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-217">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="1c83f-218">Get-CsClientAccessLicense コマンドレットを使用して、管理者がライセンス数を取得できない</span><span class="sxs-lookup"><span data-stu-id="1c83f-218">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="1c83f-219">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-219">**Issue:**</span></span>

<span data-ttu-id="1c83f-220">管理者は、 **Get-help Clientaccesslicense** コマンドレットを使用して、クライアントライセンスの正確な使用状況を取得できません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-220">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="1c83f-221">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-221">**Workaround:**</span></span>

<span data-ttu-id="1c83f-222">サーバーライセンスの種類を確認するには、 **-CsService** コマンドレットを実行して、すべてのデータベースの完全修飾ドメイン名 (FDQNs) を取得します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-222">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="1c83f-223">フロントエンドサーバーの FQDN がバックエンドデータベースの FQDN と同じである場合、ライセンスは Standard edition ライセンスです。</span><span class="sxs-lookup"><span data-stu-id="1c83f-223">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="1c83f-224">それ以外の場合、ライセンスは Enterprise edition ライセンスです。</span><span class="sxs-lookup"><span data-stu-id="1c83f-224">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="1c83f-225">クライアントライセンスの数が正確に報告されない</span><span class="sxs-lookup"><span data-stu-id="1c83f-225">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="1c83f-226">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-226">**Issue:**</span></span>

<span data-ttu-id="1c83f-227">クライアントライセンスの数を決定するときには、次のような状況が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-227">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="1c83f-228">**モバイルユーザーのライセンス数が正しくない**</span><span class="sxs-lookup"><span data-stu-id="1c83f-228">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="1c83f-229">ライセンス数は、デバイスベースのユーザーの一意の IP アドレスの数に基づいています。</span><span class="sxs-lookup"><span data-stu-id="1c83f-229">The license count is based on the number of unique IP addresses for device-based users.</span></span> <span data-ttu-id="1c83f-230">ライセンス数は、次の方法で制限されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-230">The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="1c83f-231">ユーザーの IP アドレスが Lync セッション中に変更されると、ライセンスは過剰にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-231">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="1c83f-232">これは、ユーザーがデスクトップクライアントを使用して複数の場所から Lync Server に接続している場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-232">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="1c83f-233">ユーザーがモバイルクライアントを使用して接続する場合は、デバイスの IP アドレスを特定できないため、ライセンスが過小にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-233">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="1c83f-234">**公衆交換電話網 (PSTN) から Lync クライアントへの通話、Lync クライアントから PSTN 回線への通話、および PSTN 回線に転送された Lync 通話でライセンスが2回カウントされる**</span><span class="sxs-lookup"><span data-stu-id="1c83f-234">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="1c83f-235">次のシナリオでは、電話番号と Lync ユーザーの両方がカウントされ、使用されているライセンスの数が判別されるため、2つの追加ライセンスは1つではなく、カウントされます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-235">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used.</span></span> <span data-ttu-id="1c83f-236">正確なライセンスデータを取得するには、電話番号によって生成されたライセンスを手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-236">To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="1c83f-237">Lync への PSTN 電話通話</span><span class="sxs-lookup"><span data-stu-id="1c83f-237">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="1c83f-238">PSTN 回線への Lync 通話</span><span class="sxs-lookup"><span data-stu-id="1c83f-238">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="1c83f-239">Lync への PSTN 通話。 Lync は、通話を PSTN 回線に転送します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-239">A PSTN call to Lync, and then Lync forwards the call to a PSTN line.</span></span> <span data-ttu-id="1c83f-240">PSTN 回線の1つをカウントします。</span><span class="sxs-lookup"><span data-stu-id="1c83f-240">One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="1c83f-241">**ログオンしている Lync 電話のライセンスがカウントされない**</span><span class="sxs-lookup"><span data-stu-id="1c83f-241">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="1c83f-242">ユーザーが Lync 認定電話を使用している場合、電話がログインしていて、接続を維持すると、電話がログインした後にライセンスのクエリが発生した場合、その電話はライセンスを使用したものとしてカウントされません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-242">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="1c83f-243">**電話会議に参加している PSTN 電話に対してカウントされたライセンス**</span><span class="sxs-lookup"><span data-stu-id="1c83f-243">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="1c83f-244">ユーザーが PSTN 電話機を使用して電話会議に参加すると、電話会議への参加のためのライセンスが不正確にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-244">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference.</span></span> <span data-ttu-id="1c83f-245">ただし、PSTN 電話で会議に参加するためにライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-245">However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="1c83f-246">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-246">**Workaround:**</span></span>

1.  <span data-ttu-id="1c83f-247">**モバイルユーザーのライセンス数が正しくない**</span><span class="sxs-lookup"><span data-stu-id="1c83f-247">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="1c83f-248">同じデバイスに属する IP アドレスを手動で特定し、そのうちの1つをライセンス数で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-248">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="1c83f-249">Lync クライアントを使用して接続するモバイルデバイスでこの問題を回避する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-249">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="1c83f-250">**Lync クライアントへの PSTN 通話、Lync クライアントから PSTN 回線への通話、および PSTN 回線に転送された Lync 通話でライセンスが2回カウントされる**</span><span class="sxs-lookup"><span data-stu-id="1c83f-250">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="1c83f-251">PSTN 電話番号を手動で特定し、その番号に対して生成されたライセンス数を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-251">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="1c83f-252">**ログインしている Lync 電話のライセンスがカウントされない**</span><span class="sxs-lookup"><span data-stu-id="1c83f-252">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="1c83f-253">ユーザーがログオフするように Lync phone を構成し、定期的に (3 か月ごとなど) ログオンし直すことができます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-253">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="1c83f-254">**電話会議に参加している PSTN 電話に対してカウントされたライセンス**</span><span class="sxs-lookup"><span data-stu-id="1c83f-254">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="1c83f-255">電話会議への参加に使用される PSTN 電話番号を手動で特定し、その電話番号によって生成されたライセンスを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-255">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="1c83f-256">Lync Server コントロールパネルは、Silverlight 5 へのアップグレード後の VMware 環境での動作を停止します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-256">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="1c83f-257">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-257">**Issue:**</span></span>

<span data-ttu-id="1c83f-258">VMware 環境で Lync Server コントロールパネルを使用すると、Microsoft Silverlight をバージョン5にアップグレードした後、Lync Server コントロールパネルが機能しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-258">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="1c83f-259">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-259">**Workaround:**</span></span>

<span data-ttu-id="1c83f-260">この問題を回避するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1c83f-260">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="1c83f-261">Silverlight 5 をアンインストールし、から Silverlight 4 をインストール [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156) します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-261">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="1c83f-262">VMware 仮想コンピューターではないコンピューターから Lync Server コントロールパネルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="1c83f-262">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="1c83f-263">そのためには、lync Server 管理ツールがコンピューターにインストールされている場合は、サーバーの Windows **スタート** メニューから Lync Server コントロールパネルを起動できます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-263">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="1c83f-264">Web ブラウザーを使用して Lync Server コントロールパネルにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-264">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="1c83f-265">URL は https:///cscp. に似ています。 \<frontend\_pool\_fqdn\></span><span class="sxs-lookup"><span data-stu-id="1c83f-265">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="1c83f-266">Active Directory でユーザーの識別名が変更されても、アドレス帳サービスのユーザー情報が更新されない</span><span class="sxs-lookup"><span data-stu-id="1c83f-266">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="1c83f-267">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-267">**Issue:**</span></span>

<span data-ttu-id="1c83f-268">Active Directory ドメインサービスでユーザーの識別名 (DN とも言う) が変更された場合、アドレス帳サービス (ABS) 内の追加の変更は更新されません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-268">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="1c83f-269">これは、ユーザーのサインインまたはプレゼンスには影響を与えませんが、検索によって古い SIP アドレスが返されるため、SIP アドレスも変更された場合にユーザーの通信ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-269">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="1c83f-270">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-270">**Workaround:**</span></span>

<span data-ttu-id="1c83f-271">この問題を回避するには、ユーザーの DN を変更しないようにします。</span><span class="sxs-lookup"><span data-stu-id="1c83f-271">To work around this issue, do not change a user’s DN.</span></span> <span data-ttu-id="1c83f-272">ユーザーの DN を以前の値に戻すと、アドレス帳サービスに更新が反映されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-272">If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="1c83f-273">インストール</span><span class="sxs-lookup"><span data-stu-id="1c83f-273">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="1c83f-274">非 ASCII 文字を使用すると、Lync server の起動が失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-274">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="1c83f-275">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-275">**Issue:**</span></span>

<span data-ttu-id="1c83f-276">宛先フォルダーの名前に ASCII 以外の文字 (UNICODE、2バイト文字セット (DBCS)、UTF-8、UTF-16 を含む) が含まれている場合、セットアップは失敗します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-276">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="1c83f-277">さらに、セットアップは成功する可能性がありますが、次のいずれかに ASCII 以外の文字が含まれていると、サーバーは起動しません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-277">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="1c83f-278">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="1c83f-278">Computer name</span></span>

  - <span data-ttu-id="1c83f-279">ドメイン名</span><span class="sxs-lookup"><span data-stu-id="1c83f-279">Domain name</span></span>

  - <span data-ttu-id="1c83f-280">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="1c83f-280">User name</span></span>

  - <span data-ttu-id="1c83f-281">ユーザー SIP URI</span><span class="sxs-lookup"><span data-stu-id="1c83f-281">User SIP URI</span></span>

  - <span data-ttu-id="1c83f-282">サービスアカウント名</span><span class="sxs-lookup"><span data-stu-id="1c83f-282">Service account name</span></span>

<span data-ttu-id="1c83f-283">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-283">**Workaround:**</span></span>

<span data-ttu-id="1c83f-284">移動先のフォルダー名、コンピューター名、ドメイン名、ユーザー名、ユーザーの SIP URI、およびサービスアカウント名には ASCII 文字のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-284">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="1c83f-285">"ヒープの破損" という修正プログラムは、Lync Server 2013 をインストールする前に、モジュールが InsertEntityBody メソッドを IIS 7.5 で呼び出したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-285">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="1c83f-286">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-286">**Issue:**</span></span>

<span data-ttu-id="1c83f-287">「モジュールが IIS 7.5 で InsertEntityBody メソッドを呼び出すときに発生するヒープの破損」 () については、「 [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) Microsoft サポート技術情報の記事 264886 ()」を参照し [https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603) てください。 Lync Server 2013 をインストールする前に、をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-287">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="1c83f-288">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-288">**Workaround:**</span></span>

<span data-ttu-id="1c83f-289">「Microsoft ダウンロードセンター」から修正プログラムをダウンロードしてインストールし [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) ます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-289">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="1c83f-290">Lync Server 2013 のインストールが ITA Windows Server 2012 OS RTM バージョンに失敗する</span><span class="sxs-lookup"><span data-stu-id="1c83f-290">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="1c83f-291">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-291">**Issue:**</span></span>

<span data-ttu-id="1c83f-292">Windows Fabric のインストールに失敗したため、ITA Windows Server 2012 で Lync Server 2013 のインストールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-292">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="1c83f-293">Fabric トレースは、時間形式 HH: MM: SS で作成されるため、Windows Fabric のインストールに失敗します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-293">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS.</span></span> <span data-ttu-id="1c83f-294">ただし、ITA Windows Server では、時間の形式は HH です。MM.SS。</span><span class="sxs-lookup"><span data-stu-id="1c83f-294">However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="1c83f-295">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-295">**Workaround:**</span></span>

<span data-ttu-id="1c83f-296">この問題を回避するには、Lync Server 2013 をインストールする前に、システムレジストリを更新します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-296">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="1c83f-297">更新する必要のあるレジストリキーは次のとおりです。 HKEY \_ ユーザー \\ 。既定 \\ のコントロールパネル \\ インターナショナル \\ の形式。</span><span class="sxs-lookup"><span data-stu-id="1c83f-297">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="1c83f-298">Windows PowerShell コマンドラインインターフェイスを使用して、次に示すように、[形式] の値を HH: mm: ss に変更します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-298">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="1c83f-299">Windows PowerShell を起動し、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-299">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="1c83f-300">現在の値を表示するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-300">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="1c83f-301">インストールの完了後に復元できるように、このプロパティの現在の値をメモしておいてください。</span><span class="sxs-lookup"><span data-stu-id="1c83f-301">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="1c83f-302">新しい値を設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-302">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="1c83f-303">Lync Server 2013 が正常にインストールされた後、次のコマンドレットを実行して、この形式の元の値を復元します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-303">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="1c83f-304">Set-ItemProperty $a、手順3でメモした <値の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-304">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="1c83f-305">上記の> "</span><span class="sxs-lookup"><span data-stu-id="1c83f-305">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="1c83f-306">身体</span><span class="sxs-lookup"><span data-stu-id="1c83f-306">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="1c83f-307">サーバーフェールオーバープロセス中のモバイルクライアントの問題</span><span class="sxs-lookup"><span data-stu-id="1c83f-307">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="1c83f-308">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-308">**Issue:**</span></span>

<span data-ttu-id="1c83f-309">Lync Server に障害が発生し、フェールオーバープロセスが開始されると、次の問題がモバイルクライアントユーザーに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-309">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="1c83f-310">フェールオーバーの開始から最大10分間、Lync 通話または着信通知がありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-310">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="1c83f-311">着信チャット要求を受け入れることができない</span><span class="sxs-lookup"><span data-stu-id="1c83f-311">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="1c83f-312">障害が発生したサーバーがユーザーのホームサーバーの場合、会議に参加できない</span><span class="sxs-lookup"><span data-stu-id="1c83f-312">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="1c83f-313">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-313">**Workaround:**</span></span>

<span data-ttu-id="1c83f-314">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-314">There is no workaround for this issue.</span></span> <span data-ttu-id="1c83f-315">フェールオーバープロセスが完了すると、通常の機能が復元されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-315">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="1c83f-316">モバイルユーザーが別の Lync エンドポイントからの着信呼び出しを拒否した場合、その通話は Lync Mobile クライアントに不在時の変換として表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-316">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="1c83f-317">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-317">**Issue:**</span></span>

<span data-ttu-id="1c83f-318">モバイルユーザーが着信呼び出しを拒否し、別の Lync エンドポイントから発信された通話は、デバイス呼び出しリストの呼び出しではなく、Lync Mobile クライアントで不在着信として表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-318">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="1c83f-319">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-319">**Workaround:**</span></span>

<span data-ttu-id="1c83f-320">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-320">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="1c83f-321">モバイルクライアントが連絡先を検索するときに、フェデレーションの連絡先の表示名が表示されない場合がある</span><span class="sxs-lookup"><span data-stu-id="1c83f-321">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="1c83f-322">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-322">**Issue:**</span></span>

<span data-ttu-id="1c83f-323">フェデレーション連絡先の表示名は、連絡先リストでフェデレーション連絡先を検索する場合など、一部のシナリオでは表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-323">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="1c83f-324">これは、Lync mobile クライアントからの連絡先に対してアクティブなプレゼンスサブスクリプションが存在しない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-324">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="1c83f-325">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-325">**Workaround:**</span></span>

<span data-ttu-id="1c83f-326">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-326">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="1c83f-327">モバイルクライアントでは、会議への招待である不在着信した会話から招待者とタイムスタンプ情報が欠落しています。</span><span class="sxs-lookup"><span data-stu-id="1c83f-327">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="1c83f-328">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-328">**Issue:**</span></span>

<span data-ttu-id="1c83f-329">モバイルクライアントでは、不在着信した会話が会議への招待である場合、不在着信した会話メッセージに招待者とタイムスタンプ情報が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-329">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="1c83f-330">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-330">**Workaround:**</span></span>

<span data-ttu-id="1c83f-331">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-331">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="1c83f-332">VoIP を使用して通話を行うモバイルクライアントユーザーは、Exchange 2010 またはそれ以前のバージョンでボイスメールが構成されているユーザーにボイスメールを残すことができません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-332">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="1c83f-333">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-333">**Issue:**</span></span>

<span data-ttu-id="1c83f-334">モバイルクライアントユーザーが VoIP を使用して通話を発信している場合、ユーザーは、Microsoft Exchange Server 2007 または Microsoft Exchange Server 2010 でボイスメールを使用するように構成されたユーザーにボイスメールメッセージを残すことはできません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-334">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="1c83f-335">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-335">**Workaround:**</span></span>

<span data-ttu-id="1c83f-336">この問題を回避するには、Exchange 2010 SP1 以降のバージョンの Microsoft Exchange Server を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-336">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="1c83f-337">モバイルクライアントでクライアントバージョン構成に URL を指定して Block を使用すると、正しくないエラーメッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-337">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="1c83f-338">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-338">**Issue:**</span></span>

<span data-ttu-id="1c83f-339">モバイルクライアントでクライアントバージョン構成に **URL を** 指定したブロックを使用する場合、クライアントバージョンがサポートされていないと、正しくないエラーメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-339">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="1c83f-340">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-340">**Workaround:**</span></span>

<span data-ttu-id="1c83f-341">この問題を回避するには、 **URL を使用して block**ではなく**ブロック**を使用するようにクライアントバージョン構成を構成します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-341">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="1c83f-342">会議</span><span class="sxs-lookup"><span data-stu-id="1c83f-342">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="1c83f-343">Lync Server 2013 のフロントエンドサーバー上で実行されているウイルス対策ソフトウェアは、アプリケーションドメインのリサイクルを発生させることがあります。これにより、Lync Web App 2013、Lync Mobile 2010、Lync Mobile 2013 クライアントのサービスが一時的に中断されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-343">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="1c83f-344">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-344">**Issue:**</span></span>

<span data-ttu-id="1c83f-345">ウイルス対策ソフトウェアは、アプリケーションドメインの再起動をトリガーすることができます。これにより、Lync Mobility Service 2013 および統合コミュニケーション (UC) Web API クライアントアプリケーション (Lync Web App 2013、Lync Mobile 2010、および Lync Mobile 2013) の状態が失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-345">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="1c83f-346">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-346">**Workaround:**</span></span>

<span data-ttu-id="1c83f-347">この問題を回避するには、Web コンポーネントと .NET framework を含むフォルダーをウイルス対策スキャン対象から除外します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-347">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="1c83f-348">詳細については、「Microsoft サポート技術情報の記事312592、「PRB: ASP.NET で、アプリケーションが再起動しています」というエラーを参照してください [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592) 。</span><span class="sxs-lookup"><span data-stu-id="1c83f-348">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="1c83f-349">次のフォルダーを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-349">The following folders should be excluded:</span></span>

  - <span data-ttu-id="1c83f-350">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web コンポーネント \\ mcx \\ Ext</span><span class="sxs-lookup"><span data-stu-id="1c83f-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="1c83f-351">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web コンポーネント \\ mcx \\ Int</span><span class="sxs-lookup"><span data-stu-id="1c83f-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="1c83f-352">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web コンポーネント \\ ucwa \\ Int</span><span class="sxs-lookup"><span data-stu-id="1c83f-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="1c83f-353">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web コンポーネント \\ ucwa \\ Ext</span><span class="sxs-lookup"><span data-stu-id="1c83f-353">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="1c83f-354">% Windir% \\ Microsoft.NET \\ Framework64 \\ v v4.0.30319 \\ Config</span><span class="sxs-lookup"><span data-stu-id="1c83f-354">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="1c83f-355">会議に参加するには、Windows Internet Explorer で ActiveX コントロールまたはネイティブ XMLHTTP サポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-355">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="1c83f-356">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-356">**Issue:**</span></span>

<span data-ttu-id="1c83f-357">ユーザーが Windows Internet Explorer のインターネットブラウザー設定で ActiveX コントロールとネイティブ XMLHTTP サポートの両方を無効にしている場合、Internet Explorer が既定のブラウザーとして選択されていると、ユーザーは会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-357">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="1c83f-358">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-358">**Workaround:**</span></span>

<span data-ttu-id="1c83f-359">Internet Explorer で、ActiveX コントロールまたは "ネイティブ XMLHTTP サポート" を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1c83f-359">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="1c83f-360">Lync Server Web 会議サービスが重要なモードから回復できない</span><span class="sxs-lookup"><span data-stu-id="1c83f-360">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="1c83f-361">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-361">**Issue:**</span></span>

<span data-ttu-id="1c83f-362">重要モードでアーカイブが有効になっている場合、システム障害が発生すると、重要モードが開始され、会議は参加者に対して機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-362">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants.</span></span> <span data-ttu-id="1c83f-363">管理者がシステム障害 (データベース問題の修正など) を修正した後、データ会議サービスは自動的には回復しないため、管理者は会議サービスを再開するために手動で再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-363">After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="1c83f-364">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-364">**Workaround:**</span></span>

<span data-ttu-id="1c83f-365">システム障害が修正された後、管理者は、会議サービスを手動で再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-365">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="1c83f-366">Web 会議サービスが外部の Office Web App サーバーの HTTP プロキシを無視する</span><span class="sxs-lookup"><span data-stu-id="1c83f-366">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="1c83f-367">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-367">**Issue:**</span></span>

<span data-ttu-id="1c83f-368">Web 会議サービスの外部にある Office Web Apps サーバーを展開している (つまり、内部の企業ネットワークにないサーバー) インターネット、境界ネットワーク、および Web 会議サービスに接続するために HTTP プロキシが必要な場合、Office Web Apps サーバーの検出は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-368">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="1c83f-369">Web 会議サービスは、「Office Web Apps Server セットアップのトポロジビルダー」で定義されているように、HTTP プロキシ設定を無視します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-369">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="1c83f-370">その結果、Lync クライアントは、会議の他の参加者と Microsoft PowerPoint 2010 の共有を行うことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-370">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="1c83f-371">内部ネットワークで Lync Server をオンプレミスでインストールし、オンプレミスの Office Web Apps サーバーを構成する場合、プロキシ構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-371">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="1c83f-372">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-372">**Workaround:**</span></span>

<span data-ttu-id="1c83f-373">唯一の回避策は、外部の Office Web Apps サーバーとの通信に HTTP プロキシを使用する必要がある展開構成を行わないことです。</span><span class="sxs-lookup"><span data-stu-id="1c83f-373">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="1c83f-374">電話会議プロバイダーの会議へのビデオの追加はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="1c83f-374">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="1c83f-375">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-375">**Issue:**</span></span>

<span data-ttu-id="1c83f-376">ユーザーが音声会議プロバイダーの電話会議に参加している場合、ビデオの追加はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-376">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="1c83f-377">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-377">**Workaround:**</span></span>

<span data-ttu-id="1c83f-378">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-378">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="1c83f-379">IPv6 が有効になっているトポロジ lync web App Silverlight プラグイン自動更新を強制して、画面共有機能が Lync Web App から機能できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1c83f-379">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="1c83f-380">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-380">**Issue:**</span></span>

<span data-ttu-id="1c83f-381">IPv6 が有効な状態でトポロジを構成すると、以前のバージョンの画面共有プラグインが既にインストールされている場合、ユーザーは Lync Web App クライアントから画面を共有できません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-381">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="1c83f-382">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-382">**Workaround:**</span></span>

<span data-ttu-id="1c83f-383">Lync Web App を使用して会議に参加するときに、最新バージョンの画面共有プラグインを強制的に更新するには、次の両方のファイルで **Minsupportedbuildversion** の値を "4.0.7457.0" から "4.0.7577.380" に変更します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-383">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="1c83f-384">% ProgramFiles% \\ Microsoft Lync Server 15 \\ Web コンポーネント \\ が \\ Int \\ クライアント \\ プラグインに到達 \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="1c83f-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="1c83f-385">% ProgramFiles% \\ Microsoft Lync Server 15 \\ Web コンポーネント \\ は \\ Ext \\ クライアント \\ プラグインに到達 \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="1c83f-385">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="1c83f-386">用に構成します</span><span class="sxs-lookup"><span data-stu-id="1c83f-386">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="1c83f-387">場合によっては、IPv4 と IPv6 デュアルスタックを使用するように構成されたコンピューター上で実行されている Lync クライアントが、E911、メディアバイパス、通話受付管理、場所ベースのルーティングなどのコンピューターの IP サブネットに依存する機能をサポートしていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-387">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="1c83f-388">このセクションの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-388">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="1c83f-389">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-389">**Issue:**</span></span>

<span data-ttu-id="1c83f-390">Lync クライアントが、IPv4 と IPv6 のデュアルスタックが有効になっていて、プロキシサーバーの DNS 解決に基づいてコンピューター上で実行されている場合、クライアントはコンピューターの IPv6 アドレスを使用してサインインすることができます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-390">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="1c83f-391">その後、Lync クライアントは IPv6 に対してサポートされている機能のみをサポートします。これにより、E911、メディアバイパス、通話受付管理、および場所ベースのルーティングが除外されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-391">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="1c83f-392">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-392">**Workaround:**</span></span>

<span data-ttu-id="1c83f-393">この問題を回避するには、クライアントコンピューター上で IPv6 サポートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1c83f-393">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="1c83f-394">エンタープライズ Voip がユーザーに対して構成されていない場合、ユーザーは、電話会議からダイヤルアウトするために E164 形式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-394">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="1c83f-395">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-395">**Issue:**</span></span>

<span data-ttu-id="1c83f-396">エンタープライズ Voip がユーザーに対して構成されていない場合、そのユーザーは、E164 形式を使用して会議からのダイヤルアウトを成功させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-396">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="1c83f-397">E164 形式が使用されていない場合、ユーザーは会議からダイヤルアウトできません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-397">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="1c83f-398">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-398">**Workaround:**</span></span>

<span data-ttu-id="1c83f-399">この問題を回避するには、エンタープライズ Voip が有効になっていないユーザーは、E164 形式の番号を使用して電話会議からダイヤルアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-399">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="1c83f-400">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="1c83f-400">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="1c83f-401">統合連絡先ストアがユーザーに対して有効になっているときに、ユーザーが "招待と通信をすべてブロックする" を選択している場合、プレゼンス状態が拒否されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-401">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="1c83f-402">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-402">**Issue:**</span></span>

<span data-ttu-id="1c83f-403">統合連絡先ストアがユーザーに対して有効になっているときに、ユーザーが "招待と通信をすべてブロックする" を選択した場合、プレゼンス状態が拒否されないはずです。</span><span class="sxs-lookup"><span data-stu-id="1c83f-403">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="1c83f-404">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-404">**Workaround:**</span></span>

<span data-ttu-id="1c83f-405">この問題を回避するには、ユーザーの統合連絡先ストアを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-405">To work around this issue, you can turn off the unified contact store for the user.</span></span> <span data-ttu-id="1c83f-406">これを行うには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-406">To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="1c83f-407">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-407">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="1c83f-408">Office Communications Server 2007 R2 オンプレミスのユーザーが、ハイブリッド展開で Skype for Business Online ユーザーのプレゼンス状態を表示できない-ハイブリッド</span><span class="sxs-lookup"><span data-stu-id="1c83f-408">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="1c83f-409">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-409">**Issue:**</span></span>

<span data-ttu-id="1c83f-410">この問題は、Lync Server 2013 ディレクターを使用している場合に、ハイブリッド展開で発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-410">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="1c83f-411">Skype for Business Online に所属するユーザーのプレゼンス状態は、オンプレミスユーザーのプレゼンス不明として表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-411">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="1c83f-412">また、Skype for Business Online に所属しているユーザーは、Office Communications Server R2 オンプレミスユーザーのプレゼンス状態を表示できません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-412">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="1c83f-413">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-413">**Workaround:**</span></span>

<span data-ttu-id="1c83f-414">この問題を部分的に回避するには、Skype for Business Online ユーザーのホームサーバー (msrtcsip) を、Lync Server 2013 ディレクターではなく、Lync Server 2013 社内プールを指すように変更します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-414">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="1c83f-415">この設定は、オンプレミスのフロントエンドサーバーで変更できます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-415">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="1c83f-416">この回避策では、Office Communications Server 2007 R2 に所属するユーザーのプレゼンス状態が Skype for Business Online ユーザーに正しく表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-416">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="1c83f-417">応答グループアプリケーション、コールパークアプリケーション、グループ通話ピックアップ</span><span class="sxs-lookup"><span data-stu-id="1c83f-417">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="1c83f-418">発信者は、取得側で通話を発信している間、保留音の1秒間を聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-418">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="1c83f-419">このセクションの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-419">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="1c83f-420">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-420">**Issue:**</span></span>

<span data-ttu-id="1c83f-421">グループ通話ピックアップを使用して通話を取得した場合、発信者は取得側で通話を確立している間、保留音の1秒間を聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-421">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="1c83f-422">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-422">**Workaround:**</span></span>

<span data-ttu-id="1c83f-423">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-423">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="1c83f-424">応答グループエージェントは、Lync Server 2010 エージェントコンソールを使用して Lync server 2010 の正式なエージェントグループのみにサインインしてサインアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-424">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="1c83f-425">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-425">**Issue:**</span></span>

<span data-ttu-id="1c83f-426">Lync Server 2013 応答グループエージェントは、lync server 2010 エージェントコンソールを使用して、lync server 2010 の正式なエージェントグループのみにサインインしてサインアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-426">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="1c83f-427">Lync Server 2010 エージェントコンソールでは、ユーザーは自分が属している Lync Server 2010 応答グループのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-427">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="1c83f-428">自分が属している Lync Server 2013 応答グループを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-428">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="1c83f-429">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-429">**Workaround:**</span></span>

<span data-ttu-id="1c83f-430">応答グループエージェントが Lync Server 2013 ユーザーであり、Lync Server 2013 の正式なエージェントグループの一部である場合、ユーザーは、ブラウザーの web リンクを介して直接 Lync Server 2013 エージェントコンソールにアクセスし、Lync Server の2013エージェントグループにサインインしてサインアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-430">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="1c83f-431">Lync Server 2010 応答グループエージェントは、Lync Server 2013 応答グループの代理として通話を行うことができません</span><span class="sxs-lookup"><span data-stu-id="1c83f-431">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="1c83f-432">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-432">**Issue:**</span></span>

<span data-ttu-id="1c83f-433">Lync Server 2010 Lync Server 2013 応答グループのエージェントであるユーザーは、応答グループの代わりに通話を行うことができません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-433">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="1c83f-434">Lync Server 2013 応答グループは、通話を行うために Lync クライアントで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-434">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="1c83f-435">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-435">**Workaround:**</span></span>

<span data-ttu-id="1c83f-436">この問題を回避するには、Lync Server 2010 ユーザーを Lync Server 2013 に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-436">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="1c83f-437">Lync server 2013 に移行された後で Lync Server 2010 から応答グループを削除すると、応答グループは着信呼び出しを受け付けなくなります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-437">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="1c83f-438">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-438">**Issue:**</span></span>

<span data-ttu-id="1c83f-439">Lync server 2010 から Lync Server 2013 に移行された応答グループが lync server の [コントロールパネル] または [Lync Server 管理シェル] から2010削除された場合、Lync Server 2013 の応答グループは着信呼び出しの受信を停止します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-439">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="1c83f-440">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-440">**Workaround:**</span></span>

<span data-ttu-id="1c83f-441">この問題を回避するには、lync server 2010 から Lync Server 2013 に移行された Lync Server 2010 から応答グループを削除しないようにします。</span><span class="sxs-lookup"><span data-stu-id="1c83f-441">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="1c83f-442">応答グループが既に削除されている場合は、Lync Server 2013 に再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-442">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="1c83f-443">新しい管理ワークフローを作成時に非アクティブに設定すると、ワークフローの展開に失敗します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-443">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="1c83f-444">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-444">**Issue:**</span></span>

<span data-ttu-id="1c83f-445">新しい管理ワークフローを作成時に非アクティブに設定すると、ワークフローの展開は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-445">When a new managed workflow is set to inactive when created, deployment of the workflow will fail.</span></span> <span data-ttu-id="1c83f-446">この問題は、作成時にワークフローが非アクティブに設定されている場合に発生しますが、が展開された後に非アクティブに設定するように編集されたワークフローには影響しません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-446">This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="1c83f-447">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-447">**Workaround:**</span></span>

<span data-ttu-id="1c83f-448">ワークフローを作成して展開するときは、ワークフローをアクティブに設定して展開します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-448">When creating and deploying a workflow, set the workflow as active and then deploy it.</span></span> <span data-ttu-id="1c83f-449">ワークフローが正常に展開された後、ワークフローを編集して非アクティブに設定できます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-449">After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="1c83f-450">応答グループがバックアッププールにインポートされている場合、所有者プールから応答グループを削除すると、フェールオーバー中のすべての着信呼び出しがバックアッププールの応答グループによって受け付けられなくなります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-450">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="1c83f-451">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-451">**Issue:**</span></span>

<span data-ttu-id="1c83f-452">プライマリプールに所有されている応答グループが所有者を上書きせずにバックアッププールにインポートされ、所有者プールから応答グループが削除された場合、バックアッププールの応答グループは、フェールオーバー中に着信呼び出しを受け付けません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-452">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="1c83f-453">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-453">**Workaround:**</span></span>

<span data-ttu-id="1c83f-454">プライマリプールに応答グループを再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-454">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="1c83f-455">その後、プライマリプールから応答グループの構成をエクスポートして、もう一度バックアッププールにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-455">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="1c83f-456">バックアッププールで応答グループを再作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-456">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="1c83f-457">この場合、バックアッププールは応答グループの所有者プールになります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-457">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="1c83f-458">応答グループの代理として取得要求が行われた場合、コールパークアプリケーションから保留中の通話を取得することはできません</span><span class="sxs-lookup"><span data-stu-id="1c83f-458">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="1c83f-459">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-459">**Issue:**</span></span>

<span data-ttu-id="1c83f-460">次の条件に該当する場合、保留中の通話の取得要求は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-460">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="1c83f-461">エージェントが匿名応答グループに含まれている</span><span class="sxs-lookup"><span data-stu-id="1c83f-461">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="1c83f-462">エージェントは、呼び出しパークアプリケーションからの保留中の呼び出しを匿名応答グループを介して取得しようとします。</span><span class="sxs-lookup"><span data-stu-id="1c83f-462">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="1c83f-463">エージェントは、[代理人として呼び出し] オプションまたは Lync アテンダントクライアントの同じオプションを使用して、オービット番号をダイヤルして通話を取得しようとしています。</span><span class="sxs-lookup"><span data-stu-id="1c83f-463">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="1c83f-464">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-464">**Workaround:**</span></span>

<span data-ttu-id="1c83f-465">この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-465">There are no workarounds for this issue.</span></span> <span data-ttu-id="1c83f-466">保留中の呼び出しは、応答グループの代理としてではなく、取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-466">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="1c83f-467">Lync Server コントロール パネル、トポロジ ビルダー、および計画ツール</span><span class="sxs-lookup"><span data-stu-id="1c83f-467">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="1c83f-468">計画ツールの制限事項</span><span class="sxs-lookup"><span data-stu-id="1c83f-468">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="1c83f-469">このセクションの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-469">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="1c83f-470">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-470">**Issue:**</span></span>

<span data-ttu-id="1c83f-471">展開を計画する場合、計画ツールには次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-471">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="1c83f-472">最大10個の中央サイトがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1c83f-472">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="1c83f-473">各中央サイトには、最大14個のブランチサイトを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-473">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="1c83f-474">各中央サイトには、最大24万ユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-474">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="1c83f-475">また、計画ツールでは、推奨されるトポロジを計算する際に、次の値は含まれません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-475">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="1c83f-476">オンラインに所属しているユーザーの数</span><span class="sxs-lookup"><span data-stu-id="1c83f-476">The number of users that are homed online</span></span>

  - <span data-ttu-id="1c83f-477">XMPP フェデレーションが有効になっているユーザーの割合</span><span class="sxs-lookup"><span data-stu-id="1c83f-477">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="1c83f-478">Lync Web App を使用しているユーザーの割合</span><span class="sxs-lookup"><span data-stu-id="1c83f-478">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="1c83f-479">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-479">**Workaround:**</span></span>

<span data-ttu-id="1c83f-480">これらの問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-480">There is no workaround for these issues.</span></span> <span data-ttu-id="1c83f-481">計画ツールの詳細については、「 [計画ツールを使用して Lync Server 2013 のトポロジを設計](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c83f-481">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="1c83f-482">計画ツールでオプションを更新するときに、エッジネットワークに対して定義済みの IP アドレスが使用されないことがある</span><span class="sxs-lookup"><span data-stu-id="1c83f-482">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="1c83f-483">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-483">**Issue:**</span></span>

<span data-ttu-id="1c83f-484">計画ツールを使用して設計を完了した後、エッジネットワークオプションを変更すると、既存の IP アドレスを更新するのではなく、追加の IP アドレスが設計に追加されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-484">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="1c83f-485">これは、エッジネットワークダイアグラムの詳細を表示しているときに、 **[ここをクリックしてオプションを更新**します] を選択し、[構成オプション] ダイアログボックスの [エッジネットワーク] を選択します。 [ **同じ fqdn および IP アドレスを使用するが、エッジサーバー上のエッジサービスに異なるポートを使用**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-485">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="1c83f-486">変更を適用すると、新しい IP アドレスとエッジサーバーが設計に追加されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-486">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="1c83f-487">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-487">**Workaround:**</span></span>

<span data-ttu-id="1c83f-488">現時点では、この問題を回避する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-488">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="1c83f-489">Lync Server コントロールパネルで、[すべてのユーザーをプールに移動] が期待どおりに機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-489">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="1c83f-490">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-490">**Issue:**</span></span>

<span data-ttu-id="1c83f-491">Lync Server コントロールパネルを使用して、複数のドメインコントローラーや親/子ドメインなど、複雑な Active Directory 環境にあるプールから別のプールにすべてのユーザーを移動する場合、エラーメッセージが返されることがあります。 "指定されたユーザーはレガシユーザーではないため、代わりに Move-CsUser コマンドレットを使用してください。</span><span class="sxs-lookup"><span data-stu-id="1c83f-491">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="1c83f-492">複雑な Active Directory 環境では、レプリケーション時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-492">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="1c83f-493">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-493">**Workaround:**</span></span>

<span data-ttu-id="1c83f-494">この問題を回避するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1c83f-494">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="1c83f-495">Lync Server コントロールパネルのフィルターを使用して、レガシユーザーを検索し、それらのユーザーを選択してから、[ **選択したユーザーをプールに移動] コマンド** を使用して、 **すべてのユーザーをプールに移動**します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-495">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="1c83f-496">Lync server のコマンドレットを使用して、バッチで従来のユーザーを移動するには、Lync Server 管理シェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-496">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="1c83f-497">Microsoft Silverlight ブラウザープラグインがバージョン5に更新された後、Lync Server コントロールパネルが VMware 環境で機能しなくなる</span><span class="sxs-lookup"><span data-stu-id="1c83f-497">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="1c83f-498">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-498">**Issue:**</span></span>

<span data-ttu-id="1c83f-499">VMware 環境で Lync Server コントロールパネルを使用すると、Silverlight をバージョン5にアップグレードした後、Lync Server コントロールパネルが機能しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-499">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="1c83f-500">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-500">**Workaround:**</span></span>

<span data-ttu-id="1c83f-501">この問題を回避するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1c83f-501">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="1c83f-502">Silverlight 5 をアンインストールし、から Silverlight 4 をインストールし [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0) ます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-502">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="1c83f-503">VMware 仮想コンピューターではないコンピューターから Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-503">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="1c83f-504">リモートコンピューターから Lync server コントロールパネルを開くには、コンピューターに Lync Server 管理ツールをインストールしてから、Windows の [ **スタート** ] メニューから Lync Server コントロールパネルを起動します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-504">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="1c83f-505">Web ブラウザーに URL を入力して、Lync Server コントロールパネルを開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-505">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="1c83f-506">URL は https:///cscp. に似ています。 \<frontend\_pool\_fqdn\></span><span class="sxs-lookup"><span data-stu-id="1c83f-506">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="1c83f-507">トポロジビルダーでミラーリングデータベースを削除した後、管理者がアンインストール-csMirrorDB コマンドレットを実行できない</span><span class="sxs-lookup"><span data-stu-id="1c83f-507">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="1c83f-508">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-508">**Issue:**</span></span>

<span data-ttu-id="1c83f-509">管理者がトポロジビルダーでミラーリングデータベースを無効にした後、トポロジビルダーでミラーリングデータベースを削除すると、管理者が **install-csmirrordatabase** コマンドレットを実行して SQL Server からミラーリングを削除するように、メッセージが [タスク] 一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-509">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="1c83f-510">管理者がコマンドレットを実行しようとすると、失敗します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-510">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="1c83f-511">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-511">**Workaround:**</span></span>

<span data-ttu-id="1c83f-512">トポロジビルダーでプールの SQL ミラーリングを削除するには、最初にコマンドレットを使用して、SQL Server でミラーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-512">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="1c83f-513">次に、トポロジ ビルダーを使用して、トポロジからミラーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-513">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="1c83f-514">SQL Server でミラーを削除するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-514">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="1c83f-515">たとえば、ミラーリングを削除してユーザーデータベースのデータベースをドロップするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-515">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="1c83f-516">*Dropexistingdatabases Onmirror*パラメーターを指定すると、影響を受けるデータベースがミラーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-516">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="1c83f-517">次に、トポロジからミラーを削除するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1c83f-517">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="1c83f-518">トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c83f-518">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="1c83f-519">[ **SQL ストアミラーリングの有効化** ] をオフにして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c83f-519">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="1c83f-520">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-520">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="1c83f-521">バックエンドデータベースミラーリング関係を変更するたびに、プール内のすべてのフロントエンドサーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-521">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="1c83f-522">管理者が関連付けられた監視ストアを持つフロントエンドプールを使用して展開を削除しようとすると、トポロジビルダーで検証エラーが返される</span><span class="sxs-lookup"><span data-stu-id="1c83f-522">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="1c83f-523">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-523">**Issue:**</span></span>

<span data-ttu-id="1c83f-524">管理者がトポロジビルダーの [ **展開の削除** ] コマンドを使用して、関連付けられた監視ストアを持つフロントエンドプールを含む展開を削除しようとすると、検証エラーがトポロジビルダーに表示され、操作は続行されません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-524">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="1c83f-525">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-525">**Workaround:**</span></span>

<span data-ttu-id="1c83f-526">この問題を回避するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1c83f-526">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="1c83f-527">展開を削除する前に、ミラーリング監視ストアを削除します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-527">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="1c83f-528">フロントエンドプールのミラーリング監視ストアを追加し、削除します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-528">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="1c83f-529">計画ツールとトポロジビルダーの間で常設チャットサーバーの展開情報が矛盾している</span><span class="sxs-lookup"><span data-stu-id="1c83f-529">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="1c83f-530">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-530">**Issue:**</span></span>

<span data-ttu-id="1c83f-531">Lync Server 2013 の計画ツールが、障害復旧を有効にした常設チャットサーバーの展開のためのサイトトポロジ図を出力すると、サイトトポロジの図には複数の (物理的な) サイトが含まれ、各サイトで常設チャットサーバーが均等に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-531">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="1c83f-532">トポロジビルダーでは、すべての常設チャットサーバーは、1つの (論理的な) サイトに属するものとして表され、同じ常設チャットサーバープールノードの下に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-532">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="1c83f-533">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-533">**Workaround:**</span></span>

<span data-ttu-id="1c83f-534">現時点では、この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-534">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="1c83f-535">常設チャットサーバーの展開の計画ツールの出力を分析し、特定のニーズに合わせて計画を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-535">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="1c83f-536">ローカリゼーション</span><span class="sxs-lookup"><span data-stu-id="1c83f-536">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="1c83f-537">監視</span><span class="sxs-lookup"><span data-stu-id="1c83f-537">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="1c83f-538">日本語版の Lync Server を使用している場合、監視レポートの展開ウィザードで、特定の状況で誤った文字が表示される</span><span class="sxs-lookup"><span data-stu-id="1c83f-538">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="1c83f-539">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-539">**Issue:**</span></span>

<span data-ttu-id="1c83f-540">日本語版の Lync Server 2013 (中国語 (簡体字)、中国語 (繁体字)、日本語、韓国語を使用している場合、システムロケールが東アジア言語に設定されていないオペレーティングシステムで、[監視レポートの展開] ウィザードには、ローカライズされたメッセージではなく、疑問符または他の文字が表示されます</span><span class="sxs-lookup"><span data-stu-id="1c83f-540">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="1c83f-541">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-541">**Workaround:**</span></span>

<span data-ttu-id="1c83f-542">この問題を解決するには、オペレーティングシステムと Lync Server 2013 のロケールを同じ言語に設定して、すべてのメッセージが正しく表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="1c83f-542">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="1c83f-543">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="1c83f-543">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="1c83f-544">場合によっては、トップナビゲーションバーのページ上のトップナビゲーションバーの最初の項目が表示されなくなると、トップナビゲーションバーの最後の項目がクリックされます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-544">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="1c83f-545">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-545">**Issue:**</span></span>

<span data-ttu-id="1c83f-546">次の3つの既知のケースでは、Lync Server コントロールパネルのページにあるトップナビゲーションバーの最後の項目をクリックすると、トップナビゲーションバーの最初の項目が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-546">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="1c83f-547">フランス語版のページ "Féderation et accès externe" では、"Partenaires d'accès XMPP" がクリックされたときに "Stratégie externe fédérés" という項目が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-547">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="1c83f-548">ドイツ語版の "Clients" ページで "クリックすると" がクリックされると、アイテム "Clientversionskonfiguration" が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-548">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="1c83f-549">ロシア語版の "Конфигурациясети" ページで "Маршрутрегиона" をクリックすると、"Глобально" という項目が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-549">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="1c83f-550">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-550">**Workaround:**</span></span>

<span data-ttu-id="1c83f-551">この問題を回避するには、ブラウザーで Lync Server コントロールパネルのページを更新します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-551">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="1c83f-552">トップナビゲーションバーに表示されるすべてのアイテムと共に、ページがブラウザーに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-552">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="1c83f-553">アドレス帳</span><span class="sxs-lookup"><span data-stu-id="1c83f-553">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="1c83f-554">一部の言語で、アドレス帳のインデックス処理が期待どおりに機能しない</span><span class="sxs-lookup"><span data-stu-id="1c83f-554">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="1c83f-555">このセクションの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-555">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="1c83f-556">ユーザーのプロパティにインデックスフィールドが含まれており、そのフィールドにインデックスを作成できない文字のみが含まれている場合、そのユーザーはアドレス帳で実行される検索には表示されません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-556">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="1c83f-557">次の文字とロケールのインデックスを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-557">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="1c83f-558">大文字のキリル文字、ギリシャ文字、およびアルメニア文字</span><span class="sxs-lookup"><span data-stu-id="1c83f-558">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="1c83f-559">大文字のアクセント記号付き文字</span><span class="sxs-lookup"><span data-stu-id="1c83f-559">Upper-case accented characters</span></span>

  - <span data-ttu-id="1c83f-560">タイ語</span><span class="sxs-lookup"><span data-stu-id="1c83f-560">Thai</span></span>

  - <span data-ttu-id="1c83f-561">ラオス語</span><span class="sxs-lookup"><span data-stu-id="1c83f-561">Lao</span></span>

  - <span data-ttu-id="1c83f-562">ミャンマー</span><span class="sxs-lookup"><span data-stu-id="1c83f-562">Myanmar</span></span>

  - <span data-ttu-id="1c83f-563">デバナガリ</span><span class="sxs-lookup"><span data-stu-id="1c83f-563">Devanagari</span></span>

  - <span data-ttu-id="1c83f-564">エチオピア</span><span class="sxs-lookup"><span data-stu-id="1c83f-564">Ethiopic</span></span>

  - <span data-ttu-id="1c83f-565">チベット語</span><span class="sxs-lookup"><span data-stu-id="1c83f-565">Tibetan</span></span>

  - <span data-ttu-id="1c83f-566">ベンガル語</span><span class="sxs-lookup"><span data-stu-id="1c83f-566">Bengali</span></span>

  - <span data-ttu-id="1c83f-567">グジャラート語</span><span class="sxs-lookup"><span data-stu-id="1c83f-567">Gujarati</span></span>

  - <span data-ttu-id="1c83f-568">テルグ語</span><span class="sxs-lookup"><span data-stu-id="1c83f-568">Telugu</span></span>

  - <span data-ttu-id="1c83f-569">他のすべてのインド諸語スクリプト</span><span class="sxs-lookup"><span data-stu-id="1c83f-569">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="1c83f-570">Lync Web App、Web Scheduler、および Web コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1c83f-570">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="1c83f-571">Lync Web Scheduler、ダイヤルイン、参加起動ツール、常設チャットルーム管理、および OCTab の特定の言語の言語フォールバックが期待どおりに機能しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-571">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="1c83f-572">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-572">**Issue:**</span></span>

<span data-ttu-id="1c83f-573">Web ブラウザーでニュートラルロケールを選択する (Internet Explorer の場合) たとえば、 \[ \] 言語、スクリプト、およびロケール ("ノルウェー語、ブークモール (ノルウェー) NB-いいえ" など) を指定するロケールの代わりに、"ノルウェー no" のような仕様のない言語名は、 \[ \] Lync web Scheduler、ダイヤルイン、参加起動ツール、常設チャットルーム管理、および [octab] タブの特定の言語に対して予期しない表示動作を</span><span class="sxs-lookup"><span data-stu-id="1c83f-573">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="1c83f-574">たとえば、次の言語のいずれかが選択されている場合、ユーザーには英語のページが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-574">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="1c83f-575">ノルウェー語</span><span class="sxs-lookup"><span data-stu-id="1c83f-575">Norwegian</span></span>

  - <span data-ttu-id="1c83f-576">ポルトガル語</span><span class="sxs-lookup"><span data-stu-id="1c83f-576">Portuguese</span></span>

  - <span data-ttu-id="1c83f-577">セルビア語</span><span class="sxs-lookup"><span data-stu-id="1c83f-577">Serbian</span></span>

<span data-ttu-id="1c83f-578">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-578">**Workaround:**</span></span>

<span data-ttu-id="1c83f-579">ニュートラルロケールの言語を選択する場合は、ブラウザーの言語設定一覧で、特定のロケール (スクリプトや国コードを含む) が追加言語として追加されていることを必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="1c83f-579">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="1c83f-580">一部の web ブラウザーでは、Lync Web Scheduler、ダイヤルイン、参加起動ツール、常設チャットルーム管理、および OCTab を使用する場合に、アゼルバイジャンおよびウズベク語のサポートが制限されています。</span><span class="sxs-lookup"><span data-stu-id="1c83f-580">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="1c83f-581">このセクションの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-581">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="1c83f-582">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-582">**Issue:**</span></span>

<span data-ttu-id="1c83f-583">Internet Explorer 8 または Internet Explorer 9 を使用していて、ブラウザーの言語をアゼルバイジャン語 (ラテン) またはウズベク語 (ラテン) に設定すると、ダイヤルインページと参加起動ツールページが英語で表示されるか、ブラウザーで優先言語セットとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-583">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="1c83f-584">Firefox または Chrome ブラウザーを使用している場合、ブラウザーの言語をアゼルバイジャン語 (ラテン) またはウズベク語 (ラテン) に設定すると、Lync Web App、Lync Web Scheduler、および RGS OCTab が英語で表示されるか、ブラウザーの優先言語セットとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-584">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="1c83f-585">Safari ブラウザーでは、ウズベク語 (ラテン) ロケールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-585">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="1c83f-586">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-586">**Workaround:**</span></span>

<span data-ttu-id="1c83f-587">これらの問題を回避する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-587">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="1c83f-588">ルーマニア語版の Lync Web App の [会議に参加] リストにドロップダウン矢印が表示されない</span><span class="sxs-lookup"><span data-stu-id="1c83f-588">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="1c83f-589">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-589">**Issue:**</span></span>

<span data-ttu-id="1c83f-590">ルーマニア語版の Lync Web App を使用しているユーザーが次の手順を実行すると、[ **会議に参加** ] ドロップダウンリストにドロップダウン矢印が表示されません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-590">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="1c83f-591">[**全般**] タブの [**このコンピューターにあるメールを記憶**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-591">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="1c83f-592">[ **電話** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="1c83f-592">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="1c83f-593">[ **会議に参加**する] のドロップダウンリストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c83f-593">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="1c83f-594">ユーザーには、既定の **Lync Web App**より多くのオプションがあることを示す矢印は表示されません。これには、[ **オーディオに参加しない** ] (ルーマニア語、"ニュー se asociaža la componenta audio")、および [ **新しい番号**] (ルーマニア語、"Număr nou") が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-594">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="1c83f-595">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-595">**Workaround:**</span></span>

<span data-ttu-id="1c83f-596">このドロップダウンリストの矢印は表示されませんが、ユーザーは既定値をクリックして、リスト内の追加の設定を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-596">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="1c83f-597">トルコ語版の Lync Web Scheduler を使用している場合、[発表者となるユーザー] の [選択したユーザー] オプションを使用すると、会議を保存できません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-597">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="1c83f-598">**問題**</span><span class="sxs-lookup"><span data-stu-id="1c83f-598">**Issue:**</span></span>

<span data-ttu-id="1c83f-599">トルコ語版の Lync Web Scheduler で会議を作成または編集する場合、[発表者となるユーザー] の [選択したユーザー] オプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-599">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported.</span></span> <span data-ttu-id="1c83f-600">このオプションを選択すると、会議を保存できません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-600">When this option is selected, the meeting can't be saved.</span></span> <span data-ttu-id="1c83f-601">代わりに、1人以上のユーザーがプレゼンターを作成できないことを示すエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-601">Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="1c83f-602">**回避策**</span><span class="sxs-lookup"><span data-stu-id="1c83f-602">**Workaround:**</span></span>

<span data-ttu-id="1c83f-603">この問題を回避するには、ユーザーは "会社のユーザーからの人"、または "会社外の人を含むすべての人を含むすべてのユーザー" の既定のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-603">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company."</span></span> <span data-ttu-id="1c83f-604">開催者は後で会議に参加した後で、ユーザーを適切な役割に降格または昇格させることができます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-604">The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="1c83f-605">別の言語を理解しているユーザーは、ブラウザーでの言語の選択を他の43でサポートされている言語のいずれかに変更し、"ユーザーが選択した" オプションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-605">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="1c83f-606">著作権</span><span class="sxs-lookup"><span data-stu-id="1c83f-606">Copyright</span></span>

<span data-ttu-id="1c83f-607">このドキュメントでは、最終的な商用リリースの前に実質的に変更される可能性があるソフトウェア製品の予備リリースがサポートされています。また、Microsoft Corporation の機密情報でもあります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-607">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation.</span></span> <span data-ttu-id="1c83f-608">これは、受信者と Microsoft との間の機密保持契約に基づいて開示されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-608">It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft.</span></span> <span data-ttu-id="1c83f-609">このドキュメントは情報提供のみを目的として提供されており、このドキュメントでは明示的にも黙示的にもいかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-609">This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document.</span></span> <span data-ttu-id="1c83f-610">このドキュメントに記載されている情報 (URL やその他のインターネット web サイトへの参照を含む) は、将来予告なしに変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-610">Information in this document, including URL and other Internet website references, is subject to change without notice.</span></span> <span data-ttu-id="1c83f-611">このドキュメントを使用した場合のリスク全体またはその結果は、ユーザーによって保持されます。</span><span class="sxs-lookup"><span data-stu-id="1c83f-611">The entire risk of the use or the results from the use of this document remains with the user.</span></span> <span data-ttu-id="1c83f-612">別途記載されていない限り、このドキュメントで使用している会社、組織、製品、ドメイン名、電子メールアドレス、ロゴ、人物、場所、およびイベントは架空のものです。</span><span class="sxs-lookup"><span data-stu-id="1c83f-612">Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="1c83f-613">実在する会社、組織、製品、ドメイン名、電子メールアドレス、ロゴ、人物、場所、またはイベントには、意図されていないか、または推論する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-613">No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="1c83f-614">該当するすべての著作権法の順守は、ユーザー側の責任となります。</span><span class="sxs-lookup"><span data-stu-id="1c83f-614">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="1c83f-615">著作権法の範囲に限定されることなく、米国 Microsoft Corporation の書面による明示的な許諾なしに、このドキュメントのいかなる部分も、いかなる形式または手段 (電子的、機械的、コピー複写、記録、またはその他の方法) で、またはいかなる目的でも、複製、保存、検索システム導入、または転送することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-615">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="1c83f-p162">マイクロソフトは、このドキュメントに記載されている内容に関し、特許、特許申請、商標、著作権、またはその他の無体財産権を有する場合があります。別途マイクロソフトのライセンス契約上に明示の規定のない限り、このドキュメントはこれらの特許、商標、著作権、またはその他の無体財産権に関する権利をお客様に許諾するものではありません。</span><span class="sxs-lookup"><span data-stu-id="1c83f-p162">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="1c83f-618">c 2012 Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="1c83f-618">© 2012 Microsoft Corporation.</span></span> <span data-ttu-id="1c83f-619">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="1c83f-619">All rights reserved.</span></span>

<span data-ttu-id="1c83f-620">Microsoft、Windows、Windows Live、Active Directory、Internet Explorer、MSN、Outlook、および SQL Server は、米国 Microsoft Corporation の米国およびその他の国/地域における登録商標または商標です。</span><span class="sxs-lookup"><span data-stu-id="1c83f-620">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="1c83f-621">その他すべての商標は各社が所有しています。</span><span class="sxs-lookup"><span data-stu-id="1c83f-621">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

