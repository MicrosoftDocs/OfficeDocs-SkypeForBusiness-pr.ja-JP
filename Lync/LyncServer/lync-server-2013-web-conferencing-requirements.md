---
title: 'Lync Server 2013: Web 会議の要件'
description: 'Lync Server 2013: Web 会議の要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c1fce932d3cc02ac29364d53d04ec336693e43b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576393"
---
# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="fa3e9-103">Lync Server 2013 での Web 会議の要件</span><span class="sxs-lookup"><span data-stu-id="fa3e9-103">Web conferencing requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa3e9-104">_**トピックの最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="fa3e9-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="fa3e9-105">Web 会議を有効にすることにした場合、次のものを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-105">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="fa3e9-106">Web 会議のコンテンツを格納するために使用するファイル ストアへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-106">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="fa3e9-107">会議中に PowerPoint ファイルを共有するために必要な Office Web Apps サーバーとの統合。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-107">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="fa3e9-108">ファイル ストア</span><span class="sxs-lookup"><span data-stu-id="fa3e9-108">File Store</span></span>

<span data-ttu-id="fa3e9-109">Lync Server 2013 web 会議サービスは、会議中に共有されたコンテンツをファイルストアに保存します。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-109">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="fa3e9-110">展開の一環として、Standard Edition サーバーまたは Enterprise Edition フロントエンドプールのいずれかのファイルストアとして使用するファイル共有を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-110">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="fa3e9-111">既存のファイル共有をファイルストアに使用することも、ファイル共有を配置するファイルサーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-111">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="fa3e9-112">詳細については、「トポロジビルダー-フロントエンドのファイルストアを定義する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-112">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="fa3e9-113">Web 会議サービスは、コンテンツを暗号化してからファイルストアに保存します。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-113">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="fa3e9-114">Lync Server 2013 では、直接接続ストレージ (DAS) またはストレージエリアネットワーク (SAN) (分散ファイルシステム (DFS) や、ファイルストア用の独立したディスク (RAID) の冗長アレイ) のいずれかでのファイル共有の使用がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-114">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="fa3e9-115">Lync server 展開ウィザードによってファイル共有の場所が定義されると、Lync Server は次のようなファイル共有内にフォルダー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-115">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="fa3e9-116">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="fa3e9-116">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="fa3e9-117">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="fa3e9-117">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="fa3e9-118">1-1-1</span><span class="sxs-lookup"><span data-stu-id="fa3e9-118">1-WebServices-1</span></span>
    
      - <span data-ttu-id="fa3e9-119">によっ</span><span class="sxs-lookup"><span data-stu-id="fa3e9-119">CollabContent</span></span>
    
      - <span data-ttu-id="fa3e9-120">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="fa3e9-120">CollabMetadata</span></span>
    
      - <span data-ttu-id="fa3e9-121">DataConf</span><span class="sxs-lookup"><span data-stu-id="fa3e9-121">DataConf</span></span>

<span data-ttu-id="fa3e9-122">次に、Web 会議サービスによって、PowerPoint スライド、ホワイトボード、ポーリング、および添付ファイルなどのコンテンツが WebServices フォルダーにある CollabContent フォルダーおよび CollabMetadata フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-122">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="fa3e9-123">管理者は、ファイル共有に対するアクセス許可を設定して、必要な読み取りおよび書き込みのアクセスを RTC グループに付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-123">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="fa3e9-p103">アクセス許可に関するエラーが発生する場合は、トポロジ ビルダーを開き、既存のトポロジをダウンロードして再公開してください。トポロジを公開することによって、ファイル共有のアクセス許可が検証され、必要に応じてリセットされます。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-p103">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology. Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="fa3e9-126">次の設定項目を使用すると、会議用にコンテンツを格納する方法を管理できます。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-126">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="fa3e9-127">**ContentGracePeriod**は、 [get-csconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)に配置されているため、会議が終了した後に web 会議のコンテンツをサーバー上に保持する時間を設定します。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-127">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="fa3e9-128">**Maxcontentstoragemb**は、1 [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)つの会議中にコンテンツの格納に使用できる最大ファイル領域を設定します。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-128">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="fa3e9-129">**Maxuploadfilesizemb 枠** は、Lync Web App のファイルのアップロード設定を制限しません。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-129">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="fa3e9-130">Lync Web App のファイルサイズのアップロードの制限は約30MB に設定されており、IIS web.config ファイル:/Datacollabweb/Int \[ Ext \] /ハンドラ/web.config によって制御されます。Lync Web App のファイルサイズのアップロード制限を構成するには、 `maxRequestLength` `maxAllowedContentLength` 以下に示すように、web.config ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-130">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by Lync Web App client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for Lync Web App upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

<span data-ttu-id="fa3e9-131">各フロントエンドサーバーの web.config ファイルを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-131">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="fa3e9-132">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="fa3e9-132">Office Web Apps Server</span></span>

<span data-ttu-id="fa3e9-133">これらの新機能を使用するには、管理者が Office Web Apps サーバーをインストールする必要があります。また、Office Web Apps サーバーと通信するように Lync Server 2013 を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-133">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="fa3e9-134">このドキュメントでは、Office Web Apps サーバーを使用するように Lync Server 2013 を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-134">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="fa3e9-135">このドキュメントでは、Office Web Apps サーバーのインストール方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-135">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="fa3e9-136">インストールの詳細については、「Microsoft Office Web Apps 展開 web サイト」を参照してください <https://go.microsoft.com/fwlink/p/?linkid=257525> 。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-136">For installation details, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="fa3e9-137">このガイドには、Office Web Apps サーバーの完全な前提条件に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-137">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="fa3e9-138">Office Web Apps サーバーは、Lync Server、SQL Server、またはその他のサーバーアプリケーションを実行していないスタンドアロンのコンピューターにインストールする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-138">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="fa3e9-139">(そのコンピューターに Office のバージョンがインストールされていない必要があります)。Office Web Apps サーバーを実行するために使用するすべてのコンピューターに、特定のソフトウェアセット (.NET Framework 4.5 および Windows PowerShell 3.0 を含む) がインストールされている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-139">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="fa3e9-140">これらの要件と、証明書とインターネットインフォメーションサービス (IIS) の構成の詳細については、「Microsoft Office Web Apps 展開 web サイト」を参照して <https://go.microsoft.com/fwlink/p/?linkid=257525> ください。</span><span class="sxs-lookup"><span data-stu-id="fa3e9-140">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fa3e9-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa3e9-141">See Also</span></span>


[<span data-ttu-id="fa3e9-142">Lync Server 2013 の web 会議の概要</span><span class="sxs-lookup"><span data-stu-id="fa3e9-142">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="fa3e9-143">Lync Server 2013 での web 会議の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="fa3e9-143">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

