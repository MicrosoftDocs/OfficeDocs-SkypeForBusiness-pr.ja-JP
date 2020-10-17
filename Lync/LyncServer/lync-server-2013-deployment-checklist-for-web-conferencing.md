---
title: Lync Server 2013 web 会議の展開チェックリスト
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
ms.openlocfilehash: 8c20bd593e11f032ba0a0ed852a50b6d417fa604
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531094"
---
# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a><span data-ttu-id="4efc4-102">Lync Server 2013 での web 会議の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="4efc4-102">Deployment checklist for web conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4efc4-103">_**トピックの最終更新日:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="4efc4-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="4efc4-104">他の Lync Server 2013 コンポーネントの展開と同様に、web 会議を展開するには、トポロジビルダーを使用して、会議を組み込むトポロジを作成および公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4efc4-104">As with deployment of your other Lync Server 2013 components, deployment of web conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="4efc4-105">展開順序</span><span class="sxs-lookup"><span data-stu-id="4efc4-105">Deployment Sequence</span></span>

<span data-ttu-id="4efc4-106">最初のトポロジを展開するとき、または少なくとも1つのフロントエンドプールまたは Standard Edition サーバーを展開した後に、会議を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="4efc4-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="4efc4-107">会議展開プロセス</span><span class="sxs-lookup"><span data-stu-id="4efc4-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="4efc4-108">次の表に、既存のトポロジに会議を展開するために必要なステップの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="4efc4-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4efc4-109">フェーズ</span><span class="sxs-lookup"><span data-stu-id="4efc4-109">Phase</span></span></th>
<th><span data-ttu-id="4efc4-110">手順</span><span class="sxs-lookup"><span data-stu-id="4efc4-110">Steps</span></span></th>
<th><span data-ttu-id="4efc4-111">役割とグループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="4efc4-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="4efc4-112">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="4efc4-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4efc4-113"><strong>必要なハードウェアとソフトウェアのインストール</strong></span><span class="sxs-lookup"><span data-stu-id="4efc4-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="4efc4-114">電話会議は、フロントエンドプールおよび Standard Edition サーバーのフロントエンドサーバー上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="4efc4-114">Conferencing runs on Front End Servers in a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="4efc4-115">これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。</span><span class="sxs-lookup"><span data-stu-id="4efc4-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="4efc4-116">Lync Server 2013 は、Office Web Apps および Office Web Apps サーバーを使用して、PowerPoint プレゼンテーションの共有とレンダリングを処理します。</span><span class="sxs-lookup"><span data-stu-id="4efc4-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="4efc4-117">Office Web Apps サーバーのインストールと構成の詳細については、「 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps server および Lync Server 2013 との統合の構成</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4efc4-117">For information about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="4efc4-118">ローカルの Administrators グループのメンバーであるドメイン ユーザー</span><span class="sxs-lookup"><span data-stu-id="4efc4-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="4efc4-119">「サポート」のドキュメントの「 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013 でサポートされるハードウェア</a>」</span><span class="sxs-lookup"><span data-stu-id="4efc4-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="4efc4-120">「サポート」のドキュメントの「 <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート」</a></span><span class="sxs-lookup"><span data-stu-id="4efc4-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="4efc4-121">「計画」のドキュメントの「 <a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 のシステム要件を決定</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4efc4-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="4efc4-122">「計画」のドキュメントの「 <a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 でのアーカイブの技術要件</a>」。</span><span class="sxs-lookup"><span data-stu-id="4efc4-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4efc4-123"><strong>会議をサポートするために適切な内部トポロジの作成</strong></span><span class="sxs-lookup"><span data-stu-id="4efc4-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="4efc4-124">トポロジビルダーを実行して、トポロジに会議を追加した後、トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="4efc4-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="4efc4-125">トポロジを定義するには、ローカル ユーザー グループのメンバーであるアカウント</span><span class="sxs-lookup"><span data-stu-id="4efc4-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="4efc4-126">トポロジを公開するには、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーであり、Lync Server 2013 ファイルストアに対して使用されるファイル共有のフルコントロールアクセス許可 (読み取り/書き込み/変更) を持つアカウント (トポロジビルダーが必要な Dacl を構成できるようにするため)</span><span class="sxs-lookup"><span data-stu-id="4efc4-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="4efc4-127">「展開」のドキュメントの「 <a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Topology Builder In Lync Server 2013 のトポロジを定義および構成</a>します。</span><span class="sxs-lookup"><span data-stu-id="4efc4-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4efc4-128"><strong>会議ポリシーとサポートの構成</strong></span><span class="sxs-lookup"><span data-stu-id="4efc4-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="4efc4-129">Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、会議の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="4efc4-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="4efc4-130">RTCUniversalServerAdmins グループ (Windows PowerShell のみ) またはユーザーを [] または [CSAdministrator] の役割に割り当てる</span><span class="sxs-lookup"><span data-stu-id="4efc4-130">RTCUniversalServerAdmins group ( Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="4efc4-131">「操作」のドキュメントの「 <a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 の会議ポリシー」</a> 。</span><span class="sxs-lookup"><span data-stu-id="4efc4-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4efc4-132">Lync Server 2013 には、 **Maxuploadfilesizemb 枠** が含まれるようになりました。これにより、会議中にアップロードできるファイルのサイズが制限されます。</span><span class="sxs-lookup"><span data-stu-id="4efc4-132">Lync Server 2013 now includes the **MaxUploadFileSizeMb** setting, which limits the size of files that can be uploaded during a meeting.</span></span> <span data-ttu-id="4efc4-133">この設定の既定値は 500 MB です。</span><span class="sxs-lookup"><span data-stu-id="4efc4-133">The default value for this setting is 500 MB.</span></span> <span data-ttu-id="4efc4-134">**Get-csconferencingconfiguration**コマンドレットを使用して、 **Maxuploadfilesizemb 枠**を調整できます。</span><span class="sxs-lookup"><span data-stu-id="4efc4-134">You can adjust **MaxUploadFileSizeMb** using the **Set-CsConferencingConfiguration** cmdlet.</span></span>

<span data-ttu-id="4efc4-135">**Maxuploadfilesizemb 枠** は、Lync Web App のファイルのアップロード設定を制限しません。</span><span class="sxs-lookup"><span data-stu-id="4efc4-135">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="4efc4-136">Lync Web App のファイルサイズのアップロードの制限は約30MB に設定されており、IIS web.config ファイル:/Datacollabweb/Int \[ Ext \] /ハンドラ/web.config によって制御されます。Lync Web App のファイルサイズのアップロード制限を構成するには、 `maxRequestLength` `maxAllowedContentLength` 以下に示すように、web.config ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="4efc4-136">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="4efc4-137">各フロントエンドサーバーの web.config ファイルを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4efc4-137">You must update the web.config file for each Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

