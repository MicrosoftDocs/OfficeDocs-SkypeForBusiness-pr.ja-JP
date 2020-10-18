---
title: Lync Server 2013 リソースキットツールのドキュメント
description: Lync Server 2013 リソースキットツールのマニュアル。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6866e04615014daa7e93f7e7f1081b10325d087d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573563"
---
# <a name="lync-server-2013-resource-kit-tools-documentation"></a><span data-ttu-id="da459-103">Lync Server 2013 リソースキットツールのドキュメント</span><span class="sxs-lookup"><span data-stu-id="da459-103">Lync Server 2013 Resource Kit Tools Documentation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da459-104">_**トピックの最終更新日:** 2014-01-09_</span><span class="sxs-lookup"><span data-stu-id="da459-104">_**Topic Last Modified:** 2014-01-09_</span></span>

<span data-ttu-id="da459-105">このトピックでは、Lync Server 2013 リソースキットの一部であるツールについて説明します。各ツールの目的や使用例を含みます。Lync Server 2013、リソースキットツールは、Lync Server 2013 を展開して管理する IT 管理者が日常的な作業を容易にするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="da459-105">This topic describes the tools that are part of the Lync Server 2013 Resource Kit, including the purpose of each tool, and examples of its use.The Lync Server 2013, Resource Kit Tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="da459-106">たとえば、 **Web Conf data** ツールを使用すると、オンライン会議中にユーザーによってアップロードされるデータを簡単に制御できます。</span><span class="sxs-lookup"><span data-stu-id="da459-106">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="da459-107">**SEFAUtil**ツールを使用して、代理人の着信の転送とユーザーへの応答を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="da459-107">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="da459-108">IT 管理者は、これらのツールを使用して Lync Server 2013 をより効果的に管理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da459-108">We encourage IT administrators to use these tools to more effectively manage Lync Server 2013.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="da459-109">リソースキットツールのインストール</span><span class="sxs-lookup"><span data-stu-id="da459-109">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="da459-110">Lync Server 2013 のリソースキットツールをインストールするには、 **OCSReskit.msi**をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="da459-110">To install the Lync Server 2013, Resource Kit Tools, download **OCSReskit.msi**.</span></span> <span data-ttu-id="da459-111">リソースキットツールインストーラーは、ダウンロードセンターからダウンロードでき [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429) ます。</span><span class="sxs-lookup"><span data-stu-id="da459-111">You can download the Resource Kit Tools installer from the Download Center at [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429).</span></span>

<span data-ttu-id="da459-112">**OCSResKit.msi**を実行して簡単なインストールを行います。</span><span class="sxs-lookup"><span data-stu-id="da459-112">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="da459-113">.Msi は、次のパスにあるすべてのツールをインストールします。 **% Program Files% \\ Microsoft Lync Server 2013 \\ うえ**。</span><span class="sxs-lookup"><span data-stu-id="da459-113">The .msi installs all the tools in the following path: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**.</span></span> <span data-ttu-id="da459-114">このフォルダーには、自己完結型の実行可能ファイルであるツールがあります。</span><span class="sxs-lookup"><span data-stu-id="da459-114">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="da459-115">ファイルが含まれているツールも、それぞれ独自のサブフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="da459-115">Tools that also have files are in their own subfolders.</span></span>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="da459-116">サポートされる環境</span><span class="sxs-lookup"><span data-stu-id="da459-116">Supported Environments</span></span>

<span data-ttu-id="da459-117">最適なパフォーマンスを得るために、lync server 2013、リソースキットツールは、Lync Server 2013 に必要なものと同じ環境にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-117">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="da459-118">リソースキットツールの概要</span><span class="sxs-lookup"><span data-stu-id="da459-118">Resource Kit Tools Overview</span></span>

<span data-ttu-id="da459-119">次の一覧では、Lync Server 2013 リソースキットで提供されるツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="da459-119">The following list describes the tools that are provided in the Lync Server 2013 Resource Kit.</span></span> <span data-ttu-id="da459-120">各ツールの説明 (要件および使用例を含む) については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="da459-120">A description of each tool, including the requirements and example usage is covered in the following section.</span></span>

  - <span data-ttu-id="da459-121">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="da459-121">ABSConfig</span></span>

  - <span data-ttu-id="da459-122">帯域幅ポリシーサービスモニター</span><span class="sxs-lookup"><span data-stu-id="da459-122">Bandwidth Policy Service Monitor</span></span>

  - <span data-ttu-id="da459-123">帯域幅使用率アナライザー</span><span class="sxs-lookup"><span data-stu-id="da459-123">Bandwidth Utilization Analyzer</span></span>

  - <span data-ttu-id="da459-124">コール Par・メータ計</span><span class="sxs-lookup"><span data-stu-id="da459-124">Call Parkometer</span></span>

  - <span data-ttu-id="da459-125">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="da459-125">CleanupStorageServiceData</span></span>

  - <span data-ttu-id="da459-126">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="da459-126">DBAnalyze</span></span>

  - <span data-ttu-id="da459-127">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="da459-127">ImportStorageServiceData</span></span>

  - <span data-ttu-id="da459-128">LCSSync</span><span class="sxs-lookup"><span data-stu-id="da459-128">LCSSync</span></span>

  - <span data-ttu-id="da459-129">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="da459-129">LookupUserConsole</span></span>

  - <span data-ttu-id="da459-130">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="da459-130">MsTurnPing</span></span>

  - <span data-ttu-id="da459-131">ネットワーク構成ビューアー</span><span class="sxs-lookup"><span data-stu-id="da459-131">Network Configuration Viewer</span></span>

  - <span data-ttu-id="da459-132">応答グループエージェント Live</span><span class="sxs-lookup"><span data-stu-id="da459-132">Response Group Agent Live</span></span>

  - <span data-ttu-id="da459-133">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="da459-133">SEFAUtil</span></span>

  - <span data-ttu-id="da459-134">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="da459-134">SYSPrep.ps1</span></span>

  - <span data-ttu-id="da459-135">割り当てられていない番号のアナウンスの移行</span><span class="sxs-lookup"><span data-stu-id="da459-135">Unassigned Number Announcements Migration</span></span>

  - <span data-ttu-id="da459-136">Web Conf データ</span><span class="sxs-lookup"><span data-stu-id="da459-136">Web Conf Data</span></span>

</div>

<div>

## <a name="absconfig"></a><span data-ttu-id="da459-137">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="da459-137">ABSConfig</span></span>

<span data-ttu-id="da459-138">アドレス帳サービス構成ツール (ABSConfig) は、管理者が Lync Server 2013 のアドレス帳サービス構成をカスタマイズするのに役立つ管理ツールです。</span><span class="sxs-lookup"><span data-stu-id="da459-138">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Lync Server 2013.</span></span> <span data-ttu-id="da459-139">このツールを使用すると、Lync Server 2013 管理者は、既定のアドレス帳サービス設定を復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="da459-139">This tool also enables Lync Server 2013 administrators to restore the default Address Book Service settings.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-140">説明</span><span class="sxs-lookup"><span data-stu-id="da459-140">Description</span></span>

<span data-ttu-id="da459-141">ABSConfig は、管理者がアドレス帳サービスに関連する Active Directory ドメインサービスの属性を構成できるグラフィカルユーザーインターフェイスアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="da459-141">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="da459-142">このツールの主なシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="da459-142">The primary scenarios for the tool are the following:</span></span>

  - <span data-ttu-id="da459-143">管理者が Active Directory ドメインサービスの属性を Lync Server 2013 の属性にマップできるようにします。</span><span class="sxs-lookup"><span data-stu-id="da459-143">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Lync Server 2013.</span></span>

  - <span data-ttu-id="da459-144">管理者が Active Directory ドメインサービスの属性を指定して、アドレス帳サービスファイルに含めたり除外したりできるようにします。</span><span class="sxs-lookup"><span data-stu-id="da459-144">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

  - <span data-ttu-id="da459-145">管理者が既定のアドレス帳サービス設定を復元できるようにする。</span><span class="sxs-lookup"><span data-stu-id="da459-145">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="da459-146">ABSConfig ツールは absConfig.exe ファイルを使用して開始できます。</span><span class="sxs-lookup"><span data-stu-id="da459-146">The ABSConfig tool can be started by using the absConfig.exe file.</span></span> <span data-ttu-id="da459-147">ツールが [ **Configure Attributes** ] タブに表示されます。この表には、Active Directory ドメインサービスの属性を Lync Server 2013 の属性フィールドにマップし、特定の属性フィルターに基づいてアドレス帳サービスファイルに含めるまたは除外するユーザーを指定するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="da459-147">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Lync Server 2013 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="da459-148">また、アドレス帳ファイルに含める電話番号の値をカスタマイズするためのオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="da459-148">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="da459-149">[ **既定** の設定に戻す] オプションを使用すると、管理者はアドレス帳サービスの設定を既定値に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="da459-149">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

</div>

<div>

## <a name="changes-from-lync-server-2010"></a><span data-ttu-id="da459-150">Lync Server 2010 からの変更点</span><span class="sxs-lookup"><span data-stu-id="da459-150">Changes from Lync Server 2010</span></span>

<span data-ttu-id="da459-151">Lync Server 2013 ABS 構成ツールでは、属性の [有効] チェックボックスをオフにすることで、属性 (行) を削除できます。</span><span class="sxs-lookup"><span data-stu-id="da459-151">In Lync Server 2013 ABS Configuration tool, attributes (rows) may be removed by unchecking the “enable” checkbox for the attribute.</span></span> <span data-ttu-id="da459-152">これは、Lync Server 2010 の行を削除するのと同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="da459-152">This has the same effect as deleting the row in Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da459-153">[有効にする] チェックボックスは、右端の列にあります。列を表示するには、右にスクロールする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="da459-153">The enable checkbox is in the far right column; you may need to scroll right to see the column</span></span>



</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="da459-154">出力</span><span class="sxs-lookup"><span data-stu-id="da459-154">Output</span></span>

<span data-ttu-id="da459-155">ABSConfig は、アドレス帳サービスの構成をデータベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="da459-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="da459-156">用途</span><span class="sxs-lookup"><span data-stu-id="da459-156">Purpose</span></span>

<span data-ttu-id="da459-157">ABSConfig には、Lync Server 2013 アドレス帳サービスをすばやく簡単にカスタマイズする方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="da459-157">ABSConfig provides a quick and easy way to customize Lync Server 2013 Address Book Service.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="da459-158">要件</span><span class="sxs-lookup"><span data-stu-id="da459-158">Requirements</span></span>

<div>

## <a name="computer"></a><span data-ttu-id="da459-159">コンピューター</span><span class="sxs-lookup"><span data-stu-id="da459-159">Computer</span></span>

<span data-ttu-id="da459-160">ABSConfig は、Lync Server 2013 がインストールされているドメインに参加しているコンピューターからのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="da459-160">ABSConfig can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span> <span data-ttu-id="da459-161">Lync Server 2013 Enterprise Edition の場合、セットアップ中にアドレス帳サービスが有効になっているすべてのフロントエンドサーバーでこのツールを実行できます。</span><span class="sxs-lookup"><span data-stu-id="da459-161">In the case of Lync Server 2013, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

</div>

<div>

## <a name="network"></a><span data-ttu-id="da459-162">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="da459-162">Network</span></span>

<span data-ttu-id="da459-163">コンピューターは、フロントエンドプールとバックエンドデータベースに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

</div>

<div>

## <a name="software"></a><span data-ttu-id="da459-164">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="da459-164">Software</span></span>

<span data-ttu-id="da459-165">ABSConfig ツールを実行する前に、次のソフトウェアコンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-165">The following software components must be installed before running the ABSConfig tool:</span></span>

  - <span data-ttu-id="da459-166">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da459-166">Microsoft Lync Server 2013</span></span>

</div>

<div>

## <a name="users"></a><span data-ttu-id="da459-167">ユーザー</span><span class="sxs-lookup"><span data-stu-id="da459-167">Users</span></span>

<span data-ttu-id="da459-168">Lync Server 2013 の展開を更新するのに必要なアクセス許可を持つ管理者。</span><span class="sxs-lookup"><span data-stu-id="da459-168">Administrators who have the permissions required to update the Lync Server 2013 deployment.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="da459-169">例</span><span class="sxs-lookup"><span data-stu-id="da459-169">Examples</span></span>

<span data-ttu-id="da459-170">ABSConfig を開始するには、コマンドプロンプトで **ABSConfig.exe** を入力します。</span><span class="sxs-lookup"><span data-stu-id="da459-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="da459-171">次に示すのは、ABSConfig tool のユーザーインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="da459-171">Shown below is the ABSConfig tool user interface.</span></span>

