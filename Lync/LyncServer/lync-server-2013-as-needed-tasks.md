---
title: 'Lync Server 2013: 必要に応じたタスク'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58abaf251bf479a9e892d019bd086a10b2300afc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="c8567-102">Lync Server 2013 で必要になるタスク</span><span class="sxs-lookup"><span data-stu-id="c8567-102">As-needed tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8567-103">_**トピックの最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="c8567-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="c8567-104">必要に応じて、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c8567-104">Perform the following tasks as necessary.</span></span> <span data-ttu-id="c8567-105">多くの場合、標準の手順でも説明されています。</span><span class="sxs-lookup"><span data-stu-id="c8567-105">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="c8567-106">**完全なセキュリティ監査   **この監査は、メッセージングシステムのアップグレードまたは再設計に対応して、または試行された (または成功した) セキュリティ違反に応答して、定期的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="c8567-106">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="c8567-107">この手順には、サーバーとファイアウォールのポートスキャン、セキュリティ修正プログラムの監査、およびサードパーティの侵入テストが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c8567-107">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="c8567-108">**[証明書を置き換えて、期限切れ**   になるようにする] Lync Server 証明書は、通常の週次のタスクの1つであり、管理者がすべての証明書の有効期限を記録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8567-108">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="c8567-109">このレコードを使用すると、管理者は特定の証明書が期限切れになり、必要に応じて置き換えられたときに通知を作成できます。</span><span class="sxs-lookup"><span data-stu-id="c8567-109">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="c8567-110">**パフォーマンスベースライン**   の更新アップグレードまたは構成の変更後のパフォーマンスベースラインを更新します。</span><span class="sxs-lookup"><span data-stu-id="c8567-110">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="c8567-111">組織はベースラインを使用して、パフォーマンスの変化を測定し、システムのパフォーマンスに影響する問題を検出することができます。</span><span class="sxs-lookup"><span data-stu-id="c8567-111">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="c8567-112">**エンタープライズプール**   、Standard Edition サーバー、および組織の環境内の他のサーバーのエンタープライズプールの初期構成の管理は、個々のサーバーの展開中に実行されました。</span><span class="sxs-lookup"><span data-stu-id="c8567-112">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="c8567-113">Standard Edition サーバーおよびエンタープライズプールのサーバーとプールの展開後の管理には、次のタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c8567-113">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="c8567-114">フロントエンドサーバーの管理</span><span class="sxs-lookup"><span data-stu-id="c8567-114">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="c8567-115">Web 会議の管理</span><span class="sxs-lookup"><span data-stu-id="c8567-115">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="c8567-116">会議の管理</span><span class="sxs-lookup"><span data-stu-id="c8567-116">Managing Conferencing</span></span>
    
      - <span data-ttu-id="c8567-117">サービスアカウントの資格情報の変更</span><span class="sxs-lookup"><span data-stu-id="c8567-117">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="c8567-118">データベースを管理する</span><span class="sxs-lookup"><span data-stu-id="c8567-118">Managing Databases</span></span>
    
      - <span data-ttu-id="c8567-119">サービスの開始と停止、およびサーバーの役割の非アクティブ化</span><span class="sxs-lookup"><span data-stu-id="c8567-119">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="c8567-120">サーバーとサーバーの役割の削除、プールの削除、およびサーバーとプールの使用停止</span><span class="sxs-lookup"><span data-stu-id="c8567-120">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="c8567-121">**利用状況**   の管理 Lync Server 2013 を構成して、組織にとって最も適切な機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="c8567-121">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="c8567-122">エクスポートできるものには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="c8567-122">This includes the following:</span></span>
    
      - <span data-ttu-id="c8567-123">オンプレミス Web 会議会議のサポートの管理</span><span class="sxs-lookup"><span data-stu-id="c8567-123">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="c8567-124">配布グループの使用を管理してインスタントメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="c8567-124">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="c8567-125">連絡先、プレゼンス、およびクエリを管理する</span><span class="sxs-lookup"><span data-stu-id="c8567-125">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="c8567-126">クライアントバージョンフィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="c8567-126">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="c8567-127">インテリジェント IM フィルターの構成</span><span class="sxs-lookup"><span data-stu-id="c8567-127">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="c8567-128">アーカイブ、通話詳細記録、会議のコンプライアンスの構成</span><span class="sxs-lookup"><span data-stu-id="c8567-128">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="c8567-129">**エッジサーバー接続**   の管理サーバーの継続的な管理と、外部接続を提供するために必要な設定には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c8567-129">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="c8567-130">内部サーバーとエッジサーバー間の接続の管理</span><span class="sxs-lookup"><span data-stu-id="c8567-130">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="c8567-131">エッジサーバーの内部および外部インターフェイスと証明書の構成</span><span class="sxs-lookup"><span data-stu-id="c8567-131">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="c8567-132">フェデレーションパートナーアクセスの管理</span><span class="sxs-lookup"><span data-stu-id="c8567-132">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="c8567-133">\*\*\*\*   アドレス帳の管理アドレス帳サーバーの管理には、以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c8567-133">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="c8567-134">アドレス帳サーバーの電話の正規化を構成する</span><span class="sxs-lookup"><span data-stu-id="c8567-134">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="c8567-135">コマンドラインからアドレス帳サーバーを管理する</span><span class="sxs-lookup"><span data-stu-id="c8567-135">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="c8567-136">**ユーザーアカウント**   の管理ユーザーアカウントの管理には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="c8567-136">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="c8567-137">Lync Server でユーザーアカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="c8567-137">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="c8567-138">ウィザードを使用して Lync Server ユーザーを構成する</span><span class="sxs-lookup"><span data-stu-id="c8567-138">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="c8567-139">個々の Lync Server ユーザーアカウントのプロパティを構成する</span><span class="sxs-lookup"><span data-stu-id="c8567-139">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="c8567-140">Lync Server ユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="c8567-140">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="c8567-141">Lync Server ユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="c8567-141">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="c8567-142">Lync Server ユーザーの削除</span><span class="sxs-lookup"><span data-stu-id="c8567-142">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="c8567-143">**Lync server 2013 ログファイル**   の分析トラブルシューティングに一般的に使用される便利なツールの1つは、「 [lync server 2013 logging tool の使用](https://technet.microsoft.com/library/gg558599.aspx)」で詳しく説明されている lync server 2013 ログツールです。</span><span class="sxs-lookup"><span data-stu-id="c8567-143">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](https://technet.microsoft.com/library/gg558599.aspx).</span></span>

<span data-ttu-id="c8567-144">ログツールはログファイル (サーバー単位) を生成するため、これらのログファイルは、Microsoft Office Server 12 リソースキットツールがコンピューターにインストールされている場合、Snooper ツールを使用して表示および分析できます。</span><span class="sxs-lookup"><span data-stu-id="c8567-144">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="c8567-145">それ以外の場合、ログはテキストエディターを使用して分析することができます。これは、Snooper ユーティリティを使用するよりも透過的で複雑です。</span><span class="sxs-lookup"><span data-stu-id="c8567-145">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="c8567-146">プロトコルメッセージを表示および分析するには</span><span class="sxs-lookup"><span data-stu-id="c8567-146">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="c8567-147">ログツールで、デバッグセッションを終了した後、Snooper ツールを使用してログファイルを表示するには、[ログファイルの分析] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8567-147">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="c8567-148">次のコンポーネントのプロトコルログを分析することができます。</span><span class="sxs-lookup"><span data-stu-id="c8567-148">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="c8567-149">Lync Server SipStack (SIP)</span><span class="sxs-lookup"><span data-stu-id="c8567-149">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="c8567-150">Lync Server S4 (SIP)</span><span class="sxs-lookup"><span data-stu-id="c8567-150">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="c8567-151">Lync Server 会議信号トラフィック (C3P) (MCU インフラストラクチャ C3P およびフォーカス C3P を含む)</span><span class="sxs-lookup"><span data-stu-id="c8567-151">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="c8567-152">Lync Server Web 会議トラフィック (PSOM)</span><span class="sxs-lookup"><span data-stu-id="c8567-152">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="c8567-153">Lync Server 統合コミュニケーションクライアントプラットフォームクライアント (UCCP)</span><span class="sxs-lookup"><span data-stu-id="c8567-153">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="c8567-154">アーカイブデータベースからのエラーレポート</span><span class="sxs-lookup"><span data-stu-id="c8567-154">Error reports from the archiving database</span></span>

<span data-ttu-id="c8567-155">必要なタスクのパフォーマンスを整理するには、必要に応じた操作チェックリストを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8567-155">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c8567-156">管理および管理手順の詳細については、「Microsoft Lync Server 2013 Administration Guide」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8567-156">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="c8567-157">バックアップ (および復元) ポリシーまたは構成設定</span><span class="sxs-lookup"><span data-stu-id="c8567-157">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="c8567-158">Lync Server 2013 では、システム全体をバックアップおよび復元できます。</span><span class="sxs-lookup"><span data-stu-id="c8567-158">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="c8567-159">Iif をバックアップして、構成設定の単一のポリシーまたは単一のコレクションを取得し、適切なポリシーを取得してから、そのオブジェクトを Export-clixml コマンドレットにパイプ処理して、ポリシー情報を XML ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="c8567-159">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="c8567-160">これで、RedmondClientPolicy を試して、設定の多くを変更することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="c8567-160">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="c8567-161">以前のポリシーを復元するのではなく、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c8567-161">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="c8567-162">この方法は、ほとんどのポリシーと設定で機能しますが、複雑なアイテム (複数のサブオブジェクトを含むアイテムなど) では機能しません (多数の異なる音声ルートを含むルーティング構成設定など)。</span><span class="sxs-lookup"><span data-stu-id="c8567-162">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

