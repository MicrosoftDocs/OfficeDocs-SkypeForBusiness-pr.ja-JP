---
title: 'Lync Server 2013: ディスク使用状況のチェック'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6379d110fc25ba31062d211d3893567ad92fda1f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526204"
---
# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="39a28-102">Lync Server 2013 でのディスク使用率のチェック</span><span class="sxs-lookup"><span data-stu-id="39a28-102">Checking disk usage in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39a28-103">_**トピックの最終更新日:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="39a28-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="39a28-104">ハードディスクドライブは、Lync Server 2013 展開の重要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="39a28-104">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="39a28-105">十分な空きディスクボリュームがない場合は、オペレーティングシステムと Lync Server 2013 データベースのどちらも正常に機能しません。</span><span class="sxs-lookup"><span data-stu-id="39a28-105">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="39a28-106">サーバーのディスク領域が不足しないようにするため、および必要に応じてストレージリソースを追加する準備を行うには、Lync Server 2013 バックエンドデータベース統計を毎日監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39a28-106">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="39a28-107">オペレーティングシステム、プログラムファイル、データベース、およびトランザクションログ (Lync Server 2013 バックエンド) をホストしているディスクの空き領域の確認とは別に、次の重要なデータを含むファイル共有のディスク領域が含まれるファイルシステムの使用状況を監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39a28-107">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="39a28-108">ミーティング コンテンツ</span><span class="sxs-lookup"><span data-stu-id="39a28-108">Meeting content</span></span>

  - <span data-ttu-id="39a28-109">会議コンテンツのメタデータ</span><span class="sxs-lookup"><span data-stu-id="39a28-109">Meeting content metadata</span></span>

  - <span data-ttu-id="39a28-110">会議のコンプライアンスログ</span><span class="sxs-lookup"><span data-stu-id="39a28-110">Meeting compliance logs</span></span>

  - <span data-ttu-id="39a28-111">アプリケーションデータファイル (アプリケーションサーバーコンポーネントによって内部で使用される)</span><span class="sxs-lookup"><span data-stu-id="39a28-111">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="39a28-112">グループチャットサーバーの web サービスおよびコンプライアンスフォルダー (グループチャット web サービスにアップロードされたファイルを格納する)</span><span class="sxs-lookup"><span data-stu-id="39a28-112">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="39a28-113">グループチャットコンプライアンス XML ファイル (グループチャットコンプライアンスレコードを含む)</span><span class="sxs-lookup"><span data-stu-id="39a28-113">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="39a28-114">ファイルを更新する (デバイス更新サービスの場合)</span><span class="sxs-lookup"><span data-stu-id="39a28-114">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="39a28-115">アドレス帳ファイル</span><span class="sxs-lookup"><span data-stu-id="39a28-115">Address Book files</span></span>

<span data-ttu-id="39a28-116">Lync Server 2013 には、以前に一覧表示されているファイル共有上のファイルに加えて、そのデータベースとトランザクションログを格納するためのハードディスクの空き領域が必要です。</span><span class="sxs-lookup"><span data-stu-id="39a28-116">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="39a28-117">ディスク領域を定期的に監視して、ストレージリソースが不足しているために Lync Server 2013 の展開が悪影響を受けないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="39a28-117">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="39a28-118">各 Lync Server 2013 ボリューム、およびデータベースとトランザクションログファイルの予想される容量の増加に関する統計情報を比較して管理します。</span><span class="sxs-lookup"><span data-stu-id="39a28-118">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="39a28-119">これにより、ストレージリソースが必要になったときの容量計画とストレージの追加に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="39a28-119">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="39a28-120">トラブルシューティングと障害復旧の状況に対応するために、使用可能な空きボリューム容量は、データベースのサイズの110% 以上にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39a28-120">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="39a28-121">次の方法を使用して、空きディスク領域を確認できます。</span><span class="sxs-lookup"><span data-stu-id="39a28-121">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="39a28-122">**System Center Operations Manager**    System Center Operations Manager を使用して、ボリューム領域が制限されている場合に管理者に警告を発することができます。</span><span class="sxs-lookup"><span data-stu-id="39a28-122">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="39a28-123">**スクリプト**     の実行使用可能なハードディスクの空き容量が20% を下回った場合にメッセージを送信するスクリプトを実行して、ディスク容量を監視します。</span><span class="sxs-lookup"><span data-stu-id="39a28-123">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="39a28-124">TechNet の Microsoft Script Center でサンプルスクリプトを確認するには、次の点を確認してください。 [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="39a28-124">You can find a sample script on Microsoft Script Center on TechNet, examine: [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="39a28-125">**Windows エクスプローラー**    Windows エクスプローラーを使用して、Lync Server 2013 のログおよびデータベースを格納するボリューム上のディスク領域をチェックします。</span><span class="sxs-lookup"><span data-stu-id="39a28-125">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

