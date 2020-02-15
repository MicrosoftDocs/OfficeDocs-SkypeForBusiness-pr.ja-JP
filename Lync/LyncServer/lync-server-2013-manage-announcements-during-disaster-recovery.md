---
title: 'Lync Server 2013: 障害復旧時のアナウンスの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6058974b8473bc2c6db91abaaeb1550647ba592d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="ca896-102">Lync Server 2013 での障害復旧時のアナウンスの管理</span><span class="sxs-lookup"><span data-stu-id="ca896-102">Manage announcements during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca896-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ca896-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ca896-104">Lync Server 2013 は、停止中に割り当てられていない番号への通話のアナウンスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ca896-104">Lync Server 2013 supports announcements for calls to unassigned numbers during outages.</span></span> <span data-ttu-id="ca896-105">停止中のアナウンス機能の復元は任意です。</span><span class="sxs-lookup"><span data-stu-id="ca896-105">Restoring announcement functionality during an outage is optional.</span></span> <span data-ttu-id="ca896-106">停止中にアナウンスを復元する場合は、バックアップ プールでアナウンス構成を再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca896-106">If you choose to restore announcements during an outage, you need recreate your announcement configuration in the backup pool.</span></span> <span data-ttu-id="ca896-107">このセクションでは、障害復旧中にアナウンスを復元する場合に、何を行う必要があるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ca896-107">This section describes what you need to do if you choose to restore announcements during disaster recovery.</span></span>

<span data-ttu-id="ca896-108">このセクションは、アナウンスアプリケーションを使用する割り当てられていない番号範囲に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ca896-108">This section applies to unassigned number ranges that use the Announcement application.</span></span> <span data-ttu-id="ca896-109">Exchange ユニファイド メッセージング (UM) 自動応答を使用する割り当てなしの番号範囲には適用されません。</span><span class="sxs-lookup"><span data-stu-id="ca896-109">This section does not apply to unassigned number ranges that use Exchange Unified Messaging (UM) Auto Attendant.</span></span>

<div>

## <a name="before-an-outage"></a><span data-ttu-id="ca896-110">停止前</span><span class="sxs-lookup"><span data-stu-id="ca896-110">Before an Outage</span></span>

<span data-ttu-id="ca896-111">システム停止時にアナウンスを使用するかどうかにかかわらず、アナウンスアプリケーション用に構成したカスタマイズされたオーディオファイルのバックアップを個別に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca896-111">Regardless of whether you choose to use announcements during outages, you should take separate backups of any customized audio files that you configured for the Announcement application.</span></span> <span data-ttu-id="ca896-112">カスタマイズしたアナウンスは、Lync Server の障害復旧プロセスの一環としてバックアップされません。</span><span class="sxs-lookup"><span data-stu-id="ca896-112">Customized announcements are not backed up as part of the Lync Server disaster recovery process.</span></span> <span data-ttu-id="ca896-113">ファイルのバックアップを別途作成しておらず、サーバーにアップロードしたファイルが破損したり消去されたりした場合、ファイルは失われます。</span><span class="sxs-lookup"><span data-stu-id="ca896-113">If you do not take separate backups of the files and the files that you uploaded to the server or pool are damaged, corrupted, or erased, the files will be lost.</span></span>

<span data-ttu-id="ca896-114">カスタマイズされたオーディオファイルのバックアップコピーがなく、元のオーディオファイルが使用できなくなった場合は、元のサーバーまたはプールのファイルストアを調べて、アナウンスアプリケーション用に構成したオーディオファイルを見つけることができます。ファイルをインポートしました。</span><span class="sxs-lookup"><span data-stu-id="ca896-114">If you do not have backup copies of customized audio files, and the original audio files are no longer available, you can find the audio files that you configured for an Announcement application by looking in the File Store for the server or pool where you originally imported the files.</span></span> <span data-ttu-id="ca896-115">アナウンスメントアプリケーションに対して構成したすべてのオーディオファイルを、ファイルストアからコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="ca896-115">You can copy all the audio files that you configured for the Announcement application from the File Store.</span></span>

<span data-ttu-id="ca896-116">**ファイルストアからオーディオファイルをコピーするには**</span><span class="sxs-lookup"><span data-stu-id="ca896-116">**To copy audio files from the file store**</span></span>

1.  <span data-ttu-id="ca896-117">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca896-117">At the command line, run:</span></span>
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    <span data-ttu-id="ca896-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ca896-118">For example:</span></span>
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    <span data-ttu-id="ca896-119">X-ApplicationServer-X は、プールのアプリケーション サーバーのサービス ID です (例: 1-ApplicationServer-1")</span><span class="sxs-lookup"><span data-stu-id="ca896-119">Where X-ApplicationServer-X refers to the service ID of the Application Server of the pool (for example, 1-ApplicationServer-1")</span></span>


</div>

<div>

## <a name="during-an-outage"></a><span data-ttu-id="ca896-120">停止中</span><span class="sxs-lookup"><span data-stu-id="ca896-120">During an Outage</span></span>

