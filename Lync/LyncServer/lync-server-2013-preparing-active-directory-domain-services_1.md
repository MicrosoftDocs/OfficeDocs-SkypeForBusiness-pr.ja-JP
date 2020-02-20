---
title: 'Lync Server 2013: Active Directory ドメインサービスの準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b6e0e44367af86ea42099241ef3d9bbfa750133
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="654e8-102">Lync Server 2013 での Active Directory ドメインサービスの準備</span><span class="sxs-lookup"><span data-stu-id="654e8-102">Preparing Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="654e8-103">_**トピックの最終更新日:** 2014-02-19_</span><span class="sxs-lookup"><span data-stu-id="654e8-103">_**Topic Last Modified:** 2014-02-19_</span></span>

<span data-ttu-id="654e8-104">Lync Server 2013 では、Lync Server 展開ウィザードを使用して Active Directory ドメインサービスを準備することや、Lync Server 管理シェルコマンドレットを直接使用することができます。</span><span class="sxs-lookup"><span data-stu-id="654e8-104">In Lync Server 2013, you can use the Lync Server Deployment Wizard to prepare Active Directory Domain Services, or you can use Lync Server Management Shell cmdlets directly.</span></span> <span data-ttu-id="654e8-105">このトピックの後半の説明に従って、ldifde.exe コマンド ライン ツールをドメイン コントローラーで直接使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="654e8-105">You can also use the ldifde.exe command line tool directly on your domain controllers, as described later in this topic.</span></span>

