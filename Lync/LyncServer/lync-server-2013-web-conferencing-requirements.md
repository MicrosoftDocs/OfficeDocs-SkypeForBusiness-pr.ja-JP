---
title: 'Lync Server 2013: Web 会議の要件'
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
ms.openlocfilehash: 56a030329f9d69a3748b2b76179c7a783b13cb0f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="98867-102">Lync Server 2013 での Web 会議の要件</span><span class="sxs-lookup"><span data-stu-id="98867-102">Web conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98867-103">_**トピックの最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="98867-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="98867-104">Web 会議を有効にすることにした場合、次のものを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98867-104">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="98867-105">Web 会議のコンテンツを格納するために使用するファイル ストアへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="98867-105">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="98867-106">会議中に PowerPoint ファイルを共有するために必要な Office Web Apps サーバーとの統合。</span><span class="sxs-lookup"><span data-stu-id="98867-106">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="98867-107">ファイル ストア</span><span class="sxs-lookup"><span data-stu-id="98867-107">File Store</span></span>

<span data-ttu-id="98867-108">Lync Server 2013 web 会議サービスは、会議中に共有されたコンテンツをファイルストアに保存します。</span><span class="sxs-lookup"><span data-stu-id="98867-108">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="98867-109">展開の一環として、Standard Edition サーバーまたは Enterprise Edition フロントエンドプールのいずれかのファイルストアとして使用するファイル共有を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98867-109">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="98867-110">既存のファイル共有をファイルストアに使用することも、ファイル共有を配置するファイルサーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="98867-110">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="98867-111">詳細については、「トポロジビルダー-フロントエンドのファイルストアを定義する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98867-111">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="98867-112">Web 会議サービスは、コンテンツを暗号化してからファイルストアに保存します。</span><span class="sxs-lookup"><span data-stu-id="98867-112">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="98867-113">Lync Server 2013 では、直接接続ストレージ (DAS) またはストレージエリアネットワーク (SAN) (分散ファイルシステム (DFS) や、ファイルストア用の独立したディスク (RAID) の冗長アレイ) のいずれかでのファイル共有の使用がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="98867-113">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="98867-114">Lync server 展開ウィザードによってファイル共有の場所が定義されると、Lync Server は次のようなファイル共有内にフォルダー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="98867-114">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="98867-115">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="98867-115">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="98867-116">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="98867-116">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="98867-117">1-1-1</span><span class="sxs-lookup"><span data-stu-id="98867-117">1-WebServices-1</span></span>
    
      - <span data-ttu-id="98867-118">によっ</span><span class="sxs-lookup"><span data-stu-id="98867-118">CollabContent</span></span>
    
      - <span data-ttu-id="98867-119">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="98867-119">CollabMetadata</span></span>
    
      - <span data-ttu-id="98867-120">DataConf</span><span class="sxs-lookup"><span data-stu-id="98867-120">DataConf</span></span>

<span data-ttu-id="98867-121">次に、Web 会議サービスによって、PowerPoint スライド、ホワイトボード、ポーリング、および添付ファイルなどのコンテンツが WebServices フォルダーにある CollabContent フォルダーおよび CollabMetadata フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="98867-121">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="98867-122">管理者は、ファイル共有に対するアクセス許可を設定して、必要な読み取りおよび書き込みのアクセスを RTC グループに付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98867-122">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="98867-p103">アクセス許可に関するエラーが発生する場合は、トポロジ ビルダーを開き、既存のトポロジをダウンロードして再公開してください。トポロジを公開することによって、ファイル共有のアクセス許可が検証され、必要に応じてリセットされます。</span><span class="sxs-lookup"><span data-stu-id="98867-p103">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology. Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="98867-125">次の設定項目を使用すると、会議用にコンテンツを格納する方法を管理できます。</span><span class="sxs-lookup"><span data-stu-id="98867-125">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="98867-126">**ContentGracePeriod**は、 [get-csconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)に配置されているため、会議が終了した後に web 会議のコンテンツをサーバー上に保持する時間を設定します。</span><span class="sxs-lookup"><span data-stu-id="98867-126">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="98867-127">**Maxcontentstoragemb**は、1 [](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)つの会議中にコンテンツの格納に使用できる最大ファイル領域を設定します。</span><span class="sxs-lookup"><span data-stu-id="98867-127">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="98867-128">**Maxuploadfilesizemb 枠**は、Lync Web App のファイルのアップロード設定を制限しません。</span><span class="sxs-lookup"><span data-stu-id="98867-128">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="98867-129">Lync Web App のファイルサイズのアップロードの制限は約30MB に設定されており、IIS web.config ファイルによって制御されます。/\[Datacollabweb/Int Ext\]/ハンドラー/web¥ config。Lync Web App のファイルサイズのアップロード制限を構成するに`maxRequestLength`は`maxAllowedContentLength` 、以下に示すように、web.config ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="98867-129">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="98867-130">各フロントエンドサーバーの web.config ファイルを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98867-130">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="98867-131">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="98867-131">Office Web Apps Server</span></span>

<span data-ttu-id="98867-132">これらの新機能を使用するには、管理者が Office Web Apps サーバーをインストールする必要があります。また、Office Web Apps サーバーと通信するように Lync Server 2013 を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98867-132">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="98867-133">このドキュメントでは、Office Web Apps サーバーを使用するように Lync Server 2013 を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98867-133">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="98867-134">このドキュメントでは、Office Web Apps サーバーのインストール方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98867-134">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="98867-135">インストールの詳細については、「Microsoft Office Web Apps <https://go.microsoft.com/fwlink/p/?linkid=257525>展開 web サイト」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98867-135">For installation details, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="98867-136">このガイドには、Office Web Apps サーバーの完全な前提条件に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="98867-136">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="98867-137">Office Web Apps サーバーは、Lync Server、SQL Server、またはその他のサーバーアプリケーションを実行していないスタンドアロンのコンピューターにインストールする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="98867-137">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="98867-138">(そのコンピューターに Office のバージョンがインストールされていない必要があります)。Office Web Apps サーバーを実行するために使用するすべてのコンピューターに、特定のソフトウェアセット (.NET Framework 4.5 および Windows PowerShell 3.0 を含む) がインストールされている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="98867-138">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="98867-139">これらの要件と、証明書とインターネットインフォメーションサービス (IIS) の構成の詳細については、「Microsoft Office Web Apps 展開 web <https://go.microsoft.com/fwlink/p/?linkid=257525>サイト」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98867-139">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="98867-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="98867-140">See Also</span></span>


[<span data-ttu-id="98867-141">Lync Server 2013 の web 会議の概要</span><span class="sxs-lookup"><span data-stu-id="98867-141">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="98867-142">Lync Server 2013 での web 会議の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="98867-142">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