<span data-ttu-id="da459-172">![ABSConfig.exe ツール。](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "ABSConfig.exe ツール。")</span><span class="sxs-lookup"><span data-stu-id="da459-172">![The ABSConfig.exe tool.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "The ABSConfig.exe tool.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="da459-173">要約</span><span class="sxs-lookup"><span data-stu-id="da459-173">Summary</span></span>

<span data-ttu-id="da459-174">ABSConfig ツールを使用すると、管理者は、Lync Server 2013 アドレス帳サービスをカスタマイズするためのツールをすばやく簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="da459-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Lync Server 2013 Address Book Service.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="da459-175">帯域幅ポリシーサービスモニター</span><span class="sxs-lookup"><span data-stu-id="da459-175">Bandwidth Policy Service Monitor</span></span>

<span data-ttu-id="da459-176">帯域幅ポリシーサービスモニターツールを使用すると、管理者は以下の一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="da459-176">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1.  <span data-ttu-id="da459-177">トポロジ内のすべての構成済み Lync Server 2013 帯域幅ポリシーサービス (認証とコア)</span><span class="sxs-lookup"><span data-stu-id="da459-177">All the configured Lync Server 2013 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2.  <span data-ttu-id="da459-178">各サービスが他の帯域幅ポリシーサービスとエッジサーバーに対して行う接続</span><span class="sxs-lookup"><span data-stu-id="da459-178">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3.  <span data-ttu-id="da459-179">ネットワーク構成ドキュメントに構成されているすべてのリンク、および各帯域幅ポリシーサービスによって報告されるリアルタイムの帯域幅の使用状況</span><span class="sxs-lookup"><span data-stu-id="da459-179">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-180">説明</span><span class="sxs-lookup"><span data-stu-id="da459-180">Description</span></span>

<span data-ttu-id="da459-181">帯域幅ポリシーサービスモニターツールは、GUI ベースのアプリケーションとして実装されています。</span><span class="sxs-lookup"><span data-stu-id="da459-181">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="da459-182">管理者は PDPMonUI.exe を実行してツールを開始します。</span><span class="sxs-lookup"><span data-stu-id="da459-182">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="da459-183">ツールが開始すると、トポロジ内の帯域幅ポリシーサービスの一覧の検出が試みられます。</span><span class="sxs-lookup"><span data-stu-id="da459-183">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="da459-184">最初の更新が完了すると、ウィンドウの左側にあるウィンドウに、所属するクラスターによってグループ化されたサービスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="da459-184">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="da459-185">管理者が特定の帯域幅ポリシーサービスを選択すると、右側のウィンドウにその特定のサービスに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="da459-185">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="da459-186">このウィンドウには、情報を表示するための2つの主要なタブもあります。</span><span class="sxs-lookup"><span data-stu-id="da459-186">That pane also has two main tabs that display information.</span></span>

<div>

## <a name="machine-info-tab"></a><span data-ttu-id="da459-187">[コンピューター情報] タブ</span><span class="sxs-lookup"><span data-stu-id="da459-187">Machine Info Tab</span></span>

<span data-ttu-id="da459-188">[ **コンピューター情報** ] タブには、選択されている帯域幅ポリシーサービスの詳細と、選択した帯域幅ポリシーサービスによって他のサービスに対して行われたすべての接続のリストと状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="da459-188">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

</div>

<div>

## <a name="topology-info-tab"></a><span data-ttu-id="da459-189">[トポロジ情報] タブ</span><span class="sxs-lookup"><span data-stu-id="da459-189">Topology Info Tab</span></span>

<span data-ttu-id="da459-190">[ **トポロジ情報** ] タブには、ネットワーク構成設定で構成されているすべてのリンクの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="da459-190">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="da459-191">各リンクについて、音声およびビデオの帯域幅の容量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="da459-191">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="da459-192">さらに、現在使用されている帯域幅が、Kbps で、容量の割合として表示されます。</span><span class="sxs-lookup"><span data-stu-id="da459-192">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="da459-193">このツールは、色分けを使用して、使用率が近づいているリンクを強調表示します。これにより、管理者はそのようなリンクをすばやく分離することができます。</span><span class="sxs-lookup"><span data-stu-id="da459-193">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da459-194">構成された帯域幅ポリシーサービスに接続するときに、帯域幅ポリシーサービスモニターツールでエラーが発生した場合、[ <STRONG>コンピューター情報</STRONG> ] タブと [ <STRONG>トポロジ情報</STRONG> ] タブに情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="da459-194">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the <STRONG>Machine Info</STRONG> and the <STRONG>Topology Info</STRONG> tabs won’t be populated.</span></span> <span data-ttu-id="da459-195">ただし、最初に接続した後、サービスへの接続が失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da459-195">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="da459-196">このような場合、管理者が古い情報を表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="da459-196">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="da459-197">各タブに <STRONG>最後に更新</STRONG> されたタイムスタンプがあり、管理者は特定の帯域幅ポリシーサービスのデータが最後に更新された日時を確認できます。</span><span class="sxs-lookup"><span data-stu-id="da459-197">There is a <STRONG>Last Updated</STRONG> time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="da459-198">出力</span><span class="sxs-lookup"><span data-stu-id="da459-198">Output</span></span>

<span data-ttu-id="da459-199">コマンドライン出力はありません。プログラムの出力は、メインのグラフィカルユーザーインターフェイス (GUI) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="da459-199">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="da459-200">用途</span><span class="sxs-lookup"><span data-stu-id="da459-200">Purpose</span></span>

<span data-ttu-id="da459-201">帯域幅ポリシーサービス監視ツールの目的は、管理者がトポロジで定義されている各帯域幅ポリシーサービスの状態を表示できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="da459-201">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="da459-202">さらに、管理者は、ネットワーク構成ドキュメントで定義されているすべてのリンクについて、リアルタイムの帯域幅使用量を確認できます。</span><span class="sxs-lookup"><span data-stu-id="da459-202">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="da459-203">要件</span><span class="sxs-lookup"><span data-stu-id="da459-203">Requirements</span></span>

<span data-ttu-id="da459-204">帯域幅ポリシーサービスモニターツールは、Lync Server トポロジの一部であるコンピューター上で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-204">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Lync Server topology.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="da459-205">要約</span><span class="sxs-lookup"><span data-stu-id="da459-205">Summary</span></span>

<span data-ttu-id="da459-206">帯域幅ポリシーサービスモニターツールは、管理者にとって貴重なリソースとなり、トポロジ内のすべての帯域幅ポリシーサービスの状態を検査したり、ネットワーク構成設定で定義されているリンクのリアルタイムの帯域幅の使用状況を取得したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="da459-206">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="da459-207">帯域幅使用率アナライザー</span><span class="sxs-lookup"><span data-stu-id="da459-207">Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="da459-208">帯域幅使用率アナライザーは、エンタープライズネットワーク内の WAN リンク全体にわたる UC エンドポイントによる帯域幅消費量のさまざまな表示に関するレポートを作成するツールです。</span><span class="sxs-lookup"><span data-stu-id="da459-208">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="da459-209">これらのレポートを使用して、現在の帯域幅の使用パターンを理解し、帯域幅の容量計画に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="da459-209">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-210">説明</span><span class="sxs-lookup"><span data-stu-id="da459-210">Description</span></span>

<span data-ttu-id="da459-211">帯域幅使用率アナライザーは、GUI ベースのアプリケーションとして実装されています。</span><span class="sxs-lookup"><span data-stu-id="da459-211">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="da459-212">このツールは、ネットワーク全体の音声使用に特化したレポートを生成し、容量計画に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="da459-212">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="da459-213">また、さまざまなリンクに割り当てられている帯域幅容量を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="da459-213">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="da459-214">出力</span><span class="sxs-lookup"><span data-stu-id="da459-214">Output</span></span>

<span data-ttu-id="da459-215">帯域幅使用率アナライザーは、システム内で構成されているすべての WAN リンクについて、帯域幅容量とオーディオの使用率を図で示しています。</span><span class="sxs-lookup"><span data-stu-id="da459-215">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="da459-216">用途</span><span class="sxs-lookup"><span data-stu-id="da459-216">Purpose</span></span>

<span data-ttu-id="da459-217">音声およびビデオの展開では、企業ネットワーク全体のメディアトラフィックの帯域幅使用率の傾向を監視し、理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="da459-217">In any voice and video deployment, it’s critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="da459-218">帯域幅使用率アナライザーツールを使用すると、管理者はこれを実現することができます。</span><span class="sxs-lookup"><span data-stu-id="da459-218">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="da459-219">このツールは、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="da459-219">This tool does the following:</span></span>

  - <span data-ttu-id="da459-220">ネットワーク全体の音声使用状況に関する特定のレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="da459-220">Generates specific reports for audio utilization across the network</span></span>

  - <span data-ttu-id="da459-221">さまざまなリンクに割り当てられている帯域幅容量に対して、さらに効果的な容量計画と反復処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="da459-221">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="da459-222">帯域幅使用率アナライザーは、帯域幅容量と使用率レポートをグラフィカルにプロットすることができます。次のようになります。</span><span class="sxs-lookup"><span data-stu-id="da459-222">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

  - <span data-ttu-id="da459-223">エンタープライズネットワーク内のすべての WAN リンク</span><span class="sxs-lookup"><span data-stu-id="da459-223">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="da459-224">選択された WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="da459-224">Filtered by selected WAN links that have been chosen</span></span>

  - <span data-ttu-id="da459-225">リンク容量を超過した WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="da459-225">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="da459-226">プロビジョニングされた帯域幅を利用している WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="da459-226">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

  - <span data-ttu-id="da459-227">重大レベルに達している WAN リンクでフィルター処理する (WAN リンクの帯域幅の容量の90% を超える帯域幅の使用率)</span><span class="sxs-lookup"><span data-stu-id="da459-227">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="da459-228">WAN リンクの種類によるフィルター処理—ネットワークサイトリンク、地域間リンク、サイト内のリンク</span><span class="sxs-lookup"><span data-stu-id="da459-228">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

  - <span data-ttu-id="da459-229">ネットワーク地域でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="da459-229">Filtered by network region</span></span>

<div>

## <a name="applications"></a><span data-ttu-id="da459-230">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="da459-230">Applications</span></span>

<span data-ttu-id="da459-231">帯域幅使用率アナライザーには、次の2つのアプリケーション (ツール) があります。</span><span class="sxs-lookup"><span data-stu-id="da459-231">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

  - <span data-ttu-id="da459-232">**WanLinkLogCollector.exe**    このツールを使用すると、ユーザーは必要な情報を入力できます。</span><span class="sxs-lookup"><span data-stu-id="da459-232">**WanLinkLogCollector.exe**   This tool enables its user to input the required information.</span></span>

  - <span data-ttu-id="da459-233">**BandwidthUtilizationAnalyzer.xlsm**   Microsoft Excel スプレッドシートソフトウェアレポートは、WanLinkLogCollector.exe によって自動的に起動されます。</span><span class="sxs-lookup"><span data-stu-id="da459-233">**BandwidthUtilizationAnalyzer.xlsm**  A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="da459-234">このアプリケーションでは、この記事で後述するように、ユーザーがレポートにフィルターを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="da459-234">This application allows the user to apply filters to the report as shown later in this article.</span></span>

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="da459-235">帯域幅使用率アナライザーを使用するフェーズ</span><span class="sxs-lookup"><span data-stu-id="da459-235">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="da459-236">帯域幅使用アナライザーを使用する場合は、次の2つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="da459-236">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

  - <span data-ttu-id="da459-237">ログを収集する WanLinkLogCollector.exe を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="da459-237">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

  - <span data-ttu-id="da459-238">BandwidthUtilizationAnalyzer.xlsm を使用して実行されるレポートをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="da459-238">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="da459-239">エンドユーザーが手動で BandwidthUtilizationAnalyzer.xlsm を起動しないようにすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da459-239">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="da459-240">帯域幅使用率分析の開始</span><span class="sxs-lookup"><span data-stu-id="da459-240">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="da459-241">コマンドプロンプトまたはエクスプローラーを使用して WanLinkLogCollector.exe を起動します。</span><span class="sxs-lookup"><span data-stu-id="da459-241">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

<span data-ttu-id="da459-242">\*\*WanLinkLogCollector.exeを使用する \*\*</span><span class="sxs-lookup"><span data-stu-id="da459-242">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="da459-243">WanLinkLogCollector.exe を使用するには、次の3つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="da459-243">There are three steps to using WanLinkLogCollector.exe:</span></span>

1.  <span data-ttu-id="da459-244">**タイムライン**     のログを記録するレポートを生成するために必要なタイムラインを指定する</span><span class="sxs-lookup"><span data-stu-id="da459-244">**Log the timeline**   Provide the timeline that the report needs to be generated for</span></span>

2.  <span data-ttu-id="da459-245">**ファイルディレクトリ**     を指定するファイルの場所情報を指定する</span><span class="sxs-lookup"><span data-stu-id="da459-245">**Specify the file directories**   Provide file location information</span></span>

3.  <span data-ttu-id="da459-246">**ログを収集してレポートビューアー**    を起動するコマンドを実行してレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="da459-246">**Collect the logs and launch the report viewer**  Execute the command to generate the report</span></span>

<div>

## <a name="step-1---log-the-timeline"></a><span data-ttu-id="da459-247">手順 1-タイムラインのログを記録する</span><span class="sxs-lookup"><span data-stu-id="da459-247">Step 1 - Log the timeline</span></span>

<span data-ttu-id="da459-248">タイムラインのログを記録すると、次の図に示すように、ツールユーザーは次のものを指定できます。</span><span class="sxs-lookup"><span data-stu-id="da459-248">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1.  <span data-ttu-id="da459-249">**開始日** これは、レポートが生成されるタイムラインの開始日です。たとえば、2010年8月1日。</span><span class="sxs-lookup"><span data-stu-id="da459-249">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2.  <span data-ttu-id="da459-250">**終了日** これは、レポートが生成されるタイムラインの終了日です。たとえば、2010年9月30日。</span><span class="sxs-lookup"><span data-stu-id="da459-250">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
    <span data-ttu-id="da459-251">![帯域幅使用率の開始日と終了日](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "帯域幅使用率の開始日と終了日")</span><span class="sxs-lookup"><span data-stu-id="da459-251">![Start and End dates in the Bandwidth Utilization A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start and End dates in the Bandwidth Utilization A")</span></span>  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="da459-252">手順 2-ファイルディレクトリを指定する</span><span class="sxs-lookup"><span data-stu-id="da459-252">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="da459-253">表示されているように、次のファイルディレクトリをユーザーが指定できます。</span><span class="sxs-lookup"><span data-stu-id="da459-253">The following file directories can be specified by the user as shown.</span></span>

  - <span data-ttu-id="da459-254">**サーバーログファイルの場所** 帯域幅ポリシーサーバーのログが格納されるフォルダーの場所。</span><span class="sxs-lookup"><span data-stu-id="da459-254">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="da459-255">これは通常、 \<fileserver\> \\ \<choice of FE\> \\ appserverfiles \\ PDP にあります。</span><span class="sxs-lookup"><span data-stu-id="da459-255">This is typically in \<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP.</span></span>

  - <span data-ttu-id="da459-256">**一時ファイルの保存場所** レポートの生成中に中間ファイルが保存される一時ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="da459-256">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

<span data-ttu-id="da459-257">![帯域幅使用率 Anal のファイルディレクトリ](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "帯域幅使用率 Anal のファイルディレクトリ")</span><span class="sxs-lookup"><span data-stu-id="da459-257">![File directories in the Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "File directories in the Bandwidth Utilization Anal")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da459-258">サーバーログと一時ファイルストアフォルダーへの十分なファイルアクセスがツールユーザーに提供されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da459-258">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="da459-259">手順 3-ログを収集してレポートビューアーを起動する</span><span class="sxs-lookup"><span data-stu-id="da459-259">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="da459-260">ログを収集してレポートビューアーを起動するには、下の図のように [ **実行** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da459-260">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="da459-261">この手順では、必要なデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="da459-261">This step collects the required data.</span></span>

<span data-ttu-id="da459-262">![帯域幅使用率の収集におけるデータの収集の概要 y](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "帯域幅使用率の収集におけるデータの収集の概要 y")</span><span class="sxs-lookup"><span data-stu-id="da459-262">![Collecting data in the Bandwidth Utilization Analy](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecting data in the Bandwidth Utilization Analy")</span></span>

<span data-ttu-id="da459-263">入力の検証に成功すると、次に示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da459-263">When the input validation is successful, the message shown below is displayed.</span></span>

<span data-ttu-id="da459-264">![帯域幅 Bandwidthutilizationanalyzer で収集された通知を記録します。](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "帯域幅 Bandwidthutilizationanalyzer で収集された通知を記録します。")</span><span class="sxs-lookup"><span data-stu-id="da459-264">![Logs collected notification in the Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Logs collected notification in the Bandwidth Utili")</span></span>

<span data-ttu-id="da459-265">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da459-265">Click **OK**.</span></span> <span data-ttu-id="da459-266">BandwidthUtilizationAnalyzer.xlsm が自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="da459-266">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="da459-267">メッセージボックスの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="da459-267">Follow the instructions in the message box.</span></span> <span data-ttu-id="da459-268">詳細については、次のセクションの「 **Using BandwidthUtilizationAnalyzer.xlsm** 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da459-268">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>

</div>

<div>


<span data-ttu-id="da459-269">**BandwidthUtilizationAnalyzer.xlsm の使用**</span><span class="sxs-lookup"><span data-stu-id="da459-269">**Using BandwidthUtilizationAnalyzer.xlsm**</span></span>

1.  <span data-ttu-id="da459-270">BandwidthUtilizationAnalyzer.xlsm が自動的に開始されたら、下の図のように [ **更新** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da459-270">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
    <span data-ttu-id="da459-271">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span><span class="sxs-lookup"><span data-stu-id="da459-271">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span></span>

2.  <span data-ttu-id="da459-272">ファイルフォルダーが開いたら、次に示すように、メッセージボックスに指定されている場所から [consolidated.csv] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da459-272">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="da459-273">また、 **C: \\ Temp**という場所も表示されます。</span><span class="sxs-lookup"><span data-stu-id="da459-273">It also shows the location as **C:\\Temp**.</span></span>
    
    <span data-ttu-id="da459-274">![Bandwidthutilizationanalyzer.xlsm でフォルダーを開きます。](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Bandwidthutilizationanalyzer.xlsm でフォルダーを開きます。")</span><span class="sxs-lookup"><span data-stu-id="da459-274">![Opening a folder in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Opening a folder in BandwidthUtilizationAnalyzer.")</span></span>

3.  <span data-ttu-id="da459-275">[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da459-275">Click **Import**.</span></span>

4.  <span data-ttu-id="da459-276">グラフィカルプロットが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="da459-276">The graphical plot is automatically generated.</span></span> <span data-ttu-id="da459-277">このツールは、バックグラウンドで動作しているポインターが表示されなくなったときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="da459-277">It is available when the working-in-the-background pointer disappears.</span></span>
    
    <span data-ttu-id="da459-278">![レポートビューでフィルターを適用します。](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "レポートビューでフィルターを適用します。")</span><span class="sxs-lookup"><span data-stu-id="da459-278">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="da459-279">レポートビューにフィルターを適用する</span><span class="sxs-lookup"><span data-stu-id="da459-279">Applying Filters to the Report View</span></span>

<span data-ttu-id="da459-280">以下に示すように、レポートビューに適用できるフィルターについては、次のように説明します。</span><span class="sxs-lookup"><span data-stu-id="da459-280">The filters that can be applied to the report view as shown below are described as follows:</span></span>

<span data-ttu-id="da459-281">![レポートビューでフィルターを適用します。](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "レポートビューでフィルターを適用します。")</span><span class="sxs-lookup"><span data-stu-id="da459-281">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

1.  <span data-ttu-id="da459-282">**名前** WAN リンクでフィルター処理します (グラフの右側にフィルターがあります)。プレフィックスは次のリンクの種類を示します。垂直 (青) のボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-282">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
      - <span data-ttu-id="da459-283">**S サイト** ネットワークサイトからネットワーク地域への WAN リンク</span><span class="sxs-lookup"><span data-stu-id="da459-283">**S Site** The WAN link from a network site to a network region</span></span>
    
      - <span data-ttu-id="da459-284">**サイト間** 2つのネットワークサイト間の WAN リンク</span><span class="sxs-lookup"><span data-stu-id="da459-284">**IS Inter-Site** The WAN link between two network sites</span></span>
    
      - <span data-ttu-id="da459-285">**R 地域間** 2つのネットワーク地域間の WAN リンク</span><span class="sxs-lookup"><span data-stu-id="da459-285">**R Inter-Region** The WAN link between two network region</span></span>

2.  <span data-ttu-id="da459-286">**制限を超え** た帯域幅の使用率が帯域幅の容量を超えている WAN リンクでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="da459-286">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3.  <span data-ttu-id="da459-287">**重要なレベル** 帯域幅の使用率が90% 以上に達したか、帯域幅の容量を超えている WAN リンクでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="da459-287">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4.  <span data-ttu-id="da459-288">**低使用時** 帯域幅の使用率が帯域幅の容量の25% 未満である WAN リンクでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="da459-288">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5.  <span data-ttu-id="da459-289">**リンクの種類** 次の WAN リンクの種類でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="da459-289">**Link type** Filter by the following WAN links types:</span></span>
    
      - <span data-ttu-id="da459-290">**ネットワークサイト** の種類</span><span class="sxs-lookup"><span data-stu-id="da459-290">**Network site** type</span></span>
    
      - <span data-ttu-id="da459-291">**サイト間の** 種類</span><span class="sxs-lookup"><span data-stu-id="da459-291">**Inter-site** type</span></span>
    
      - <span data-ttu-id="da459-292">**地域間リンクの** 種類</span><span class="sxs-lookup"><span data-stu-id="da459-292">**Inter-Region link** type</span></span>

6.  <span data-ttu-id="da459-293">**Region** ネットワーク地域によるフィルター</span><span class="sxs-lookup"><span data-stu-id="da459-293">**Region** Filter by network region</span></span>

<span data-ttu-id="da459-294">次の図は、以前に説明したフィルターを示しています。</span><span class="sxs-lookup"><span data-stu-id="da459-294">The following figures show the previously described filters.</span></span>

<span data-ttu-id="da459-295">**名前**でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="da459-295">Filter by **Name**.</span></span> <span data-ttu-id="da459-296">グラフに表示する必要があるリンクの一覧を選択します。</span><span class="sxs-lookup"><span data-stu-id="da459-296">Select the list of links that need to be displayed in the graph.</span></span>

<span data-ttu-id="da459-297">![Bandwidthutilizationanalyzer.xlsm での名前によるフィルター処理。](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Bandwidthutilizationanalyzer.xlsm での名前によるフィルター処理。")</span><span class="sxs-lookup"><span data-stu-id="da459-297">![Filtering by Name in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtering by Name in BandwidthUtilizationAnalyzer.")</span></span>

<span data-ttu-id="da459-298">制限を **超え**てフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="da459-298">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="da459-299">フィルターを適用するには、[ **True** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da459-299">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="da459-300">![制限を超過したフィルター処理。](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "制限を超過したフィルター処理。")</span><span class="sxs-lookup"><span data-stu-id="da459-300">![Filtering by Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtering by Exceeded Limit.")</span></span>

<span data-ttu-id="da459-301">**重要レベル**でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="da459-301">Filter by **Critical levels**.</span></span> <span data-ttu-id="da459-302">フィルターを適用するには、[ **True** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da459-302">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="da459-303">![重要レベルでのフィルター処理。](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "重要レベルでのフィルター処理。")</span><span class="sxs-lookup"><span data-stu-id="da459-303">![Filtering by Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtering by Critical Levels.")</span></span>

<span data-ttu-id="da459-304">**使用率**の低いフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="da459-304">Filter by **Under utilized**.</span></span> <span data-ttu-id="da459-305">フィルターを適用するには、[ **True** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da459-305">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="da459-306">![フィルター処理に使用されます。](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "フィルター処理に使用されます。")</span><span class="sxs-lookup"><span data-stu-id="da459-306">![Filtering by Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtering by Under Utilized.")</span></span>

<span data-ttu-id="da459-307">リンクの **種類**でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="da459-307">Filter by **Link Type**.</span></span> <span data-ttu-id="da459-308">表示する必要のある種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="da459-308">Select the type or types that need to be displayed.</span></span>

<span data-ttu-id="da459-309">![リンクの種類によるフィルター処理。](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "リンクの種類によるフィルター処理。")</span><span class="sxs-lookup"><span data-stu-id="da459-309">![Filtering by Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtering by Link Type.")</span></span>

<span data-ttu-id="da459-310">**地域**でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="da459-310">Filter by **Region**.</span></span> <span data-ttu-id="da459-311">リンクを表示する必要がある地域の一覧を選択します。</span><span class="sxs-lookup"><span data-stu-id="da459-311">Select a list of regions whose links need to be displayed.</span></span>

<span data-ttu-id="da459-312">![地域別のフィルター処理。](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "地域別のフィルター処理。")</span><span class="sxs-lookup"><span data-stu-id="da459-312">![Filtering by Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtering by Region.")</span></span>

</div>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="da459-313">要件</span><span class="sxs-lookup"><span data-stu-id="da459-313">Requirements</span></span>

  - <span data-ttu-id="da459-314">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="da459-314">The .NET Framework 3.5</span></span>

  - <span data-ttu-id="da459-315">Microsoft Excel 2010 または Excel 2007</span><span class="sxs-lookup"><span data-stu-id="da459-315">Microsoft Excel 2010 or Excel 2007</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="da459-316">要約</span><span class="sxs-lookup"><span data-stu-id="da459-316">Summary</span></span>

<span data-ttu-id="da459-317">帯域幅使用率アナライザーは、ネットワーク経由で UC トラフィックのオーディオ帯域幅の使用率をプロットするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="da459-317">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="da459-318">このツールを使用して、ネットワーク上のビデオ帯域幅の使用状況を報告することもできます。</span><span class="sxs-lookup"><span data-stu-id="da459-318">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

</div>

</div>

<div>

## <a name="call-parkometer"></a><span data-ttu-id="da459-319">コール Par・メータ計</span><span class="sxs-lookup"><span data-stu-id="da459-319">Call Parkometer</span></span>

<span data-ttu-id="da459-320">Call Par・ m は、コールパークオービットデータベースへの簡単なアクセスを提供するコマンドラインアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="da459-320">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-321">説明</span><span class="sxs-lookup"><span data-stu-id="da459-321">Description</span></span>

<span data-ttu-id="da459-322">Call Par・メータは、現在パークされている通話を追跡するためのツールです。</span><span class="sxs-lookup"><span data-stu-id="da459-322">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="da459-323">また、オービットおよびコールパークサーバー (CPS) の使用状況に関する統計を収集します。</span><span class="sxs-lookup"><span data-stu-id="da459-323">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="da459-324">このコマンドラインツールを使用すると、ローカルまたはリモートで接続されているコンピューターから、CPS による SQL Server データベースの読み取りおよび書き込みアクセスの両方を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="da459-324">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="da459-325">すべてのオプションは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="da459-325">All options are mutually exclusive.</span></span> <span data-ttu-id="da459-326">コマンドラインの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="da459-326">Command-line syntax is as follows:</span></span>

  - <span data-ttu-id="da459-327">**– o** パラメーター-このプールに構成されているすべてのオービット範囲を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-327">**–o** parameter—lists all orbit ranges configured for this pool.</span></span>

  - <span data-ttu-id="da459-328">**– n** パラメーター-このプールで現在使用されているすべてのオービットを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-328">**–n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="da459-329">表示される情報は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="da459-329">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="da459-330">Parkee および parker の SIP Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="da459-330">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
      - <span data-ttu-id="da459-331">通話が保留されている CPS のホスト名。</span><span class="sxs-lookup"><span data-stu-id="da459-331">Host name of the CPS where the call is parked.</span></span>
    
      - <span data-ttu-id="da459-332">通話が保留された時点のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="da459-332">Time stamp of when the call was parked.</span></span>

  - <span data-ttu-id="da459-333">**– f** パラメーター-プール内の現在の空きオービットの数を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-333">**–f** parameter—lists the number of currently free orbits in the pool.</span></span>

  - <span data-ttu-id="da459-334">\*\*– r \<n\> \*\*パラメーター—最後に保留された通話を一覧表示し \<n\> ます。</span><span class="sxs-lookup"><span data-stu-id="da459-334">**–r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="da459-335">表示される情報は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="da459-335">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="da459-336">Parkee SIP URI。</span><span class="sxs-lookup"><span data-stu-id="da459-336">Parkee SIP URI.</span></span>
    
      - <span data-ttu-id="da459-337">Parker SIP URI。</span><span class="sxs-lookup"><span data-stu-id="da459-337">Parker SIP URI.</span></span>
    
      - <span data-ttu-id="da459-338">呼び出しがパークされた CPS のホスト名。</span><span class="sxs-lookup"><span data-stu-id="da459-338">Host name of the CPS where the call was parked.</span></span>
    
      - <span data-ttu-id="da459-339">呼び出しが取得または削除された時点のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="da459-339">Time stamp of when the call was retrieved or dropped.</span></span>

  - <span data-ttu-id="da459-340">\*\*-t \<n\> \*\*パラメーター-データベース内でオービットを予約して、割り当てられたオービット数のランダム性を示すテストを行います。</span><span class="sxs-lookup"><span data-stu-id="da459-340">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="da459-341">出力</span><span class="sxs-lookup"><span data-stu-id="da459-341">Output</span></span>

<span data-ttu-id="da459-342">コマンドプロンプトで指定された入力パラメーターに応じて、Call Par・メータは次の出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-342">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

  - <span data-ttu-id="da459-343">このプールに対して構成されているすべてのオービット範囲</span><span class="sxs-lookup"><span data-stu-id="da459-343">All orbit ranges that are configured for this pool</span></span>

  - <span data-ttu-id="da459-344">現在パークされている通話</span><span class="sxs-lookup"><span data-stu-id="da459-344">Currently parked calls</span></span>

  - <span data-ttu-id="da459-345">空き (利用可能な) オービットの数</span><span class="sxs-lookup"><span data-stu-id="da459-345">Number of free (available) orbits</span></span>

  - <span data-ttu-id="da459-346">最近パークされた通話</span><span class="sxs-lookup"><span data-stu-id="da459-346">Recently parked calls</span></span>

  - <span data-ttu-id="da459-347">オービットは、一様でランダムなオービットの値をテストするために予約されています</span><span class="sxs-lookup"><span data-stu-id="da459-347">Reserved orbits for testing uniform and random orbit values</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="da459-348">用途</span><span class="sxs-lookup"><span data-stu-id="da459-348">Purpose</span></span>

<span data-ttu-id="da459-349">CPS ツールの目的は、CPS データベースへのコマンドラインアクセスを提供することです。</span><span class="sxs-lookup"><span data-stu-id="da459-349">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="da459-350">管理者は、CPS の使用状況を表示して、プールに割り当てられているオービットの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="da459-350">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="da459-351">要件</span><span class="sxs-lookup"><span data-stu-id="da459-351">Requirements</span></span>

<span data-ttu-id="da459-352">このツールを CPS を実行しているのと同じコンピューターで実行する場合、要件はありません。</span><span class="sxs-lookup"><span data-stu-id="da459-352">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="da459-353">このツールをリモートコンピューターで実行する場合は、Lync Server 2013 で使用される SQL Server データベースがリモートアクセスを許可するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-353">If this tool is run on a remote computer, the SQL Server database used by Lync Server 2013 must be configured to allow remote access.</span></span> <span data-ttu-id="da459-354">プールの SQL Server に接続するには、SQL Server データベース接続文字列を使用して、呼び出し Par・メータを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-354">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool’s SQL Server.</span></span> <span data-ttu-id="da459-355">この SQL Server データベースの接続文字列は、構成ファイルで定義されています **parkometer.exe.config**。parkometer.exe が配置されているのと同じディレクトリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-355">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="da459-356">次の XML ファイルは、parkometer.exe.config の例です。構成する必要があるパラメーターは、ユーザー名 (たとえば、mydomain \\ Administrator)、パスワード (mypassword など)、ホスト名 (たとえば、myserver) です。</span><span class="sxs-lookup"><span data-stu-id="da459-356">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
       <add key="SQL" value="server=myserver\RTC;
    database=cpsdyn;
    User Id=mydomain\Administrator;
    Password=mypassword.;
    Integrated Security=false;"/>
      </appSettings>
    </configuration>
```

</div>

<div>

## <a name="examples"></a><span data-ttu-id="da459-357">例</span><span class="sxs-lookup"><span data-stu-id="da459-357">Examples</span></span>

<span data-ttu-id="da459-358">展開されるオービット範囲: – o パラメーターは、このプールに構成されているすべてのオービット範囲を表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-358">Deployed orbit ranges: the –o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

<span data-ttu-id="da459-359">![呼び出し Par・メータメーターのオービット範囲。](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "呼び出し Par・メータメーターのオービット範囲。")</span><span class="sxs-lookup"><span data-stu-id="da459-359">![Orbit ranges in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbit ranges in Call Parkometer.")</span></span>

<span data-ttu-id="da459-360">現在パークされている通話: – n パラメーターは、このプールで現在使用されているすべてのオービットを示しています。</span><span class="sxs-lookup"><span data-stu-id="da459-360">Currently parked calls: the –n parameter lists all currently used orbits on this pool as shown</span></span>

<span data-ttu-id="da459-361">![Call Parm の現在パークされている通話。](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Call Parm の現在パークされている通話。")</span><span class="sxs-lookup"><span data-stu-id="da459-361">![Currently-parked calls in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Currently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="da459-362">空きオービットの数: – f パラメーターには、プール内の現在の空きオービットの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="da459-362">Number of free orbits: the –f parameter lists the number of currently free orbits in the pool as shown</span></span>

<span data-ttu-id="da459-363">![Free オービット in Call Parm。](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free オービット in Call Parm。")</span><span class="sxs-lookup"><span data-stu-id="da459-363">![Free orbits in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free orbits in Call Parkometer.")</span></span>

<span data-ttu-id="da459-364">最近パークされた通話: – r パラメーターは、次 \<n\> に示すように、最後に保留された呼び出しを示します。 \<n\></span><span class="sxs-lookup"><span data-stu-id="da459-364">Recently parked calls: the –r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

<span data-ttu-id="da459-365">![Call Parm の最近パークされた通話。](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Call Parm の最近パークされた通話。")</span><span class="sxs-lookup"><span data-stu-id="da459-365">![Recently-parked calls in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Recently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="da459-366">テストオービット予約: – t パラメーターは、次のよう \<n\> に、データベースでオービットを予約します。</span><span class="sxs-lookup"><span data-stu-id="da459-366">Test orbit reservation: the –t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

<span data-ttu-id="da459-367">![Call Parm でオービット予約をテストします。](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Call Parm でオービット予約をテストします。")</span><span class="sxs-lookup"><span data-stu-id="da459-367">![Test orbit reservations in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test orbit reservations in Call Parkometer.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="da459-368">要約</span><span class="sxs-lookup"><span data-stu-id="da459-368">Summary</span></span>

<span data-ttu-id="da459-369">Call Par・ m は、コールパークサーバーに関する詳細情報を提供するコマンドラインツールです。</span><span class="sxs-lookup"><span data-stu-id="da459-369">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a><span data-ttu-id="da459-370">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="da459-370">CleanupStorageServiceData</span></span>

<span data-ttu-id="da459-371">CleanupStorageServiceData リソースキットツールを使用すると、Lync Server Storage Service で使用するデータベースから孤立したデータを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="da459-371">The CleanupStorageServiceData resource kit tool allows for deleting of orphaned data from the database used by the Lync Server Storage Service (LYSS).</span></span> <span data-ttu-id="da459-372">ストレージサービスの1つの機能は、Lync Server と、SQL Server や Exchange などのさまざまなバックエンドデータストレージエンドポイントとの間の通信をバッファリングすることです。</span><span class="sxs-lookup"><span data-stu-id="da459-372">One function of the storage service is to buffer communication between Lync Server and various back-end data storage endpoints, like SQL Server and Exchange.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-373">説明</span><span class="sxs-lookup"><span data-stu-id="da459-373">Description</span></span>

<span data-ttu-id="da459-374">高可用性をサポートするために、明示的にはプール内の複数のフロントエンドサーバーにデータのコピーを受け取り、保存します。このデータは、最終的な長期保存場所に配信された後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="da459-374">To support high availability, LYSS accepts and saves copies of the data on multiple front end servers in the pool temporarily, and removes that data once it has been delivered to its final long-term storage location.</span></span> <span data-ttu-id="da459-375">通常どおりに動作しない場合、サーバーがクラッシュしたり、処理上の問題が発生したり、一部のデータが正しくクリーンアップされなかったりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="da459-375">There are unusual situations which may occur during otherwise normal operation, when a server might crash or experience a processing issue, and some data might not get cleaned up properly.</span></span> <span data-ttu-id="da459-376">このデータは無害ですが、制限された処理リソースを消費します。</span><span class="sxs-lookup"><span data-stu-id="da459-376">This data is harmless, but it does consume limited processing resources.</span></span> <span data-ttu-id="da459-377">通常必要なデータ保守の多くは自動化されていますが、このツールを使用すると、自動削除を実行できない場合に孤立したデータの安全な識別と削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="da459-377">Much of the normal required data maintenance is automated, but this tool allows for the safe identification and removal of such orphaned data when automated removal is not possible.</span></span> <span data-ttu-id="da459-378">このツールの使用は、health monitoring System Center Operations Manager (SCOM) アラートが発生したときに表示されます。この警告は、管理者がプール内のローカルの "SS" データベースから不要なデータを削除することを確認します。</span><span class="sxs-lookup"><span data-stu-id="da459-378">Usage of this tool is indicated when a health monitoring System Center Operations Manager (SCOM) alert is raised which asks the administrator to remove the unneeded data from the local LYSS databases in the pool.</span></span> <span data-ttu-id="da459-379">フロントエンドのイベントログには、アラートをトリガーした対応するイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="da459-379">There will be a corresponding event in the event log on the front end which triggered the alert.</span></span> <span data-ttu-id="da459-380">イベントの詳細には、フロントエンドに含まれる孤立したデータ量に関する情報が含まれ、そのデータが特定の事前決定しきい値を超えると発生します。</span><span class="sxs-lookup"><span data-stu-id="da459-380">The event details will contain information about the amount of orphaned data contained on the front end, and is raised when that data exceeds certain pre-determine thresholds</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="da459-381">要件</span><span class="sxs-lookup"><span data-stu-id="da459-381">Requirements</span></span>

<span data-ttu-id="da459-382">Lync Server 2013、リソースキットツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="da459-382">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="da459-383">このツールは、Lync Server および Lync Server 2013 管理シェルがインストールされているドメインに参加しているコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="da459-383">The tool runs on domain-joined machines where Lync Server and Lync Server 2013 Management Shell are installed.</span></span> <span data-ttu-id="da459-384">このツールは、管理シェルのコマンドレットを使用して、プール内のすべてのフロントエンドサーバーを識別します。</span><span class="sxs-lookup"><span data-stu-id="da459-384">The tool uses a cmdlet from the management shell to identify all Front End servers in the pool.</span></span> <span data-ttu-id="da459-385">2番目に、このツールは、 **Rtclocal** データベースがインストールされているプール内のコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-385">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="da459-386">このデータベースは、Lync Server ルーティングサービスと通信するために必要な接続の詳細を取得するために、CleanupStorageServiceData ツールによって使用されます。最後に、ツールを呼び出しているアカウントまたは資格情報が、出力ログの書き込み先のファイル共有に対する読み取り/書き込みアクセス許可を持っている必要があります。また、このツールはプールが安定した状態にあることに依存します。</span><span class="sxs-lookup"><span data-stu-id="da459-386">This database is used by the CleanupStorageServiceData tool to get the connection details needed to communicate with the Lync Server Routing Service.Finally, the account or credential invoking the tool must have read/write permission to the file share to which they want to write the output log.Also, this tool depends on the pool being in a stable state.</span></span> <span data-ttu-id="da459-387">基本的には、すべてのフロントエンドサーバーが稼働していることが予想され、SQL Server の LYNCLOCAL インスタンスと、その後の SS データベースはに接続できる必要があります。各ルーティンググループには、1つのプライマリフロントエンドサーバーと2台のセカンダリフロントエンドサーバーのセットが必要です。</span><span class="sxs-lookup"><span data-stu-id="da459-387">In essence this means that every Front End server is expected to be up and running, the SQL Server LYNCLOCAL instance and LYSS database must be able to be connected to, and each routing group must have a complete set of 1 primary Front End servers and 2 secondary Front End servers.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="da459-388">例</span><span class="sxs-lookup"><span data-stu-id="da459-388">Examples</span></span>

<span data-ttu-id="da459-389">C: \\ Program Files \\ Microsoft Lync Server 2013 \\ うえ \\ storageservice \> ImportStorageServiceData.exe</span><span class="sxs-lookup"><span data-stu-id="da459-389">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe</span></span>

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a><span data-ttu-id="da459-390">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="da459-390">DBAnalyze</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-391">説明</span><span class="sxs-lookup"><span data-stu-id="da459-391">Description</span></span>

<span data-ttu-id="da459-392">DBAnalyze は、管理者が Lync Server 2013 データベースに関する分析レポートを収集するのに役立つコマンドラインツールです。</span><span class="sxs-lookup"><span data-stu-id="da459-392">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Lync Server 2013 databases.</span></span> <span data-ttu-id="da459-393">DBAnalyze には、診断、ユーザーデータ、会議、Mcu、ディスクの断片化という次のモードがあります。</span><span class="sxs-lookup"><span data-stu-id="da459-393">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

  - <span data-ttu-id="da459-394">**診断モード**    テーブル (レコード数、断片化、データサイズ、およびインデックスサイズ) に関する情報を含むレポートを作成します。データおよびログファイルのサイズ、最新のバックアップ時間、Microsoft Office Communications Server を実行しているサーバー間の連絡先配分、アクセス許可の平均数、連絡先、コンテナー、サブスクリプション、発行、ユーザーごとのエンドポイント、ルーティングできないユーザー、ユーザーごとに開催された会議の平均数、会議の予定、アクティブな会議、およびデータベースバージョン。</span><span class="sxs-lookup"><span data-stu-id="da459-394">**Diagnostic mode**   Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can’t be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da459-395">診断モードを実行すると、サーバーのパフォーマンスに影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da459-395">Running diagnostic mode can affect server performance.</span></span>

    
    </div>

  - <span data-ttu-id="da459-396">**ユーザーデータモード**  指定されたユーザーまたはそのユーザーの連絡先およびアクセス許可の一覧に、連絡先、コンテナー、サブスクリプション、パブリケーション、アクセス許可、および連絡先グループのデータを報告します。</span><span class="sxs-lookup"><span data-stu-id="da459-396">**User data mode**  Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="da459-397">このモードでは、ユーザーが開催または招待されている会議の概要データも報告します。</span><span class="sxs-lookup"><span data-stu-id="da459-397">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

  - <span data-ttu-id="da459-398">**電話会議モード**    会議のすべてのスケジュール時の詳細、招待者リスト、会議に使用できるメディアの種類の一覧、アクティブな Mcu (multipoint control unit)、アクティブな参加者の一覧、各参加者の信号状態など、特定の会議の詳細データを報告します。</span><span class="sxs-lookup"><span data-stu-id="da459-398">**Conference mode**   Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant’s signaling state.</span></span>

  - <span data-ttu-id="da459-399">**会議 ID**    のデコード **/Pstnid**スイッチで指定された公衆交換電話網 (PSTN) の会議 ID をデコードしますが、バックエンドには接続せずに詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="da459-399">**Decode Meeting ID**  Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

  - <span data-ttu-id="da459-400">**電話会議**     を解決する **/Pstnid**スイッチで指定されている PSTN 会議 ID をデコードし、id で示される電話会議に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-400">**Resolve conference**   Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

  - <span data-ttu-id="da459-401">**Mcu モード**   プール内の各 MCU の ID、メディアの種類、URL、ハートビートの状態、会議の負荷、参加者の負荷などのレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="da459-401">**MCUs mode**  Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

  - <span data-ttu-id="da459-402">**ディスク断片化モード**   すべてのディスクの断片化状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-402">**Disk fragmentation mode**  Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="da459-403">このツールを使用すると、さまざまな問題を診断したり、管理者が容量計画を支援したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="da459-403">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="da459-404">たとえば、サーバー A に所属するほとんどのユーザーが、連絡先として server B に所属するユーザーを選択すると、管理者はサーバー A のユーザーをサーバー B に移動して、サーバー間のトラフィックを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="da459-404">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="da459-405">出力</span><span class="sxs-lookup"><span data-stu-id="da459-405">Output</span></span>

<span data-ttu-id="da459-406">このツールは、Lync Server 2013 データベースに関する定義済みレポートを出力します。</span><span class="sxs-lookup"><span data-stu-id="da459-406">This tool outputs predefined reports about the Lync Server 2013 database.</span></span> <span data-ttu-id="da459-407">**パス:** % ProgramFiles% \\ Microsoft Lync Server 2013 \\ うえ</span><span class="sxs-lookup"><span data-stu-id="da459-407">**Path:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="da459-408">用途</span><span class="sxs-lookup"><span data-stu-id="da459-408">Purpose</span></span>

<span data-ttu-id="da459-409">Dbanalyze.exe をインストールするには、ローカルフォルダーにコピーしてからツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="da459-409">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="da459-410">このツールを使用するには、コマンドラインから次のコマンドを実行します。`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span><span class="sxs-lookup"><span data-stu-id="da459-410">To use the tool, run the following command from the command line.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span></span> <span data-ttu-id="da459-411">コマンドラインオプションの説明を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="da459-411">The descriptions for the command-line options are shown below.</span></span>

<span data-ttu-id="da459-412">![Dbanalyze.exe のコマンドラインオプション。](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Dbanalyze.exe のコマンドラインオプション。")</span><span class="sxs-lookup"><span data-stu-id="da459-412">![Command line options for Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Command line options for Dbanalyze.exe.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="da459-413">要件</span><span class="sxs-lookup"><span data-stu-id="da459-413">Requirements</span></span>

<span data-ttu-id="da459-414">**コンピューター** DBAnalyze は、Lync Server 2013 がインストールされているドメインに参加しているコンピューターからのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="da459-414">**Computer** DBAnalyze can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span>

<span data-ttu-id="da459-415">**ネットワーク** コンピューターは、バックエンドデータベースに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-415">**Network** The computer should be able to connect to the back-end database.</span></span>

<span data-ttu-id="da459-416">**ソフトウェア** DBAnalyze を実行する前に、Lync Server 2013 ソフトウェアコンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-416">**Software** Lync Server 2013 software components must be installed before running DBAnalyze.</span></span>

<span data-ttu-id="da459-417">**ユーザー**次の表は、Lync Server 2013 データベースへのアクセスに必要なアクセス許可を持つ管理者を示しています。</span><span class="sxs-lookup"><span data-stu-id="da459-417">**Users**The table below shows the administrators who have the necessary permissions to access Lync Server 2013 databases.</span></span>

<span data-ttu-id="da459-418">![Dbanalyze.exe のアクセス許可の表。](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Dbanalyze.exe のアクセス許可の表。")</span><span class="sxs-lookup"><span data-stu-id="da459-418">![Permissions table for Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Permissions table for Dbanalyze.exe.")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da459-419"><STRONG>/Report: disk</STRONG> mode では、ローカル管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="da459-419">A local administrator account is required for <STRONG>/report:disk</STRONG> mode.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="da459-420">例</span><span class="sxs-lookup"><span data-stu-id="da459-420">Examples</span></span>

<span data-ttu-id="da459-421">有効な Dbanalyze.exe コマンドの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da459-421">The following are examples of valid Dbanalyze.exe commands:</span></span>

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a><span data-ttu-id="da459-422">要約</span><span class="sxs-lookup"><span data-stu-id="da459-422">Summary</span></span>

<span data-ttu-id="da459-423">DBAnalyzer を使用すると、管理者は Lync Server 2013 データベースをすばやく簡単に分析することができます。</span><span class="sxs-lookup"><span data-stu-id="da459-423">DBAnalyzer provides administrators a quick and easy to analyze Lync Server 2013 databases.</span></span>

</div>

</div>

<div>

## <a name="importstorageservicedata"></a><span data-ttu-id="da459-424">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="da459-424">ImportStorageServiceData</span></span>

<span data-ttu-id="da459-425">ImportStorageServiceData リソースキットツールを使用すると、ストレージサービス (一から) にフラッシュされたキューおよびエンドポイントデータをストレージサービスに再インポートできます。</span><span class="sxs-lookup"><span data-stu-id="da459-425">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-426">説明</span><span class="sxs-lookup"><span data-stu-id="da459-426">Description</span></span>

<span data-ttu-id="da459-427">ストレージサービスからフラッシュされたデータは、キューアイテムの状態またはデータベースサイズに基づいて、定期的に自動 (定期的) になっている場合があります。</span><span class="sxs-lookup"><span data-stu-id="da459-427">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="da459-428">プールフェールオーバーコマンドレットを手動で起動したか、または StorageServiceFullFlush コマンドレット (プールフェールオーバーコマンドレットによって起動される) が発生したことが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da459-428">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="da459-429">フロントエンドのデータベースサイズが通常のレベルより上にある場合は、データのエクスポートが多くなる可能性があるため、データを再インポートするのが理想的ではないことに注意してください。さらに、ストレージサービスキューを拡張する原因となったエラーに寄与する可能性がある問題は、最初に解決する必要があります (たとえば、Exchange エンドポイントのエラー、ネットワークの問題、またはその他の問題)。</span><span class="sxs-lookup"><span data-stu-id="da459-429">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

<span data-ttu-id="da459-430">**シナリオ 1:** プールのフェールオーバー中は、フロントエンドごとに記憶域サービスからファイルがフラッシュされることがあります。</span><span class="sxs-lookup"><span data-stu-id="da459-430">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="da459-431">フェールオーバーが完了したら、データを再インポートするためにツールを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-431">After failover is completed, the tool should be run to re-import the data.</span></span>

<span data-ttu-id="da459-432">**シナリオ 2:** データが毎日自動的にフラッシュされるか、特定のサイズのしきい値を超える記憶域サービスデータベースに対する応答として (たとえば、60%、80%、90% がいっぱい)。</span><span class="sxs-lookup"><span data-stu-id="da459-432">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="da459-433">この自動フラッシュされたデータは、管理者が定期的に再インポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-433">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="da459-434">上記の状況では、monitoring SCOM pack が展開されていない場合、ストレージサービスからフラッシュされるデータに関連する Lync Server ストレージサービスのイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="da459-434">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Lync Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="da459-435">32075のイベント Id (完全なフラッシュ操作が開始)、32076 (完全フラッシュの完了)、32082 (メンテナンスレベルのフラッシュが開始されました)、32083 (メンテナンスレベルのフラッシュが完了)、32089 (データベースの容量がいっぱいになったため、フラッシュが発生しました)。</span><span class="sxs-lookup"><span data-stu-id="da459-435">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="da459-436">メモこれらのイベント Id は RTM リリースに対応しています。</span><span class="sxs-lookup"><span data-stu-id="da459-436">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="da459-437">管理者にこれらのイベントが表示される場合は、フラッシュアウトされたファイルがあることを意味します。このデータは、たとえば1週間に1回、このツールを使用して定期的にインポートして戻します。</span><span class="sxs-lookup"><span data-stu-id="da459-437">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="da459-438">オンラインサービスリリースの場合、Lync Server 用の health monitoring SCOM pack が展開されていると、新しい通知が発生する可能性があります。これにより、フラッシュされたデータをストレージサービスに再インポートするように管理者に要求することができます。</span><span class="sxs-lookup"><span data-stu-id="da459-438">For the Online Service release, if health monitoring SCOM pack for Lync Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="da459-439">アラートをトリガーしたフロントエンドサーバーのイベントログに、対応するイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da459-439">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="da459-440">このイベントは、フラッシュされたデータファイルが配置されている親のパスの説明と、通知の条件に一致するファイルの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="da459-440">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="da459-441">通知の条件は、特定の親パスの下に X 個以上のファイルが存在することを示しています (X と Y は、StorageService 内で事前設定されていますが、APPCONFIG ファイルを変更することで上書きできます)。状態アラートをトリガーできるイベントの2つの例を次に示します。その違いは親パスです。</span><span class="sxs-lookup"><span data-stu-id="da459-441">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="da459-442">Web サービスのファイル共有の下にある可能性がありますが、もう1つの可能性は各フロントエンドのローカルアプリケーションデータディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="da459-442">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="da459-443">(たとえば c: \\ProgramData \\ Microsoft \\ Lync Server \\ storageservice)。</span><span class="sxs-lookup"><span data-stu-id="da459-443">( for example c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ).</span></span> <span data-ttu-id="da459-444">その後、管理者はこのうえツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="da459-444">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="da459-445">このツールを実行すると、ツールが実行されたフロントエンドがデータを所有していない場合でも、このツールを実行しているフロントエンドの CPU および IO 負荷が増加します。</span><span class="sxs-lookup"><span data-stu-id="da459-445">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="da459-446">このツールは、フロントエンドの CPU および IO 負荷が高い場合 (ピーク時間外など) に、このツールを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da459-446">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="da459-447">2番目に、このツールは、1つのデータファイルをインポートするのに 2 ~ 3 分間かかります。</span><span class="sxs-lookup"><span data-stu-id="da459-447">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="da459-448">ツールの実行時間を見積もる場合は、この点に留意してください。ツールによって生成される詳細ログファイルは、既定でファイルストアに表示されます。</span><span class="sxs-lookup"><span data-stu-id="da459-448">Keep this in mind when estimating how long tool will be running.The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="da459-449">エラーが報告されなかった場合は、ログファイルの数が数 MB 以上になる可能性があるので、削除します。</span><span class="sxs-lookup"><span data-stu-id="da459-449">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

<span data-ttu-id="da459-450">![ストレージサーバーイベントログイベントのサンプル](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "ストレージサーバーイベントログイベントのサンプル")</span><span class="sxs-lookup"><span data-stu-id="da459-450">![Sample Storage Server event log events.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Sample Storage Server event log events.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="da459-451">要件</span><span class="sxs-lookup"><span data-stu-id="da459-451">Requirements</span></span>

<span data-ttu-id="da459-452">Lync Server 2013、リソースキットツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="da459-452">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="da459-453">このツールは、Lync Server および Lync Server 管理シェルがインストールされているドメインに参加しているコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="da459-453">The tool runs on domain-joined machines where Lync Server and Lync Server Management Shell are installed.</span></span> <span data-ttu-id="da459-454">このツールは、管理シェルのコマンドレットを使用して、プール内のすべてのフロントエンドサーバーを識別します。</span><span class="sxs-lookup"><span data-stu-id="da459-454">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="da459-455">2番目に、このツールは、 **Rtclocal** データベースがインストールされているプール内のコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-455">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="da459-456">このデータベースは、ツールによって、プールの WEBSERVICE ファイル共有の場所を取得するために使用されます。さらに、ツールを使用する前に、各フロントエンドサーバーで、 **enable-psremoting** を使用して Windows PowerShell リモート処理を有効にする必要があります。また、各フロントエンドサーバーでは、そのツールが実行されているコンピューターを使用します。</span><span class="sxs-lookup"><span data-stu-id="da459-456">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="da459-457">それ以外の場合、このツールのリモート Windows PowerShell コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="da459-457">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="da459-458">Windows PowerShell リモート処理は、プール内のすべてのフロントエンドサーバーで、完了後にオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="da459-458">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="da459-459">最後に、ツールを呼び出すアカウントまたは資格情報が、このツールを実行するプールの webservice ファイル共有に対する読み取り/書き込みアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-459">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="da459-460">それ以外の場合、I/O アクセス許可エラーが発生してもツールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="da459-460">Otherwise the tool will fail with IO Permission errors.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da459-461">Windows Server 2012 では、windows PowerShell リモート処理は既定で有効になっていますが、Windows Server 2008 オペレーティングシステムでは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="da459-461">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="da459-462">例</span><span class="sxs-lookup"><span data-stu-id="da459-462">Examples</span></span>

    >  C:\StorageService>ImportStorageServiceData.exe
    Description:
    This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
    Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
    Additional Options:
    -Verbose                    : Turn verbose output on.
    
    -StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )
                                        
    -FileSharePath              : Import only all data from just under the UNC path specified.
    
    ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
    Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
    Using NetNamedPipeBinding...
    OnTopologyChanged Event received
    Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService
    
    Front Ends:
    server.vdomain.com
    server2.vdomain.com
    server1.vdomain.com
    server3.vdomain.com
    Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
    # Files found: 8
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    Items deserialized: 20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
    3832e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
    86684d3832e4__0.xml
    
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
    ain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
    287dd6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
    b46a42287dd6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
    d251e6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
    e08a15d251e6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
    17c220__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
    949ff817c220__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
    6d5317__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
    749be66d5317__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
    86b565__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
    657eda86b565__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
    All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
    vices-1\StorageService
    Importing files for: server.vdomain.com
    No files founds.
    Importing files for: server2.vdomain.com
    No files founds.
    Importing files for: server1.vdomain.com
    No files founds.
    Importing files for: server3.vdomain.com
    No files founds.
    Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
    Log20120910_1609SS
    Tool has finished execution.
    >  C:\StorageService>

</div>

</div>

<div>

## <a name="lcssync"></a><span data-ttu-id="da459-463">LCSSync</span><span class="sxs-lookup"><span data-stu-id="da459-463">LCSSync</span></span>

<span data-ttu-id="da459-464">LCSSync ツールは、Lync Server 2013 communications software を複数フォレスト環境に展開するのに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="da459-464">The LCSSync tool helps to deploy Lync Server 2013 communications software in a multi-forest environment.</span></span> <span data-ttu-id="da459-465">このツールは、異なるユーザーフォレストのユーザーおよびグループを、Active Directory ドメインサービスの連絡先オブジェクトとして、Lync Server 2013 がインストールされている中央フォレストに同期するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="da459-465">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Lync Server 2013 is installed.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-466">説明</span><span class="sxs-lookup"><span data-stu-id="da459-466">Description</span></span>

<span data-ttu-id="da459-467">LCSSync は、中央フォレストにある同期された Active Directory ドメインサービスの連絡先オブジェクトを使用して、Lync Server に対してユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="da459-467">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Lync Server.</span></span> <span data-ttu-id="da459-468">シングルサインオンを提供するには、プライマリユーザーアカウントを、Lync Server 2013 の中央フォレストの Active Directory ドメインサービスの連絡先オブジェクトにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-468">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Lync Server 2013.</span></span> <span data-ttu-id="da459-469">このツールは、そのマッピングを実行するのに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="da459-469">This tool helps perform that mapping.</span></span> <span data-ttu-id="da459-470">このツールには、Microsoft Identity Integration Server で管理エージェントを作成するためのテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="da459-470">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="da459-471">要約</span><span class="sxs-lookup"><span data-stu-id="da459-471">Summary</span></span>

<span data-ttu-id="da459-472">LCSSync ツールは、マルチフォレスト環境に Lync Server を展開するのに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="da459-472">The LCSSync tool helps to deploy Lync Server in a multi-forest environment.</span></span>

</div>

</div>

<div>

## <a name="lookupuserconsole"></a><span data-ttu-id="da459-473">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="da459-473">LookupUserConsole</span></span>

<span data-ttu-id="da459-474">LookupUserConsole ツールは、特定のユーザーに関する内部 Lync Server ルーティング情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-474">The LookupUserConsole tool displays internal Lync Server routing information about specific users.</span></span> <span data-ttu-id="da459-475">この情報は、Microsoft サポートの個人が展開とルーティングの問題を診断するのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="da459-475">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-476">説明</span><span class="sxs-lookup"><span data-stu-id="da459-476">Description</span></span>

<span data-ttu-id="da459-477">LookupUserConsole.exe を実行すると、SIP アドレスを受け付け、それらに関連する内部 Lync Server ルーティング情報の表示を試みるコマンドプロンプトが開きます。</span><span class="sxs-lookup"><span data-stu-id="da459-477">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Lync Server routing information relating them.</span></span> <span data-ttu-id="da459-478">「 **Exit** 」と入力して、LookupUserConsole ツールを終了します。</span><span class="sxs-lookup"><span data-stu-id="da459-478">Type **exit** to quit the LookupUserConsole tool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="da459-479">要件</span><span class="sxs-lookup"><span data-stu-id="da459-479">Requirements</span></span>

<span data-ttu-id="da459-480">Lync Server 2013、リソースキットツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="da459-480">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="da459-481">このツールは、Lync Server がインストールされているドメインに参加しているコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="da459-481">The tool runs on domain-joined machines where Lync Server is installed</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="da459-482">例</span><span class="sxs-lookup"><span data-stu-id="da459-482">Examples</span></span>

<span data-ttu-id="da459-483">C: \\ Program Files \\ Microsoft Lync Server 2013 \\ うえ \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="da459-483">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe</span></span>

    > sip:john.doe@vdomain.com
    
      Execution time (ms):                            171.094
      Exeuction result:                               Success
      SIP URI:                                        sip:john.doe@vdomain.com
      User info:
        SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
        Grouping ID:                                  00000000-0000-0000-0000-...
        Line URI:                                     <null>
        Policy assignment:                            TenantId={00000000--0000-000....
        SIP enabled:                                  True
        UC enabled:                                   False
        Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
        Active cluster:                               pool0.vdomain.com
        Backup registrar cluster:                     <null>
        Deployment location:                          <null>
        Home Front-End FQDN:                          SERVER.vdomain.com
        Primary Registrar cluster:                    pool0.vdomain.com
        Remote Director external SIP FQDN:            <null>
        Remote Director internal SIP FQDN:            <null>
        Remote Director Web FQDN:                     <null>
        Routing group ID:                             4501e04e-ae48-5605-9346...
        Service tag ID:                               1266953005
        User Front-End resolved:                      True
        User in local forest:                         True
        User in remote forest:                        False
        User in split domain:                         False
        User-Services cluster:                        pool0.vdomain.com
    
    > sip:nouser@vdomain.com
    
      Execution time (ms):                            948.7574
      Exeuction result:                               UserDoesNotExist
    
    > exit

</div>

</div>

<div>

## <a name="msturnping"></a><span data-ttu-id="da459-484">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="da459-484">MsTurnPing</span></span>

<span data-ttu-id="da459-485">MSTurnPing ツールを使用すると、Microsoft Lync Server 2013 communications software の管理者は、音声ビデオエッジと音声ビデオ認証サービスを実行しているサーバーと、トポロジ内で帯域幅ポリシーサービスを実行しているサーバーの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="da459-485">The MSTurnPing tool allows an administrator of Microsoft Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-486">説明</span><span class="sxs-lookup"><span data-stu-id="da459-486">Description</span></span>

<span data-ttu-id="da459-487">MSTurnPing ツールを使用すると、Lync Server 2013 communications software の管理者は、音声ビデオエッジと音声ビデオ認証サービスを実行しているサーバーと、トポロジ内で帯域幅ポリシーサービスを実行しているサーバーの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="da459-487">The MSTurnPing tool allows an administrator of Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="da459-488">このツールを使用すると、管理者は次のテストを実行できます。</span><span class="sxs-lookup"><span data-stu-id="da459-488">The tool allows the administrator to perform the following tests:</span></span>

1.  <span data-ttu-id="da459-489">音声ビデオエッジサーバーテスト: このツールは、次の手順を実行して、トポロジ内のすべての音声ビデオエッジサーバーに対してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="da459-489">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="da459-490">Lync Server Audio/Video Authentication service が開始されており、適切な資格情報を発行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da459-490">Verifying that the Lync Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="da459-491">Lync Server 音声ビデオエッジサービスが開始されていることを確認し、外部エッジにリソースを正常に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="da459-491">Verifying that the Lync Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2.  <span data-ttu-id="da459-492">帯域幅ポリシーサービステスト: このツールは、次の手順を実行して、トポロジ内の帯域幅ポリシーサービスを実行しているすべてのサーバーに対してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="da459-492">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="da459-493">Lync Server 帯域幅ポリシーサービス (認証) が開始されており、適切な資格情報を発行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da459-493">Verifying that the Lync Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="da459-494">Lync Server 帯域幅ポリシーサービス (コア) が開始されており、帯域幅の確認を正常に実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da459-494">Verifying that the Lync Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="da459-495">このツールは、トポロジの一部であり、ローカルストアがインストールされているコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-495">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="da459-496">出力</span><span class="sxs-lookup"><span data-stu-id="da459-496">Output</span></span>

<span data-ttu-id="da459-497">ツールによって各操作の結果が出力されます。</span><span class="sxs-lookup"><span data-stu-id="da459-497">The tool outputs the results of each of the operations.</span></span>

  - <span data-ttu-id="da459-498">**AudioVideoEdgeServer**テストが実行された場合、ツールの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="da459-498">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="da459-499">トポロジで Lync Server 音声/ビデオ認証サービスを提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="da459-499">The test results of the computers that provide the Lync Server Audio/Video Authentication service in the topology</span></span>
    
      - <span data-ttu-id="da459-500">トポロジで Lync Server 音声ビデオエッジサービスを提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="da459-500">The test results of the computers that provide the Lync Server Audio/Video Edge service in the topology</span></span>

  - <span data-ttu-id="da459-501">**BandwidthPolicyServer**テストが実行された場合、ツールの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="da459-501">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="da459-502">トポロジで Lync Server 帯域幅ポリシーサービス (認証) を提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="da459-502">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Authentication) in the topology</span></span>
    
      - <span data-ttu-id="da459-503">トポロジで Lync Server 帯域幅ポリシーサービス (コア) を提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="da459-503">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Core) in the topology</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="da459-504">要件</span><span class="sxs-lookup"><span data-stu-id="da459-504">Requirements</span></span>

  - <span data-ttu-id="da459-505">このツールは、トポロジ内にあり、ローカルストアを持つコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-505">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

  - <span data-ttu-id="da459-506">このツールは、ローカルストアへのアクセス権を持つ管理者として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-506">The tool must be run as an administrator who has access to the local store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="da459-507">例</span><span class="sxs-lookup"><span data-stu-id="da459-507">Examples</span></span>

<span data-ttu-id="da459-508">ツール入力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da459-508">The following is an example of the tool input.</span></span>

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a><span data-ttu-id="da459-509">要約</span><span class="sxs-lookup"><span data-stu-id="da459-509">Summary</span></span>

<span data-ttu-id="da459-510">このツールは、Lync Server 2013 管理者にとって、音声ビデオおよび帯域幅ポリシーサービスを実行しているサーバーの状態を確認するのに役立つ、貴重なリソースになることがあります。</span><span class="sxs-lookup"><span data-stu-id="da459-510">This tool can be a valuable resource to Lync Server 2013 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a><span data-ttu-id="da459-511">ネットワーク構成ビューアー</span><span class="sxs-lookup"><span data-stu-id="da459-511">Network Configuration Viewer</span></span>

<span data-ttu-id="da459-512">ネットワーク構成ビューアーは、Microsoft Lync Server 2013 communications software 管理者が、指定された帯域幅容量に基づく音声またはビデオ通話などのリアルタイム通信セッションを許可するようにプロビジョニングされている企業の通話受付管理 (CAC) ネットワークトポロジを表示するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="da459-512">Network Configuration Viewer can be used by Microsoft Lync Server 2013 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="da459-513">Lync Server 2013 管理者は、Lync Server 2013 と共にインストールされる帯域幅ポリシーサービスによって適用される CAC ポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="da459-513">Lync Server 2013 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Lync Server 2013.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-514">説明</span><span class="sxs-lookup"><span data-stu-id="da459-514">Description</span></span>

<span data-ttu-id="da459-515">ネットワーク構成ビューアー (NetworkConfigurationViewer.exe) を使用すると、管理者は次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="da459-515">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

  - <span data-ttu-id="da459-516">Lync Server 2013 の展開からの CAC ネットワークトポロジを、グラフィカルな形式で読み込んで表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-516">Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format.</span></span>

  - <span data-ttu-id="da459-517">帯域幅ポリシーサーバーのログファイルから、画像形式で CAC ネットワークトポロジを読み込んで表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-517">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

  - <span data-ttu-id="da459-518">CAC ネットワークトポロジをディスク上の XML 形式で保存して保存します。</span><span class="sxs-lookup"><span data-stu-id="da459-518">Save and store CAC network topology in an XML format on the disk.</span></span>

  - <span data-ttu-id="da459-519">CAC ネットワークトポロジダイアグラムを JPG または BMP 形式で保存して保存します。</span><span class="sxs-lookup"><span data-stu-id="da459-519">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

  - <span data-ttu-id="da459-520">CAC ネットワークトポロジ構成データを表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-520">View CAC network topology configuration data.</span></span>

  - <span data-ttu-id="da459-521">ツリービュースタイルで CAC ネットワークトポロジを表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-521">View CAC network topology in a tree-view style.</span></span>

  - <span data-ttu-id="da459-522">CAC ネットワークトポロジリンク (たとえば、サイト間、地域間、サイト間リンクなど) 用のカスタムコネクタを定義してください。</span><span class="sxs-lookup"><span data-stu-id="da459-522">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

  - <span data-ttu-id="da459-523">CAC ネットワークトポロジサイト情報、地域情報、およびプロビジョニングされた帯域幅ポリシーとネットワークリンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-523">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="da459-524">用途</span><span class="sxs-lookup"><span data-stu-id="da459-524">Purpose</span></span>

<span data-ttu-id="da459-525">グラフィカルインターフェイスでエンタープライズ CAC ネットワークトポロジリンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-525">View enterprise CAC network topology links in a graphical interface.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="da459-526">例</span><span class="sxs-lookup"><span data-stu-id="da459-526">Examples</span></span>

<span data-ttu-id="da459-527">**Lync Server 2013 の展開からの CAC ネットワークトポロジを、次のようなグラフィカルな形式で読み込んで表示します。** Lync Server 2013 管理者は、次の図に示すように、[ **ネットワーク構成のダウンロード** ] オプションを使用して、任意の lync server 2013 コンピューター上の CAC ネットワークトポロジ構成をロードおよび表示できます。</span><span class="sxs-lookup"><span data-stu-id="da459-527">**Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format:** Lync Server 2013 administrators can load and view CAC network topology configuration on any Lync Server 2013 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="da459-528">このツールは、Lync 構成ストアに接続されていないコンピューターに展開された場合に、このような構成のダウンロードまたは表示に失敗します。</span><span class="sxs-lookup"><span data-stu-id="da459-528">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Lync configuration store.</span></span>

<span data-ttu-id="da459-529">![ネットワーク構成のダウンロード。](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "ネットワーク構成のダウンロード。")</span><span class="sxs-lookup"><span data-stu-id="da459-529">![Downloading the network configuration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Downloading the network configuration.")</span></span>

<span data-ttu-id="da459-530">**帯域幅ポリシーサーバーのログファイルから、画像形式で CAC ネットワークトポロジを読み込み、表示します。** Lync Server 2013 帯域幅ポリシーサーバー Lync Server 2013 ファイル共有の場所のログ機構の一部として、CAC ネットワークトポロジを保存します。</span><span class="sxs-lookup"><span data-stu-id="da459-530">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Lync Server 2013 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Lync Server 2013 file share location.</span></span> <span data-ttu-id="da459-531">Lync Server 管理者は、次に示すように、[ **Open Network Configuration** ] オプションを使用して、このようなファイルをグラフィカルな形式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="da459-531">Lync Server administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

<span data-ttu-id="da459-532">![帯域幅ポリシーサーバーのログファイルを開きます。](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "帯域幅ポリシーサーバーのログファイルを開きます。")</span><span class="sxs-lookup"><span data-stu-id="da459-532">![Opening a Bandwidth Policy Server log file.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Opening a Bandwidth Policy Server log file.")</span></span>

<span data-ttu-id="da459-533">CAC ネットワークトポロジをディスク上の XML 形式で保存および格納する: Lync Server 2013 管理者は、以下に示すように、[ **ネットワーク構成のコピーを保存** する] オプションを使用して cac ネットワークトポロジ構成ファイルを xml 形式で保存できます。</span><span class="sxs-lookup"><span data-stu-id="da459-533">Save and store CAC network topology in an XML format on the disk: Lync Server 2013 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="da459-534">保存した構成ファイルは、グラフィック表示のためにオフラインで使用できます。</span><span class="sxs-lookup"><span data-stu-id="da459-534">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

<span data-ttu-id="da459-535">![ネットワーク構成を XML ファイルとして保存します。](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "ネットワーク構成を XML ファイルとして保存します。")</span><span class="sxs-lookup"><span data-stu-id="da459-535">![Saving the network configuration as an XML file.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Saving the network configuration as an XML file.")</span></span>

<span data-ttu-id="da459-536">CAC ネットワークトポロジダイアグラムを JPG または BMP 形式で保存および格納する: Lync Server 2013 管理者は、以下に示すように、[ **ネットワーク構成ダイアグラムを画像として保存** する] オプションを使用して、cac ネットワークトポロジ構成をグラフィカルな形式 (JPG および bmp ファイル形式) で保存できます。</span><span class="sxs-lookup"><span data-stu-id="da459-536">Save and Store CAC network topology diagram in JPG or BMP format: Lync Server 2013 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

<span data-ttu-id="da459-537">![ネットワーク構成を画像として保存します。](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "ネットワーク構成を画像として保存します。")</span><span class="sxs-lookup"><span data-stu-id="da459-537">![Saving the network configuration as a picture.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Saving the network configuration as a picture.")</span></span>

<span data-ttu-id="da459-538">**CAC ネットワークトポロジ構成データを表示します。** Lync Server 2013 管理者は、以下に示すように、[ネットワーク構成データの表示] オプションを使用して、ネットワーク地域、ネットワークサイト、帯域幅プロファイル、およびサイトサブネットの IP アドレスなど、関連するネットワーク構成データをテキスト形式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="da459-538">**View CAC network topology configuration data:** Lync Server 2013 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

<span data-ttu-id="da459-539">![ネットワーク構成データを表示する。](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "ネットワーク構成データを表示する。")</span><span class="sxs-lookup"><span data-stu-id="da459-539">![Viewing network configuration data.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Viewing network configuration data.")</span></span>

<span data-ttu-id="da459-540">**ツリービュー形式の CAC ネットワークトポロジを表示します。** Lync Server 2013 管理者は、次に示すように、ツールウィンドウの左側にあるコントロールパネルを使用して、関連するネットワーク構成データをグラフィカルなツリービュースタイルで表示できます。</span><span class="sxs-lookup"><span data-stu-id="da459-540">**View CAC network topology in a tree-view style:** Lync Server 2013 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

<span data-ttu-id="da459-541">![ツリービューでのネットワーク構成データの表示。](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "ツリービューでのネットワーク構成データの表示。")</span><span class="sxs-lookup"><span data-stu-id="da459-541">![Viewing network configuration data in a tree-view.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Viewing network configuration data in a tree-view.")</span></span>

<span data-ttu-id="da459-542">**CAC ネットワークトポロジリンクのカスタムコネクタ (サイト間、地域間、サイト間のリンクなど) を定義します。-:** Lync Server 2013 管理者は、次に示すように設定オプションを使用して、CAC ネットワーク構成の WAN リンク用のカスタムグラフィカルコネクタを定義できます。</span><span class="sxs-lookup"><span data-stu-id="da459-542">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Lync Server 2013 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="da459-543">これにより、ネットワーク構成でプロビジョニングされたさまざまな種類のネットワークリンクを区別することができます。</span><span class="sxs-lookup"><span data-stu-id="da459-543">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

<span data-ttu-id="da459-544">![CAC ネットワークトポロジ用のカスタムコネクタを定義する](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "CAC ネットワークトポロジ用のカスタムコネクタを定義する")</span><span class="sxs-lookup"><span data-stu-id="da459-544">![Define custom connectors for CAC network topology](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Define custom connectors for CAC network topology")</span></span>

<span data-ttu-id="da459-545">**CAC ネットワークトポロジのサイト情報、地域情報、およびプロビジョニングされた帯域幅ポリシーを表示します。** Lync Server 2013 管理者は、以下に示すオプションを使用して、関連する CAC ネットワーク地域情報、サイト情報、および CAC 帯域幅プロビジョニング情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="da459-545">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Lync Server 2013 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="da459-546">(たとえば、[ネットワーク地域またはネットワークサイトオブジェクトの **情報** ] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="da459-546">(For example, click **Info** in a network region or network site object.)</span></span>

<span data-ttu-id="da459-547">![ネットワークのカスタムコネクタを定義します。](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "ネットワークのカスタムコネクタを定義します。")</span><span class="sxs-lookup"><span data-stu-id="da459-547">![Defining custom connectors for your network.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Defining custom connectors for your network.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="da459-548">要約</span><span class="sxs-lookup"><span data-stu-id="da459-548">Summary</span></span>

<span data-ttu-id="da459-549">このツールは、Lync Server 2013 管理者が、展開のための CAC ネットワークトポロジをグラフィカルな形式で表示するための貴重なリソースになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da459-549">This tool can be a valuable resource to Lync Server 2013 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

</div>

</div>

<div>

## <a name="response-group-agent-live"></a><span data-ttu-id="da459-550">応答グループエージェント Live</span><span class="sxs-lookup"><span data-stu-id="da459-550">Response Group Agent Live</span></span>

<span data-ttu-id="da459-551">応答グループアプリケーションによって、エージェントは組み込みの Web サービスを使用して、便利なリアルタイム情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="da459-551">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="da459-552">残念ながら、このデータのグラフィック表示はアプリケーションの外部では使用できません。</span><span class="sxs-lookup"><span data-stu-id="da459-552">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="da459-553">Response Group Agent Live Resource Kit tool では、このような情報にアクセスするためのシンプルでグラフィカルな方法を提供することで、この問題を解決します。これは、Microsoft Lync 2013 のリアルタイム通信ソフトウェア情報 (他のエージェントのプレゼンスなど) によって拡張されます。</span><span class="sxs-lookup"><span data-stu-id="da459-553">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Microsoft Lync 2013 communications software information such as the presence of other agents.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-554">説明</span><span class="sxs-lookup"><span data-stu-id="da459-554">Description</span></span>

<span data-ttu-id="da459-555">応答グループエージェント Live は、サインインとサインアウトの機能、およびいくつかのリアルタイム情報 (グループメンバーシップ、現在の通話数など) を応答グループエージェントに提供する Windows アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="da459-555">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="da459-556">エージェントグループページの拡張バージョンになることを意図しています (Lync 2013 からアクセスできます)。</span><span class="sxs-lookup"><span data-stu-id="da459-556">It is meant to be an enhanced version of the Agent Groups page (accessible from Lync 2013.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="da459-557">用途</span><span class="sxs-lookup"><span data-stu-id="da459-557">Purpose</span></span>

<span data-ttu-id="da459-558">応答グループアプリケーションは、着信呼び出しをキューに入れ、それらをエージェントグループにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="da459-558">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="da459-559">サービスに対する呼び出しを決定するために、エージェントはエージェントグループに関するリアルタイムの情報にアクセスできます。これには、他にどのエージェントを使用できるかや、各キューで待機している呼び出しの数などがあります。</span><span class="sxs-lookup"><span data-stu-id="da459-559">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="da459-560">この情報は、最初は応答グループサービスを介してのみアクセス可能です。これは、応答グループエージェント Live により直観的な方法で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="da459-560">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

<div>

## <a name="features"></a><span data-ttu-id="da459-561">機能</span><span class="sxs-lookup"><span data-stu-id="da459-561">Features</span></span>

<span data-ttu-id="da459-562">応答グループエージェント Live ツールは、応答グループサービスおよび Microsoft Lync 2013 SDK に基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="da459-562">The Response Group Agent Live tool is built on the Response Group service and the Microsoft Lync 2013 SDK.</span></span> <span data-ttu-id="da459-563">応答グループのエージェントは、応答グループサービス (グループメンバーシップ、他のエージェントのプレゼンス、待機中の通話数など) から利用できる情報と機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="da459-563">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="da459-564">下の図は、応答グループエージェント Live の主要なインターフェイスを示しています。</span><span class="sxs-lookup"><span data-stu-id="da459-564">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

<span data-ttu-id="da459-565">![応答グループエージェント Live ツール。](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "応答グループエージェント Live ツール。")</span><span class="sxs-lookup"><span data-stu-id="da459-565">![The Response Group Agent Live tool.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "The Response Group Agent Live tool.")</span></span>

<span data-ttu-id="da459-566">応答グループエージェント Live のエージェントでは、次の3つの主要な機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="da459-566">The following three main features are available for agents in Response Group Agent Live:</span></span>

  - <span data-ttu-id="da459-567">**サインイン/サインアウト:** [エージェントグループ] ページ (Lync 2013 からアクセス可能) とは異なり、応答グループエージェント Live では、エージェントのみが一度にサインインするか、またはすべてのエージェントグループからサインアウトできます。</span><span class="sxs-lookup"><span data-stu-id="da459-567">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Lync 2013), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="da459-568">このアプリケーションでは、エージェントがサインインまたはサインアウトするための3つの簡単な方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="da459-568">This application provides three quick ways for agents to sign in or out:</span></span>
    
      - <span data-ttu-id="da459-569">アプリケーション内の [サインイン/出力 (緑と赤)] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="da459-569">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
      - <span data-ttu-id="da459-570">システムトレイアイコンを右クリックし、[サインイン] または [サインアウト] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da459-570">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
      - <span data-ttu-id="da459-571">構成可能なキーボードショートカットを使用する。</span><span class="sxs-lookup"><span data-stu-id="da459-571">Using configurable keyboard shortcuts.</span></span>

  - <span data-ttu-id="da459-572">**グループメンバーシップ:** エージェントグループが選択されている場合、応答グループエージェントのライブには、このグループのエージェントの一覧が右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="da459-572">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="da459-573">Lync 2013 がこのアプリケーションと同じコンピューター上で実行されている場合、プレゼンス情報と連絡先カードが応答グループエージェント Live に表示されます。</span><span class="sxs-lookup"><span data-stu-id="da459-573">If Lync 2013 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="da459-574">エージェントは、そこから直接 IM を送信したり、他のエージェントを呼び出したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="da459-574">Agents can send an IM or call other agents directly from there.</span></span>

  - <span data-ttu-id="da459-575">**リアルタイムの統計情報:** 応答グループエージェント Live は、すべてのエージェントグループのリアルタイム統計情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="da459-575">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="da459-576">更新間隔は1分です。</span><span class="sxs-lookup"><span data-stu-id="da459-576">The update frequency is one minute.</span></span> <span data-ttu-id="da459-577">呼び出しが応答グループによって応答されると、そのグループ名の横に、キューに入れられている現在の呼び出しの数で視覚的なインジケーターが追加されます。</span><span class="sxs-lookup"><span data-stu-id="da459-577">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="da459-578">また、グループの上にポインターを置くと、待機時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="da459-578">Pausing the pointer over a group also displays the longest waiting time.</span></span>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="da459-579">要件</span><span class="sxs-lookup"><span data-stu-id="da459-579">Requirements</span></span>

<span data-ttu-id="da459-580">応答グループエージェント Live には、.NET Framework 4.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="da459-580">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="da459-581">また、プレゼンスおよび連絡先カードの機能を利用するには、Lync 2013 をローカルでインストールする必要があり、実行中である必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-581">In addition, to take advantage of the presence and contact card features, Lync 2013 must be installed locally (and be running).</span></span>

<div>

## <a name="configuration"></a><span data-ttu-id="da459-582">構成</span><span class="sxs-lookup"><span data-stu-id="da459-582">Configuration</span></span>

<span data-ttu-id="da459-583">応答グループエージェント Live は、アプリケーションの [オプション] ダイアログボックスを使用して、個々の設定に合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="da459-583">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="da459-584">さらに、管理者は、RGAgentLive.exe.config ファイルの defaultHostAddress プロパティを直接編集することによって、既定のホストアドレスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="da459-584">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="da459-585">次の図は、エージェントがホストアドレスとショートカットキーを構成する際に使用できる [オプション] ダイアログボックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="da459-585">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="da459-586">このダイアログには、メインインターフェイスの右上にある [オプション] ボタンをクリックするとアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="da459-586">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

<span data-ttu-id="da459-587">![応答グループエージェントの [Live オプション] ダイアログボックス](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "応答グループエージェントの [Live オプション] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="da459-587">![The Response Group Agent Live Options dialog box.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "The Response Group Agent Live Options dialog box.")</span></span>

<span data-ttu-id="da459-588">Response Group Agent Live 構成では、次の3種類の設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="da459-588">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

  - <span data-ttu-id="da459-589">[ホストアドレス: これは通常、エージェントのホームプールに属する web プールの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="da459-589">Host address: This is typically the web pool FQDN belonging to the agent’s home pool.</span></span> <span data-ttu-id="da459-590">正確な応答グループサービスのアドレスは、この情報から (ホストの後に適切なパスを追加することによって) バックグラウンドで自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="da459-590">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

  - <span data-ttu-id="da459-591">ショートカット: サインイン/アウトの正確なショートカットをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="da459-591">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="da459-592">唯一の制限は、両方のショートカットに "Windows ロゴ" キーが含まれている必要があることです (少なくとも他のキーに加えて)。</span><span class="sxs-lookup"><span data-stu-id="da459-592">The only limitation is that both shortcuts must contain the “Windows Logo” key (in addition to at least another key).</span></span>

  - <span data-ttu-id="da459-593">Windows で起動する: アプリケーションは、Windows で自動的に起動するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="da459-593">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="da459-594">例</span><span class="sxs-lookup"><span data-stu-id="da459-594">Examples</span></span>

<span data-ttu-id="da459-595">次の図は、右側のウィンドウで連絡先を右クリックして、他のエージェントに電話をかけたり、IM を送信したりする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="da459-595">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

<span data-ttu-id="da459-596">![電話をかけたり、IM を送信したりする。](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "電話をかけたり、IM を送信したりする。")</span><span class="sxs-lookup"><span data-stu-id="da459-596">![Making a call or sending an IM.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Making a call or sending an IM.")</span></span>

<span data-ttu-id="da459-597">次の図は、応答グループエージェント Live が、キュー内の現在の呼び出し数と、これらのすべての着信呼び出しのうちで最長の待機時間を表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="da459-597">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

<span data-ttu-id="da459-598">![キュー情報の表示。](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "キュー情報の表示。")</span><span class="sxs-lookup"><span data-stu-id="da459-598">![Viewing queue information.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Viewing queue information.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="da459-599">要約</span><span class="sxs-lookup"><span data-stu-id="da459-599">Summary</span></span>

<span data-ttu-id="da459-600">Fast サインインとサインアウト、グループメンバーシップ、および基本的なリアルタイム統計情報は、応答グループサービスからアプリケーションの外部でのみ使用可能な、興味深い応答グループエージェントの機能です。</span><span class="sxs-lookup"><span data-stu-id="da459-600">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="da459-601">Response Group Agent Live Resource Kit tool を使用すると、Lync 管理者は、迅速でグラフィカルな方法でタスクを実行できる Windows アプリケーションでエージェントを提供できます。</span><span class="sxs-lookup"><span data-stu-id="da459-601">With the Response Group Agent Live Resource Kit tool, Lync administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

</div>

</div>

<div>

## <a name="sefautil"></a><span data-ttu-id="da459-602">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="da459-602">SEFAUtil</span></span>

<span data-ttu-id="da459-603">SEFAUtil (第2拡張機能のアクティブ化) は、Microsoft Lync Server 2013 communications software 管理者およびヘルプデスク担当者が、Lync Server 2013 ユーザーに代わって、委任、着信転送、同時呼び出し、チーム呼び出しの設定、グループ通話ピックアップを構成できるようにするコマンドラインツールです。</span><span class="sxs-lookup"><span data-stu-id="da459-603">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Microsoft Lync Server 2013 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="da459-604">また、このツールを使用すると、管理者は特定のユーザーに対して公開されている呼び出しルーティング設定を照会することができます。SEFAUtil ツールを使用すると、管理者は着信の転送を有効/無効にしたり、ユーザーの代わりに同時に呼び出したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="da459-604">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="da459-605">管理者は、ターゲット (SIP URI の形式) を指定するか、ユーザーによって既に公開されているターゲットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="da459-605">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="da459-606">このツールを使用すると、管理者は、ユーザーの代わりに代理人またはチーム呼び出しグループのメンバーを追加または削除することもできます。このツールは、Microsoft 統合コミュニケーション Managed API (UCMA) 3.0 上に構築されており、管理者は SEFAUtil の中央管理ストアで信頼済みアプリケーションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-606">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil</span></span>

<span data-ttu-id="da459-607">SEFAUtil (第2拡張機能のアクティブ化) Lync Server 2013 管理者およびヘルプデスク担当者は、Lync Server 2013 ユーザーに代わって、委任、着信転送、同時呼び出し、チーム呼び出しの設定、グループ通話ピックアップを構成できます。</span><span class="sxs-lookup"><span data-stu-id="da459-607">SEFAUtil (secondary extension feature activation) enables Lync Server 2013 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="da459-608">また、このツールを使用すると、管理者は特定のユーザーに対して公開されている呼び出しルーティング設定を照会することができます。</span><span class="sxs-lookup"><span data-stu-id="da459-608">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-609">説明</span><span class="sxs-lookup"><span data-stu-id="da459-609">Description</span></span>

<span data-ttu-id="da459-610">SEFAUtil の現在のバージョンはコマンドラインツールにすぎません。グラフィカルユーザーインターフェイスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="da459-610">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="da459-611">このツールは、Microsoft 統合コミュニケーション Managed API (UCMA) 3.0 に基づいています。</span><span class="sxs-lookup"><span data-stu-id="da459-611">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="da459-612">このツールの機能により、管理者とヘルプデスク担当者は次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="da459-612">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

  - <span data-ttu-id="da459-613">ユーザーのすべての通話ルーティング設定を表示する (着信転送、委任、同時呼び出し、チーム呼び出し、グループ通話ピックアップを含む)</span><span class="sxs-lookup"><span data-stu-id="da459-613">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

  - <span data-ttu-id="da459-614">通話転送設定の有効化/無効化/変更 (送信先と応答なしのタイマーを含む)</span><span class="sxs-lookup"><span data-stu-id="da459-614">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

  - <span data-ttu-id="da459-615">着信転送の即時構成の有効化/無効化/変更</span><span class="sxs-lookup"><span data-stu-id="da459-615">Enable/disable/modify call-forwarding immediate configurations</span></span>

  - <span data-ttu-id="da459-616">委任設定の有効化/無効化/変更</span><span class="sxs-lookup"><span data-stu-id="da459-616">Enable/disable/modify delegation settings</span></span>

  - <span data-ttu-id="da459-617">チーム呼び出しグループの設定の有効化/無効化/変更</span><span class="sxs-lookup"><span data-stu-id="da459-617">Enable/disable/modify team-call group settings</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da459-618">Lync Server 2013 SEFAUtil ツールの新サービス</span><span class="sxs-lookup"><span data-stu-id="da459-618">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="da459-619">同時呼び出しの設定の有効化/無効化/変更 (destination を含む)</span><span class="sxs-lookup"><span data-stu-id="da459-619">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da459-620">Lync Server 2013 SEFAUtil ツールの新サービス</span><span class="sxs-lookup"><span data-stu-id="da459-620">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="da459-621">グループ通話ピックアップ設定の有効化/無効化/変更</span><span class="sxs-lookup"><span data-stu-id="da459-621">Enable/disable/modify group call pickup settings</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="da459-622">Lync Server 2013 SEFAUtil ツールの新サービス</span><span class="sxs-lookup"><span data-stu-id="da459-622">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

<span data-ttu-id="da459-623">このツールには次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="da459-623">This tool has the following limitations:</span></span>

  - <span data-ttu-id="da459-624">Lync Server プールに所属しているユーザーに対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="da459-624">Supported only for users homed in a Lync Server pool</span></span>

  - <span data-ttu-id="da459-625">複数のユーザーの通話ルーティング設定の一括編集はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="da459-625">Bulk-edit of call routing settings for several users is not supported</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="da459-626">出力</span><span class="sxs-lookup"><span data-stu-id="da459-626">Output</span></span>

<span data-ttu-id="da459-627">このツールの現在のバージョンでは、コマンドプロンプトウィンドウにのみ出力が提供されます。</span><span class="sxs-lookup"><span data-stu-id="da459-627">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="da459-628">詳細については、このドキュメントで後述する「例」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="da459-628">For details, see the Examples section later in this document.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="da459-629">用途</span><span class="sxs-lookup"><span data-stu-id="da459-629">Purpose</span></span>

<span data-ttu-id="da459-630">このツールが使用される主なシナリオのいくつかを次に示します。</span><span class="sxs-lookup"><span data-stu-id="da459-630">Following are some of the key scenarios where this tool may be used:</span></span>

  - <span data-ttu-id="da459-631">Bob は役員で、Lync Server テレフォニーに移行されました。</span><span class="sxs-lookup"><span data-stu-id="da459-631">Bob is an executive and has been moved to Lync Server telephony.</span></span> <span data-ttu-id="da459-632">既存の PBX システム上で委任を行います。</span><span class="sxs-lookup"><span data-stu-id="da459-632">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="da459-633">Lync への移行の一環として、管理者は、既存の委任構成を反映するように Bob のルーティングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="da459-633">As part of the move to Lync, the administrator is able to configure Bob’s routing to reflect his pre-existing delegation configuration.</span></span>

  - <span data-ttu-id="da459-634">Alice は出張中で、お客様の1人からの重要な連絡を期待していることを認識しています。</span><span class="sxs-lookup"><span data-stu-id="da459-634">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="da459-635">しかし、彼女はホテルにいて、コンピューターにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="da459-635">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="da459-636">ヘルプデスクに電話をかけて、自分の勤務先番号へのすべての通話に対して、自分の携帯電話番号への転送を要求します。</span><span class="sxs-lookup"><span data-stu-id="da459-636">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="da459-637">ヘルプデスク担当者は、自分の代わりに構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="da459-637">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

  - <span data-ttu-id="da459-638">仕事の電話番号に対する Joe の呼び出しは、自分が勤務しているときに、携帯電話のボイスメールに送られます。ただし、その他の多くの場所では正常に動作しているように見えます。</span><span class="sxs-lookup"><span data-stu-id="da459-638">Joe’s calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="da459-639">ヘルプデスク技術者は、Joe のルーティング構成を表示して、Joe が自分の携帯電話に対して同時呼び出しを構成していることを検出できます。</span><span class="sxs-lookup"><span data-stu-id="da459-639">The helpdesk technician is able to view Joe’s routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="da459-640">この技術者は、自分のオフィスのモバイルの範囲について Joe に質問をし、同時呼び出しが、ネットワークのカバレージが悪い場合に、その通話が Joe のモバイルボイスメールに送られる原因となっていることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="da459-640">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe’s mobile voicemail when his network coverage is poor.</span></span>

  - <span data-ttu-id="da459-641">Mike は Contoso 社の新入社員で、チーム呼び出しに対してすべてのメンバーを構成する新しいチームに参加しています。 Microsoft Lync が有効になっている場合、管理者はチーム呼び出しグループの設定を変更して、チームのメンバーごとにチーム呼び出しグループのメンバーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="da459-641">Mike is a new employee at Contoso and he’s joining a new team on which all members are configured for team-call, when being enabled for Microsoft Lync, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

  - <span data-ttu-id="da459-642">Contoso 社の人事部のカスタマーサービスプラクティスでは、最初の呼び出し以降のすべての発信者に対して個人サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="da459-642">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="da459-643">部署のすべてのメンバーが互いに近い場所に配置されているため、すべての電話がチーム呼び出しで同時に着信すると、チームの業務が非常に中断されます。</span><span class="sxs-lookup"><span data-stu-id="da459-643">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="da459-644">チームメンバーを中断せずに最高のサービスを提供するために、Lync 管理者はグループ通話ピックアップ機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="da459-644">To provide the best service without disrupting the team members, the Lync administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="da459-645">管理者は、すべての部門メンバーをピックアップグループに追加し、その部署に pickup グループ番号を伝えます。</span><span class="sxs-lookup"><span data-stu-id="da459-645">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="da459-646">Samantha がデスクから不在になっている場合、Joe は自分の電話が鳴ったことを通知し、彼は自分の席から呼び出しに応答することになります。</span><span class="sxs-lookup"><span data-stu-id="da459-646">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="da459-647">要件</span><span class="sxs-lookup"><span data-stu-id="da459-647">Requirements</span></span>

<span data-ttu-id="da459-648">SEFAUtil ツールは、信頼されたアプリケーションプールの一部であるコンピューターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="da459-648">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="da459-649">UCMA 3.0 をそのコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-649">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="da459-650">ツールを実行するには、SEFAUtil アプリケーション ID を持つ新しい信頼されたアプリケーションをそのプールに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-650">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

<span data-ttu-id="da459-651">**SEFAUtil ツール用の新しい信頼されたアプリケーションを作成する**</span><span class="sxs-lookup"><span data-stu-id="da459-651">**Creating a new Trusted Application for the SEFAUtil tool**</span></span>

1.  <span data-ttu-id="da459-652">SEFAUTil ツールは、信頼されたアプリケーションプールの一部であるコンピューターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="da459-652">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="da459-653">必要に応じて、次のコマンドレットを使用して、新しい信頼されたアプリケーションプールとしてのプールの追加を Lync Server 管理シェルで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="da459-653">If needed, adding a pool as a new trusted application pool can be done via the Lync Server Management Shell with the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da459-654">SEFAUtil ツールの実行に使用するすべてのコンピューターに UCMA 3.0 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-654">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

    
    </div>

2.  <span data-ttu-id="da459-655">信頼されたアプリケーションは、SEFAUtil ツールのトポロジで定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-655">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="da459-656">SEFAUtil を新しい信頼されたアプリケーションとして定義するには、Lync Server 管理シェルを使用して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="da459-656">To define SEFAUtil as a new trusted application, use the Lync Server Management Shell and execute the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da459-657">必要に応じて、別のポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="da459-657">A different port can be used if needed.</span></span>

    
    </div>

3.  <span data-ttu-id="da459-658">トポロジの変更を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-658">The topology changes need to be enabled.</span></span> <span data-ttu-id="da459-659">トポロジの変更を有効にするには、次のコマンドレットを実行して、Lync Server 管理シェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="da459-659">Enabling the topology changes can be done via the Lync Server Management Shell by executing the following cmdlet:</span></span>
    
        Enable-CsToplogy

4.  <span data-ttu-id="da459-660">必要に応じて、SEFAUtil ツールの実行に使用するサーバーに Lync Server 2013 リソースキットツールをインストールします (サーバーは、信頼されたアプリケーションプールの一部である必要があります)。</span><span class="sxs-lookup"><span data-stu-id="da459-660">If needed, install the Lync Server 2013 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5.  <span data-ttu-id="da459-661">SEFAUtil が正しく動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da459-661">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="da459-662">これを行うには、管理者特権を使用して windows コマンドプロンプトからツールを実行し、展開内のユーザーの着信転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="da459-662">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="da459-663">既定では、このツールは次 \\ の場所にあります。Program Files \\ Microsoft Lync Server 2013 \\ うえ "。</span><span class="sxs-lookup"><span data-stu-id="da459-663">By default the tool will be located in: “…\\Program Files\\Microsoft Lync Server 2013\\Reskit”.</span></span> <span data-ttu-id="da459-664">ユーザーの着信転送設定を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="da459-664">To display the call forwarding settings of a user, use the following command:</span></span>
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    <span data-ttu-id="da459-665">ユーザーの着信転送設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="da459-665">The call forwarding settings of the user should be displayed.</span></span>

<div>

## <a name="group-call-pickup"></a><span data-ttu-id="da459-666">グループ通話ピックアップ</span><span class="sxs-lookup"><span data-stu-id="da459-666">Group Call Pickup</span></span>

<span data-ttu-id="da459-667">グループ通話ピックアップで機能を完全に有効にするには、Lync Server で追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="da459-667">Group Call Pickup requires additional configuration in Lync Server for the capability to be fully enabled.</span></span> <span data-ttu-id="da459-668">ピックアップグループをユーザーに割り当てる前に、この機能の計画と展開の手順については、「Group Call Pickup product documentation」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da459-668">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="da459-669">例</span><span class="sxs-lookup"><span data-stu-id="da459-669">Examples</span></span>

<div>

## <a name="display-current-call-handling-settings"></a><span data-ttu-id="da459-670">現在の通話処理の設定を表示する</span><span class="sxs-lookup"><span data-stu-id="da459-670">Display Current Call Handling Settings</span></span>

<span data-ttu-id="da459-671">次のコマンドを実行すると、ユーザーの通話処理が表示されます。</span><span class="sxs-lookup"><span data-stu-id="da459-671">The following command displays the call handling for the user.</span></span> `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> <span data-ttu-id="da459-672">この例では、 <STRONG>/server</STRONG> スイッチを使用して、接続先の Lync server を指定します。</span><span class="sxs-lookup"><span data-stu-id="da459-672">This example uses the <STRONG>/server</STRONG> switch to specify the Lync Server to connect to.</span></span>



</div>

<span data-ttu-id="da459-673">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-673">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="da459-674">着信転送/応答のない宛先を設定する</span><span class="sxs-lookup"><span data-stu-id="da459-674">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="da459-675">次の使用例は、着信転送/着信応答の宛先を指定せず、リングの遅延を設定します。</span><span class="sxs-lookup"><span data-stu-id="da459-675">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="da459-676">ここでは、/server スイッチは提供されていません。SEFAUtil は、Lync Server の自動検出を試行します。</span><span class="sxs-lookup"><span data-stu-id="da459-676">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Lync Server.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

<span data-ttu-id="da459-677">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-677">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="da459-678">直ちに着信転送を有効にする</span><span class="sxs-lookup"><span data-stu-id="da459-678">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="da459-679">この例では、別のユーザーへの着信転送をすぐに有効にします。</span><span class="sxs-lookup"><span data-stu-id="da459-679">This example immediately enables call-forwarding to another user.</span></span>

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

<span data-ttu-id="da459-680">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-680">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="da459-681">直ちに着信転送を無効にする</span><span class="sxs-lookup"><span data-stu-id="da459-681">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="da459-682">この例では、すぐに着信転送を無効にします。</span><span class="sxs-lookup"><span data-stu-id="da459-682">This example immediately disables call forwarding.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

<span data-ttu-id="da459-683">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-683">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="da459-684">代理人としてユーザーを追加し、代理人の同時呼び出しを設定する</span><span class="sxs-lookup"><span data-stu-id="da459-684">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="da459-685">この例では、ユーザーを代理人として追加し、代理人の同時呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="da459-685">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

<span data-ttu-id="da459-686">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-686">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="da459-687">代理人の同時呼び出しルールを変更する</span><span class="sxs-lookup"><span data-stu-id="da459-687">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="da459-688">この例では、前の例で設定した同時呼び出しルールを遅延呼び出しルールに変更します。</span><span class="sxs-lookup"><span data-stu-id="da459-688">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

<span data-ttu-id="da459-689">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-689">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a><span data-ttu-id="da459-690">代理人を削除する</span><span class="sxs-lookup"><span data-stu-id="da459-690">Remove the Delegate</span></span>

<span data-ttu-id="da459-691">この例では、代理人を削除します。</span><span class="sxs-lookup"><span data-stu-id="da459-691">This example removes the delegate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da459-692">最後の代理人が削除されると、代理人の着信は自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="da459-692">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

<span data-ttu-id="da459-693">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-693">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="da459-694">代理人を追加し、代理人のルールに Call-Forward を設定する</span><span class="sxs-lookup"><span data-stu-id="da459-694">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="da459-695">この例では、代理人を追加し、代理人に呼び出しを転送するルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="da459-695">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

<span data-ttu-id="da459-696">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-696">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="da459-697">同時呼び出しを有効にして、宛先番号を設定する</span><span class="sxs-lookup"><span data-stu-id="da459-697">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="da459-698">この例では、同時呼び出しを有効にして、同時呼び出し先番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="da459-698">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> <span data-ttu-id="da459-699">既に同時呼び出しが有効になっているユーザーの同時呼び出し先番号を変更するには、コマンドを/enablesimulring スイッチにします。そうしないと、宛先番号は変更されません。</span><span class="sxs-lookup"><span data-stu-id="da459-699">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>



</div>

<span data-ttu-id="da459-700">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-700">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a><span data-ttu-id="da459-701">同時呼び出しを無効にする</span><span class="sxs-lookup"><span data-stu-id="da459-701">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="da459-702">この例では、同時呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="da459-702">This example disables simultaneous ringing.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

<span data-ttu-id="da459-703">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-703">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="da459-704">Team-Call のチームメンバーを追加し、Team-Call メンバーグループに同時呼び出しを設定する</span><span class="sxs-lookup"><span data-stu-id="da459-704">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="da459-705">この例では、ユーザーのチーム呼び出しグループにチームメンバーを追加し、チーム呼び出しグループへの同時呼び出しを有効にします。</span><span class="sxs-lookup"><span data-stu-id="da459-705">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="da459-706">ユーザーのチーム呼び出しグループにメンバーを追加すると、そのユーザーの同時呼び出しの切り替わりがチーム呼び出しグループに自動的に切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="da459-706">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>



</div>

<span data-ttu-id="da459-707">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-707">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="da459-708">Team-Call グループからメンバーを削除する</span><span class="sxs-lookup"><span data-stu-id="da459-708">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="da459-709">この例では、ユーザーのチーム呼び出しグループのチームメンバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="da459-709">This example removes a team member of the team-call group of a user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> <span data-ttu-id="da459-710">削除されるメンバーがチーム呼び出しグループの唯一のメンバーである場合は、同時にチーム呼び出しグループへの呼び出しが自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="da459-710">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>



</div>

<span data-ttu-id="da459-711">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-711">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="da459-712">遅延呼び出しを Team-Call グループに設定します。</span><span class="sxs-lookup"><span data-stu-id="da459-712">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="da459-713">この例では、遅延呼び出しをチーム呼び出しグループ時間設定に変更します。</span><span class="sxs-lookup"><span data-stu-id="da459-713">This example changes the delayed ring to the team-call group time setting.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

<span data-ttu-id="da459-714">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-714">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a><span data-ttu-id="da459-715">Team-Call を有効にする</span><span class="sxs-lookup"><span data-stu-id="da459-715">Enable Team-Call</span></span>

<span data-ttu-id="da459-716">この例では、指定したユーザーのチーム呼び出しを有効にします。</span><span class="sxs-lookup"><span data-stu-id="da459-716">This example enables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="da459-717">ユーザーのチーム呼び出しグループにメンバーがいない場合、チーム呼び出しは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="da459-717">If the team-call group of the user has no members, team-call won’t be enabled.</span></span>



</div>

<span data-ttu-id="da459-718">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-718">**Output**</span></span>

</div>

<div>

## <a name="disable-team-call"></a><span data-ttu-id="da459-719">Team-Call を無効にする</span><span class="sxs-lookup"><span data-stu-id="da459-719">Disable Team-Call</span></span>

<span data-ttu-id="da459-720">この例では、指定したユーザーのチーム呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="da459-720">This example disables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

<span data-ttu-id="da459-721">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-721">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="da459-722">グループ通話ピックアップを有効にし、ユーザーにピックアップグループを割り当てる</span><span class="sxs-lookup"><span data-stu-id="da459-722">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="da459-723">この例では、ピックアップグループをユーザーに割り当て、グループ通話ピックアップを有効にします。</span><span class="sxs-lookup"><span data-stu-id="da459-723">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

<span data-ttu-id="da459-724">**出力**</span><span class="sxs-lookup"><span data-stu-id="da459-724">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a><span data-ttu-id="da459-725">グループ通話ピックアップを無効にする</span><span class="sxs-lookup"><span data-stu-id="da459-725">Disable Group Call Pickup</span></span>

<span data-ttu-id="da459-726">この例では、指定したユーザーのグループ通話ピックアップを無効にします。</span><span class="sxs-lookup"><span data-stu-id="da459-726">This example disables Group Call Pickup for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> <span data-ttu-id="da459-727">ユーザーのグループ通話ピックアップを無効にしても、ユーザーに割り当てられていたグループ番号は保持されません。</span><span class="sxs-lookup"><span data-stu-id="da459-727">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="da459-728">その後、そのユーザーのグループ通話ピックアップを再度有効にする場合は、グループ番号を/enablegrouppickup スイッチを使用して再度割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-728">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a><span data-ttu-id="da459-729">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="da459-729">SYSPrep.ps1</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-730">説明</span><span class="sxs-lookup"><span data-stu-id="da459-730">Description</span></span>

<span data-ttu-id="da459-731">SYSPrep.ps1 は、Windows Server 2008 オペレーティングシステムコンピューターに、次の Lync Server 2013 の必須コンポーネントをインストールする Windows PowerShell スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="da459-731">SYSPrep.ps1 is a Windows PowerShell script that will install the following Lync Server 2013 prerequisites on your Windows Server 2008 operating system machine.</span></span>

  - <span data-ttu-id="da459-732">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="da459-732">Microsoft .Net Framework 4.5</span></span>

  - <span data-ttu-id="da459-733">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="da459-733">Microsoft SQL Server Express</span></span>

  - <span data-ttu-id="da459-734">Windows Powershell バージョン3.0</span><span class="sxs-lookup"><span data-stu-id="da459-734">Windows Powershell version 3.0</span></span>

  - <span data-ttu-id="da459-735">Visual C++ 2010 再頒布可能パッケージ</span><span class="sxs-lookup"><span data-stu-id="da459-735">Visual C++ 2010 Redistributable</span></span>

  - <span data-ttu-id="da459-736">インターネットインフォメーションサービスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="da459-736">Internet Information Server Updates</span></span>

  - <span data-ttu-id="da459-737">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="da459-737">Windows Identity Foundation</span></span>

  - <span data-ttu-id="da459-738">Lync Server 2013 コアファイル</span><span class="sxs-lookup"><span data-stu-id="da459-738">Lync Server 2013 Core files</span></span>

<span data-ttu-id="da459-739">このスクリプト名は、Microsoft Windows オペレーティングシステムのシステム準備ツールに似ていますが、これらは異なります。</span><span class="sxs-lookup"><span data-stu-id="da459-739">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="da459-740">このスクリプトでは、Lync Server 2013 に必要な前提条件のみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="da459-740">This script will only install the required prerequisites for Lync Server 2013.</span></span> <span data-ttu-id="da459-741">これらの前提条件がインストールされたら、Windows SYSPrep ツールを使用してサーバーのイメージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="da459-741">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="da459-742">要件</span><span class="sxs-lookup"><span data-stu-id="da459-742">Requirements</span></span>

<span data-ttu-id="da459-743">SYSPrep.ps1 スクリプトを実行する前に、前提条件となるファイルを Windows Server 2008 オペレーティングシステムコンピューター上のローカルフォルダーにコピーする必要があります (例 **: D: \\ セットアップ)**。</span><span class="sxs-lookup"><span data-stu-id="da459-743">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\\Setup)**.</span></span> <span data-ttu-id="da459-744">このフォルダーには、Lync Server 2013 ファイル (特にSetup.exe のコピーも含める必要があり \*\* ます。\*\*</span><span class="sxs-lookup"><span data-stu-id="da459-744">This folder must also include a copy of the Lync Server 2013 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="da459-745">前提条件となるファイルは、次の場所からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="da459-745">The prerequisite files can be downloaded from the following locations:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da459-746">前提条件</span><span class="sxs-lookup"><span data-stu-id="da459-746">Prerequisite</span></span></th>
<th><span data-ttu-id="da459-747">場所</span><span class="sxs-lookup"><span data-stu-id="da459-747">Location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da459-748">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="da459-748">Microsoft .Net Framework 4.5</span></span></p></td>
<td><p>https://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da459-749">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="da459-749">Microsoft SQL Server Express 2008 R2</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da459-750">Windows Powershell バージョン3.0</span><span class="sxs-lookup"><span data-stu-id="da459-750">Windows Powershell version 3.0</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da459-751">Visual C++ 2010 再頒布可能パッケージ</span><span class="sxs-lookup"><span data-stu-id="da459-751">Visual C++ 2010 Redistributable</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da459-752">インターネットインフォメーションサービスの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="da459-752">Internet Information Server Updates</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da459-753">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="da459-753">Windows Identity Foundation</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da459-754">Lync Server 2013 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="da459-754">Lync Server 2013 Setup.exe</span></span></p></td>
<td><p><span data-ttu-id="da459-755">Lync Server 2013 メディアからのコピー</span><span class="sxs-lookup"><span data-stu-id="da459-755">Copy from Lync Server 2013 media</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a><span data-ttu-id="da459-756">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da459-756">Parameter</span></span>

<span data-ttu-id="da459-757">**– Setupfolder**パラメーターには、必須コンポーネントファイルのディレクトリの場所を引数として指定します。</span><span class="sxs-lookup"><span data-stu-id="da459-757">The **–SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="da459-758">例</span><span class="sxs-lookup"><span data-stu-id="da459-758">Examples</span></span>

<span data-ttu-id="da459-759">SYSPrep.ps1 スクリプトを実行して、Lync Server 2013 の前提条件をインストールするには、管理者特権でのコマンドプロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="da459-759">To run the SYSPrep.ps1 script and install the Lync Server 2013 prerequisites, run the following command from an elevated command prompt:</span></span>

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="da459-760">割り当てられていない番号のアナウンスの移行</span><span class="sxs-lookup"><span data-stu-id="da459-760">Unassigned Number Announcements Migration</span></span>

<span data-ttu-id="da459-761">割り当てられていない番号のアナウンス移行ツールを使用すると、Lync 管理者は、アナウンスアプリケーションによってサービスを受けている割り当てられていない番号の構成を、ソース Lync サーバーまたはプールから目的の Lync サーバーまたはプールに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="da459-761">The Unassigned Number Announcements Migration tool enables a Lync administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Lync Server or Pool to a destination Lync Server or Pool.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-762">説明</span><span class="sxs-lookup"><span data-stu-id="da459-762">Description</span></span>

<span data-ttu-id="da459-763">割り当てられていない番号のアナウンス移行ツールは、元のサーバーまたはプールのアナウンスアプリケーションによって処理された割り当てられていない番号の構成を別のサーバーまたはプールに移動する Windows PowerShell スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="da459-763">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="da459-764">割り当てられていない番号のアナウンス移行スクリプトを実行すると、次の操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="da459-764">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1.  <span data-ttu-id="da459-765">移動元のサーバーまたはプールでホストされているアナウンスアプリケーションの、割り当てられていない番号アナウンスによって使用されるすべてのオーディオファイルを、展開先のサーバーまたはプールのファイルストアに移動します。</span><span class="sxs-lookup"><span data-stu-id="da459-765">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da459-766">オーディオファイルは、移動先のプールにコピーされると、ソースプールから削除されます。</span><span class="sxs-lookup"><span data-stu-id="da459-766">the audio files are removed from the source pool once they’re copied to the destination pool.</span></span>

    
    </div>

2.  <span data-ttu-id="da459-767">移行元のサーバーまたはプールでホストされているアナウンスアプリケーションに対して構成されている、割り当てられていない番号のアナウンスを、宛先のサーバーまたはプールに移動します</span><span class="sxs-lookup"><span data-stu-id="da459-767">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3.  <span data-ttu-id="da459-768">移行元のサーバーまたはプールでホストされているアナウンスアプリケーションによってサービスを受けているすべての未使用の番号範囲を、宛先のサーバーまたはプールに再割り当てします。</span><span class="sxs-lookup"><span data-stu-id="da459-768">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="da459-769">スクリプトの実行に成功すると、移動元のサーバーまたはプールでホストされていたアナウンスアプリケーションによって処理された、割り当てられていないすべての番号の範囲が、移行先のサーバーまたはプールで同じ構成で処理されるようになります。</span><span class="sxs-lookup"><span data-stu-id="da459-769">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="da459-770">出力</span><span class="sxs-lookup"><span data-stu-id="da459-770">Output</span></span>

<span data-ttu-id="da459-771">**Move-CsAnnouncementConfiguration**スクリプトは、Lync 管理シェルウィンドウで、移行操作の成功または失敗を実行した場所を示します。</span><span class="sxs-lookup"><span data-stu-id="da459-771">The **Move-CsAnnouncementConfiguration** script indicates in the Lync Management Shell window from where it’s executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="da459-772">操作の実行がエラーによって中断された場合、宛先に正常に移動された割り当てられていない番号の範囲は、運用フォームの移動先に残り、割り当てられていない番号の範囲の残りはソースと共に運用フォームに残ります。</span><span class="sxs-lookup"><span data-stu-id="da459-772">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="da459-773">残りの構成を完全に移行するには、エラーに対処した後、スクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="da459-773">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="da459-774">用途</span><span class="sxs-lookup"><span data-stu-id="da459-774">Purpose</span></span>

<span data-ttu-id="da459-775">割り当てられていない番号のアナウンス移行スクリプトは、次の3つのシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="da459-775">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

  - <span data-ttu-id="da459-776">**次のように、構成設定を Lync Server の新しいバージョンに移行します。** Contoso 社は Lync Server 2013 への移行プロセスにおいて、移行プロセスの一環として、lync server の管理者が、アナウンスアプリケーションによって処理された割り当てられていない番号の構成を Lync Server 2010 展開から新しい Lync Server 2013 展開に移動することを希望しています。</span><span class="sxs-lookup"><span data-stu-id="da459-776">**Migrating configuration settings to a new version of Lync Server:** Contoso is in the process of migrating to Lync Server 2013 and as part of the migration process the Lync Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2010 deployment to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="da459-777">構成設定を移動するために、Lync Server 管理者は、割り当てられていない番号のアナウンス移行ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="da459-777">To move the configuration settings, the Lync Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

  - <span data-ttu-id="da459-778">**Lync server 2013 から Lync server 2010 に展開をロールバックする:** 予期しない要因が発生したため、Contoso 社は移行を新しい Lync Server 2013 展開にロールバックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-778">**Rolling back a deployment from Lync Server 2013 to Lync Server 2010:** Due unexpected factors, Contoso has to roll back the migration to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="da459-779">サービスへの中断を最小限に抑えるために、Lync Server 管理者は割り当てられていない番号のアナウンス移行ツールを使用して、Lync Server 2013 展開から Lync Server 2010 展開への構成をロールバックします。</span><span class="sxs-lookup"><span data-stu-id="da459-779">To minimize disruptions to the service, the Lync Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Lync Server 2013 deployment to the Lync Server 2010 deployment.</span></span>

  - <span data-ttu-id="da459-780">**Lync 展開間でのデータの移動:** Contoso 社は、1つのプールのすべてのサーバーを新しいサーバーに置き換える処理を行っています。</span><span class="sxs-lookup"><span data-stu-id="da459-780">**Moving data between Lync deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="da459-781">その戦略は、新しい Lync Server 2013 プールを展開し、古いプールから新しいプールにすべてのデータを移動して、古いプールを廃止することです。</span><span class="sxs-lookup"><span data-stu-id="da459-781">Their strategy is to deploy a new Lync Server 2013 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="da459-782">新しいプールを展開した後、割り当てられていない番号のアナウンス移行ツールを使用して、古いプールから新しいプールに構成を移動します。</span><span class="sxs-lookup"><span data-stu-id="da459-782">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

<div>

## <a name="requirements"></a><span data-ttu-id="da459-783">要件</span><span class="sxs-lookup"><span data-stu-id="da459-783">Requirements</span></span>

<span data-ttu-id="da459-784">ツールを正常に実行するために必要な主な要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="da459-784">The following are the main requirements needed to successfully run the tool:</span></span>

1.  <span data-ttu-id="da459-785">このスクリプトは、Lync Server 2013 管理シェルがインストールされているコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-785">The script must be run from a computer that has Lync Server 2013 Management Shell installed.</span></span>

2.  <span data-ttu-id="da459-786">アナウンスアプリケーションは、移行元と移行先の Lync サーバーまたはプールに正常に展開される必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-786">The announcement application has to be successfully deployed in the source and destination Lync Servers or Pools.</span></span>

<div>

## <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="da459-787">Move-CsAnnouncementConfiguration スクリプト</span><span class="sxs-lookup"><span data-stu-id="da459-787">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="da459-788">Move-CsAnnouncementConfiguration スクリプトには、以下の表で説明する2つのパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="da459-788">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

<span data-ttu-id="da459-789">![CsAnnouncementConfiguration パラメーターを移動します。](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration パラメーター。")</span><span class="sxs-lookup"><span data-stu-id="da459-789">![Move-CsAnnouncementConfiguration parameters.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parameters.")</span></span>

</div>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="da459-790">例</span><span class="sxs-lookup"><span data-stu-id="da459-790">Examples</span></span>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="da459-791">割り当てられていない番号のアナウンス構成を Lync Server 2010 プールから Lync Server 2013 プールに移動する</span><span class="sxs-lookup"><span data-stu-id="da459-791">Moving the Unassigned Number Announcements Configuration from a Lync Server 2010 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="da459-792">この例では、割り当てられていない番号のアナウンスをソースプール (Lync Server 2010) から移行先のプール (Lync Server 2013) に移動します。</span><span class="sxs-lookup"><span data-stu-id="da459-792">This example moves the unassigned number announcements from the source pool (Lync Server 2010) to the destination pool (Lync Server 2013).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a><span data-ttu-id="da459-793">割り当てられていない番号のアナウンス構成を Lync Server 2013 プールから Lync Server 2010 プールに移動する</span><span class="sxs-lookup"><span data-stu-id="da459-793">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Lync Server 2010 Pool</span></span>

<span data-ttu-id="da459-794">この例では、割り当てられていない番号のアナウンスをソースプール (Lync Server 2013) から移行先のプール (Lync Server 2010) に移動します。</span><span class="sxs-lookup"><span data-stu-id="da459-794">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Lync Server 2010).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a><span data-ttu-id="da459-795">Web Conf データ</span><span class="sxs-lookup"><span data-stu-id="da459-795">Web Conf Data</span></span>

<span data-ttu-id="da459-796">Web Conf データツールを使用すると、Lync Server 2013 コミュニケーションソフトウェアの管理者は、開催者の Web 会議に関連付けられているデータをより詳細に制御することができます。</span><span class="sxs-lookup"><span data-stu-id="da459-796">The Web Conf Data Tool allows an administrator of Lync Server 2013 communications software to have more control over the data associated with an organizer’s Web conferences.</span></span> <span data-ttu-id="da459-797">シナリオには、タイムスタンプの条件に基づいて特定のユーザーの会議データを削除する機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="da459-797">Scenarios include the ability to delete a specific user’s meeting data based on a time stamp criteria.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="da459-798">説明</span><span class="sxs-lookup"><span data-stu-id="da459-798">Description</span></span>

<span data-ttu-id="da459-799">このツールを使用すると、管理者は次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="da459-799">This tool allows the administrator to perform the following operations:</span></span>

1.  <span data-ttu-id="da459-800">単一のユーザーに関連付けられているすべての Web 会議データを検索します。</span><span class="sxs-lookup"><span data-stu-id="da459-800">Find all Web conferencing data associated with a single user.</span></span>

2.  <span data-ttu-id="da459-801">1人のユーザーに関連付けられているすべての Web 会議データを削除します。</span><span class="sxs-lookup"><span data-stu-id="da459-801">Delete all Web conferencing data associated with a single user.</span></span>

3.  <span data-ttu-id="da459-802">特定の日付よりも前の1人のユーザーに関連付けられているすべての Web 会議データを削除します。</span><span class="sxs-lookup"><span data-stu-id="da459-802">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4.  <span data-ttu-id="da459-803">ユーザーがあるプールから別のプールに移動したときに、1人のユーザーに関連付けられているすべての Web 会議データを移動します。</span><span class="sxs-lookup"><span data-stu-id="da459-803">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da459-804">Lync Server 2010 のリソースキットツールは、1人のユーザーに関連付けられているすべての Web 会議データを、あるプールから別のプールに移動した場合にサポートされていました。</span><span class="sxs-lookup"><span data-stu-id="da459-804">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="da459-805">このツールでは、 <STRONG>Moveconferencedata</STRONG> パラメーターを使用してこの機能が廃止されました。</span><span class="sxs-lookup"><span data-stu-id="da459-805">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span></span> <span data-ttu-id="da459-806">このパラメーターの詳細については、「 <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-CsUser</A> コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da459-806">For details about this parameter, see the <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-CsUser</A> cmdlet.</span></span>



</div>

<span data-ttu-id="da459-807">このツールは、非アクティブな会議の会議データのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="da459-807">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="da459-808">アクティブな会議 (またはセッション中の会議) を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="da459-808">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="da459-809">このツールは、ターゲットユーザーと同じプールにあるコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-809">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="da459-810">このツールで管理されている会議コンテンツデータのユーザーは、同じユーザープールに所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-810">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="da459-811">出力</span><span class="sxs-lookup"><span data-stu-id="da459-811">Output</span></span>

<span data-ttu-id="da459-812">このツールでは、各操作の結果が出力されます。</span><span class="sxs-lookup"><span data-stu-id="da459-812">This tool outputs the results of each of the operations:</span></span>

  - <span data-ttu-id="da459-813">クエリが実行されると、そのユーザーが開催者として設定されているすべての非アクティブな会議データフォルダーの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="da459-813">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

  - <span data-ttu-id="da459-814">削除が実行されると、そのデータが削除されるすべての会議データフォルダーの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="da459-814">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="da459-815">要件</span><span class="sxs-lookup"><span data-stu-id="da459-815">Requirements</span></span>

<span data-ttu-id="da459-816">このツールは、開催者が現在所属しているのと同じプールで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-816">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="da459-817">このツールは、コンテンツファイルストアにアクセスできる管理者権限を使用して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da459-817">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="da459-818">例</span><span class="sxs-lookup"><span data-stu-id="da459-818">Examples</span></span>

<span data-ttu-id="da459-819">次の表では、パラメーターについて説明します。これらのパラメーターについては、例で使用します。</span><span class="sxs-lookup"><span data-stu-id="da459-819">The following table describes the parameters, some of which are used in the examples.</span></span>

<span data-ttu-id="da459-820">![Web Conf データツールのパラメーター。](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf データツールのパラメーター。")</span><span class="sxs-lookup"><span data-stu-id="da459-820">![Web Conf Data Tool parameters.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data Tool parameters.")</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

<span data-ttu-id="da459-821">前の例では、クエリコマンドがどのように動作するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="da459-821">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="da459-822">このようなコマンドの出力は、このツールによって影響を受けるすべての会議コンテンツフォルダーのリストになります。</span><span class="sxs-lookup"><span data-stu-id="da459-822">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

<span data-ttu-id="da459-823">上記は、delete コマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="da459-823">The preceding is an example of a delete command.</span></span> <span data-ttu-id="da459-824">[削除] コマンドを実行すると、このユーザーからすべての非アクティブな会議フォルダーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="da459-824">The delete command will remove all inactive meeting folders from this user.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="da459-825">要約</span><span class="sxs-lookup"><span data-stu-id="da459-825">Summary</span></span>

<span data-ttu-id="da459-826">このツールは、会議の会議データをより正確に制御する必要がある管理者にとって、貴重なリソースになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da459-826">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
