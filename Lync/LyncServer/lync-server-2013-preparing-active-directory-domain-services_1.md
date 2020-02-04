---
title: 'Lync Server 2013: Active Directory ドメイン サービスの準備'
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
ms.openlocfilehash: 8abab29930e8b09d0642c84f1e02026d4c554637
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="6f8fd-102">Lync Server 2013 での Active Directory ドメイン サービスの準備</span><span class="sxs-lookup"><span data-stu-id="6f8fd-102">Preparing Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f8fd-103">_**最終更新日:** 2014-02-19_</span><span class="sxs-lookup"><span data-stu-id="6f8fd-103">_**Topic Last Modified:** 2014-02-19_</span></span>

<span data-ttu-id="6f8fd-104">Lync server 2013 では、Lync Server Deployment ウィザードを使って Active Directory ドメインサービスを準備するか、Lync Server Management Shell コマンドレットを直接使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-104">In Lync Server 2013, you can use the Lync Server Deployment Wizard to prepare Active Directory Domain Services, or you can use Lync Server Management Shell cmdlets directly.</span></span> <span data-ttu-id="6f8fd-105">このトピックの後半で説明するように、ドメインコントローラーでは、ldifde コマンドラインツールを直接使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-105">You can also use the ldifde.exe command line tool directly on your domain controllers, as described later in this topic.</span></span>

<span data-ttu-id="6f8fd-106">Lync Server 展開ウィザードの指示に従って、各 Active Directory の準備タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-106">The Lync Server Deployment Wizard guides you through each Active Directory preparation task.</span></span> <span data-ttu-id="6f8fd-107">展開ウィザードでは、Lync Server 管理シェルコマンドレットが実行されます。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-107">The Deployment Wizard runs Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="6f8fd-108">このツールは、1つのドメインと1つのフォレストのトポロジ、または同様のトポロジを持つ環境で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-108">This tool is useful for environments with a single domain and single forest topology, or other similar topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6f8fd-109">Lync Server は、一部のオペレーティングシステムの32ビットバージョンを実行するフォレストまたはドメイン (詳細については、「 <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Lync server 2013 の Active Directory インフラストラクチャの要件</A>」を参照してください) に展開できます。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-109">You can deploy Lync Server in a forest or domain where domain controllers run 32-bit versions of some operating systems (for details, see <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure requirements for Lync Server 2013</A>).</span></span> <span data-ttu-id="6f8fd-110">ただし、展開ウィザードとサポートファイルは64ビットのみであるため、Lync Server 展開ウィザードを使って、これらの環境でスキーマ、フォレスト、ドメインの準備を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-110">However, you cannot use the Lync Server Deployment Wizard to run schema, forest, and domain preparation in these environments because the Deployment Wizard and supporting files are 64-bit only.</span></span> <span data-ttu-id="6f8fd-111">代わりに、32ビットドメインコントローラーで ldifde と関連付けられている .ldf ファイルを使用して、スキーマ、フォレスト、ドメインを準備することができます。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-111">Instead, you can use ldifde.exe and the associated .ldf files on a 32-bit domain controller to prepare the schema, forest and domain.</span></span> <span data-ttu-id="6f8fd-112">このトピックの後半の「コマンドレットと Ldifde の使用」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-112">See the section “Using Cmdlets and Ldifde.exe” later in this topic.</span></span>



</div>

<span data-ttu-id="6f8fd-113">Lync Server 管理シェルコマンドレットを使用して、リモートで、またはより複雑な環境でタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-113">You can use Lync Server Management Shell cmdlets to run tasks remotely or for more complex environments.</span></span>

<div>

## <a name="active-directory-preparation-prerequisites"></a><span data-ttu-id="6f8fd-114">Active Directory の準備の前提条件</span><span class="sxs-lookup"><span data-stu-id="6f8fd-114">Active Directory Preparation Prerequisites</span></span>

<span data-ttu-id="6f8fd-115">Windows Server 2012、Windows Server 2012 R2、または Windows Server 2008 R2 SP1 (64 ビット) を実行しているコンピューターで Active Directory の準備手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-115">You must run Active Directory preparation steps on a computer running Windows Server 2012, Windows Server 2012 R2, or Windows Server 2008 R2 with SP1 (64-bit).</span></span> <span data-ttu-id="6f8fd-116">Active Directory の準備には、Lync Server 管理シェルと OCSCore が必要です。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-116">Active Directory preparation requires Lync Server Management Shell and OCSCore.</span></span>

