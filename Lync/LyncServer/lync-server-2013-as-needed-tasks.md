---
title: 'Lync Server 2013: 必要に応じてタスク'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e96fd6e73e043c5ea7c476f939b3a3e06eadbdfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="16d19-102">Lync Server 2013 での必要なタスク</span><span class="sxs-lookup"><span data-stu-id="16d19-102">As-needed tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16d19-103">_**最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="16d19-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="16d19-104">必要に応じて、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="16d19-104">Perform the following tasks as necessary.</span></span> <span data-ttu-id="16d19-105">通常、標準の手順でもカバーされています。</span><span class="sxs-lookup"><span data-stu-id="16d19-105">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="16d19-106">**完全なセキュリティ監査   **この監査は、メッセージングシステムのアップグレードまたは再設計、または試行された (または成功した) セキュリティ違反に対応して、定期的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="16d19-106">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="16d19-107">この手順では、サーバーやファイアウォールでのポートスキャン、セキュリティ修正プログラムの監査、サードパーティのペネトレーションテストなどを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="16d19-107">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="16d19-108">**証明書に関する情報を期限切れ**   にするには Lync Server 証明書は通常の週間タスクの1つであり、管理者はすべての証明書の有効期限を記録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16d19-108">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="16d19-109">このレコードを使用すると、特定の証明書が期限切れになり、必要に応じて置き換えられるときに、管理者が通知を作成できます。</span><span class="sxs-lookup"><span data-stu-id="16d19-109">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="16d19-110">**パフォーマンスの基準計画**   を更新するアップグレードまたは構成の変更後にパフォーマンスベースラインを更新します。</span><span class="sxs-lookup"><span data-stu-id="16d19-110">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="16d19-111">組織では、ベースラインを使用してパフォーマンスの変化を測定し、システムのパフォーマンスに影響する問題を検出することができます。</span><span class="sxs-lookup"><span data-stu-id="16d19-111">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="16d19-112">**エンタープライズプール**   、標準エディションサーバー、および組織内の他のすべてのサーバーのエンタープライズプールの初期構成を管理するには、個々のサーバーを展開するときに行いました。</span><span class="sxs-lookup"><span data-stu-id="16d19-112">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="16d19-113">Standard Edition server とエンタープライズプールの展開後のサーバーとプールの管理には、次のタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="16d19-113">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="16d19-114">フロントエンドサーバーの管理</span><span class="sxs-lookup"><span data-stu-id="16d19-114">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="16d19-115">Web 会議を管理する</span><span class="sxs-lookup"><span data-stu-id="16d19-115">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="16d19-116">会議を管理する</span><span class="sxs-lookup"><span data-stu-id="16d19-116">Managing Conferencing</span></span>
    
      - <span data-ttu-id="16d19-117">サービスアカウントの資格情報を変更する</span><span class="sxs-lookup"><span data-stu-id="16d19-117">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="16d19-118">データベースの管理</span><span class="sxs-lookup"><span data-stu-id="16d19-118">Managing Databases</span></span>
    
      - <span data-ttu-id="16d19-119">サービスを開始および停止し、サーバーの役割を非アクティブ化する</span><span class="sxs-lookup"><span data-stu-id="16d19-119">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="16d19-120">サーバーとサーバーの役割の削除、プールの削除、サーバーとプールの無効化</span><span class="sxs-lookup"><span data-stu-id="16d19-120">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="16d19-121">**利用状況**   の管理 Lync Server 2013 を構成して、組織に最も適した機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="16d19-121">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="16d19-122">これには、次のポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="16d19-122">This includes the following:</span></span>
    
      - <span data-ttu-id="16d19-123">オンプレミスの Web 会議会議のサポートを管理する</span><span class="sxs-lookup"><span data-stu-id="16d19-123">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="16d19-124">インスタントメッセージを送信するための配布グループの使用を管理する</span><span class="sxs-lookup"><span data-stu-id="16d19-124">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="16d19-125">連絡先、プレゼンス、およびクエリを管理する</span><span class="sxs-lookup"><span data-stu-id="16d19-125">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="16d19-126">クライアントのバージョンのフィルター処理を構成する</span><span class="sxs-lookup"><span data-stu-id="16d19-126">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="16d19-127">インテリジェント IM フィルターの設定</span><span class="sxs-lookup"><span data-stu-id="16d19-127">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="16d19-128">アーカイブ、通話の詳細の記録、会議のコンプライアンスを構成する</span><span class="sxs-lookup"><span data-stu-id="16d19-128">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="16d19-129">**エッジサーバー**   への接続の管理外部接続を提供するために必要なサーバーと設定の進行状況には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="16d19-129">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="16d19-130">内部サーバーとエッジサーバー間の接続の管理</span><span class="sxs-lookup"><span data-stu-id="16d19-130">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="16d19-131">エッジサーバーの内部および外部インターフェイスと証明書の構成</span><span class="sxs-lookup"><span data-stu-id="16d19-131">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="16d19-132">フェデレーションパートナーへのアクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="16d19-132">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="16d19-133">\*\*\*\*   アドレス帳の管理アドレス帳サーバーを管理するには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="16d19-133">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="16d19-134">アドレス帳のサーバー電話の正規化を構成する</span><span class="sxs-lookup"><span data-stu-id="16d19-134">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="16d19-135">コマンドラインからアドレス帳サーバーを管理する</span><span class="sxs-lookup"><span data-stu-id="16d19-135">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="16d19-136">\*\*\*\*   ユーザーアカウントの管理を管理するには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="16d19-136">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="16d19-137">Lync Server のユーザーアカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="16d19-137">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="16d19-138">ウィザードを使用して Lync Server ユーザーを構成する</span><span class="sxs-lookup"><span data-stu-id="16d19-138">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="16d19-139">Lync Server の個々のユーザーアカウントのプロパティを構成する</span><span class="sxs-lookup"><span data-stu-id="16d19-139">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="16d19-140">Lync Server ユーザーを検索する</span><span class="sxs-lookup"><span data-stu-id="16d19-140">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="16d19-141">Lync Server ユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="16d19-141">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="16d19-142">Lync Server ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="16d19-142">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="16d19-143">**Lync server 2013 ログファイル**   の分析一般的なトラブルシューティングに使用される便利なツールの1つについては、「lync server [2013 logging ツールの使用](http://technet.microsoft.com/en-us/library/gg558599.aspx)について詳しく説明されている lync server 2013 ログツール」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="16d19-143">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](http://technet.microsoft.com/en-us/library/gg558599.aspx).</span></span>

<span data-ttu-id="16d19-144">ログツールによって (サーバーごとに) ログファイルが生成されるため、Microsoft Office Server 12 リソースキットツールがコンピューターにインストールされている場合は、Snooper ツールを使用してこれらのログファイルを表示および分析することができます。</span><span class="sxs-lookup"><span data-stu-id="16d19-144">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="16d19-145">そうしないと、ログもテキストエディターを使って分析することができます。これは、Snooper ユーティリティを使用する場合よりも透明で、より複雑なものになります。</span><span class="sxs-lookup"><span data-stu-id="16d19-145">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="16d19-146">プロトコルメッセージの表示と分析を行うには</span><span class="sxs-lookup"><span data-stu-id="16d19-146">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="16d19-147">ログツールで、デバッグセッションを終了したら、[ログファイルの分析] をクリックし、Snooper ツールを使用してログファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="16d19-147">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="16d19-148">次のコンポーネントのプロトコルログを分析できます。</span><span class="sxs-lookup"><span data-stu-id="16d19-148">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="16d19-149">Lync Server SipStack (SIP)</span><span class="sxs-lookup"><span data-stu-id="16d19-149">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="16d19-150">Lync Server S4 (SIP)</span><span class="sxs-lookup"><span data-stu-id="16d19-150">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="16d19-151">MCU インフラストラクチャ C3P とフォーカス C3P を含む Lync Server 会議のシグナリングトラフィック (C3P)</span><span class="sxs-lookup"><span data-stu-id="16d19-151">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="16d19-152">Lync Server Web 会議トラフィック (PSOM)</span><span class="sxs-lookup"><span data-stu-id="16d19-152">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="16d19-153">Lync Server ユニファイドコミュニケーションクライアントプラットフォームクライアント (UCCP)</span><span class="sxs-lookup"><span data-stu-id="16d19-153">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="16d19-154">アーカイブデータベースからのエラーレポート</span><span class="sxs-lookup"><span data-stu-id="16d19-154">Error reports from the archiving database</span></span>

<span data-ttu-id="16d19-155">必要なタスクのパフォーマンスを整理するために、必要に応じて操作のチェックリストを確認します。</span><span class="sxs-lookup"><span data-stu-id="16d19-155">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="16d19-156">詳細な管理手順と管理手順については、「Microsoft Lync Server 2013 管理者ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16d19-156">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="16d19-157">バックアップ (および復元) ポリシーまたは構成設定</span><span class="sxs-lookup"><span data-stu-id="16d19-157">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="16d19-158">Lync Server 2013 を使用すると、システム全体のバックアップと復元を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="16d19-158">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="16d19-159">1つのポリシーまたは構成設定の単一のコレクションをバックアップして、適切なポリシーを取得し、そのオブジェクトを Clixml コマンドレットにパイプして、ポリシー情報を XML ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="16d19-159">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="16d19-160">これで、RedmondClientPolicy を試して、設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="16d19-160">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="16d19-161">以前のポリシーを復元する場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="16d19-161">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="16d19-162">この方法はほとんどのポリシーと設定で動作しますが、より複雑な項目 (ルーティング構成設定など、複数の異なる音声ルートを含むアイテム) では動作しません。</span><span class="sxs-lookup"><span data-stu-id="16d19-162">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

