---
title: Skype for Business Server での障害復旧テスト
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server プール サーバーのシステム回復を実行して、文書化された障害復旧プロセスをテストする
ms.openlocfilehash: 92515a59f4ada2589a371cc9384c63a376e96cf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832817"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="c2a2c-103">Skype for Business Server での障害復旧テスト</span><span class="sxs-lookup"><span data-stu-id="c2a2c-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="c2a2c-104">Skype for Business Server プール サーバーのシステム回復を実行して、文書化された障害復旧プロセスをテストします。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="c2a2c-105">このテストは、1 つのサーバーの完全なハードウェア障害をシミュレートし、リソース、計画、およびデータが復旧に使用できる保証に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="c2a2c-106">毎月テストの焦点を変え、組織が毎回異なるサーバーまたは他の機器の障害をテストします。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="c2a2c-107">組織が障害復旧テストを実行するスケジュールは異なる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="c2a2c-108">障害復旧テストを無視したり、無視したりすることが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="c2a2c-109">Skype for Business Server のトポロジ、ポリシー、および構成設定をファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="c2a2c-110">特に、このファイルを使用して、アップグレード、ハードウェア障害、その他の問題によってデータが失われる結果、中央管理ストアにこの情報を復元できます。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="c2a2c-111">次のコマンドに示すように、Skype for Business Server のトポロジ、ポリシー、および構成設定を中央管理ストアまたはローカル コンピューターにインポートします。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="c2a2c-112">実稼働データをバックアップするには:</span><span class="sxs-lookup"><span data-stu-id="c2a2c-112">To back up production data:</span></span>

- <span data-ttu-id="c2a2c-113">RTC データベースと LCSLog データベースをバックアップするには、標準の SQL Server バックアップ プロセスを使用して、データベースをファイルまたはテープ ダンプ デバイスにダンプします。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="c2a2c-114">サードパーティのバックアップ アプリケーションを使用して、データをファイルまたはテープにバックアップします。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="c2a2c-115">RTC データベースExport-CsUserData XML エクスポートを作成するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="c2a2c-116">ファイル システムバックアップまたはサードパーティバックアップを使用して、会議コンテンツとコンプライアンス ログをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="c2a2c-117">Skype for Business Server Export-CsConfigurationバックアップするには、次のコマンド ライン ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="c2a2c-118">フェールオーバー手順の最初の手順には、ユーザーを実稼働プールから障害復旧プールに強制的に移動する手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="c2a2c-119">これは、ユーザーの再配置を受け入れる実稼働プールを使用できないので、強制的な移動になります。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="c2a2c-120">Skype for Business Server の移動ユーザー プロセスは、RTC データベース上のレコード更新に加えて、ユーザー アカウント オブジェクトの属性SQLです。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="c2a2c-121">このデータは、標準の SQL Server 復元プロセスを使用するか、サードパーティのバックアップ/復元ユーティリティを使用して、実稼働 SQL Server から元のバックアップ ダンプ デバイスから復元できます。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="c2a2c-122">このデータが復元された後、ユーザーは効率的に障害復旧プールに接続し、通常どおり動作できます。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="c2a2c-123">ユーザーが障害復旧プールに接続するには、DNS レコードの変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="c2a2c-124">実稼働 Skype for Business プールは、次の自動構成および DNS SRV レコードを使用してクライアントによって参照されます。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="c2a2c-125">SRV: _sip._tls。\<domain></span><span class="sxs-lookup"><span data-stu-id="c2a2c-125">SRV: _sip._tls.\<domain></span></span> <span data-ttu-id="c2a2c-126">/CNAME: SIP。\<domain></span><span class="sxs-lookup"><span data-stu-id="c2a2c-126">/CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="c2a2c-127">CNAME: SIP。\<domain></span><span class="sxs-lookup"><span data-stu-id="c2a2c-127">CNAME: SIP.\<domain></span></span> <span data-ttu-id="c2a2c-128">/cvc-pool-1.\<domain></span><span class="sxs-lookup"><span data-stu-id="c2a2c-128">/cvc-pool-1.\<domain></span></span>

<span data-ttu-id="c2a2c-129">フェールオーバーを容易にするために、この CNAME レコードを更新して DROCSPool FQDN を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2a2c-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="c2a2c-130">CNAME: SIP。<domain></span><span class="sxs-lookup"><span data-stu-id="c2a2c-130">CNAME: SIP.<domain></span></span> <span data-ttu-id="c2a2c-131">/DROCSPool。\<domain></span><span class="sxs-lookup"><span data-stu-id="c2a2c-131">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="c2a2c-132">Sip。\<domain></span><span class="sxs-lookup"><span data-stu-id="c2a2c-132">Sip.\<domain></span></span>
- <span data-ttu-id="c2a2c-133">AV。\<domain></span><span class="sxs-lookup"><span data-stu-id="c2a2c-133">AV.\<domain></span></span>
- <span data-ttu-id="c2a2c-134">webconf。\<domain></span><span class="sxs-lookup"><span data-stu-id="c2a2c-134">webconf.\<domain></span></span>