<span data-ttu-id="6f8fd-117">Active Directory の準備タスクを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-117">The following components are required to run Active Directory preparation tasks:</span></span>

  - <span data-ttu-id="6f8fd-118">Lync Server コアコンポーネント (OCScore)</span><span class="sxs-lookup"><span data-stu-id="6f8fd-118">Lync Server Core components (OCScore.msi)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6f8fd-119">Lync Server Management Shell を Active Directory の準備のために使用する予定がある場合は、最初に Lync Server 展開ウィザードを実行して、コアコンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-119">If you plan to use Lync Server Management Shell for Active Directory preparation, you must run the Lync Server Deployment Wizard first to install Core components.</span></span>

    
    </div>

  - <span data-ttu-id="6f8fd-120">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="6f8fd-120">Microsoft .NET Framework 4.5</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6f8fd-121">Windows Server 2012 および Windows Server 2012 R2 の場合、サーバーマネージャーを使用して .NET Framework 4.5 をインストールしてアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-121">For Windows Server 2012 and Windows Server 2012 R2, you install and activate .NET Framework 4.5 by using Server Manager.</span></span> <span data-ttu-id="6f8fd-122">詳細については、「 <A href="lync-server-2013-additional-software-requirements.md">Lync Server 2013 のその他のソフトウェア要件</A>」の「Microsoft .net Framework 4.5」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-122">For details, see "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">Additional software requirements for Lync Server 2013</A>.</span></span> <span data-ttu-id="6f8fd-123">Windows Server&nbsp;2008&nbsp;R2 の場合は、Microsoft Web サイトから<A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.net Framework 4.5</A>をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-123">For Windows Server&nbsp;2008&nbsp;R2, download and install <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.Net Framework 4.5</A> from the Microsoft web site.</span></span>

    
    </div>

  - <span data-ttu-id="6f8fd-124">リモートサーバー管理ツール (RSAT)</span><span class="sxs-lookup"><span data-stu-id="6f8fd-124">Remote Server Administration Tools (RSAT)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6f8fd-125">ドメインコントローラーではなく、メンバーサーバーで Active Directory の準備手順を実行する場合、一部の RSAT ツールが必要になります。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-125">Some RSAT tools are required if you run Active Directory preparation steps on a member server rather than on a domain controller.</span></span> <span data-ttu-id="6f8fd-126">サーバーマネージャーの [AD DS と AD LDS ツール] ノードから、AD DS スナップインおよびコマンドラインツールと、Windows PowerShell 用 Active Directory モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-126">Install the AD DS snap-ins and command-line tools and the Active Directory Module for Windows PowerShell from the AD DS and AD LDS Tools node in Server Manager.</span></span>

    
    </div>

  - <span data-ttu-id="6f8fd-127">Microsoft Visual C++ 11 再頒布可能</span><span class="sxs-lookup"><span data-stu-id="6f8fd-127">Microsoft Visual C++ 11 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6f8fd-128">この必須コンポーネントがまだコンピューターにインストールされていない場合は、セットアップによってインストールするように求められます。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-128">Setup prompts you to install this prerequisite if it is not already installed on the computer.</span></span> <span data-ttu-id="6f8fd-129">パッケージは提供されているため、別途入手する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-129">The package is supplied for you, and you will not have to acquire it separately.</span></span>

    
    </div>

  - <span data-ttu-id="6f8fd-130">Windows PowerShell 3.0 (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="6f8fd-130">Windows PowerShell 3.0 (64-bit)</span></span>
    
    <span data-ttu-id="6f8fd-131">Windows Server 2012 および Windows Server 2012 R2 の場合は、Lync Server 2013 のインストールに Windows PowerShell 3.0 が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-131">For Windows Server 2012 and Windows Server 2012 R2, Windows PowerShell 3.0 should be included with your Lync Server 2013 installation.</span></span> <span data-ttu-id="6f8fd-132">Windows Server 2008 R2 の場合は、Windows PowerShell 3.0 をインストールまたはアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-132">For Windows Server 2008 R2, you need to install or upgrade to Windows PowerShell 3.0.</span></span> <span data-ttu-id="6f8fd-133">詳細については、「 [Lync Server 2013 用に Windows PowerShell 3.0 をインストールする](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-133">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span></span>

</div>

<div>

## <a name="administrator-rights-and-roles"></a><span data-ttu-id="6f8fd-134">管理者の権限と役割</span><span class="sxs-lookup"><span data-stu-id="6f8fd-134">Administrator Rights and Roles</span></span>

<span data-ttu-id="6f8fd-135">次の表は、各 Active Directory 準備タスクに必要な管理者権限と役割を示しています。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-135">The following table shows the administrative rights and roles required for each Active Directory preparation task.</span></span>

### <a name="user-rights-required-for-active-directory-preparation"></a><span data-ttu-id="6f8fd-136">Active Directory の準備に必要なユーザー権利</span><span class="sxs-lookup"><span data-stu-id="6f8fd-136">User Rights Required for Active Directory Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f8fd-137">手順</span><span class="sxs-lookup"><span data-stu-id="6f8fd-137">Procedure</span></span></th>
<th><span data-ttu-id="6f8fd-138">権限または役割</span><span class="sxs-lookup"><span data-stu-id="6f8fd-138">Rights or roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f8fd-139">スキーマの準備</span><span class="sxs-lookup"><span data-stu-id="6f8fd-139">Schema preparation</span></span></p></td>
<td><p><span data-ttu-id="6f8fd-140">スキーママスターのフォレストルートドメインと管理者権限の Schema Admins グループのメンバー</span><span class="sxs-lookup"><span data-stu-id="6f8fd-140">Member of Schema Admins group for the forest root domain and administrator rights on the schema master</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f8fd-141">フォレストの準備</span><span class="sxs-lookup"><span data-stu-id="6f8fd-141">Forest preparation</span></span></p></td>
<td><p><span data-ttu-id="6f8fd-142">フォレストの Enterprise Admins グループのメンバー</span><span class="sxs-lookup"><span data-stu-id="6f8fd-142">Member of Enterprise Admins group for the forest</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f8fd-143">ドメインの準備</span><span class="sxs-lookup"><span data-stu-id="6f8fd-143">Domain preparation</span></span></p></td>
<td><p><span data-ttu-id="6f8fd-144">指定したドメインの Enterprise Admins または Domain Admins グループのメンバー</span><span class="sxs-lookup"><span data-stu-id="6f8fd-144">Member of Enterprise Admins or Domain Admins group for the specified domain</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a><span data-ttu-id="6f8fd-145">Active Directory の準備コマンドレット</span><span class="sxs-lookup"><span data-stu-id="6f8fd-145">Active Directory Preparation Cmdlets</span></span>

<span data-ttu-id="6f8fd-146">次の表では、AD DS を準備するために使用される Lync Server 管理シェルコマンドレットを、Microsoft Office Communications Server 2007 R2 で AD DS を準備するために使用される Lcscmd.exe コマンドに比較しています。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-146">The following table compares the Lync Server Management Shell cmdlets used to prepare AD DS to the LcsCmd commands used to prepare AD DS in Microsoft Office Communications Server 2007 R2.</span></span>

### <a name="cmdlets-compared-to-lcscmd"></a><span data-ttu-id="6f8fd-147">Lcscmd.exe と比較したコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6f8fd-147">Cmdlets Compared to LcsCmd</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f8fd-148">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6f8fd-148">Cmdlets</span></span></th>
<th><span data-ttu-id="6f8fd-149">Log</span><span class="sxs-lookup"><span data-stu-id="6f8fd-149">LcsCmd</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f8fd-150">Install-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="6f8fd-150">Install-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="6f8fd-151">Lcscmd.exe/forest/action: SchemaPrep/schematype: Server</span><span class="sxs-lookup"><span data-stu-id="6f8fd-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f8fd-152">CsAdServerSchema の入手</span><span class="sxs-lookup"><span data-stu-id="6f8fd-152">Get-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="6f8fd-153">Lcscmd.exe/forest/action: CheckSchemaPrepState</span><span class="sxs-lookup"><span data-stu-id="6f8fd-153">Lcscmd /forest /action:CheckSchemaPrepState</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f8fd-154">CsAdForest を有効にする</span><span class="sxs-lookup"><span data-stu-id="6f8fd-154">Enable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="6f8fd-155">Lcscmd.exe/forest/action: ForestPrep</span><span class="sxs-lookup"><span data-stu-id="6f8fd-155">Lcscmd /forest /action:ForestPrep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f8fd-156">CsAdForest を無効にする</span><span class="sxs-lookup"><span data-stu-id="6f8fd-156">Disable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="6f8fd-157">Lcscmd.exe/forest/action: ForestUnprep</span><span class="sxs-lookup"><span data-stu-id="6f8fd-157">Lcscmd /forest /action:ForestUnprep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f8fd-158">CsAdForest の入手</span><span class="sxs-lookup"><span data-stu-id="6f8fd-158">Get-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="6f8fd-159">Lcscmd.exe/forest/action: CheckForestPrepState</span><span class="sxs-lookup"><span data-stu-id="6f8fd-159">Lcscmd /forest /action:CheckForestPrepState</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f8fd-160">使用できるようにする-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="6f8fd-160">Enable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="6f8fd-161">Lcscmd.exe/domain/action: DomainPrep</span><span class="sxs-lookup"><span data-stu-id="6f8fd-161">Lcscmd /domain /action:DomainPrep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f8fd-162">無効-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="6f8fd-162">Disable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="6f8fd-163">Lcscmd.exe/domain/action: ドメイン準備の解除</span><span class="sxs-lookup"><span data-stu-id="6f8fd-163">Lcscmd /domain /action: DomainUnprep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f8fd-164">入手-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="6f8fd-164">Get-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="6f8fd-165">Lcscmd.exe/domain/action: CheckDomainPrepState</span><span class="sxs-lookup"><span data-stu-id="6f8fd-165">Lcscmd /domain /action:CheckDomainPrepState</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a><span data-ttu-id="6f8fd-166">ロックダウンされた Active Directory の要件</span><span class="sxs-lookup"><span data-stu-id="6f8fd-166">Locked Down Active Directory Requirements</span></span>

<span data-ttu-id="6f8fd-167">権限の継承が無効になっているか、認証されたユーザー権限を組織で無効にする必要がある場合は、ドメインの準備中に追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-167">If permissions inheritance is disabled or authenticated user permissions must be disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="6f8fd-168">詳細については、「 [Lync Server 2013 のロックダウン Active Directory ドメインサービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-168">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

</div>

<div>

## <a name="custom-container-permissions"></a><span data-ttu-id="6f8fd-169">カスタムコンテナーの権限</span><span class="sxs-lookup"><span data-stu-id="6f8fd-169">Custom Container Permissions</span></span>

<span data-ttu-id="6f8fd-170">組織で、3つの組み込みコンテナー (ユーザー、コンピューター、ドメインコントローラー) ではなくカスタムコンテナーを使用している場合は、認証されたユーザーグループのカスタムコンテナーへの読み取りアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-170">If your organization uses custom containers instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the custom containers for the Authenticated Users group.</span></span> <span data-ttu-id="6f8fd-171">ドメインの準備には、コンテナーへの読み取りアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-171">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="6f8fd-172">詳細については、「 [Lync Server 2013 用にドメインを準備する](lync-server-2013-preparing-domains.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-172">For details, see [Preparing domains for Lync Server 2013](lync-server-2013-preparing-domains.md).</span></span>

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a><span data-ttu-id="6f8fd-173">コマンドレットと Ldifde を使用する</span><span class="sxs-lookup"><span data-stu-id="6f8fd-173">Using Cmdlets and Ldifde.exe</span></span>

<span data-ttu-id="6f8fd-174">Lync Server 展開ウィザードと**インストール-CsAdServerSchema**コマンドレットの [**スキーマの準備**] 手順では、64ビットオペレーティングシステムを実行しているドメインコントローラー上の Active Directory スキーマを拡張します。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-174">The **Prepare Schema** step in the Lync Server Deployment Wizard and the **Install-CsAdServerSchema** cmdlet extend the Active Directory schema on domain controllers running a 64-bit operating system.</span></span> <span data-ttu-id="6f8fd-175">32ビットオペレーティングシステムを実行しているドメインコントローラーで Active Directory スキーマを拡張する必要がある場合は、メンバーサーバーからリモートで**CsAdServerSchema**コマンドレットをリモートで実行できます (推奨される方法)。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-175">If you need to extend the Active Directory schema on a domain controller running a 32-bit operating system, you can run the **Install-CsAdServerSchema** cmdlet remotely from a member server (recommended approach).</span></span> <span data-ttu-id="6f8fd-176">ただし、スキーマ準備を直接ドメインコントローラーで実行する必要がある場合は、Ldifde ツールを使用してスキーマファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-176">If you need to run schema preparation directly on the domain controller, however, you can use the Ldifde.exe tool to import the schema files.</span></span> <span data-ttu-id="6f8fd-177">Ldifde ツールには、ほとんどのバージョンの Windows オペレーティングシステムが付属しています。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-177">The Ldifde.exe tool comes with most versions of the Windows operating system.</span></span>

<span data-ttu-id="6f8fd-178">スキーマファイルをインポートするために Ldifde を使用している場合は、以前のバージョンから移行するか、またはクリーンインストールを実行するかに関係なく、4つのファイルをすべてインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-178">If you use Ldifde.exe to import the schema files, you must import all four files, regardless of whether you are migrating from a previous version or performing a clean installation.</span></span> <span data-ttu-id="6f8fd-179">次の順序でインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-179">You must import them in the following sequence:</span></span>

1.  <span data-ttu-id="6f8fd-180">ExternalSchema. .ldf</span><span class="sxs-lookup"><span data-stu-id="6f8fd-180">ExternalSchema.ldf</span></span>

2.  <span data-ttu-id="6f8fd-181">ServerSchema. .ldf</span><span class="sxs-lookup"><span data-stu-id="6f8fd-181">ServerSchema.ldf</span></span>

3.  <span data-ttu-id="6f8fd-182">BackCompatSchema</span><span class="sxs-lookup"><span data-stu-id="6f8fd-182">BackCompatSchema.ldf</span></span>

4.  <span data-ttu-id="6f8fd-183">VersionSchema</span><span class="sxs-lookup"><span data-stu-id="6f8fd-183">VersionSchema.ldf</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6f8fd-184">4つの .ldf ファイルは、インストールメディアまたはダウンロードの \Support\Schema ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-184">The four .ldf files are located in \Support\Schema directory of your installation media or download.</span></span>



</div>

<span data-ttu-id="6f8fd-185">Ldifde を使用して、スキーママスターであるドメインコントローラーに4つのスキーマファイルをインポートするには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-185">To use Ldifde.exe to import the four schema files on a domain controller that is the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

<span data-ttu-id="6f8fd-186">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-186">For example:</span></span>

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> <span data-ttu-id="6f8fd-187">別のユーザーとしてログインしている場合にのみ b パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-187">Use the b parameter only if you are logged in as a different user.</span></span> <span data-ttu-id="6f8fd-188">必要なユーザー権限について詳しくは、このトピックの「管理者の権限と役割」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-188">For details about the required user rights, see the "Administrator Rights and Roles" section earlier in this topic.</span></span>



</div>

<span data-ttu-id="6f8fd-189">Ldifde を使用して、スキーママスターではないドメインコントローラーに4つのスキーマファイルをインポートするには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-189">To use Ldifde.exe to import the four schema files on a domain controller that is not the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

<span data-ttu-id="6f8fd-190">Ldifde の使い方の詳細については、「Microsoft サポート技術情報の記事237677、「LDIFDE を使用してディレクトリオブジェクトを[http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)Active directory にインポートおよびエクスポートする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f8fd-190">For details about using Ldifde, see Microsoft Knowledge Base article 237677, "Using LDIFDE to import and export directory objects to Active Directory," at [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6f8fd-191">このセクション中</span><span class="sxs-lookup"><span data-stu-id="6f8fd-191">In This Section</span></span>

  - [<span data-ttu-id="6f8fd-192">Lync Server 2013 での Active Directory スキーマの準備</span><span class="sxs-lookup"><span data-stu-id="6f8fd-192">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)

  - [<span data-ttu-id="6f8fd-193">Lync Server 2013 でのフォレストの準備</span><span class="sxs-lookup"><span data-stu-id="6f8fd-193">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)

  - [<span data-ttu-id="6f8fd-194">Lync Server 2013 のドメインの準備</span><span class="sxs-lookup"><span data-stu-id="6f8fd-194">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

