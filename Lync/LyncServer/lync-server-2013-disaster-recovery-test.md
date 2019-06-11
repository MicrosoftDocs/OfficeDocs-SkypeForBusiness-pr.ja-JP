---
title: 'Lync Server 2013: 障害復旧テスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9b17f5841cad96cb83399082f61c00194ec4828
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="d740c-102">Lync Server 2013 での障害復旧テスト</span><span class="sxs-lookup"><span data-stu-id="d740c-102">Disaster recovery test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d740c-103">_**最終更新日:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="d740c-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="d740c-104">Lync Server 2013 プールサーバーのシステム回復を実行して、文書化された障害回復プロセスをテストします。</span><span class="sxs-lookup"><span data-stu-id="d740c-104">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="d740c-105">このテストは、サーバーの完全なハードウェア エラーをシミュレーションを実行して、リソース、プラン、およびデータを回復に利用できることを保証するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d740c-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="d740c-106">異なるサーバーやその他の装置のエラーをいつでもテストできるようにテストの焦点を各月で循環させるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="d740c-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="d740c-p102">組織が障害回復テストを実施するスケジュールは異なることに注意してください。障害回復テストが無視またはなおざりにされないことが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="d740c-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="d740c-109">Lync Server 2013 のトポロジ、ポリシー、構成設定をファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d740c-109">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="d740c-110">また、アップグレード、ハードウェア障害、またはその他の問題のためにデータを消失してしまっても、このファイルを使用して、これらの情報を中央管理ストアに復元することができます。</span><span class="sxs-lookup"><span data-stu-id="d740c-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="d740c-111">次のコマンドで示されているように、Lync Server 2013 のトポロジ、ポリシー、構成設定を中央管理ストアまたはローカルコンピューターにインポートします。</span><span class="sxs-lookup"><span data-stu-id="d740c-111">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="d740c-112">プロダクション用の Lync Server 2013 データをバックアップするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d740c-112">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="d740c-113">標準の SQL Server バックアッププロセスを使用して、RTC と LCSLog データベースのバックアップを作成し、ファイルまたはテープダンプデバイスにデータベースをダンプします。</span><span class="sxs-lookup"><span data-stu-id="d740c-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="d740c-114">サードパーティ バックアップ アプリケーションを使用してデータをファイルまたはテープにバック アップします。</span><span class="sxs-lookup"><span data-stu-id="d740c-114">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="d740c-115">Export-CsUserData コマンドレットを使用して、RTC データベース全体の XML エクスポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="d740c-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="d740c-116">ファイル システム バックアップまたはサードパーティ バックアップ アプリケーションを使用して、会議コンテンツやコンプライアンス ログをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="d740c-116">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="d740c-117">エクスポート-CsConfiguration コマンドラインツールを使用して、Lync Server 2013 の設定をバックアップします。</span><span class="sxs-lookup"><span data-stu-id="d740c-117">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="d740c-118">フェールオーバー手順の最初の手順には、運用プールから障害回復プールへのユーザーの強制的な移動が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d740c-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="d740c-119">運用プールはユーザーの再配置を受け入れることができないため、これは強制的な移動になります。</span><span class="sxs-lookup"><span data-stu-id="d740c-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="d740c-120">Lync Server 2013 の移動ユーザープロセスは、実質的には、RTC SQL データベースのレコードの更新に加えて、ユーザーアカウントオブジェクトの属性に対する変更になります。</span><span class="sxs-lookup"><span data-stu-id="d740c-120">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="d740c-121">このデータは、以下の 2 つの処理を通じて復元できます。</span><span class="sxs-lookup"><span data-stu-id="d740c-121">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="d740c-122">RTC データベースは、標準の SQL Server 復元プロセスを使用するか、サードパーティのバックアップ/復元ユーティリティを使用して、実働 SQL Server から元のバックアップダンプデバイスから復元することができます。</span><span class="sxs-lookup"><span data-stu-id="d740c-122">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="d740c-123">ユーザー連絡先データは、運用 SQL Server エクスポートから作成した XML ファイルを使用して、DBIMPEXP.exe ユーティリティで復元できます。</span><span class="sxs-lookup"><span data-stu-id="d740c-123">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="d740c-124">このデータが復元されると、ユーザーは効果的に Disaster Recovery Lync Server 2013 プールに接続し、通常どおりに動作することができます。</span><span class="sxs-lookup"><span data-stu-id="d740c-124">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="d740c-125">ユーザーが Disaster Recovery Lync Server 2013 プールに接続できるようにするには、DNS レコードの変更が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d740c-125">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="d740c-126">プロダクション Lync Server 2013 プールは、次の自動構成と DNS SRV レコードを使用してクライアントから参照されます。</span><span class="sxs-lookup"><span data-stu-id="d740c-126">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="d740c-127">SRV: \_sip。\_tls。\<ドメイン\> /CNAME: SIP。\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="d740c-127">SRV: \_sip.\_tls.\<domain\> /CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="d740c-128">CNAME: SIP。\<domain\> /cvc¥ pool1。\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="d740c-128">CNAME: SIP.\<domain\> /cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="d740c-129">フェールオーバーを促進するために、この CNAME レコードを更新して DROCSPool FQDN を次のように参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d740c-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="d740c-130">CNAME: SIP。\<domain\> /DROCSPool.\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="d740c-130">CNAME: SIP.\<domain\> /DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="d740c-131">フェデレーション.\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="d740c-131">Sip.\<domain\></span></span>

  - <span data-ttu-id="d740c-132">AV。\<ドメイン名\></span><span class="sxs-lookup"><span data-stu-id="d740c-132">AV.\<domain\></span></span>

  - <span data-ttu-id="d740c-133">webconf\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="d740c-133">webconf.\<domain\></span></span>

  - <span data-ttu-id="d740c-134">OCSServices。\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="d740c-134">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d740c-135">管理と管理の詳細な手順については、「 <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Lync Server 2013 のバックアップと復元</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d740c-135">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d740c-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="d740c-136">See Also</span></span>


[<span data-ttu-id="d740c-137">Lync Server 2013 での高可用性および障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="d740c-137">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="d740c-138">Lync Server 2013 のバックアップと高可用性のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d740c-138">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="d740c-139">インポート-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d740c-139">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="d740c-140">Lync Server 2013 のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="d740c-140">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="d740c-141">Lync Server 2013 の障害復旧、高可用性およびバックアップ サービスの管理</span><span class="sxs-lookup"><span data-stu-id="d740c-141">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

