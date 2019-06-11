---
title: 'Lync Server 2013: Web 会議の要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dddfd7c2fdfe6cbcefcca7533e93c3c377cceea8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="d7244-102">Lync Server 2013 での Web 会議の要件</span><span class="sxs-lookup"><span data-stu-id="d7244-102">Web conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7244-103">_**最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="d7244-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="d7244-104">Web 会議を有効にすることにした場合、次のものを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7244-104">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="d7244-105">Web 会議のコンテンツを格納するために使用するファイル ストアへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="d7244-105">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="d7244-106">会議中に PowerPoint ファイルを共有するために必要な Office Web Apps サーバーとの統合。</span><span class="sxs-lookup"><span data-stu-id="d7244-106">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="d7244-107">ファイル ストア</span><span class="sxs-lookup"><span data-stu-id="d7244-107">File Store</span></span>

<span data-ttu-id="d7244-108">Lync Server 2013 web 会議サービスでは、会議中に共有されたコンテンツをファイルストアに保存します。</span><span class="sxs-lookup"><span data-stu-id="d7244-108">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="d7244-109">展開の一環として、Standard Edition server または Enterprise Edition のフロントエンドプールのファイルストアとして使用するファイル共有を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7244-109">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="d7244-110">ファイルストアには既存のファイル共有を使用できます。また、ファイル共有が配置されているファイルサーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7244-110">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="d7244-111">詳細については、「トポロジビルダー–フロントエンド用のファイルストアの定義」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7244-111">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="d7244-112">Web 会議サービスによって、コンテンツがファイルストアに保存される前に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="d7244-112">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="d7244-113">Lync Server 2013 は、直接接続型ストレージ (DAS) またはストレージエリアネットワーク (SAN) 上でのファイル共有の使用をサポートします。これには、分散ファイルシステム (DFS) や、ファイルストアの独立したディスク (RAID) の冗長配列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d7244-113">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="d7244-114">Lync Server 展開ウィザードでファイル共有の場所が定義されると、Lync Server によって、次のようなファイル共有内にフォルダー構造が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d7244-114">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="d7244-115">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="d7244-115">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="d7244-116">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="d7244-116">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="d7244-117">1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="d7244-117">1-WebServices-1</span></span>
    
      - <span data-ttu-id="d7244-118">CollabContent</span><span class="sxs-lookup"><span data-stu-id="d7244-118">CollabContent</span></span>
    
      - <span data-ttu-id="d7244-119">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="d7244-119">CollabMetadata</span></span>
    
      - <span data-ttu-id="d7244-120">DataConf</span><span class="sxs-lookup"><span data-stu-id="d7244-120">DataConf</span></span>

<span data-ttu-id="d7244-121">次に、Web 会議サービスによって、PowerPoint スライド、ホワイトボード、ポーリング、および添付ファイルなどのコンテンツが WebServices フォルダーにある CollabContent フォルダーおよび CollabMetadata フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d7244-121">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="d7244-122">管理者は、ファイル共有に対するアクセス許可を設定して、RTC グループが必要な読み取りおよび書き込みアクセス権を持つようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7244-122">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="d7244-123">権限に関するエラーが発生した場合は、トポロジビルダーを開き、既存のトポロジをダウンロードして再公開します。</span><span class="sxs-lookup"><span data-stu-id="d7244-123">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology.</span></span> <span data-ttu-id="d7244-124">トポロジを公開することで、ファイル共有のアクセス許可を確認し、必要に応じてリセットできます。</span><span class="sxs-lookup"><span data-stu-id="d7244-124">Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="d7244-125">会議のコンテンツの保存方法を管理するには、次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7244-125">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="d7244-126">**ContentGracePeriod**は、 [CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)で指定された web 会議コンテンツが、会議終了後にサーバー上に残る長さを設定します。</span><span class="sxs-lookup"><span data-stu-id="d7244-126">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="d7244-127">**Maxcontentstoragemb**は、1 [](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)回の会議中にコンテンツの保存に使用できるファイル領域の最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="d7244-127">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="d7244-128">**Maxuploadfilesizemb 枠**は、Lync Web App のファイルアップロード設定を制限していません。</span><span class="sxs-lookup"><span data-stu-id="d7244-128">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="d7244-129">Lync Web App のファイルサイズのアップロードの上限は約30MB に設定されており、IIS の web.config ファイルで制御されます:/Datacollabweb/Int\[\]Lync Web App のファイルサイズのアップロード制限を構成するに`maxRequestLength`は`maxAllowedContentLength` 、以下に示すように、web.config ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7244-129">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="d7244-130">各フロントエンドサーバーの web.config ファイルを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7244-130">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="d7244-131">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="d7244-131">Office Web Apps Server</span></span>

<span data-ttu-id="d7244-132">これらの新機能を使用するには、管理者が Office Web Apps サーバーをインストールしている必要があります。また、管理者は、Office Web Apps サーバーと通信するように Lync Server 2013 を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7244-132">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="d7244-133">このドキュメントでは、Lync Server 2013 を Office Web Apps サーバーと連携するように構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7244-133">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="d7244-134">このドキュメントでは、Office Web Apps サーバーをインストールする方法について説明していません。</span><span class="sxs-lookup"><span data-stu-id="d7244-134">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="d7244-135">インストールの詳細については、の Microsoft Office Web Apps <http://go.microsoft.com/fwlink/p/?linkid=257525>展開 web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7244-135">For installation details, see the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="d7244-136">このガイドには、Office Web Apps サーバーの必要な情報がすべて記載されています。</span><span class="sxs-lookup"><span data-stu-id="d7244-136">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="d7244-137">Office Web Apps サーバーは、Lync Server、SQL Server、またはその他のサーバーアプリケーションを実行していないスタンドアロンコンピューターにインストールする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d7244-137">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="d7244-138">(そのコンピューターに Office のバージョンがインストールされていない必要があります)。Office Web Apps サーバーを実行するために使用されるコンピューターには、特定のソフトウェアセット (.NET Framework 4.5 および Windows PowerShell 3.0 を含む) がインストールされている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="d7244-138">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="d7244-139">これらの要件と、証明書とインターネットインフォメーションサービス (IIS) を構成する方法については、Microsoft Office Web Apps 展開の web <http://go.microsoft.com/fwlink/p/?linkid=257525>サイトで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="d7244-139">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d7244-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7244-140">See Also</span></span>


[<span data-ttu-id="d7244-141">Lync Server 2013 での web 会議の概要</span><span class="sxs-lookup"><span data-stu-id="d7244-141">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="d7244-142">Lync Server 2013 の web 会議の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="d7244-142">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

