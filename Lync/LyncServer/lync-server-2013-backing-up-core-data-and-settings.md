---
title: 'Lync Server 2013: コアデータと設定のバックアップ'
description: 'Lync Server 2013: コアデータと設定をバックアップしています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 637eeb950a3b8380f6e756f46a5083f51b5d7e1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543743"
---
# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="bd17a-103">Lync Server 2013 でのコアデータと設定のバックアップ</span><span class="sxs-lookup"><span data-stu-id="bd17a-103">Backing up core data and settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd17a-104">_**トピックの最終更新日:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="bd17a-104">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="bd17a-105">次の手順では、Lync Server 管理シェルコマンドレットを使用して、コアサービスの設定とデータのバックアップファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd17a-105">The following procedures use Lync Server Management Shell cmdlets to create backup files for settings and data for core services.</span></span> <span data-ttu-id="bd17a-106">このセクションで使用されているツールの詳細については、「 [Lync Server 2013 のバックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)」を参照してください。ツールとアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="bd17a-106">For details about the tools used in this section, including where they are located, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span> <span data-ttu-id="bd17a-107">アーカイブおよび監視データのバックアップの詳細については、「 [Lync Server 2013 でのアーカイブおよび監視データベースのバックアップ](lync-server-2013-backing-up-archiving-and-monitoring-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd17a-107">For details about backing up Archiving and Monitoring data, see [Backing up Archiving and Monitoring databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd17a-108">中央管理ストアをバックアップするためのこのセクションの手順には、アーカイブと監視の設定と構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bd17a-108">The step in this section to back up the Central Management store includes the settings and configuration for Archiving and Monitoring.</span></span>



</div>

<span data-ttu-id="bd17a-109">ここで説明するコマンドレットは、ローカルでもリモートでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="bd17a-109">You can run the cmdlets described in this section locally or remotely.</span></span>

<div>

## <a name="to-back-up-core-data-and-settings"></a><span data-ttu-id="bd17a-110">コア データおよび設定をバックアップするには</span><span class="sxs-lookup"><span data-stu-id="bd17a-110">To back up core data and settings</span></span>

1.  <span data-ttu-id="bd17a-111">RTCUniversalServerAdmins グループのメンバーであるユーザー アカウントから、内部展開内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bd17a-111">From a user account that is a member of the RTCUniversalServerAdmins group, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bd17a-112">以下の手順で作成するバックアップを格納するため、新しい共有フォルダーを作成し、**$Backup** によって参照されているパスを新しい共有フォルダーに更新します。</span><span class="sxs-lookup"><span data-stu-id="bd17a-112">To store the backups you create in the following steps, create a new shared folder and update the path referenced by **$Backup** to the new shared folder.</span></span>

3.  <span data-ttu-id="bd17a-113">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd17a-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="bd17a-114">中央管理ストア構成ファイルをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="bd17a-114">Back up the Central Management store configuration file.</span></span> <span data-ttu-id="bd17a-115">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bd17a-115">At the command line, type the following:</span></span>
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="bd17a-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd17a-116">For example:</span></span>
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd17a-117">この手順では、Lync Server のトポロジ、ポリシー、および構成設定をファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="bd17a-117">This step exports your Lync Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="bd17a-118">トポロジ データをバックアップするために他の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bd17a-118">No other step is required to backup topology data.</span></span>

    
    </div>

5.  <span data-ttu-id="bd17a-119">バックアップした中央管理ストア構成ファイルを $Backup にコピーし \\ ます。</span><span class="sxs-lookup"><span data-stu-id="bd17a-119">Copy the backed-up Central Management store configuration file to $Backup\\.</span></span>

6.  <span data-ttu-id="bd17a-p104">場所情報サービスのデータをバックアップします。コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bd17a-p104">Back up Location Information service data. At the command line, type the following:</span></span>
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="bd17a-122">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd17a-122">For example:</span></span>
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  <span data-ttu-id="bd17a-123">バックアップした場所情報サービス構成ファイルを $Backup にコピーし \\ ます。</span><span class="sxs-lookup"><span data-stu-id="bd17a-123">Copy the backed-up Location Information service configuration file to $Backup\\.</span></span>

8.  <span data-ttu-id="bd17a-124">フロントエンドプールおよびすべての Standard Edition サーバーのすべてのバックエンドデータベースについて、ユーザーデータをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="bd17a-124">Back up user data on every back-end database of a Front End pool and every Standard Edition server.</span></span> <span data-ttu-id="bd17a-125">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bd17a-125">At the command line, type the following:</span></span>
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    <span data-ttu-id="bd17a-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd17a-126">For example:</span></span>
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  <span data-ttu-id="bd17a-127">バックアップしたユーザーファイルを $Backup にコピーし \\ ます。</span><span class="sxs-lookup"><span data-stu-id="bd17a-127">Copy the backed up user file to $Backup\\.</span></span>

10. <span data-ttu-id="bd17a-128">応答グループアプリケーションが実行されているすべてのプールで、応答グループ構成をバックアップします。</span><span class="sxs-lookup"><span data-stu-id="bd17a-128">On every pool that runs the Response Group application, back up the Response Group configuration.</span></span> <span data-ttu-id="bd17a-129">次の操作を実行してください。</span><span class="sxs-lookup"><span data-stu-id="bd17a-129">Do the following:</span></span>
    
    1.  <span data-ttu-id="bd17a-130">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bd17a-130">At the command line, type:</span></span>
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        <span data-ttu-id="bd17a-131">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd17a-131">For example:</span></span>
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. <span data-ttu-id="bd17a-132">バックアップされた応答グループ構成ファイルを $Backup にコピーし \\ ます。</span><span class="sxs-lookup"><span data-stu-id="bd17a-132">Copy the backed up Response Group configuration file to $Backup\\.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

