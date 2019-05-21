---
title: Skype for Business Server での障害回復テスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server プールサーバーのシステム回復を実行して、文書化された障害回復プロセスをテストする
ms.openlocfilehash: d65f8bfa512a3954728e09d659b571335d32a379
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279215"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="8769a-103">Skype for Business Server での障害回復テスト</span><span class="sxs-lookup"><span data-stu-id="8769a-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="8769a-104">Skype for Business Server プールサーバーのシステム回復を実行して、文書化された障害回復プロセスをテストします。</span><span class="sxs-lookup"><span data-stu-id="8769a-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="8769a-105">このテストでは、1台のサーバーの完全なハードウェア障害がシミュレートされ、リソース、計画、データを回復できることを保証するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8769a-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="8769a-106">異なるサーバーやその他の装置のエラーをいつでもテストできるようにテストの焦点を各月で循環させるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8769a-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="8769a-p102">組織が障害回復テストを実施するスケジュールは異なることに注意してください。障害回復テストが無視またはなおざりにされないことが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="8769a-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="8769a-109">Skype for Business Server のトポロジ、ポリシー、構成設定をファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="8769a-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="8769a-110">また、アップグレード、ハードウェア障害、またはその他の問題のためにデータを消失してしまっても、このファイルを使用して、これらの情報を中央管理ストアに復元することができます。</span><span class="sxs-lookup"><span data-stu-id="8769a-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="8769a-111">次のコマンドで示されているように、Skype for Business Server のトポロジ、ポリシー、構成設定を中央管理ストアまたはローカルコンピューターにインポートします。</span><span class="sxs-lookup"><span data-stu-id="8769a-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="8769a-112">運用データをバックアップするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8769a-112">To back up production data:</span></span>

- <span data-ttu-id="8769a-113">標準の SQL Server バックアッププロセスを使用して、RTC と LCSLog データベースのバックアップを作成し、ファイルまたはテープダンプデバイスにデータベースをダンプします。</span><span class="sxs-lookup"><span data-stu-id="8769a-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="8769a-114">サードパーティ バックアップ アプリケーションを使用してデータをファイルまたはテープにバック アップします。</span><span class="sxs-lookup"><span data-stu-id="8769a-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="8769a-115">Export-CsUserData コマンドレットを使用して、RTC データベース全体の XML エクスポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="8769a-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="8769a-116">ファイルシステムバックアップまたはサードパーティバックアップを使用して、会議コンテンツとコンプライアンスログをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="8769a-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="8769a-117">エクスポート-CsConfiguration コマンドラインツールを使用して、Skype for Business Server の設定をバックアップします。</span><span class="sxs-lookup"><span data-stu-id="8769a-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="8769a-118">フェールオーバー手順の最初の手順には、運用プールから障害回復プールへのユーザーの強制的な移動が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8769a-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="8769a-119">運用プールはユーザーの再配置を受け入れることができないため、これは強制的な移動になります。</span><span class="sxs-lookup"><span data-stu-id="8769a-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="8769a-120">Skype for Business Server の移動ユーザーのプロセスは、実質的には、RTC SQL データベースのレコードの更新に加えて、ユーザーアカウントオブジェクトの属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="8769a-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="8769a-121">このデータは、標準の SQL Server restore プロセスを使用するか、サードパーティのバックアップ/復元ユーティリティを使用して、実働 SQL Server から元のバックアップダンプデバイスから復元することができます。</span><span class="sxs-lookup"><span data-stu-id="8769a-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="8769a-122">このデータが復元されると、ユーザーは効率的に障害回復プールに接続し、通常どおりに動作することができます。</span><span class="sxs-lookup"><span data-stu-id="8769a-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="8769a-123">ユーザーが Disaster Recovery プールに接続できるようにするには、DNS レコードの変更が必要になります。</span><span class="sxs-lookup"><span data-stu-id="8769a-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="8769a-124">プロダクション Skype for Business プールは、次のような自動構成と DNS SRV レコードを使用してクライアントによって参照されます。</span><span class="sxs-lookup"><span data-stu-id="8769a-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="8769a-125">SRV: eap-tls。\<domain>/CNAME: SIP。\<domain></span><span class="sxs-lookup"><span data-stu-id="8769a-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="8769a-126">CNAME: SIP。\<domain>/cvc¥ pool1。\<domain></span><span class="sxs-lookup"><span data-stu-id="8769a-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="8769a-127">フェールオーバーを促進するために、この CNAME レコードを更新して DROCSPool FQDN を次のように参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8769a-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="8769a-128">CNAME: SIP。<domain></span><span class="sxs-lookup"><span data-stu-id="8769a-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="8769a-129">/DROCSPool.\<domain></span><span class="sxs-lookup"><span data-stu-id="8769a-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="8769a-130">フェデレーション.\<domain></span><span class="sxs-lookup"><span data-stu-id="8769a-130">Sip.\<domain></span></span>
- <span data-ttu-id="8769a-131">\<Domain></span><span class="sxs-lookup"><span data-stu-id="8769a-131">AV.\<domain></span></span>
- <span data-ttu-id="8769a-132">webconf\<domain></span><span class="sxs-lookup"><span data-stu-id="8769a-132">webconf.\<domain></span></span>
