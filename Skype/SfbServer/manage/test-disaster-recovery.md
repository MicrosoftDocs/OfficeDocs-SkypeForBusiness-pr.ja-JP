---
title: Skype ビジネス サーバーのテスト、災害復旧
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 文書化されている障害回復プロセスをテストするには、ビジネス サーバー プールの Skype のシステム回復を実行します。
ms.openlocfilehash: 876470f0e4193f02efe0a2094be80f7bdf891fdd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884965"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="ddc31-103">Skype ビジネス サーバーのテスト、災害復旧</span><span class="sxs-lookup"><span data-stu-id="ddc31-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="ddc31-104">文書化されている障害回復プロセスをテストするには、ビジネス サーバー プールの Skype のシステム回復を実行します。</span><span class="sxs-lookup"><span data-stu-id="ddc31-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="ddc31-105">このテストでは、1 つのサーバーの完全なハードウェア障害をシミュレートするは、リソース、計画、およびデータがリカバリに使用できることを保証するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ddc31-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="ddc31-106">異なるサーバーやその他の装置のエラーをいつでもテストできるようにテストの焦点を各月で循環させるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="ddc31-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="ddc31-p102">組織が障害回復テストを実施するスケジュールは異なることに注意してください。障害回復テストが無視またはなおざりにされないことが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="ddc31-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="ddc31-109">Business Server のトポロジ、ポリシー、および構成の設定は、Skype をファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ddc31-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="ddc31-110">また、アップグレード、ハードウェア障害、またはその他の問題のためにデータを消失してしまっても、このファイルを使用して、これらの情報を中央管理ストアに復元することができます。</span><span class="sxs-lookup"><span data-stu-id="ddc31-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="ddc31-111">コマンドを次に示すように、中央管理ストアまたはローカル コンピューターにビジネス サーバーのトポロジ、ポリシー、および構成の設定は、Skype をインポートします。</span><span class="sxs-lookup"><span data-stu-id="ddc31-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="ddc31-112">本番データをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="ddc31-112">To back up production data:</span></span>

- <span data-ttu-id="ddc31-113">標準の SQL Server を使用して、RTC と LCSLog データベースをバックアップ ファイルまたはテープ ダンプ デバイスにデータベースをダンプするプロセスをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="ddc31-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="ddc31-114">サードパーティ バックアップ アプリケーションを使用してデータをファイルまたはテープにバック アップします。</span><span class="sxs-lookup"><span data-stu-id="ddc31-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="ddc31-115">Export-CsUserData コマンドレットを使用して、RTC データベース全体の XML エクスポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="ddc31-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="ddc31-116">ミーティングのコンテンツとコンプライアンスのログをバックアップするには、ファイル システムのバックアップまたはサードパーティ製のバックアップを使用します。</span><span class="sxs-lookup"><span data-stu-id="ddc31-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="ddc31-117">エクスポート CsConfiguration コマンド ライン ツールを使用すると、Skype をビジネスのサーバー設定のバックアップを作成します。</span><span class="sxs-lookup"><span data-stu-id="ddc31-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="ddc31-118">フェールオーバー手順の最初の手順には、運用プールから障害回復プールへのユーザーの強制的な移動が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ddc31-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="ddc31-119">運用プールはユーザーの再配置を受け入れることができないため、これは強制的な移動になります。</span><span class="sxs-lookup"><span data-stu-id="ddc31-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="ddc31-120">ビジネス サーバー移動のユーザー プロセスの Skype は、事実上、RTC の SQL データベースのレコードの更新だけでなく、ユーザー アカウント オブジェクトの属性への変更です。</span><span class="sxs-lookup"><span data-stu-id="ddc31-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="ddc31-121">このデータを復元することが、本番環境から元のバックアップ ダンプ デバイスから SQL Server の標準的な SQL Server のリストア ・ プロセスを使用するか、サード パーティを使用するバックアップと復元ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="ddc31-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="ddc31-122">このデータが復元されると、ユーザーは効果的に災害復旧のプールに接続して通常どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="ddc31-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="ddc31-123">災害復旧のプールに接続するユーザーを有効にするには、DNS レコードの変更が必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddc31-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="ddc31-124">生産 Skype のビジネスのプールは、クライアントの自動構成および DNS SRV レコードを使用してによって参照されます。</span><span class="sxs-lookup"><span data-stu-id="ddc31-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="ddc31-125">SRV: ゾーンに追加します。\<domain>/CNAME: SIP。\<domain></span><span class="sxs-lookup"><span data-stu-id="ddc31-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="ddc31-126">CNAME: SIP。\<domain>/cvc-pool-1。\<domain></span><span class="sxs-lookup"><span data-stu-id="ddc31-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="ddc31-127">フェールオーバーを促進するために、この CNAME レコードを更新して DROCSPool FQDN を次のように参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddc31-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="ddc31-128">CNAME: SIP。<domain></span><span class="sxs-lookup"><span data-stu-id="ddc31-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="ddc31-129">/DROCSPool です。\<domain></span><span class="sxs-lookup"><span data-stu-id="ddc31-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="ddc31-130">Sip。\<domain></span><span class="sxs-lookup"><span data-stu-id="ddc31-130">Sip.\<domain></span></span>
- <span data-ttu-id="ddc31-131">AV.\<domain></span><span class="sxs-lookup"><span data-stu-id="ddc31-131">AV.\<domain></span></span>
- <span data-ttu-id="ddc31-132">webconf。\<domain></span><span class="sxs-lookup"><span data-stu-id="ddc31-132">webconf.\<domain></span></span>