<span data-ttu-id="654e8-106">Lync Server 展開ウィザードは、各 Active Directory 準備タスクをガイドします。</span><span class="sxs-lookup"><span data-stu-id="654e8-106">The Lync Server Deployment Wizard guides you through each Active Directory preparation task.</span></span> <span data-ttu-id="654e8-107">展開ウィザードは、Lync Server 管理シェルコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="654e8-107">The Deployment Wizard runs Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="654e8-108">このツールは、単一のドメインと単一のフォレストのトポロジ、またはその他の類似のトポロジの環境で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="654e8-108">This tool is useful for environments with a single domain and single forest topology, or other similar topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="654e8-109">ドメインコントローラーが32ビットバージョンの一部のオペレーティングシステムを実行するフォレストまたはドメインに Lync Server を展開することができます (詳細については、「 <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure 2013 の要件</A>」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="654e8-109">You can deploy Lync Server in a forest or domain where domain controllers run 32-bit versions of some operating systems (for details, see <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure requirements for Lync Server 2013</A>).</span></span> <span data-ttu-id="654e8-110">ただし、展開ウィザードと関連ファイルは64ビットであるため、Lync Server 展開ウィザードを使用して、これらの環境でスキーマ、フォレスト、およびドメインの準備を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="654e8-110">However, you cannot use the Lync Server Deployment Wizard to run schema, forest, and domain preparation in these environments because the Deployment Wizard and supporting files are 64-bit only.</span></span> <span data-ttu-id="654e8-111">代わりに、32 ビット ドメイン コントローラーで ldifde.exe ファイルおよび関連する .ldf ファイルを使用して、スキーマ、フォレスト、およびドメインを準備することができます。</span><span class="sxs-lookup"><span data-stu-id="654e8-111">Instead, you can use ldifde.exe and the associated .ldf files on a 32-bit domain controller to prepare the schema, forest and domain.</span></span> <span data-ttu-id="654e8-112">このトピックの後半の「コマンドレットと Ldifde.exe の使用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654e8-112">See the section “Using Cmdlets and Ldifde.exe” later in this topic.</span></span>



</div>

<span data-ttu-id="654e8-113">Lync Server 管理シェルコマンドレットを使用して、リモートで、またはより複雑な環境に対してタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="654e8-113">You can use Lync Server Management Shell cmdlets to run tasks remotely or for more complex environments.</span></span>

<div>

## <a name="active-directory-preparation-prerequisites"></a><span data-ttu-id="654e8-114">Active Directory の準備の前提条件</span><span class="sxs-lookup"><span data-stu-id="654e8-114">Active Directory Preparation Prerequisites</span></span>

<span data-ttu-id="654e8-115">Active Directory の準備手順は、Windows Server 2012、Windows Server 2012 R2、または Windows Server 2008 R2 SP1 (64 ビット) を実行しているコンピューターで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="654e8-115">You must run Active Directory preparation steps on a computer running Windows Server 2012, Windows Server 2012 R2, or Windows Server 2008 R2 with SP1 (64-bit).</span></span> <span data-ttu-id="654e8-116">Active Directory の準備には、Lync Server 管理シェルと OCSCore が必要です。</span><span class="sxs-lookup"><span data-stu-id="654e8-116">Active Directory preparation requires Lync Server Management Shell and OCSCore.</span></span>

<span data-ttu-id="654e8-117">Active Directory の準備作業を実行するには、以下のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="654e8-117">The following components are required to run Active Directory preparation tasks:</span></span>

  - <span data-ttu-id="654e8-118">Lync Server コアコンポーネント (OCScore)</span><span class="sxs-lookup"><span data-stu-id="654e8-118">Lync Server Core components (OCScore.msi)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="654e8-119">Lync Server 管理シェルを Active Directory の準備のために使用する予定の場合は、最初に Lync Server 展開ウィザードを実行して、コアコンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="654e8-119">If you plan to use Lync Server Management Shell for Active Directory preparation, you must run the Lync Server Deployment Wizard first to install Core components.</span></span>

    
    </div>

  - <span data-ttu-id="654e8-120">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="654e8-120">Microsoft .NET Framework 4.5</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="654e8-121">Windows Server 2012 および Windows Server 2012 R2 では、サーバーマネージャーを使用して .NET Framework 4.5 をインストールしてアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="654e8-121">For Windows Server 2012 and Windows Server 2012 R2, you install and activate .NET Framework 4.5 by using Server Manager.</span></span> <span data-ttu-id="654e8-122">詳細については、「 <A href="lync-server-2013-additional-software-requirements.md">Lync Server 2013 の追加ソフトウェア要件</A>」の「Microsoft .net Framework 4.5」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654e8-122">For details, see "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">Additional software requirements for Lync Server 2013</A>.</span></span> <span data-ttu-id="654e8-123">Windows Server&nbsp;2008&nbsp;R2 の場合は、Microsoft Web サイトから<A href="https://www.microsoft.com/download/details.aspx?id=30653">.net Framework 4.5</A>をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="654e8-123">For Windows Server&nbsp;2008&nbsp;R2, download and install <A href="https://www.microsoft.com/download/details.aspx?id=30653">.Net Framework 4.5</A> from the Microsoft web site.</span></span>

    
    </div>

  - <span data-ttu-id="654e8-124">リモート サーバー管理ツール (RSAT)</span><span class="sxs-lookup"><span data-stu-id="654e8-124">Remote Server Administration Tools (RSAT)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="654e8-125">Active Directory の準備手順をドメイン コントローラーではなくメンバー サーバーで実行する場合、RSAT ツールがいくつか必要です。</span><span class="sxs-lookup"><span data-stu-id="654e8-125">Some RSAT tools are required if you run Active Directory preparation steps on a member server rather than on a domain controller.</span></span> <span data-ttu-id="654e8-126">サーバーマネージャーの ad DS および AD LDS ツールノードから、AD DS スナップインおよびコマンドラインツールと、Windows PowerShell の Active Directory モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="654e8-126">Install the AD DS snap-ins and command-line tools and the Active Directory Module for Windows PowerShell from the AD DS and AD LDS Tools node in Server Manager.</span></span>

    
    </div>

  - <span data-ttu-id="654e8-127">Microsoft Visual C++ 11 (再頒布可能)</span><span class="sxs-lookup"><span data-stu-id="654e8-127">Microsoft Visual C++ 11 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="654e8-p107">コンピューターにまだインストールされていない場合、セットアップで、このソフトウェアをインストールするように求められます。 パッケージは提供されているため、個別に入手する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="654e8-p107">Setup prompts you to install this prerequisite if it is not already installed on the computer. The package is supplied for you, and you will not have to acquire it separately.</span></span>

    
    </div>

  - <span data-ttu-id="654e8-130">Windows PowerShell 3.0 (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="654e8-130">Windows PowerShell 3.0 (64-bit)</span></span>
    
    <span data-ttu-id="654e8-131">Windows Server 2012 および Windows Server 2012 R2 では、Windows PowerShell 3.0 が Lync Server 2013 インストールに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="654e8-131">For Windows Server 2012 and Windows Server 2012 R2, Windows PowerShell 3.0 should be included with your Lync Server 2013 installation.</span></span> <span data-ttu-id="654e8-132">Windows Server 2008 R2 の場合は、Windows PowerShell 3.0 にインストールするか、アップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="654e8-132">For Windows Server 2008 R2, you need to install or upgrade to Windows PowerShell 3.0.</span></span> <span data-ttu-id="654e8-133">詳細については、「 [Windows PowerShell 3.0 For Lync Server 2013 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654e8-133">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span></span>

</div>

<div>

## <a name="administrator-rights-and-roles"></a><span data-ttu-id="654e8-134">管理者権限と役割</span><span class="sxs-lookup"><span data-stu-id="654e8-134">Administrator Rights and Roles</span></span>

<span data-ttu-id="654e8-135">次の表に、Active Directory の各準備作業に必要となる管理者権限と役割を示します。</span><span class="sxs-lookup"><span data-stu-id="654e8-135">The following table shows the administrative rights and roles required for each Active Directory preparation task.</span></span>

### <a name="user-rights-required-for-active-directory-preparation"></a><span data-ttu-id="654e8-136">Active Directory の準備に必要な権限</span><span class="sxs-lookup"><span data-stu-id="654e8-136">User Rights Required for Active Directory Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="654e8-137">Procedure</span><span class="sxs-lookup"><span data-stu-id="654e8-137">Procedure</span></span></th>
<th><span data-ttu-id="654e8-138">権限または役割</span><span class="sxs-lookup"><span data-stu-id="654e8-138">Rights or roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="654e8-139">スキーマの準備</span><span class="sxs-lookup"><span data-stu-id="654e8-139">Schema preparation</span></span></p></td>
<td><p><span data-ttu-id="654e8-140">フォレストのルート ドメインの Schema Admins グループのメンバーで、スキーマ マスターにおける管理者権限を持つメンバー</span><span class="sxs-lookup"><span data-stu-id="654e8-140">Member of Schema Admins group for the forest root domain and administrator rights on the schema master</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654e8-141">フォレストの準備</span><span class="sxs-lookup"><span data-stu-id="654e8-141">Forest preparation</span></span></p></td>
<td><p><span data-ttu-id="654e8-142">フォレストの Enterprise Admins グループのメンバー</span><span class="sxs-lookup"><span data-stu-id="654e8-142">Member of Enterprise Admins group for the forest</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654e8-143">ドメインの準備</span><span class="sxs-lookup"><span data-stu-id="654e8-143">Domain preparation</span></span></p></td>
<td><p><span data-ttu-id="654e8-144">指定のドメインの Enterprise Admins グループまたは Domain Admins グループのメンバー</span><span class="sxs-lookup"><span data-stu-id="654e8-144">Member of Enterprise Admins or Domain Admins group for the specified domain</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a><span data-ttu-id="654e8-145">Active Directory の準備のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="654e8-145">Active Directory Preparation Cmdlets</span></span>

<span data-ttu-id="654e8-146">次の表では、AD DS の準備に使用される Lync Server 管理シェルコマンドレットを、Microsoft Office Communications Server 2007 R2 で AD DS を準備するために使用される Lcscmd.exe コマンドに比較しています。</span><span class="sxs-lookup"><span data-stu-id="654e8-146">The following table compares the Lync Server Management Shell cmdlets used to prepare AD DS to the LcsCmd commands used to prepare AD DS in Microsoft Office Communications Server 2007 R2.</span></span>

### <a name="cmdlets-compared-to-lcscmd"></a><span data-ttu-id="654e8-147">コマンドレットと LcsCmd の比較</span><span class="sxs-lookup"><span data-stu-id="654e8-147">Cmdlets Compared to LcsCmd</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="654e8-148">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="654e8-148">Cmdlets</span></span></th>
<th><span data-ttu-id="654e8-149">Log</span><span class="sxs-lookup"><span data-stu-id="654e8-149">LcsCmd</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="654e8-150">Install-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="654e8-150">Install-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="654e8-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span><span class="sxs-lookup"><span data-stu-id="654e8-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654e8-152">取得-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="654e8-152">Get-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="654e8-153">Lcscmd /forest /action:CheckSchemaPrepState</span><span class="sxs-lookup"><span data-stu-id="654e8-153">Lcscmd /forest /action:CheckSchemaPrepState</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654e8-154">Enable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="654e8-154">Enable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="654e8-155">Lcscmd /forest /action:ForestPrep</span><span class="sxs-lookup"><span data-stu-id="654e8-155">Lcscmd /forest /action:ForestPrep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654e8-156">無効-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="654e8-156">Disable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="654e8-157">Lcscmd /forest /action:ForestUnprep</span><span class="sxs-lookup"><span data-stu-id="654e8-157">Lcscmd /forest /action:ForestUnprep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654e8-158">取得-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="654e8-158">Get-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="654e8-159">Lcscmd /forest /action:CheckForestPrepState</span><span class="sxs-lookup"><span data-stu-id="654e8-159">Lcscmd /forest /action:CheckForestPrepState</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654e8-160">Enable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="654e8-160">Enable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="654e8-161">Lcscmd /domain /action:DomainPrep</span><span class="sxs-lookup"><span data-stu-id="654e8-161">Lcscmd /domain /action:DomainPrep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654e8-162">無効-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="654e8-162">Disable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="654e8-163">Lcscmd /domain /action: DomainUnprep</span><span class="sxs-lookup"><span data-stu-id="654e8-163">Lcscmd /domain /action: DomainUnprep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654e8-164">取得-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="654e8-164">Get-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="654e8-165">Lcscmd /domain /action:CheckDomainPrepState</span><span class="sxs-lookup"><span data-stu-id="654e8-165">Lcscmd /domain /action:CheckDomainPrepState</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a><span data-ttu-id="654e8-166">ロックダウンされた Active Directory の要件</span><span class="sxs-lookup"><span data-stu-id="654e8-166">Locked Down Active Directory Requirements</span></span>

<span data-ttu-id="654e8-167">組織において、アクセス許可の継承が無効になっているか、認証ユーザーのアクセス許可を無効にする必要がある場合は、ドメインの準備で追加のステップを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="654e8-167">If permissions inheritance is disabled or authenticated user permissions must be disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="654e8-168">詳細については、「 [Lync Server 2013 のロックダウンされた Active Directory ドメインサービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654e8-168">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

</div>

<div>

## <a name="custom-container-permissions"></a><span data-ttu-id="654e8-169">カスタム コンテナーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="654e8-169">Custom Container Permissions</span></span>

<span data-ttu-id="654e8-170">3 つの組み込みコンテナー (Users、Computers、および Domain Controllers) ではなく、カスタム コンテナーを使用している場合は、Authenticated Users グループにカスタム コンテナーの読み取りアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="654e8-170">If your organization uses custom containers instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the custom containers for the Authenticated Users group.</span></span> <span data-ttu-id="654e8-171">ドメインの準備には、コンテナーの読み取りアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="654e8-171">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="654e8-172">詳細については、「 [Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654e8-172">For details, see [Preparing domains for Lync Server 2013](lync-server-2013-preparing-domains.md).</span></span>

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a><span data-ttu-id="654e8-173">コマンドレットと Ldifde.exe の使用</span><span class="sxs-lookup"><span data-stu-id="654e8-173">Using Cmdlets and Ldifde.exe</span></span>

<span data-ttu-id="654e8-174">Lync Server 展開ウィザードおよび**Install-CsAdServerSchema**コマンドレットの**スキーマの準備**手順は、64ビットオペレーティングシステムを実行しているドメインコントローラー上の Active Directory スキーマを拡張します。</span><span class="sxs-lookup"><span data-stu-id="654e8-174">The **Prepare Schema** step in the Lync Server Deployment Wizard and the **Install-CsAdServerSchema** cmdlet extend the Active Directory schema on domain controllers running a 64-bit operating system.</span></span> <span data-ttu-id="654e8-175">32 ビット オペレーティング システムを実行しているドメイン コントローラーの Active Directory スキーマを拡張する必要がある場合は、メンバー サーバーからリモートで **Install-CsAdServerSchema** コマンドレットを実行します (推奨される方法)。</span><span class="sxs-lookup"><span data-stu-id="654e8-175">If you need to extend the Active Directory schema on a domain controller running a 32-bit operating system, you can run the **Install-CsAdServerSchema** cmdlet remotely from a member server (recommended approach).</span></span> <span data-ttu-id="654e8-176">ただし、スキーマの準備をドメイン コントローラーで直接実行する必要がある場合は、Ldifde.exe ツールを使用してスキーマ ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="654e8-176">If you need to run schema preparation directly on the domain controller, however, you can use the Ldifde.exe tool to import the schema files.</span></span> <span data-ttu-id="654e8-177">Ldifde.exe ツールは、ほとんどのバージョンの Windows オペレーティング システムに付属しています。</span><span class="sxs-lookup"><span data-stu-id="654e8-177">The Ldifde.exe tool comes with most versions of the Windows operating system.</span></span>

<span data-ttu-id="654e8-p112">Ldifde.exe を使用してスキーマ ファイルをインポートする場合、以前のバージョンから移行するのかクリーン インストールを実行するのかに関係なく、4 つのファイルすべてをインポートする必要があります。 これらのファイルは次の順序でインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="654e8-p112">If you use Ldifde.exe to import the schema files, you must import all four files, regardless of whether you are migrating from a previous version or performing a clean installation. You must import them in the following sequence:</span></span>

1.  <span data-ttu-id="654e8-180">ExternalSchema. .ldf</span><span class="sxs-lookup"><span data-stu-id="654e8-180">ExternalSchema.ldf</span></span>

2.  <span data-ttu-id="654e8-181">ServerSchema</span><span class="sxs-lookup"><span data-stu-id="654e8-181">ServerSchema.ldf</span></span>

3.  <span data-ttu-id="654e8-182">BackCompatSchema</span><span class="sxs-lookup"><span data-stu-id="654e8-182">BackCompatSchema.ldf</span></span>

4.  <span data-ttu-id="654e8-183">VersionSchema</span><span class="sxs-lookup"><span data-stu-id="654e8-183">VersionSchema.ldf</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="654e8-184">これらの 4 つの .ldf ファイルは、インストール メディアまたはダウンロードの \Support\Schema ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="654e8-184">The four .ldf files are located in \Support\Schema directory of your installation media or download.</span></span>



</div>

<span data-ttu-id="654e8-185">Ldifde.exe を使用してスキーマ マスターであるドメイン コントローラーにこれらの 4 つのスキーマ ファイルをインポートするには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="654e8-185">To use Ldifde.exe to import the four schema files on a domain controller that is the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

<span data-ttu-id="654e8-186">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="654e8-186">For example:</span></span>

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> <span data-ttu-id="654e8-p113">b パラメーターは、別のユーザーとしてログインしている場合のみ使用します。 必要なユーザー権限の詳細については、このトピックの前半の「管理者権限と役割」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654e8-p113">Use the b parameter only if you are logged in as a different user. For details about the required user rights, see the "Administrator Rights and Roles" section earlier in this topic.</span></span>



</div>

<span data-ttu-id="654e8-189">Ldifde.exe を使用してスキーマ マスターでないドメイン コントローラーにこれらの 4 つのスキーマ ファイルをインポートするには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="654e8-189">To use Ldifde.exe to import the four schema files on a domain controller that is not the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

<span data-ttu-id="654e8-190">Ldifde の使用の詳細については、Microsoft サポート技術情報の記事237677「LDIFDE を使用してディレクトリオブジェクトを Active Directory [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204)にインポートおよびエクスポートする」 () を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654e8-190">For details about using Ldifde, see Microsoft Knowledge Base article 237677, "Using LDIFDE to import and export directory objects to Active Directory," at [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="654e8-191">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="654e8-191">In This Section</span></span>

  - [<span data-ttu-id="654e8-192">Lync Server 2013 での Active Directory スキーマの準備</span><span class="sxs-lookup"><span data-stu-id="654e8-192">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)

  - [<span data-ttu-id="654e8-193">Lync Server 2013 のフォレストの準備</span><span class="sxs-lookup"><span data-stu-id="654e8-193">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)

  - [<span data-ttu-id="654e8-194">Lync Server 2013 のドメインの準備</span><span class="sxs-lookup"><span data-stu-id="654e8-194">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