<span data-ttu-id="ca896-121">停止中にアナウンスメントアプリケーションを使用するには、このセクションで説明されているタスクを実行して、バックアッププールでアナウンス構成を再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca896-121">To use the Announcement application during an outage, you need to recreate the announcement configuration in the backup pool by performing the tasks described in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca896-122">手順 2 を実行するとすぐに割り当てなしの番号範囲の所有権をバックアップ プールが取得するので、これらのタスクは、バックアップ プールへのフェールオーバー後に実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ca896-122">We recommend that you perform these tasks after you fail over to the backup pool, because as soon as you perform step 2, the backup pool takes ownership of the unassigned number ranges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ca896-123">この手順は、Exchange UM 自動応答の電話番号を使用する番号範囲については必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ca896-123">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="ca896-124">**バックアッププールでアナウンス構成を再作成するには**</span><span class="sxs-lookup"><span data-stu-id="ca896-124">**To recreate the announcement configuration in the backup pool**</span></span>

1.  <span data-ttu-id="ca896-125">次の手順を実行して、プライマリ プールに展開したアナウンスをバックアップ プールに再作成します。</span><span class="sxs-lookup"><span data-stu-id="ca896-125">Recreate the announcements that you deployed in the primary pool in the backup pool by doing the following:</span></span>
    
    1.  <span data-ttu-id="ca896-126">プライマリ プールで使用していたオーディオ ファイルがある場合は、**Import-CsAnnouncementFile** コマンドレットを使用し、Parent パラメーターにバックアップ プールを指定して、そのオーディオ ファイルをバックアップ プールにインポートします。</span><span class="sxs-lookup"><span data-stu-id="ca896-126">Import any audio files used in the primary pool to the backup pool by using the **Import-CsAnnouncementFile** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    2.  <span data-ttu-id="ca896-127">**New-CsAnnouncement** コマンドレットを使用し、Parent パラメーターにバックアップ プールを指定して、個々のアナウンスを再作成します。</span><span class="sxs-lookup"><span data-stu-id="ca896-127">Recreate each announcement by using the **New-CsAnnouncement** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca896-128">これらのパラメーターを使用してバックアッププールにアナウンスを作成する方法の詳細については、「 <A href="lync-server-2013-create-an-announcement.md">create a アナウンスメント In Lync Server 2013</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca896-128">For details about using these parameters to create announcements in the backup pool, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="ca896-129">すべてのアナウンスがバックアップ プールに再作成されたら、プライマリ プールでアナウンスを使用している割り当てなしの番号範囲をすべて、バックアップ プールに再作成したアナウンスに転送します。</span><span class="sxs-lookup"><span data-stu-id="ca896-129">After all announcements are recreated in the backup pool, redirect all the unassigned number ranges that use announcements in the primary pool to the recreated announcements in the backup pool.</span></span>
    
    <span data-ttu-id="ca896-130">プライマリ プールでアナウンスを使用している割り当てなしの番号範囲ごとに、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca896-130">For each unassigned number range that uses an announcement in the primary pool, run the following:</span></span>
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a><span data-ttu-id="ca896-131">停止後</span><span class="sxs-lookup"><span data-stu-id="ca896-131">After the Outage</span></span>

<span data-ttu-id="ca896-132">プライマリ プールが利用可能になったら、停止中に変更した割り当てなしの番号範囲を、再びプライマリ プールに転送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca896-132">When the primary pool becomes available, you need to redirect the unassigned number ranges that you changed for the outage back to the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca896-133">この手順は、Exchange UM 自動応答の電話番号を使用する番号範囲については必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ca896-133">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="ca896-134">**プライマリプールでアナウンスを復元するには**</span><span class="sxs-lookup"><span data-stu-id="ca896-134">**To restore announcements in the primary pool**</span></span>

1.  <span data-ttu-id="ca896-p105">復旧中にプライマリ プールを再構築した場合は、バックアップ プールで実行したのと同様にオーディオ ファイルをインポートし、アナウンスを作成することによって、プライマリ プールにアナウンスを再作成する必要があります。ただし、この場合は Parent パラメーターにプライマリ プールを指定しません。詳細については、このトピックで前述した「停止中」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca896-p105">If you had to rebuild the primary pool during the recovery, you need to recreate the announcements in the primary pool by importing the audio files and creating announcements, just as you did in the backup pool, except that you specify the primary pool for the Parent parameter. For details, see "During an Outage" earlier in this topic.</span></span>

2.  <span data-ttu-id="ca896-137">停止中に変更した割り当てなしの番号範囲ごとに、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca896-137">For each unassigned number range that you changed for the outage, run the following:</span></span>
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  <span data-ttu-id="ca896-138">必要に応じて、バックアッププールで再作成したアナウンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="ca896-138">Optionally, remove the announcements that you recreated in the backup pool.</span></span> <span data-ttu-id="ca896-139">バックアッププールアナウンスアプリケーションのアナウンスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="ca896-139">Get a list of announcements for the backup pool Announcement application.</span></span> <span data-ttu-id="ca896-140">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca896-140">At the command line, run:</span></span>
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    <span data-ttu-id="ca896-141">例:</span><span class="sxs-lookup"><span data-stu-id="ca896-141">For example:</span></span>
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    <span data-ttu-id="ca896-p107">結果の一覧で、削除するアナウンスを特定し、その GUID をコピーします。削除するアナウンスごとに、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca896-p107">In the resulting list, locate the announcements you want to remove and copy the GUIDs. For each announcement you want to remove, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    <span data-ttu-id="ca896-144">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ca896-144">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

