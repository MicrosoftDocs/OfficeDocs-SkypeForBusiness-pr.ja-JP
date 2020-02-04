---
title: 'Lync Server 2013: 応答グループ構成のアクセス許可と前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcf10a61ed5285fe5cfc907c2624a14112d96eae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a><span data-ttu-id="867b3-102">Lync Server 2013 の応答グループ構成のアクセス許可と前提条件</span><span class="sxs-lookup"><span data-stu-id="867b3-102">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="867b3-103">_**最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="867b3-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="867b3-104">応答グループは、エンタープライズの音声通話管理機能です。</span><span class="sxs-lookup"><span data-stu-id="867b3-104">Response Group is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="867b3-105">このトピックでは、応答グループを構成し、構成タスクを実行するために必要な管理資格情報とアクセス許可を構成するために必要な準備について説明します。</span><span class="sxs-lookup"><span data-stu-id="867b3-105">This topic describes what you need to have in place before you can configure Response Group and the administrative credentials and permissions you need to perform configuration tasks.</span></span>

<span data-ttu-id="867b3-106">このセクションでは、回答グループに関連する計画ドキュメントを読み取っていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="867b3-106">This section assumes that you have read the planning documentation related to Response Group.</span></span> <span data-ttu-id="867b3-107">詳細については、計画ドキュメントの「 [Lync Server 2013 での通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="867b3-107">For details, see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) in the Planning documentation.</span></span>

<div>

## <a name="configuration-tools-and-administrative-roles"></a><span data-ttu-id="867b3-108">構成ツールと管理者ロール</span><span class="sxs-lookup"><span data-stu-id="867b3-108">Configuration Tools and Administrative Roles</span></span>

<span data-ttu-id="867b3-109">応答グループを構成するには、次の管理ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="867b3-109">You can use the following administrative tools to configure Response Group:</span></span>

  - <span data-ttu-id="867b3-110">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="867b3-110">Lync Server Control Panel</span></span>

  - <span data-ttu-id="867b3-111">応答グループ構成ツール</span><span class="sxs-lookup"><span data-stu-id="867b3-111">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="867b3-112">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="867b3-112">Lync Server Management Shell</span></span>

