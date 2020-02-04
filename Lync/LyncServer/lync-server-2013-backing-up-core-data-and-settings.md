---
title: 'Lync Server 2013: コアデータと設定のバックアップ'
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
ms.openlocfilehash: 4185c02bc85077b0f68ca76d83fd48203e0e5fd9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="8fd0a-102">Lync Server 2013 でのコアデータと設定のバックアップ</span><span class="sxs-lookup"><span data-stu-id="8fd0a-102">Backing up core data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fd0a-103">_**最終更新日:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="8fd0a-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="8fd0a-104">次の手順では、Lync Server Management Shell コマンドレットを使用して、コアサービスの設定とデータのバックアップファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-104">The following procedures use Lync Server Management Shell cmdlets to create backup files for settings and data for core services.</span></span> <span data-ttu-id="8fd0a-105">このセクションで使用されるツールの詳細については、「 [Lync Server 2013 のバックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)」を参照してください。ツールと権限。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-105">For details about the tools used in this section, including where they are located, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span> <span data-ttu-id="8fd0a-106">アーカイブと監視データのバックアップの詳細については、「 [Lync Server 2013 でのアーカイブと監視データベースのバックアップ](lync-server-2013-backing-up-archiving-and-monitoring-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-106">For details about backing up Archiving and Monitoring data, see [Backing up Archiving and Monitoring databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8fd0a-107">このセクションの中央管理ストアをバックアップする手順には、アーカイブと監視の設定と構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-107">The step in this section to back up the Central Management store includes the settings and configuration for Archiving and Monitoring.</span></span>



</div>

<span data-ttu-id="8fd0a-108">このセクションで説明されているコマンドレットは、ローカルまたはリモートで実行できます。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-108">You can run the cmdlets described in this section locally or remotely.</span></span>

<div>

## <a name="to-back-up-core-data-and-settings"></a><span data-ttu-id="8fd0a-109">コアデータと設定をバックアップするには</span><span class="sxs-lookup"><span data-stu-id="8fd0a-109">To back up core data and settings</span></span>

1.  <span data-ttu-id="8fd0a-110">RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、社内展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-110">From a user account that is a member of the RTCUniversalServerAdmins group, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8fd0a-111">次の手順で作成したバックアップを保存するには、新しい共有フォルダーを作成し、 **$Backup**によって参照されるパスを新しい共有フォルダーに更新します。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-111">To store the backups you create in the following steps, create a new shared folder and update the path referenced by **$Backup** to the new shared folder.</span></span>

3.  <span data-ttu-id="8fd0a-112">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="8fd0a-113">一元管理ストア構成ファイルをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-113">Back up the Central Management store configuration file.</span></span> <span data-ttu-id="8fd0a-114">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-114">At the command line, type the following:</span></span>
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="8fd0a-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-115">For example:</span></span>
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8fd0a-116">この手順では、Lync サーバーのトポロジ、ポリシー、構成の設定をファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-116">This step exports your Lync Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="8fd0a-117">トポロジデータをバックアップするために、他の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-117">No other step is required to backup topology data.</span></span>

    
    </div>

5.  <span data-ttu-id="8fd0a-118">バックアップされた全体管理ストア構成ファイルを $Backup\\にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-118">Copy the backed-up Central Management store configuration file to $Backup\\.</span></span>

6.  <span data-ttu-id="8fd0a-119">位置情報サービスのデータをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-119">Back up Location Information service data.</span></span> <span data-ttu-id="8fd0a-120">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-120">At the command line, type the following:</span></span>
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="8fd0a-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-121">For example:</span></span>
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  <span data-ttu-id="8fd0a-122">バックアップされた場所情報サービス構成ファイルを $Backup\\にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-122">Copy the backed-up Location Information service configuration file to $Backup\\.</span></span>

8.  <span data-ttu-id="8fd0a-123">フロントエンドプールおよびすべての Standard Edition サーバーの各バックエンドデータベースで、ユーザーデータをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-123">Back up user data on every back-end database of a Front End pool and every Standard Edition server.</span></span> <span data-ttu-id="8fd0a-124">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-124">At the command line, type the following:</span></span>
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    <span data-ttu-id="8fd0a-125">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-125">For example:</span></span>
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  <span data-ttu-id="8fd0a-126">バックアップされたユーザーファイルを $Backup\\にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-126">Copy the backed up user file to $Backup\\.</span></span>

10. <span data-ttu-id="8fd0a-127">応答グループアプリケーションを実行するすべてのプールで、応答グループの構成をバックアップします。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-127">On every pool that runs the Response Group application, back up the Response Group configuration.</span></span> <span data-ttu-id="8fd0a-128">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-128">Do the following:</span></span>
    
    1.  <span data-ttu-id="8fd0a-129">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-129">At the command line, type:</span></span>
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        <span data-ttu-id="8fd0a-130">例:</span><span class="sxs-lookup"><span data-stu-id="8fd0a-130">For example:</span></span>
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. <span data-ttu-id="8fd0a-131">バックアップされた応答グループ構成ファイルを $Backup\\にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8fd0a-131">Copy the backed up Response Group configuration file to $Backup\\.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

