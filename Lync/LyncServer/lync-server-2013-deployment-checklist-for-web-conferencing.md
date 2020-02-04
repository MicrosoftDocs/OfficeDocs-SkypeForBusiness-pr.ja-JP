---
title: Lync Server 2013 web 会議用の展開チェックリスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 426f6419b2127a09dd3c758cdb7d6e418e6c4fc6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a><span data-ttu-id="69641-102">Lync Server 2013 の web 会議の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="69641-102">Deployment checklist for web conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69641-103">_**最終更新日:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="69641-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="69641-104">他の Lync Server 2013 コンポーネントの展開と同様に、web 会議の展開では、会議を組み込んだトポロジを作成して公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69641-104">As with deployment of your other Lync Server 2013 components, deployment of web conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="69641-105">展開シーケンス</span><span class="sxs-lookup"><span data-stu-id="69641-105">Deployment Sequence</span></span>

<span data-ttu-id="69641-106">最初のトポロジを展開するとき、または少なくとも1つのフロントエンドプールまたは Standard Edition サーバーを展開した後で、会議を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="69641-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="69641-107">会議展開プロセス</span><span class="sxs-lookup"><span data-stu-id="69641-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="69641-108">次の表は、既存のトポロジに会議を展開するために必要な手順の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="69641-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69641-109">段階</span><span class="sxs-lookup"><span data-stu-id="69641-109">Phase</span></span></th>
<th><span data-ttu-id="69641-110">手順</span><span class="sxs-lookup"><span data-stu-id="69641-110">Steps</span></span></th>
<th><span data-ttu-id="69641-111">役割とグループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="69641-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="69641-112">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="69641-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69641-113"><strong>必要なハードウェアとソフトウェアのインストール</strong></span><span class="sxs-lookup"><span data-stu-id="69641-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="69641-114">会議は、フロントエンドプールと Standard Edition サーバーで、フロントエンドサーバー上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="69641-114">Conferencing runs on Front End Servers in a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="69641-115">これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。</span><span class="sxs-lookup"><span data-stu-id="69641-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="69641-116">Lync Server 2013 は、PowerPoint プレゼンテーションの共有とレンダリングを処理するために、Office Web Apps と Office Web Apps サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="69641-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="69641-117">Office Web Apps サーバーのインストールと構成の詳細については、「 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps サーバーおよび Lync server 2013 との統合を構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69641-117">For information about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="69641-118">ローカル Administrators グループのメンバーであるドメイン ユーザー</span><span class="sxs-lookup"><span data-stu-id="69641-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="69641-119"><a href="lync-server-2013-supported-hardware.md">サポートされているドキュメントの Lync Server 2013 でサポートされているハードウェア</a></span><span class="sxs-lookup"><span data-stu-id="69641-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="69641-120">サポートドキュメントの<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート</a></span><span class="sxs-lookup"><span data-stu-id="69641-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="69641-121">計画ドキュメントの<a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 のシステム要件を決定</a>する。</span><span class="sxs-lookup"><span data-stu-id="69641-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="69641-122">計画ドキュメントの<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 でのアーカイブの技術要件</a>。</span><span class="sxs-lookup"><span data-stu-id="69641-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69641-123"><strong>会議をサポートするために適切な内部トポロジの作成</strong></span><span class="sxs-lookup"><span data-stu-id="69641-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="69641-124">トポロジに会議を追加するには、トポロジビルダーを実行して、トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="69641-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="69641-125">トポロジを定義するには、ローカル Users グループのメンバーであるアカウント</span><span class="sxs-lookup"><span data-stu-id="69641-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="69641-126">トポロジを公開するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであり、Lync Server 2013 ファイルストアで使用するフルコントロールのアクセス許可 (読み取り/書き込み/変更) を持つアカウント (トポロジビルダーが必要な Dacl を構成できるようにする)</span><span class="sxs-lookup"><span data-stu-id="69641-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="69641-127">展開ドキュメントで、「<a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">トポロジビルダーでの Lync Server 2013 のトポロジを定義して構成する」</a>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69641-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69641-128"><strong>会議のポリシーとサポートを構成する</strong></span><span class="sxs-lookup"><span data-stu-id="69641-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="69641-129">Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、会議の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="69641-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="69641-130">RTCUniversalServerAdmins group (Windows PowerShell のみ) またはユーザーを [] または [CSAdministrator] の役割に割り当てる</span><span class="sxs-lookup"><span data-stu-id="69641-130">RTCUniversalServerAdmins group ( Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="69641-131">運用ドキュメントの<a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 での会議ポリシー</a> 。</span><span class="sxs-lookup"><span data-stu-id="69641-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="69641-132">Lync Server 2013 には**Maxuploadfilesizemb 枠**の設定が含まれるようになりました。これにより、会議中にアップロードできるファイルのサイズが制限されます。</span><span class="sxs-lookup"><span data-stu-id="69641-132">Lync Server 2013 now includes the **MaxUploadFileSizeMb** setting, which limits the size of files that can be uploaded during a meeting.</span></span> <span data-ttu-id="69641-133">この設定の既定値は 500 MB です。</span><span class="sxs-lookup"><span data-stu-id="69641-133">The default value for this setting is 500 MB.</span></span> <span data-ttu-id="69641-134">**Set-CsConferencingConfiguration**コマンドレットを使用して、 **Maxuploadfilesizemb 飾り枠**を調整できます。</span><span class="sxs-lookup"><span data-stu-id="69641-134">You can adjust **MaxUploadFileSizeMb** using the **Set-CsConferencingConfiguration** cmdlet.</span></span>

<span data-ttu-id="69641-135">**Maxuploadfilesizemb 枠**は、Lync Web App のファイルアップロード設定を制限していません。</span><span class="sxs-lookup"><span data-stu-id="69641-135">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="69641-136">Lync Web App のファイルサイズのアップロードの上限は約30MB に設定されており、IIS の web.config ファイルで制御されます:/Datacollabweb/Int\[\]Lync Web App のファイルサイズのアップロード制限を構成するに`maxRequestLength`は`maxAllowedContentLength` 、以下に示すように、web.config ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="69641-136">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

<span data-ttu-id="69641-137">各フロントエンドサーバーの web.config ファイルを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69641-137">You must update the web.config file for each Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