<span data-ttu-id="867b3-113">応答グループを構成するには、次の管理役割のうち 1 つ以上のメンバーになる必要があります。</span><span class="sxs-lookup"><span data-stu-id="867b3-113">To configure response groups, you must be a member of at least one of the following administrative roles:</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="867b3-114"><strong>Active Directory セキュリティ グループ (1)</strong></span><span class="sxs-lookup"><span data-stu-id="867b3-114"><strong>Active Directory Security Group (1)</strong></span></span></p></td>
<td><p><span data-ttu-id="867b3-115">ワークフローの作成</span><span class="sxs-lookup"><span data-stu-id="867b3-115">Create Workflow</span></span></p></td>
<td><p><span data-ttu-id="867b3-116">マネージャーの割り当て</span><span class="sxs-lookup"><span data-stu-id="867b3-116">Assign Manager</span></span></p></td>
<td><p><span data-ttu-id="867b3-117">エージェント、キューの作成/割り当て</span><span class="sxs-lookup"><span data-stu-id="867b3-117">Create /assign agents, queues</span></span></p></td>
<td><p><span data-ttu-id="867b3-118">休日と営業時間の作成/管理</span><span class="sxs-lookup"><span data-stu-id="867b3-118">Create / manage holiday and business hours</span></span></p></td>
<td><p><span data-ttu-id="867b3-119">ワークフローのアクティブ化/非アクティブ化</span><span class="sxs-lookup"><span data-stu-id="867b3-119">Activate / deactivate workflow</span></span></p></td>
<td><p><span data-ttu-id="867b3-120">ワークフローの構成 (IVR またはハント グループ)</span><span class="sxs-lookup"><span data-stu-id="867b3-120">Configure workflow (IVR or Hunt Group)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="867b3-121"><strong>CsResponseGroupAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="867b3-121"><strong>CsResponseGroupAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="867b3-122">√</span><span class="sxs-lookup"><span data-stu-id="867b3-122">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-123">√</span><span class="sxs-lookup"><span data-stu-id="867b3-123">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-124">√</span><span class="sxs-lookup"><span data-stu-id="867b3-124">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-125">√</span><span class="sxs-lookup"><span data-stu-id="867b3-125">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-126">√</span><span class="sxs-lookup"><span data-stu-id="867b3-126">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-127">√</span><span class="sxs-lookup"><span data-stu-id="867b3-127">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="867b3-128"><strong>CsResponseGroupManager</strong></span><span class="sxs-lookup"><span data-stu-id="867b3-128"><strong>CsResponseGroupManager</strong></span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="867b3-129">√(2)</span><span class="sxs-lookup"><span data-stu-id="867b3-129">√(2)</span></span></p></td>
<td><p><span data-ttu-id="867b3-130">√(3)</span><span class="sxs-lookup"><span data-stu-id="867b3-130">√(3)</span></span></p></td>
<td><p><span data-ttu-id="867b3-131">√(3)</span><span class="sxs-lookup"><span data-stu-id="867b3-131">√(3)</span></span></p></td>
<td><p><span data-ttu-id="867b3-132">√(3)</span><span class="sxs-lookup"><span data-stu-id="867b3-132">√(3)</span></span></p></td>
<td><p><span data-ttu-id="867b3-133">√(3)</span><span class="sxs-lookup"><span data-stu-id="867b3-133">√(3)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="867b3-134"><strong>CsVoiceAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="867b3-134"><strong>CsVoiceAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="867b3-135">√</span><span class="sxs-lookup"><span data-stu-id="867b3-135">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-136">√</span><span class="sxs-lookup"><span data-stu-id="867b3-136">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-137">√</span><span class="sxs-lookup"><span data-stu-id="867b3-137">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-138">√</span><span class="sxs-lookup"><span data-stu-id="867b3-138">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-139">√</span><span class="sxs-lookup"><span data-stu-id="867b3-139">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-140">√</span><span class="sxs-lookup"><span data-stu-id="867b3-140">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="867b3-141"><strong>CsServerAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="867b3-141"><strong>CsServerAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="867b3-142">√</span><span class="sxs-lookup"><span data-stu-id="867b3-142">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-143">√</span><span class="sxs-lookup"><span data-stu-id="867b3-143">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-144">√</span><span class="sxs-lookup"><span data-stu-id="867b3-144">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-145">√</span><span class="sxs-lookup"><span data-stu-id="867b3-145">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-146">√</span><span class="sxs-lookup"><span data-stu-id="867b3-146">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-147">√</span><span class="sxs-lookup"><span data-stu-id="867b3-147">√</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="867b3-148"><strong>CsAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="867b3-148"><strong>CsAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="867b3-149">√</span><span class="sxs-lookup"><span data-stu-id="867b3-149">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-150">√</span><span class="sxs-lookup"><span data-stu-id="867b3-150">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-151">√</span><span class="sxs-lookup"><span data-stu-id="867b3-151">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-152">√</span><span class="sxs-lookup"><span data-stu-id="867b3-152">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-153">√</span><span class="sxs-lookup"><span data-stu-id="867b3-153">√</span></span></p></td>
<td><p><span data-ttu-id="867b3-154">√</span><span class="sxs-lookup"><span data-stu-id="867b3-154">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="867b3-155"><strong>CsViewOnlyAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="867b3-155"><strong>CsViewOnlyAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="867b3-156">√(4)</span><span class="sxs-lookup"><span data-stu-id="867b3-156">√(4)</span></span></p></td>
<td><p><span data-ttu-id="867b3-157">√(4)</span><span class="sxs-lookup"><span data-stu-id="867b3-157">√(4)</span></span></p></td>
<td><p><span data-ttu-id="867b3-158">√(4)</span><span class="sxs-lookup"><span data-stu-id="867b3-158">√(4)</span></span></p></td>
<td><p><span data-ttu-id="867b3-159">√(4)</span><span class="sxs-lookup"><span data-stu-id="867b3-159">√(4)</span></span></p></td>
<td><p><span data-ttu-id="867b3-160">√(4)</span><span class="sxs-lookup"><span data-stu-id="867b3-160">√(4)</span></span></p></td>
<td><p><span data-ttu-id="867b3-161">√(4)</span><span class="sxs-lookup"><span data-stu-id="867b3-161">√(4)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="867b3-162"><STRONG>(1)</STRONG> Active Directory ドメインサービスのユーザーオブジェクトは、一覧表示されている指定の active directory セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="867b3-162"><STRONG>(1)</STRONG> An Active Directory Domain Services user object must be a member of the specified Active Directory security group listed.</span></span> <span data-ttu-id="867b3-163">セキュリティグループにユーザーを追加するための適切な権限を持つ管理者またはその他の委任された Active Directory グループのメンバー (管理者、アカウントオペレーターなど) には、ユーザーが次のことをできるように、一覧表示されたセキュリティグループまたはグループにユーザーオブジェクトを追加する必要があります。記載されている関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="867b3-163">An administrator or other delegated Active Directory group member with appropriate permissions to add users to a security group (For example, Administrator, Account Operators) must add a user object to the listed security group or group for the user to be able to perform the functions listed.</span></span> <span data-ttu-id="867b3-164"><STRONG>(2)</STRONG> Csresponsegroupadministrator に割り当てられているワークフローのみ。</span><span class="sxs-lookup"><span data-stu-id="867b3-164"><STRONG>(2)</STRONG> Only for workflows that the CsResponseGroupAdministrator has assigned to the CsResponseGroupManager.</span></span> <span data-ttu-id="867b3-165"><STRONG>(3)</STRONG>応答グループマネージャーは、現在の管理者が既に管理しているワークフローに、CsResponseGroupManager の別のメンバーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="867b3-165"><STRONG>(3)</STRONG> A Response Group Manager can assign another member of CsResponseGroupManager to a workflow that the current manager already manages.</span></span> <span data-ttu-id="867b3-166"><STRONG>(4)</STRONG> csviewonlyadministrator は動詞 "Get" Lync Server 管理シェルコマンドレットのみを実行できます。</span><span class="sxs-lookup"><span data-stu-id="867b3-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator can only run verb "Get" Lync Server Management Shell cmdlets.</span></span>



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a><span data-ttu-id="867b3-167">応答グループの構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="867b3-167">Response Group Configuration Prerequisites</span></span>

<span data-ttu-id="867b3-168">応答グループには次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="867b3-168">Response Group requires the following components:</span></span>

  - <span data-ttu-id="867b3-169">アプリケーション サービス</span><span class="sxs-lookup"><span data-stu-id="867b3-169">Application service</span></span>

  - <span data-ttu-id="867b3-170">応答グループ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="867b3-170">Response Group application</span></span>

  - <span data-ttu-id="867b3-171">言語パック</span><span class="sxs-lookup"><span data-stu-id="867b3-171">Language packs</span></span>

  - <span data-ttu-id="867b3-172">ファイル ストア (オーディオ ファイルを格納)</span><span class="sxs-lookup"><span data-stu-id="867b3-172">File store (to hold audio files)</span></span>

  - <span data-ttu-id="867b3-173">Web サービス (応答グループの構成ツールとエージェントのサインインとサインアウトコンソールが含まれます)</span><span class="sxs-lookup"><span data-stu-id="867b3-173">Web Services (includes the Response Group Configuration Tool and the agents' sign-in and sign-out console)</span></span>

<span data-ttu-id="867b3-174">エンタープライズボイスを展開すると、これらのすべてのコンポーネントが既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="867b3-174">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="867b3-175">応答グループを構成する前に、次のタスクを実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="867b3-175">You might need to perform the following tasks before configuring Response Group:</span></span>

  - <span data-ttu-id="867b3-176">Lync Server 2013 およびエンタープライズ Voip のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="867b3-176">Enable users for Lync Server 2013 and Enterprise Voice.</span></span>

  - <span data-ttu-id="867b3-177">Federal Information Processing Standards (FIPS) に準拠するように構成ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="867b3-177">Modify a configuration file to be compliant with Federal Information Processing Standards (FIPS).</span></span>

  - <span data-ttu-id="867b3-178">キュー名やエージェント グループ名で Yi、Meng、および Zang の文字がサポートされるようにデータベースの照合順序を変更します。</span><span class="sxs-lookup"><span data-stu-id="867b3-178">Modify the database collation to support Yi, Meng, and Zang characters for queue names and agent group names.</span></span>

<div>

## <a name="enabling-users"></a><span data-ttu-id="867b3-179">ユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="867b3-179">Enabling Users</span></span>

<span data-ttu-id="867b3-180">応答グループを構成するための最初の手順は、エージェントグループを作成することです。</span><span class="sxs-lookup"><span data-stu-id="867b3-180">The first step in configuring Response Group is to create agent groups.</span></span> <span data-ttu-id="867b3-181">エージェントグループを作成する前に、Lync Server 2013 およびエンタープライズ Voip の返信グループに対してエージェントとなるユーザーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="867b3-181">Before you can create an agent group, you must enable the users who will be agents for Response Group for Lync Server 2013 and Enterprise Voice.</span></span> <span data-ttu-id="867b3-182">Lync Server 2013 でユーザーを有効にするには、通常、Enterprise Edition server または Standard Edition server の展開の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="867b3-182">Enabling users for Lync Server 2013 is typically a step in the Enterprise Edition server or Standard Edition server deployment.</span></span> <span data-ttu-id="867b3-183">Lync Server 2013 でユーザーを有効にする方法の詳細については、「 [Lync server 2013 のユーザーアカウントを無効にする、または再度有効にする](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="867b3-183">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="867b3-184">エンタープライズ Voip のユーザーを有効にするには、通常、エンタープライズ Voip 展開の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="867b3-184">Enabling users for Enterprise Voice is typically a step in the Enterprise Voice deployment.</span></span> <span data-ttu-id="867b3-185">詳細については、「 [Lync Server 2013 でエンタープライズ voip のユーザーを有効にする](lync-server-2013-enable-users-for-enterprise-voice.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="867b3-185">For details, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>

</div>

<div>

## <a name="complying-with-fips-requirements"></a><span data-ttu-id="867b3-186">FIPS 要件の準拠</span><span class="sxs-lookup"><span data-stu-id="867b3-186">Complying with FIPS requirements</span></span>

<span data-ttu-id="867b3-187">このセクションは、組織が FIPS (Federal Information Processing Standards) に準拠する必要がある場合にのみ参照してください。</span><span class="sxs-lookup"><span data-stu-id="867b3-187">This section applies to you only if your organization needs to comply with Federal Information Processing Standards (FIPS).</span></span>

<span data-ttu-id="867b3-188">FIPS に準拠するには、Web サービスをインストールした後に別の暗号化アルゴリズムを使用するようにアプリケーションレベルの web.config ファイルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="867b3-188">To be compliant with FIPS, you need to modify the application-level Web.config file to use a different cryptography algorithm after you install Web Services.</span></span> <span data-ttu-id="867b3-189">ASP.NET で、トリプルデータ暗号化標準 (3DES) アルゴリズムを使ってビューステートデータを処理するように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="867b3-189">You need to specify that ASP.NET use the Triple Data Encryption Standard (3DES) algorithm to process view state data.</span></span> <span data-ttu-id="867b3-190">応答グループアプリケーションの場合、この要件は、応答グループ構成ツールと、エージェントのサインインとサインアウトコンソールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="867b3-190">For the Response Group application, this requirement applies to the Response Group Configuration Tool and the agent sign-in and sign-out console.</span></span> <span data-ttu-id="867b3-191">この要件の詳細については、「Microsoft サポート技術情報の記事 911722 "ASP.NET 1.1 から ASP.NET 2.0" にアップグレードした後に ViewState が有効になっている ASP.NET web ページに[http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)アクセスすると、エラーメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="867b3-191">For details about this requirement, see Microsoft Knowledge Base article 911722, "You may receive an error message when you access ASP.NET webpages that have ViewState enabled after you upgrade from ASP.NET 1.1 to ASP.NET 2.0," at [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183).</span></span>

<span data-ttu-id="867b3-192">Web.config ファイルを変更するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="867b3-192">To modify the Web.config file, do the following:</span></span>

1.  <span data-ttu-id="867b3-193">メモ帳などのテキスト エディターで、アプリケーションレベルの Web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="867b3-193">In a text editor such as Notepad, open the application-level Web.config file.</span></span>

2.  <span data-ttu-id="867b3-194">Web.config ファイルで、 `<system.web>`セクションを見つけます。</span><span class="sxs-lookup"><span data-stu-id="867b3-194">In the Web.config file, locate the `<system.web>` section.</span></span>

3.  <span data-ttu-id="867b3-195">`<system.web>`セクションのに次`<machineKey>`のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="867b3-195">Add the following `<machineKey>` section to in the `<system.web>` section:</span></span>
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  <span data-ttu-id="867b3-196">Web.config ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="867b3-196">Save the Web.config file.</span></span>

5.  <span data-ttu-id="867b3-197">コマンドプロンプトで次のコマンドを実行して、インターネットインフォメーションサービス (IIS) サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="867b3-197">Restart the Internet Information Services (IIS) service by running the following command at a command prompt:</span></span>
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a><span data-ttu-id="867b3-198">Yi、Meng、および Zang の文字のサポート</span><span class="sxs-lookup"><span data-stu-id="867b3-198">Supporting Yi, Meng, and Zang Characters</span></span>

<span data-ttu-id="867b3-199">このセクションは、組織で Yi、Meng、または Zang の文字をサポートする必要がある場合に参照してください。</span><span class="sxs-lookup"><span data-stu-id="867b3-199">This section applies to you only if your organization needs to support Yi, Meng, or Zang characters.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="867b3-200">Yi、Meng、および Zang 文字の概要と、それらが展開にとって重要である理由については、「GB18030 文字セット<A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>」の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="867b3-200">For information on what the Yi, Meng, and Zang characters are and why they may be important to your deployment, see the information on the GB18030 character sets <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>.</span></span>



</div>

<span data-ttu-id="867b3-p106">Yi、Meng、または Zang の文字をサポートするには、Rgsconfig データベースの照合順序を変更する必要があります。各 Rgsconfig データベースの以下のテーブルにある [**名前**] 列の照合順序を変更します。</span><span class="sxs-lookup"><span data-stu-id="867b3-p106">To support Yi, Meng, or Zang characters, you need to modify the collation for the Rgsconfig database. Change the collation of the **Name** column in the following tables in each Rgsconfig database:</span></span>

  - <span data-ttu-id="867b3-203">dbo.AgentGroups</span><span class="sxs-lookup"><span data-stu-id="867b3-203">dbo.AgentGroups</span></span>

  - <span data-ttu-id="867b3-204">dbo.BusinessHours</span><span class="sxs-lookup"><span data-stu-id="867b3-204">dbo.BusinessHours</span></span>

  - <span data-ttu-id="867b3-205">dbo.HolidaySets</span><span class="sxs-lookup"><span data-stu-id="867b3-205">dbo.HolidaySets</span></span>

  - <span data-ttu-id="867b3-206">dbo.Queues</span><span class="sxs-lookup"><span data-stu-id="867b3-206">dbo.Queues</span></span>

  - <span data-ttu-id="867b3-207">dbo.Workflows</span><span class="sxs-lookup"><span data-stu-id="867b3-207">dbo.Workflows</span></span>

<span data-ttu-id="867b3-208">SQL Server 2008 R2 および SQL Server 2012 の場合は、Latin\_General\_100 (アクセントに依存) の照合順序を使用します。</span><span class="sxs-lookup"><span data-stu-id="867b3-208">For SQL Server 2008 R2 and SQL Server 2012, use the Latin\_General\_100 (Accent Sensitive) collation.</span></span> <span data-ttu-id="867b3-209">この照合順序を使用する場合は、どのオブジェクト名も大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="867b3-209">If you use this collation, all object names are not case-sensitive.</span></span>

<span data-ttu-id="867b3-210">照合順序は、Microsoft SQL Server Management Studio を使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="867b3-210">You can change the collation by using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="867b3-211">このツールの使用方法の詳細については、の「SQL Server [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)Management Studio を使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="867b3-211">For details about using this tool, see "Using SQL Server Management Studio" at [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184).</span></span> <span data-ttu-id="867b3-212">照合順序を変更するには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="867b3-212">Follow these steps to change the collation:</span></span>

1.  <span data-ttu-id="867b3-213">テーブルの再作成を必要とする変更が SQL Server Management Studio で許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="867b3-213">Be sure that SQL Server Management Studio is configured to allow changes that require tables to be recreated.</span></span> <span data-ttu-id="867b3-214">詳細については、「[保存 (許可されて[http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186)いません)] ダイアログボックス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="867b3-214">For details, see "Save (Not Permitted) Dialog Box" at [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186).</span></span> <span data-ttu-id="867b3-215">列の照合順序の設定の詳細については、「」の「方法: 列の[http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)照合順序を設定する (Visual Database Tools)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="867b3-215">For details about setting a column collation, see "How to: Set Column Collation (Visual Database Tools)" at [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185).</span></span>

2.  <span data-ttu-id="867b3-216">Microsoft SQL Server Management Studio を使用して、Rgsconfig データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="867b3-216">Using Microsoft SQL Server Management Studio, connect to the Rgsconfig database.</span></span>

3.  <span data-ttu-id="867b3-217">Rgsconfig データベースで変更したいテーブルを見つけて右クリックし、[**設計**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="867b3-217">Find the table you want to change in the Rgsconfig database, right-click the table, and click **Design**.</span></span>

4.  <span data-ttu-id="867b3-218">[**名前**] 列の照合順序を変更して、テーブルを保存します。</span><span class="sxs-lookup"><span data-stu-id="867b3-218">Change the collation of the **Name** column and save the table.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

