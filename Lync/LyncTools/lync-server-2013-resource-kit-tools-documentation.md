---
title: Lync Server 2013 リソースキットツールのドキュメント
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
ms.openlocfilehash: 511a4ee9920237e1671a44a2f7481b40fbeb8e1a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a><span data-ttu-id="787a1-102">Lync Server 2013 リソースキットツールのドキュメント</span><span class="sxs-lookup"><span data-stu-id="787a1-102">Lync Server 2013 Resource Kit Tools Documentation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="787a1-103">_**最終更新日:** 2014-01-09_</span><span class="sxs-lookup"><span data-stu-id="787a1-103">_**Topic Last Modified:** 2014-01-09_</span></span>

<span data-ttu-id="787a1-104">このトピックでは、Lync Server 2013 リソースキットの一部であるツールとその用途の例について説明します。Lync Server 2013 のリソースキットツールは、Lync Server 2013 を展開して管理する IT 管理者が日常的なタスクを簡単に行うことができるようにするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="787a1-104">This topic describes the tools that are part of the Lync Server 2013 Resource Kit, including the purpose of each tool, and examples of its use.The Lync Server 2013, Resource Kit Tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="787a1-105">たとえば、**Web Conf Data** ツールを使用すると、オンライン会議中にユーザーによってアップロードされたデータを簡単に制御できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-105">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="787a1-106">**SEFAUtil** ツールを使用すると、ユーザーの問い合わせに対して自動転送や自動応答を設定できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-106">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="787a1-107">IT 管理者はこれらのツールを使用して、より効率的に Lync Server 2013 を管理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="787a1-107">We encourage IT administrators to use these tools to more effectively manage Lync Server 2013.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="787a1-108">リソース キット ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="787a1-108">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="787a1-109">Lync Server 2013 のリソースキットツールをインストールするには、 **OCSReskit**をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="787a1-109">To install the Lync Server 2013, Resource Kit Tools, download **OCSReskit.msi**.</span></span> <span data-ttu-id="787a1-110">リソースキットツールのインストーラーは、のダウンロードセンターからダウンロードでき[http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429)ます。</span><span class="sxs-lookup"><span data-stu-id="787a1-110">You can download the Resource Kit Tools installer from the Download Center at [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429).</span></span>

<span data-ttu-id="787a1-111">**OCSResKit.msi** を実行すると、簡易インストールが行われます。</span><span class="sxs-lookup"><span data-stu-id="787a1-111">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="787a1-112">.Msi は、次のパスにあるすべてのツールをインストールします。 **% Program Files\\%\\Microsoft Lync Server 2013 ResKit**。</span><span class="sxs-lookup"><span data-stu-id="787a1-112">The .msi installs all the tools in the following path: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**.</span></span> <span data-ttu-id="787a1-113">このフォルダーには、自己完結型のツールの実行可能ファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-113">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="787a1-114">ファイルが自分のサブフォルダーにもあるツール。</span><span class="sxs-lookup"><span data-stu-id="787a1-114">Tools that also have files are in their own subfolders.</span></span>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="787a1-115">サポートされる環境</span><span class="sxs-lookup"><span data-stu-id="787a1-115">Supported Environments</span></span>

<span data-ttu-id="787a1-116">最適なパフォーマンスを実現するには、Lync Server 2013、リソースキットツールを同じ環境にインストールして、Lync Server 2013 で必要とされる仕様と同じようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-116">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="787a1-117">リソース キット ツールの概要</span><span class="sxs-lookup"><span data-stu-id="787a1-117">Resource Kit Tools Overview</span></span>

<span data-ttu-id="787a1-118">次の一覧では、Lync Server 2013 リソースキットで提供されるツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="787a1-118">The following list describes the tools that are provided in the Lync Server 2013 Resource Kit.</span></span> <span data-ttu-id="787a1-119">各ツールの説明 (要件、使用例など) については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="787a1-119">A description of each tool, including the requirements and example usage is covered in the following section.</span></span>

  - <span data-ttu-id="787a1-120">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="787a1-120">ABSConfig</span></span>

  - <span data-ttu-id="787a1-121">Bandwidth Policy Service Monitor</span><span class="sxs-lookup"><span data-stu-id="787a1-121">Bandwidth Policy Service Monitor</span></span>

  - <span data-ttu-id="787a1-122">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="787a1-122">Bandwidth Utilization Analyzer</span></span>

  - <span data-ttu-id="787a1-123">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="787a1-123">Call Parkometer</span></span>

  - <span data-ttu-id="787a1-124">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="787a1-124">CleanupStorageServiceData</span></span>

  - <span data-ttu-id="787a1-125">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="787a1-125">DBAnalyze</span></span>

  - <span data-ttu-id="787a1-126">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="787a1-126">ImportStorageServiceData</span></span>

  - <span data-ttu-id="787a1-127">LCSSync</span><span class="sxs-lookup"><span data-stu-id="787a1-127">LCSSync</span></span>

  - <span data-ttu-id="787a1-128">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="787a1-128">LookupUserConsole</span></span>

  - <span data-ttu-id="787a1-129">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="787a1-129">MsTurnPing</span></span>

  - <span data-ttu-id="787a1-130">Network Configuration Viewer</span><span class="sxs-lookup"><span data-stu-id="787a1-130">Network Configuration Viewer</span></span>

  - <span data-ttu-id="787a1-131">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="787a1-131">Response Group Agent Live</span></span>

  - <span data-ttu-id="787a1-132">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="787a1-132">SEFAUtil</span></span>

  - <span data-ttu-id="787a1-133">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="787a1-133">SYSPrep.ps1</span></span>

  - <span data-ttu-id="787a1-134">Unassigned Number Announcements Migration</span><span class="sxs-lookup"><span data-stu-id="787a1-134">Unassigned Number Announcements Migration</span></span>

  - <span data-ttu-id="787a1-135">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="787a1-135">Web Conf Data</span></span>

</div>

<div>

## <a name="absconfig"></a><span data-ttu-id="787a1-136">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="787a1-136">ABSConfig</span></span>

<span data-ttu-id="787a1-137">アドレス帳サービス構成ツール (ABSConfig) は、管理者が Lync Server 2013 のアドレス帳サービスの構成をカスタマイズするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="787a1-137">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Lync Server 2013.</span></span> <span data-ttu-id="787a1-138">このツールを使用すると、Lync Server 2013 管理者が既定のアドレス帳サービス設定を復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="787a1-138">This tool also enables Lync Server 2013 administrators to restore the default Address Book Service settings.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-139">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-139">Description</span></span>

<span data-ttu-id="787a1-140">ABSConfig は、管理者がアドレス帳サービスに関連する Active Directory ドメインサービスの属性を構成できるようにするグラフィカルユーザーインターフェイスアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="787a1-140">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="787a1-141">このツールを使用する主なシナリオは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="787a1-141">The primary scenarios for the tool are the following:</span></span>

  - <span data-ttu-id="787a1-142">管理者が Active Directory ドメインサービスの属性を Lync Server 2013 の属性にマッピングできるようにするには、</span><span class="sxs-lookup"><span data-stu-id="787a1-142">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Lync Server 2013.</span></span>

  - <span data-ttu-id="787a1-143">管理者が Active Directory ドメイン サービスの属性をアドレス帳サービスのファイルに含めるか、ファイルから除外できるようにする。</span><span class="sxs-lookup"><span data-stu-id="787a1-143">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

  - <span data-ttu-id="787a1-144">管理者がアドレス帳サービスの既定の設定を復元できるようにする。</span><span class="sxs-lookup"><span data-stu-id="787a1-144">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="787a1-145">ABSConfig ツールは、absConfig ファイルを使って開始できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-145">The ABSConfig tool can be started by using the absConfig.exe file.</span></span> <span data-ttu-id="787a1-146">ツールが [属性の**構成**] タブに表示されます。この表には、Active Directory ドメインサービスの属性を Lync Server 2013 の属性フィールドにマップし、特定の属性フィルターに基づいてアドレス帳サービスファイルに含めるか除外するかを指定するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="787a1-146">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Lync Server 2013 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="787a1-147">また、アドレス帳ファイルに含める電話番号の値をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="787a1-147">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="787a1-148">[**Restore Defaults**] オプションを使用すると、アドレス帳サービスの設定を既定の値に復元できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-148">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

</div>

<div>

## <a name="changes-from-lync-server-2010"></a><span data-ttu-id="787a1-149">Lync Server 2010 からの変更点</span><span class="sxs-lookup"><span data-stu-id="787a1-149">Changes from Lync Server 2010</span></span>

<span data-ttu-id="787a1-150">Lync Server 2013 ABS 構成ツールでは、属性の [有効] チェックボックスをオフにすることで、属性 (行) を削除できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-150">In Lync Server 2013 ABS Configuration tool, attributes (rows) may be removed by unchecking the “enable” checkbox for the attribute.</span></span> <span data-ttu-id="787a1-151">これは、Lync Server 2010 での行の削除と同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-151">This has the same effect as deleting the row in Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="787a1-152">[有効にする] チェックボックスは、右端の列にあります。列を表示するには、右にスクロールする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-152">The enable checkbox is in the far right column; you may need to scroll right to see the column</span></span>



</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="787a1-153">出力</span><span class="sxs-lookup"><span data-stu-id="787a1-153">Output</span></span>

<span data-ttu-id="787a1-154">ABSConfig は、アドレス帳サービスの構成をデータベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="787a1-154">ABSConfig stores the Address Book Service configuration in the database.</span></span>

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="787a1-155">用途</span><span class="sxs-lookup"><span data-stu-id="787a1-155">Purpose</span></span>

<span data-ttu-id="787a1-156">ABSConfig を使用すると、Lync Server 2013 アドレス帳サービスをすばやく簡単にカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-156">ABSConfig provides a quick and easy way to customize Lync Server 2013 Address Book Service.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="787a1-157">要件</span><span class="sxs-lookup"><span data-stu-id="787a1-157">Requirements</span></span>

<div>

## <a name="computer"></a><span data-ttu-id="787a1-158">コンピューター</span><span class="sxs-lookup"><span data-stu-id="787a1-158">Computer</span></span>

<span data-ttu-id="787a1-159">ABSConfig は、Lync Server 2013 がインストールされているドメインに参加しているコンピューターからのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-159">ABSConfig can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span> <span data-ttu-id="787a1-160">Lync Server 2013 Enterprise Edition の場合、このツールは、セットアップ時にアドレス帳サービスが有効になっているすべてのフロントエンドサーバーで実行できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-160">In the case of Lync Server 2013, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

</div>

<div>

## <a name="network"></a><span data-ttu-id="787a1-161">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="787a1-161">Network</span></span>

<span data-ttu-id="787a1-162">コンピューターは、フロントエンド プールとバックエンド データベースに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-162">The computer should be able to connect to the Front End pool and back-end database.</span></span>

</div>

<div>

## <a name="software"></a><span data-ttu-id="787a1-163">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="787a1-163">Software</span></span>

<span data-ttu-id="787a1-164">ABSConfig ツールを実行する前に、次のソフトウェア コンポーネントをインストールしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-164">The following software components must be installed before running the ABSConfig tool:</span></span>

  - <span data-ttu-id="787a1-165">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="787a1-165">Microsoft Lync Server 2013</span></span>

</div>

<div>

## <a name="users"></a><span data-ttu-id="787a1-166">ユーザー</span><span class="sxs-lookup"><span data-stu-id="787a1-166">Users</span></span>

<span data-ttu-id="787a1-167">Lync Server 2013 の展開を更新するのに必要な権限を持っている管理者。</span><span class="sxs-lookup"><span data-stu-id="787a1-167">Administrators who have the permissions required to update the Lync Server 2013 deployment.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="787a1-168">例</span><span class="sxs-lookup"><span data-stu-id="787a1-168">Examples</span></span>

<span data-ttu-id="787a1-p109">ABSConfig は、コマンド プロンプトで **ABSConfig.exe** と入力して起動することができます。ABSConfig ツールのユーザー インターフェイスを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-p109">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt. Shown below is the ABSConfig tool user interface.</span></span>

<span data-ttu-id="787a1-171">![ABSConfig.exe ツール](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "ABSConfig.exe ツール")</span><span class="sxs-lookup"><span data-stu-id="787a1-171">![The ABSConfig.exe tool.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "The ABSConfig.exe tool.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="787a1-172">概要</span><span class="sxs-lookup"><span data-stu-id="787a1-172">Summary</span></span>

<span data-ttu-id="787a1-173">ABSConfig ツールを使用すると、管理者は、Lync Server 2013 アドレス帳サービスをカスタマイズするための簡単で使いやすいツールが提供されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-173">The ABSConfig tool provides administrators a quick and easy to use tool to customize Lync Server 2013 Address Book Service.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="787a1-174">Bandwidth Policy Service Monitor</span><span class="sxs-lookup"><span data-stu-id="787a1-174">Bandwidth Policy Service Monitor</span></span>

<span data-ttu-id="787a1-175">Bandwidth Policy Service Monitor ツールを使用すると、管理者は以下のリストを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-175">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1.  <span data-ttu-id="787a1-176">トポロジで構成されているすべての Lync Server 2013 帯域幅ポリシーサービス (認証とコア)</span><span class="sxs-lookup"><span data-stu-id="787a1-176">All the configured Lync Server 2013 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2.  <span data-ttu-id="787a1-177">各サービスの帯域幅ポリシー サービスとエッジ サーバーへの接続状況</span><span class="sxs-lookup"><span data-stu-id="787a1-177">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3.  <span data-ttu-id="787a1-178">ネットワーク構成ドキュメントで構成されたすべてのリンクと、各帯域幅ポリシー サービスから報告されたリアルタイムの帯域幅の使用状況</span><span class="sxs-lookup"><span data-stu-id="787a1-178">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-179">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-179">Description</span></span>

<span data-ttu-id="787a1-p110">Bandwidth Policy Service Monitor ツールは、GUI ベースのアプリケーションとして実装されています。管理者は、PDPMonUI.exe を実行してツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="787a1-p110">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application. Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="787a1-p111">ツールを起動すると、ツールはトポロジ内の帯域幅ポリシー サービスの一覧を検索します。初期アップデートが完了すると、ウィンドウの左ペインに、所属するクラスターによってグループ分けされたサービスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p111">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology. After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="787a1-p112">管理者が特定の帯域幅ポリシー サービスを選ぶと、右ペインにそのサービスの情報が表示されます。次の 2 つのメイン タブにそれぞれ情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p112">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service. That pane also has two main tabs that display information.</span></span>

<div>

## <a name="machine-info-tab"></a><span data-ttu-id="787a1-186">[Machine Info] タブ</span><span class="sxs-lookup"><span data-stu-id="787a1-186">Machine Info Tab</span></span>

<span data-ttu-id="787a1-187">[**Machine Info**] タブには、選択した帯域幅ポリシー サービスの詳細と、選択した帯域幅ポリシー サービスから別のサービスへの接続の一覧と状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-187">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

</div>

<div>

## <a name="topology-info-tab"></a><span data-ttu-id="787a1-188">[Topology Info] タブ</span><span class="sxs-lookup"><span data-stu-id="787a1-188">Topology Info Tab</span></span>

<span data-ttu-id="787a1-p113">[**Topology Info**] タブには、ネットワーク構成設定で構成されたすべてのリンクの一覧が表示されます。各リンクには、音声とビデオの帯域幅容量が表示されます。さらに、現在使用されている帯域幅が、Kbps と容量に対する割合で表示されます。ツールでは色分けが使用され、容量の上限に近づいているリンクが強調表示されます。これにより、管理者は対象のリンクをすばやく分離できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p113">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings. For each link, the audio and video bandwidth capacity is displayed. Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity. The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="787a1-p114"> 構成済みの任意の帯域幅ポリシー サービスに Bandwidth Policy Service Monitor ツールを接続するときに問題が発生すると、[<STRONG>Machine Info </STRONG>] タブと [<STRONG>Topology Info</STRONG>] タブに情報が表示されません。ただし、最初は接続されたにもかかわらず、後にサービスへの接続が途切れることもあります。このような場合、管理者に古い情報が表示されることがあります。各タブには [<STRONG>Last Updated</STRONG>] タイムスタンプが用意されているため、管理者は特定の帯域幅ポリシー サービスのデータが最後に更新された時間を確認できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p114">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the <STRONG>Machine Info</STRONG> and the <STRONG>Topology Info</STRONG> tabs won’t be populated. However, it is possible that the tool might connect initially but subsequently lose its connection to the service. In such cases, administrators might see outdated information. There is a <STRONG>Last Updated</STRONG> time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="787a1-197">出力</span><span class="sxs-lookup"><span data-stu-id="787a1-197">Output</span></span>

<span data-ttu-id="787a1-198">コマンドラインの出力はありません。プログラムの出力は、メインのグラフィカル ユーザー インターフェイス (GUI) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="787a1-198">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="787a1-199">用途</span><span class="sxs-lookup"><span data-stu-id="787a1-199">Purpose</span></span>

<span data-ttu-id="787a1-p115">Bandwidth Policy Service Monitor ツールを使用すると、管理者はトポロジに定義された各帯域幅ポリシー サービスの詳細を確認できます。さらに、管理者はネットワーク構成ドキュメントに定義されたすべてのリンクの帯域幅の使用状況を、リアルタイムで確認できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p115">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology. In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="787a1-202">要件</span><span class="sxs-lookup"><span data-stu-id="787a1-202">Requirements</span></span>

<span data-ttu-id="787a1-203">帯域幅ポリシーのサービスモニターツールは、Lync Server トポロジの一部であるコンピューターで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-203">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Lync Server topology.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="787a1-204">概要</span><span class="sxs-lookup"><span data-stu-id="787a1-204">Summary</span></span>

<span data-ttu-id="787a1-205">Bandwidth Policy Service Monitor ツールを使用すると、トポロジ内の帯域幅ポリシー サービスの状態を確認できます。さらに、ネットワーク構成設定で定義されたリンクの帯域幅のリアルタイムの使用状況を把握できるため、管理者にとって非常に重要なリソースです。</span><span class="sxs-lookup"><span data-stu-id="787a1-205">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="787a1-206">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="787a1-206">Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="787a1-p116">Bandwidth Utilization Analyzer は、エンタープライズ ネットワークの WAN リンク全体の UC エンドポイントで消費される帯域幅を、さまざまな観点から確認できるレポートを作成するツールです。これらのレポートを使用すると、現在の帯域幅の消費パターンを把握して、帯域幅の容量計画に活用できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p116">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network. These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-209">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-209">Description</span></span>

<span data-ttu-id="787a1-p117">Bandwidth Utilization Analyzer は、GUI ベースのアプリケーションとして実装されます。このツールは、ネットワーク全体音声に限定した使用状況に関するレポートを作成し、容量の計画に活用できます。また、さまざまなリンクに割り当てられた帯域幅容量を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="787a1-p117">Bandwidth Utilization Analyzer is implemented as a GUI-based application. This tool generates reports specifically for audio utilization across the network and helps with capacity planning. It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="787a1-213">出力</span><span class="sxs-lookup"><span data-stu-id="787a1-213">Output</span></span>

<span data-ttu-id="787a1-214">Bandwidth Utilization Analyzer には、システムで構成されたすべての WAN リンクにおける、音声の帯域幅容量と使用状況に関するグラフィカル プロットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="787a1-214">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="787a1-215">用途</span><span class="sxs-lookup"><span data-stu-id="787a1-215">Purpose</span></span>

<span data-ttu-id="787a1-p118">音声やビデオを配信する際に、エンタープライズ ネットワーク全体のメディア トラフィックによる帯域幅の使用状況の傾向を把握することは重要です。Bandwidth Utilization Analyzer ツールを使用すると、管理者はそれを把握できます。このツールでは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p118">In any voice and video deployment, it’s critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network. The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that. This tool does the following:</span></span>

  - <span data-ttu-id="787a1-219">ネットワーク全体にわたる音声の使用状況に関するレポートを生成する</span><span class="sxs-lookup"><span data-stu-id="787a1-219">Generates specific reports for audio utilization across the network</span></span>

  - <span data-ttu-id="787a1-220">より効果的な容量計画の立案と、さまざまなリンクに割り当てられた帯域幅容量の反復処理をサポートする</span><span class="sxs-lookup"><span data-stu-id="787a1-220">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="787a1-221">Bandwidth Utilization Analyzer では、帯域幅容量のグラフィカル プロットと使用状況レポートを作成できます。その範囲と実行可能な操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="787a1-221">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

  - <span data-ttu-id="787a1-222">エンタープライズ ネットワーク内のすべての WAN リンク</span><span class="sxs-lookup"><span data-stu-id="787a1-222">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="787a1-223">事前に指定した WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="787a1-223">Filtered by selected WAN links that have been chosen</span></span>

  - <span data-ttu-id="787a1-224">リンク容量を超過した WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="787a1-224">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="787a1-225">帯域幅の使用率が予測を下回る WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="787a1-225">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

  - <span data-ttu-id="787a1-226">重大レベル (WAN リンクの帯域幅使用率が容量の 90% を超過している) に達している WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="787a1-226">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="787a1-227">WAN リンクの種類 (ネットワーク サイト リンク、地域間リンク、サイト内リンク) でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="787a1-227">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

  - <span data-ttu-id="787a1-228">ネットワーク地域でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="787a1-228">Filtered by network region</span></span>

<div>

## <a name="applications"></a><span data-ttu-id="787a1-229">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="787a1-229">Applications</span></span>

<span data-ttu-id="787a1-230">Bandwidth Utilization Analyzer には、次の 2 つのアプリケーション (ツール) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="787a1-230">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

  - <span data-ttu-id="787a1-231">**WanLinkLogCollector**   このツールを使用すると、ユーザーは必要な情報を入力することができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-231">**WanLinkLogCollector.exe**   This tool enables its user to input the required information.</span></span>

  - <span data-ttu-id="787a1-232">**BandwidthUtilizationAnalyzer**  Microsoft Excel スプレッドシートソフトウェアレポートは、WanLinkLogCollector によって自動的に起動されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-232">**BandwidthUtilizationAnalyzer.xlsm**  A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="787a1-233">このアプリケーションでは、レポートにフィルターを適用できます (この記事の後半で説明します)。</span><span class="sxs-lookup"><span data-stu-id="787a1-233">This application allows the user to apply filters to the report as shown later in this article.</span></span>

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="787a1-234">Bandwidth Utilization Analyzer の使用フェーズ</span><span class="sxs-lookup"><span data-stu-id="787a1-234">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="787a1-235">Bandwidth Utilization Analyzer の使用は、次の 2 つのフェーズに分けられます。</span><span class="sxs-lookup"><span data-stu-id="787a1-235">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

  - <span data-ttu-id="787a1-236">ログの収集 (WanLinkLogCollector.exe を使用)</span><span class="sxs-lookup"><span data-stu-id="787a1-236">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

  - <span data-ttu-id="787a1-237">レポートのカスタマイズ (BandwidthUtilizationAnalyzer.xlsm を使用)</span><span class="sxs-lookup"><span data-stu-id="787a1-237">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="787a1-238">BandwidthUtilizationAnalyzer.xlsm はエンド ユーザーが手動で起動できないようにすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="787a1-238">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="787a1-239">Bandwidth Utilization Analyzer の起動</span><span class="sxs-lookup"><span data-stu-id="787a1-239">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="787a1-240">コマンド プロンプトで WanLinkLogCollector.exe を実行するか、Windows エクスプローラーを使用して起動します。</span><span class="sxs-lookup"><span data-stu-id="787a1-240">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

<span data-ttu-id="787a1-241">**WanLinkLogCollector.exe の使用**</span><span class="sxs-lookup"><span data-stu-id="787a1-241">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="787a1-242">WanLinkLogCollector.exe を使用するには、次の 3 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="787a1-242">There are three steps to using WanLinkLogCollector.exe:</span></span>

1.  <span data-ttu-id="787a1-243">**ログの記録**   レポートを生成する必要があるタイムラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="787a1-243">**Log the timeline**   Provide the timeline that the report needs to be generated for</span></span>

2.  <span data-ttu-id="787a1-244">**ファイルの**   場所情報を提供するファイルディレクトリを指定する</span><span class="sxs-lookup"><span data-stu-id="787a1-244">**Specify the file directories**   Provide file location information</span></span>

3.  <span data-ttu-id="787a1-245">**ログを収集し、レポートビューアー**  を起動するコマンドを実行してレポートを生成する</span><span class="sxs-lookup"><span data-stu-id="787a1-245">**Collect the logs and launch the report viewer**  Execute the command to generate the report</span></span>

<div>

## <a name="step-1---log-the-timeline"></a><span data-ttu-id="787a1-246">手順 1 - ログのタイムラインを指定する</span><span class="sxs-lookup"><span data-stu-id="787a1-246">Step 1 - Log the timeline</span></span>

<span data-ttu-id="787a1-247">タイムラインのログを記録するには、以下の図に示すように、次の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="787a1-247">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1.  <span data-ttu-id="787a1-248">**Start date** レポートを生成するタイムラインの開始日 (例: 2010 年 8 月 1 日)。</span><span class="sxs-lookup"><span data-stu-id="787a1-248">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2.  <span data-ttu-id="787a1-249">**End date** レポートを生成するタイムラインの終了日 (例: 2010 年 9 月 30 日)。</span><span class="sxs-lookup"><span data-stu-id="787a1-249">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
    <span data-ttu-id="787a1-250">![Bandwidth Utilization Analyzer の開始日/終了日](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Bandwidth Utilization Analyzer の開始日/終了日")</span><span class="sxs-lookup"><span data-stu-id="787a1-250">![Start and End dates in the Bandwidth Utilization A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start and End dates in the Bandwidth Utilization A")</span></span>  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="787a1-251">手順 2 - ファイルのディレクトリを指定する</span><span class="sxs-lookup"><span data-stu-id="787a1-251">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="787a1-252">図に示すように、以下のファイル ディレクトリを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-252">The following file directories can be specified by the user as shown.</span></span>

  - <span data-ttu-id="787a1-253">**サーバーのログファイルの場所**帯域幅ポリシーサーバーログが保存されているフォルダーの場所。</span><span class="sxs-lookup"><span data-stu-id="787a1-253">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="787a1-254">通常、これは\<、\>\\\<ファイルサーバーで\>\\FE appserverfiles\\PDP を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-254">This is typically in \<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP.</span></span>

  - <span data-ttu-id="787a1-255">**一時ファイルの保存場所**レポートの生成中に中間ファイルが保存される一時ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="787a1-255">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

<span data-ttu-id="787a1-256">![Bandwidth Utilization Analyzer のファイル ディレクトリ](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Bandwidth Utilization Analyzer のファイル ディレクトリ")</span><span class="sxs-lookup"><span data-stu-id="787a1-256">![File directories in the Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "File directories in the Bandwidth Utilization Anal")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="787a1-257">サーバー ログや一時ファイルを格納するフォルダーにアクセスできる十分な権限をツールのユーザーに割り当てるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="787a1-257">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="787a1-258">手順 3 - ログを収集してレポート ビューアーを起動する</span><span class="sxs-lookup"><span data-stu-id="787a1-258">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="787a1-p121">ログを収集してレポート ビューアーを起動するには、以下の図に示す [**Execute**] をクリックします。この手順により、必要なデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p121">To collect the logs and start the report viewer, click **Execute** as shown below. This step collects the required data.</span></span>

<span data-ttu-id="787a1-261">![Bandwidth Utilization Analyzer でのデータの収集](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Bandwidth Utilization Analyzer でのデータの収集")</span><span class="sxs-lookup"><span data-stu-id="787a1-261">![Collecting data in the Bandwidth Utilization Analy](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecting data in the Bandwidth Utilization Analy")</span></span>

<span data-ttu-id="787a1-262">入力の検証が正常に行われると、以下のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-262">When the input validation is successful, the message shown below is displayed.</span></span>

<span data-ttu-id="787a1-263">![BandwidthUtilizationAnalyzer でログに収集された通知](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "BandwidthUtilizationAnalyzer でログに収集された通知")</span><span class="sxs-lookup"><span data-stu-id="787a1-263">![Logs collected notification in the Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Logs collected notification in the Bandwidth Utili")</span></span>

<span data-ttu-id="787a1-p122">[**OK **] をクリックします。BandwidthUtilizationAnalyzer.xlsm は自動的に起動します。メッセージ ボックスの指示に従います。詳細については、次のセクション「**BandwidthUtilizationAnalyzer.xlsm の使用**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="787a1-p122">Click **OK**. BandwidthUtilizationAnalyzer.xlsm is automatically started. Follow the instructions in the message box. For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>

</div>

<div>


<span data-ttu-id="787a1-268">**BandwidthUtilizationAnalyzer.xlsm の使用**</span><span class="sxs-lookup"><span data-stu-id="787a1-268">**Using BandwidthUtilizationAnalyzer.xlsm**</span></span>

1.  <span data-ttu-id="787a1-269">BandwidthUtilizationAnalyzer.xlsm が自動的に起動したら、以下の図に示す [**Refresh**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="787a1-269">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
    <span data-ttu-id="787a1-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span><span class="sxs-lookup"><span data-stu-id="787a1-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span></span>

2.  <span data-ttu-id="787a1-271">ファイルのフォルダーが開いたら、メッセージ ボックスで指定した場所にある consolidated.csv を選びます。</span><span class="sxs-lookup"><span data-stu-id="787a1-271">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="787a1-272">また、場所が**C:\\Temp**として表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-272">It also shows the location as **C:\\Temp**.</span></span>
    
    <span data-ttu-id="787a1-273">![BandwidthUtilizationAnalyzer でフォルダーを開く](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "BandwidthUtilizationAnalyzer でフォルダーを開く")</span><span class="sxs-lookup"><span data-stu-id="787a1-273">![Opening a folder in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Opening a folder in BandwidthUtilizationAnalyzer.")</span></span>

3.  <span data-ttu-id="787a1-274">[**Import**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="787a1-274">Click **Import**.</span></span>

4.  <span data-ttu-id="787a1-p124">グラフィカル プロットが自動的に生成されます。バックグラウンドで作業中のポインターが表示されなくなると、使用できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p124">The graphical plot is automatically generated. It is available when the working-in-the-background pointer disappears.</span></span>
    
    <span data-ttu-id="787a1-277">![レポート ビューでのフィルターの適用](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "レポート ビューでのフィルターの適用")</span><span class="sxs-lookup"><span data-stu-id="787a1-277">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="787a1-278">レポート ビューにフィルターを適用する</span><span class="sxs-lookup"><span data-stu-id="787a1-278">Applying Filters to the Report View</span></span>

<span data-ttu-id="787a1-279">レポート ビューに適用できるフィルター (以下の図を参照) は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="787a1-279">The filters that can be applied to the report view as shown below are described as follows:</span></span>

<span data-ttu-id="787a1-280">![レポート ビューでのフィルターの適用](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "レポート ビューでのフィルターの適用")</span><span class="sxs-lookup"><span data-stu-id="787a1-280">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

1.  <span data-ttu-id="787a1-281">**Name** WAN リンクでフィルター処理 (グラフの右側のフィルター)。プレフィックス (縦長の青いボックスを参照) は、次のようなリンクの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-281">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
      - <span data-ttu-id="787a1-282">**S: Site** ネットワーク サイトからネットワーク地域への WAN リンク</span><span class="sxs-lookup"><span data-stu-id="787a1-282">**S Site** The WAN link from a network site to a network region</span></span>
    
      - <span data-ttu-id="787a1-283">**IS Inter-Site** 2 つのネットワーク サイト間の WAN リンク</span><span class="sxs-lookup"><span data-stu-id="787a1-283">**IS Inter-Site** The WAN link between two network sites</span></span>
    
      - <span data-ttu-id="787a1-284">**R Inter-Region** 2 つのネットワーク地域間の WAN リンク</span><span class="sxs-lookup"><span data-stu-id="787a1-284">**R Inter-Region** The WAN link between two network region</span></span>

2.  <span data-ttu-id="787a1-285">**Exceeded limit** 帯域幅の使用率が帯域幅容量を超過している WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="787a1-285">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3.  <span data-ttu-id="787a1-286">**Critical levels** 帯域幅の使用率が帯域幅容量の 90% 以上に達した WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="787a1-286">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4.  <span data-ttu-id="787a1-287">**Under-utilized** 帯域幅の使用率が帯域幅容量の 25% に達していない WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="787a1-287">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5.  <span data-ttu-id="787a1-288">**Link type** 次に示す WAN リンクの種類でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="787a1-288">**Link type** Filter by the following WAN links types:</span></span>
    
      - <span data-ttu-id="787a1-289">**Network site** タイプ</span><span class="sxs-lookup"><span data-stu-id="787a1-289">**Network site** type</span></span>
    
      - <span data-ttu-id="787a1-290">**Inter-site** タイプ</span><span class="sxs-lookup"><span data-stu-id="787a1-290">**Inter-site** type</span></span>
    
      - <span data-ttu-id="787a1-291">**Inter-Region link** タイプ</span><span class="sxs-lookup"><span data-stu-id="787a1-291">**Inter-Region link** type</span></span>

6.  <span data-ttu-id="787a1-292">**Region** ネットワーク地域でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="787a1-292">**Region** Filter by network region</span></span>

<span data-ttu-id="787a1-293">次の図は、これまでに紹介したフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-293">The following figures show the previously described filters.</span></span>

<span data-ttu-id="787a1-p125">[**Name**] でフィルター処理します。グラフに表示するリンクのリストを選びます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p125">Filter by **Name**. Select the list of links that need to be displayed in the graph.</span></span>

<span data-ttu-id="787a1-296">![BandwidthUtilizationAnalyzer での [Name] でのフィルター処理](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "BandwidthUtilizationAnalyzer での [Name] でのフィルター処理")</span><span class="sxs-lookup"><span data-stu-id="787a1-296">![Filtering by Name in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtering by Name in BandwidthUtilizationAnalyzer.")</span></span>

<span data-ttu-id="787a1-297">[**Exceeded limit**] でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="787a1-297">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="787a1-298">フィルターを適用するには、[**True**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="787a1-298">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="787a1-299">![[Exceeded Limit] でのフィルター処理](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "[Exceeded Limit] でのフィルター処理")</span><span class="sxs-lookup"><span data-stu-id="787a1-299">![Filtering by Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtering by Exceeded Limit.")</span></span>

<span data-ttu-id="787a1-300">[\*\*Critical levels \*\*] でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="787a1-300">Filter by **Critical levels**.</span></span> <span data-ttu-id="787a1-301">フィルターを適用するには、[\*\*TRUE \*\*] を選びます。</span><span class="sxs-lookup"><span data-stu-id="787a1-301">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="787a1-302">![[Critical Levels] でのフィルター処理](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "[Critical Levels] でのフィルター処理")</span><span class="sxs-lookup"><span data-stu-id="787a1-302">![Filtering by Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtering by Critical Levels.")</span></span>

<span data-ttu-id="787a1-303">[\*\*Under-utilized \*\*] でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="787a1-303">Filter by **Under utilized**.</span></span> <span data-ttu-id="787a1-304">フィルターを適用するには、[\*\*TRUE \*\*] を選びます。</span><span class="sxs-lookup"><span data-stu-id="787a1-304">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="787a1-305">![[Under Utilized] でのフィルター処理](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "[Under Utilized] でのフィルター処理")</span><span class="sxs-lookup"><span data-stu-id="787a1-305">![Filtering by Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtering by Under Utilized.")</span></span>

<span data-ttu-id="787a1-306">[**Link Type**] でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="787a1-306">Filter by **Link Type**.</span></span> <span data-ttu-id="787a1-307">表示する種類を 1 つ以上選びます。</span><span class="sxs-lookup"><span data-stu-id="787a1-307">Select the type or types that need to be displayed.</span></span>

<span data-ttu-id="787a1-308">![[Link Type] でのフィルター処理](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "[Link Type] でのフィルター処理")</span><span class="sxs-lookup"><span data-stu-id="787a1-308">![Filtering by Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtering by Link Type.")</span></span>

<span data-ttu-id="787a1-309">[**Region**] でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="787a1-309">Filter by **Region**.</span></span> <span data-ttu-id="787a1-310">リンクを表示する地域のリストを選びます。</span><span class="sxs-lookup"><span data-stu-id="787a1-310">Select a list of regions whose links need to be displayed.</span></span>

<span data-ttu-id="787a1-311">![[Region] でのフィルター処理](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "[Region] でのフィルター処理")</span><span class="sxs-lookup"><span data-stu-id="787a1-311">![Filtering by Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtering by Region.")</span></span>

</div>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="787a1-312">要件</span><span class="sxs-lookup"><span data-stu-id="787a1-312">Requirements</span></span>

  - <span data-ttu-id="787a1-313">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="787a1-313">The .NET Framework 3.5</span></span>

  - <span data-ttu-id="787a1-314">Microsoft Excel 2010 または Excel 2007</span><span class="sxs-lookup"><span data-stu-id="787a1-314">Microsoft Excel 2010 or Excel 2007</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="787a1-315">概要</span><span class="sxs-lookup"><span data-stu-id="787a1-315">Summary</span></span>

<span data-ttu-id="787a1-p131">Bandwidth Utilization Analyzer は、ネットワーク全体の UC トラフィックにおける音声の帯域幅の使用状況をプロットするために使用します。このツールは、ビデオの帯域幅の使用状況を報告する場合にも同様に使用できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p131">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network. This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

</div>

</div>

<div>

## <a name="call-parkometer"></a><span data-ttu-id="787a1-318">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="787a1-318">Call Parkometer</span></span>

<span data-ttu-id="787a1-319">Call Parkometer は、コール パーク オービット デバイスに簡単にアクセスできるコマンドライン アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="787a1-319">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-320">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-320">Description</span></span>

<span data-ttu-id="787a1-321">Call Parkometer は、現在パークされている通話を追跡するツールです。</span><span class="sxs-lookup"><span data-stu-id="787a1-321">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="787a1-322">オービットやコール パーク サーバー (CPS) の使用状況に関する統計情報も収集します。</span><span class="sxs-lookup"><span data-stu-id="787a1-322">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="787a1-323">このコマンドラインツールは、CPS への読み取りアクセスと書き込みアクセスの両方を提供します。これには、ローカルまたはリモート接続コンピューターからの SQL Server データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-323">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="787a1-p133">すべてのオプションは同時に使用できません。コマンドライン構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="787a1-p133">All options are mutually exclusive. Command-line syntax is as follows:</span></span>

  - <span data-ttu-id="787a1-326">**–o** パラメーター - このプールで構成されたすべてのオービット範囲を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-326">**–o** parameter—lists all orbit ranges configured for this pool.</span></span>

  - <span data-ttu-id="787a1-p134">**–n** パラメーター - このプールで現在使用されているすべてのオービットを一覧表示します。情報は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p134">**–n** parameter—lists all currently used orbits in this pool. The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="787a1-329">パーク元とパーク先の SIP Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="787a1-329">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
      - <span data-ttu-id="787a1-330">通話のパーク先の CPS のホスト名。</span><span class="sxs-lookup"><span data-stu-id="787a1-330">Host name of the CPS where the call is parked.</span></span>
    
      - <span data-ttu-id="787a1-331">通話がパークされた時点のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="787a1-331">Time stamp of when the call was parked.</span></span>

  - <span data-ttu-id="787a1-332">**–f** パラメーター - プールで現在使用されていないオービットの数を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-332">**–f** parameter—lists the number of currently free orbits in the pool.</span></span>

  - <span data-ttu-id="787a1-333">\*\*– r \<n\> \*\*パラメーター—\>最後に\<保留した通話の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-333">**–r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="787a1-334">情報は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-334">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="787a1-335">パーク先の SIP URI。</span><span class="sxs-lookup"><span data-stu-id="787a1-335">Parkee SIP URI.</span></span>
    
      - <span data-ttu-id="787a1-336">パーク元の SIP URI。</span><span class="sxs-lookup"><span data-stu-id="787a1-336">Parker SIP URI.</span></span>
    
      - <span data-ttu-id="787a1-337">通話のパーク先の CPS のホスト名。</span><span class="sxs-lookup"><span data-stu-id="787a1-337">Host name of the CPS where the call was parked.</span></span>
    
      - <span data-ttu-id="787a1-338">通話が保留解除または切断された時点のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="787a1-338">Time stamp of when the call was retrieved or dropped.</span></span>

  - <span data-ttu-id="787a1-339">\*\*-t\<n\> \*\*パラメーター-データベース内のオービットを予約して、割り当てられた値の乱数をランダムに表示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-339">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="787a1-340">出力</span><span class="sxs-lookup"><span data-stu-id="787a1-340">Output</span></span>

<span data-ttu-id="787a1-341">コマンド プロンプトで指定された入力パラメーターによっては、Call Parkometer に次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-341">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

  - <span data-ttu-id="787a1-342">このプールで構成されたすべてのオービット範囲</span><span class="sxs-lookup"><span data-stu-id="787a1-342">All orbit ranges that are configured for this pool</span></span>

  - <span data-ttu-id="787a1-343">現在パークされている通話</span><span class="sxs-lookup"><span data-stu-id="787a1-343">Currently parked calls</span></span>

  - <span data-ttu-id="787a1-344">有効な (使用可能な) オービットの数</span><span class="sxs-lookup"><span data-stu-id="787a1-344">Number of free (available) orbits</span></span>

  - <span data-ttu-id="787a1-345">最近パークされた通話</span><span class="sxs-lookup"><span data-stu-id="787a1-345">Recently parked calls</span></span>

  - <span data-ttu-id="787a1-346">一定およびランダムなオービットの値をテストするために予約されたオービット</span><span class="sxs-lookup"><span data-stu-id="787a1-346">Reserved orbits for testing uniform and random orbit values</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="787a1-347">用途</span><span class="sxs-lookup"><span data-stu-id="787a1-347">Purpose</span></span>

<span data-ttu-id="787a1-p136">CPS ツールを使用すると、CPS データベースへのコマンドライン アクセスを確立できます。管理者は、CPS の使用状況を確認して、プールに割り当てられているオービットの数を把握できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p136">The purpose of the CPS tool is to provide command-line access to the CPS database. The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="787a1-350">要件</span><span class="sxs-lookup"><span data-stu-id="787a1-350">Requirements</span></span>

<span data-ttu-id="787a1-351">CPS が実行されている同じコンピューターで実行する場合、このツールの使用に必要な条件はありません。</span><span class="sxs-lookup"><span data-stu-id="787a1-351">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="787a1-352">このツールがリモートコンピューターで実行される場合は、Lync Server 2013 で使用される SQL Server データベースがリモートアクセスを許可するように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-352">If this tool is run on a remote computer, the SQL Server database used by Lync Server 2013 must be configured to allow remote access.</span></span> <span data-ttu-id="787a1-353">呼び出しの場合は、プールの SQL Server に接続するために SQL Server データベース接続文字列を使用して構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-353">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool’s SQL Server.</span></span> <span data-ttu-id="787a1-354">この SQL Server データベース接続文字列は構成ファイルで定義されて**います。** このファイルは、par・・・・・・・・ m の場所にあるのと同じディレクトリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-354">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="787a1-355">次の XML ファイルは、par・メータの例です。構成する必要があるパラメーターは、ユーザー名 (たとえば、mydomain\\Administrator)、パスワード (mypassword など)、ホスト名 (たとえば、myserver) です。</span><span class="sxs-lookup"><span data-stu-id="787a1-355">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

## <a name="examples"></a><span data-ttu-id="787a1-356">例</span><span class="sxs-lookup"><span data-stu-id="787a1-356">Examples</span></span>

<span data-ttu-id="787a1-357">展開されたオービット範囲: –o パラメーターによって、このプールで構成されたすべてのオービット範囲が次のように一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-357">Deployed orbit ranges: the –o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

<span data-ttu-id="787a1-358">![Call Parkometer のオービット範囲](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Call Parkometer のオービット範囲")</span><span class="sxs-lookup"><span data-stu-id="787a1-358">![Orbit ranges in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbit ranges in Call Parkometer.")</span></span>

<span data-ttu-id="787a1-359">現在パークされている通話: –n パラメーターによって、このプールで現在使用されているすべてのオービットが次のように一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-359">Currently parked calls: the –n parameter lists all currently used orbits on this pool as shown</span></span>

<span data-ttu-id="787a1-360">![Call Parkometer で現在保留されている通話](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Call Parkometer で現在保留されている通話")</span><span class="sxs-lookup"><span data-stu-id="787a1-360">![Currently-parked calls in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Currently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="787a1-361">使用されていないオービットの数: –f パラメーターによって、プールで現在使用されていないオービットの数が次のように一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-361">Number of free orbits: the –f parameter lists the number of currently free orbits in the pool as shown</span></span>

<span data-ttu-id="787a1-362">![Call Parkometer の使用されていないオービット](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Call Parkometer の使用されていないオービット")</span><span class="sxs-lookup"><span data-stu-id="787a1-362">![Free orbits in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free orbits in Call Parkometer.")</span></span>

<span data-ttu-id="787a1-363">最近の保留中の通話: \<–\> r n パラメーター \<は\> 、次に示すように、最後の保留中の通話を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-363">Recently parked calls: the –r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

<span data-ttu-id="787a1-364">![Call Parkometer で最近保留された通話](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Call Parkometer で最近保留された通話")</span><span class="sxs-lookup"><span data-stu-id="787a1-364">![Recently-parked calls in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Recently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="787a1-365">次に示すように、軌道\<予約\>をテストします。-t n パラメーターテストでは、データベース内でオービットを予約しています。</span><span class="sxs-lookup"><span data-stu-id="787a1-365">Test orbit reservation: the –t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

<span data-ttu-id="787a1-366">![Call Parkometer のオービット予約のテスト](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Call Parkometer のオービット予約のテスト")</span><span class="sxs-lookup"><span data-stu-id="787a1-366">![Test orbit reservations in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test orbit reservations in Call Parkometer.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="787a1-367">概要</span><span class="sxs-lookup"><span data-stu-id="787a1-367">Summary</span></span>

<span data-ttu-id="787a1-368">Call Parkometer は、コール パーク サーバーに関する詳しい情報を提供するコマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="787a1-368">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a><span data-ttu-id="787a1-369">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="787a1-369">CleanupStorageServiceData</span></span>

<span data-ttu-id="787a1-370">CleanupStorageServiceData リソースキットツールを使用すると、Lync Server Storage Service によって使用されているデータベースから、孤立したデータを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-370">The CleanupStorageServiceData resource kit tool allows for deleting of orphaned data from the database used by the Lync Server Storage Service (LYSS).</span></span> <span data-ttu-id="787a1-371">ストレージサービスの1つの機能は、Lync Server と、SQL Server や Exchange などのさまざまなバックエンドデータストレージエンドポイント間の通信をバッファリングすることです。</span><span class="sxs-lookup"><span data-stu-id="787a1-371">One function of the storage service is to buffer communication between Lync Server and various back-end data storage endpoints, like SQL Server and Exchange.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-372">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-372">Description</span></span>

<span data-ttu-id="787a1-373">高可用性をサポートするために、SS は、プール内の複数のフロントエンドサーバーにあるデータのコピーを受け取り、一時的に保存し、そのデータを最終的な長期保存場所に配信した後、そのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="787a1-373">To support high availability, LYSS accepts and saves copies of the data on multiple front end servers in the pool temporarily, and removes that data once it has been delivered to its final long-term storage location.</span></span> <span data-ttu-id="787a1-374">通常の操作中に、サーバーがクラッシュしたり、処理の問題が発生したりして、一部のデータが正しくクリーンアップされないことがあります。</span><span class="sxs-lookup"><span data-stu-id="787a1-374">There are unusual situations which may occur during otherwise normal operation, when a server might crash or experience a processing issue, and some data might not get cleaned up properly.</span></span> <span data-ttu-id="787a1-375">このデータは無害ですが、制限された処理リソースを消費します。</span><span class="sxs-lookup"><span data-stu-id="787a1-375">This data is harmless, but it does consume limited processing resources.</span></span> <span data-ttu-id="787a1-376">通常必要となるデータメンテナンスの多くは自動化されていますが、このツールを使用すると、自動削除ができない場合に、孤立したデータの安全な識別と削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-376">Much of the normal required data maintenance is automated, but this tool allows for the safe identification and removal of such orphaned data when automated removal is not possible.</span></span> <span data-ttu-id="787a1-377">このツールは、health monitoring System Center Operations Manager (SCOM) アラートが発生したときに表示されます。これにより、管理者は、プール内のローカルの SS データベースから不要なデータを削除するように求められます。</span><span class="sxs-lookup"><span data-stu-id="787a1-377">Usage of this tool is indicated when a health monitoring System Center Operations Manager (SCOM) alert is raised which asks the administrator to remove the unneeded data from the local LYSS databases in the pool.</span></span> <span data-ttu-id="787a1-378">フロントエンドのイベントログに、アラートをトリガーするイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-378">There will be a corresponding event in the event log on the front end which triggered the alert.</span></span> <span data-ttu-id="787a1-379">イベントの詳細には、フロントエンドに含まれる孤立したデータの量に関する情報が含まれ、そのデータが特定の事前決定しきい値を超えたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="787a1-379">The event details will contain information about the amount of orphaned data contained on the front end, and is raised when that data exceeds certain pre-determine thresholds</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="787a1-380">要件</span><span class="sxs-lookup"><span data-stu-id="787a1-380">Requirements</span></span>

<span data-ttu-id="787a1-381">Lync Server 2013 のリソースキットツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="787a1-381">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="787a1-382">このツールは、Lync Server および Lync Server 2013 管理シェルがインストールされているドメインに参加しているコンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-382">The tool runs on domain-joined machines where Lync Server and Lync Server 2013 Management Shell are installed.</span></span> <span data-ttu-id="787a1-383">このツールは、管理シェルのコマンドレットを使用して、プール内のすべてのフロントエンドサーバーを特定します。</span><span class="sxs-lookup"><span data-stu-id="787a1-383">The tool uses a cmdlet from the management shell to identify all Front End servers in the pool.</span></span> <span data-ttu-id="787a1-384">第二に、このツールは、 **Rtclocal**データベースがインストールされているプール内のコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-384">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="787a1-385">このデータベースは、Lync Server ルーティングサービスとの通信に必要な接続の詳細情報を取得するために CleanupStorageServiceData ツールによって使用されます。最後に、ツールを呼び出すアカウントまたは資格情報に、出力ログの書き込み先のファイル共有への読み取り/書き込みアクセス許可が必要です。また、このツールは、プールが安定した状態にあることに依存します。</span><span class="sxs-lookup"><span data-stu-id="787a1-385">This database is used by the CleanupStorageServiceData tool to get the connection details needed to communicate with the Lync Server Routing Service.Finally, the account or credential invoking the tool must have read/write permission to the file share to which they want to write the output log.Also, this tool depends on the pool being in a stable state.</span></span> <span data-ttu-id="787a1-386">つまり、すべてのフロントエンドサーバーが起動して実行されていることが前提となっています。各ルーティンググループは、1つのプライマリフロントエンドサーバーと2つのセカンダリフロントエンドサーバーの完全なセットを持っている必要があります。ervers</span><span class="sxs-lookup"><span data-stu-id="787a1-386">In essence this means that every Front End server is expected to be up and running, the SQL Server LYNCLOCAL instance and LYSS database must be able to be connected to, and each routing group must have a complete set of 1 primary Front End servers and 2 secondary Front End servers.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="787a1-387">例</span><span class="sxs-lookup"><span data-stu-id="787a1-387">Examples</span></span>

<span data-ttu-id="787a1-388">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\storageservice\> ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="787a1-388">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe</span></span>

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

## <a name="dbanalyze"></a><span data-ttu-id="787a1-389">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="787a1-389">DBAnalyze</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-390">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-390">Description</span></span>

<span data-ttu-id="787a1-391">DBAnalyze は、管理者が Lync Server 2013 データベースに関する分析レポートを収集するのに役立つコマンドラインツールです。</span><span class="sxs-lookup"><span data-stu-id="787a1-391">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Lync Server 2013 databases.</span></span> <span data-ttu-id="787a1-392">DBAnalyze には、診断モード、ユーザー データ モード、会議モード、MCU モード、ディスク断片化モードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="787a1-392">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

  - <span data-ttu-id="787a1-393">**診断モード**   テーブル (レコード数) に関する情報を含むレポートを作成します。断片化、データサイズ、インデックスサイズ)、データとログファイルのサイズ、最後のバックアップ時間、連絡先の配布には、Microsoft Office Communications Server が実行されているサーバー間、アクセス許可の平均数、ユーザーごとに開催される電話会議の平均数、スケジュールされているユーザーあたりの会議の平均数、スケジュールが設定されます。会議、アクティブな会議、データベースのバージョン。</span><span class="sxs-lookup"><span data-stu-id="787a1-393">**Diagnostic mode**   Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can’t be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="787a1-394">診断モードを実行すると、サーバーのパフォーマンスに影響を与えることがあります。</span><span class="sxs-lookup"><span data-stu-id="787a1-394">Running diagnostic mode can affect server performance.</span></span>

    
    </div>

  - <span data-ttu-id="787a1-395">**ユーザーデータモード**  : 指定されたユーザーの連絡先、コンテナー、サブスクリプション、パブリケーション、アクセス許可、連絡先グループのデータ、あるいはそのユーザーを連絡先やアクセス許可の一覧に登録しているユーザーの情報をレポートします。</span><span class="sxs-lookup"><span data-stu-id="787a1-395">**User data mode**  Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="787a1-396">このモードでは、ユーザーが開催する、または招待された会議の概要データもレポートします。</span><span class="sxs-lookup"><span data-stu-id="787a1-396">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

  - <span data-ttu-id="787a1-397">**会議モード**   では、電話会議のすべてのスケジュールの詳細、出席者リスト、会議で許可されているメディアの種類の一覧、アクティブな mcu (multipoint control ユニット)、アクティブな参加者の一覧、各参加者のシグナリング状態など、特定の会議の詳細データが報告されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-397">**Conference mode**   Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant’s signaling state.</span></span>

  - <span data-ttu-id="787a1-398">**会議 id**  のデコードは、 **/pstnid**スイッチで指定されている公衆交換電話網 (PSTN) 会議 id をデコードしますが、詳細情報についてはバックエンドに接続しません。</span><span class="sxs-lookup"><span data-stu-id="787a1-398">**Decode Meeting ID**  Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

  - <span data-ttu-id="787a1-399">**会議を解決**   し、 **/pstnid**スイッチで指定されている PSTN 会議 ID をデコードし、ID で示されている会議に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-399">**Resolve conference**   Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

  - <span data-ttu-id="787a1-400">**Mcu モード**  では、プール内の各 MCU の ID、メディアの種類、URL、ハートビートの状態、会議のロード、参加者の負荷が報告されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-400">**MCUs mode**  Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

  - <span data-ttu-id="787a1-401">**ディスクの最適化モード**  では、すべてのディスクの断片化の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-401">**Disk fragmentation mode**  Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="787a1-p143">このツールは、さまざまな問題を診断し、管理者の容量計画を支援するために使用できます。たとえば、サーバー A に所属する大多数のユーザーが、サーバー B に所属するユーザーを連絡先として選択した場合、管理者はサーバー A のユーザーをサーバー B に移動して、サーバー間のトラフィックを削減できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p143">This tool can be used to diagnose various problems or to assist administrators with capacity planning. For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="787a1-404">出力</span><span class="sxs-lookup"><span data-stu-id="787a1-404">Output</span></span>

<span data-ttu-id="787a1-405">このツールは、Lync Server 2013 データベースに関する定義済みレポートを出力します。</span><span class="sxs-lookup"><span data-stu-id="787a1-405">This tool outputs predefined reports about the Lync Server 2013 database.</span></span> <span data-ttu-id="787a1-406">**パス:** % ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span><span class="sxs-lookup"><span data-stu-id="787a1-406">**Path:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="787a1-407">用途</span><span class="sxs-lookup"><span data-stu-id="787a1-407">Purpose</span></span>

<span data-ttu-id="787a1-408">Dbanalyze .exe をインストールするには、ローカルフォルダーにコピーし、ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="787a1-408">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="787a1-409">このツールを使用するには、コマンドラインから次のコマンドを実行します。`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span><span class="sxs-lookup"><span data-stu-id="787a1-409">To use the tool, run the following command from the command line.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span></span> <span data-ttu-id="787a1-410">コマンドラインオプションの説明を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-410">The descriptions for the command-line options are shown below.</span></span>

<span data-ttu-id="787a1-411">![Dbanalyze.exe のコマンド ライン オプション](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Dbanalyze.exe のコマンド ライン オプション")</span><span class="sxs-lookup"><span data-stu-id="787a1-411">![Command line options for Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Command line options for Dbanalyze.exe.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="787a1-412">要件</span><span class="sxs-lookup"><span data-stu-id="787a1-412">Requirements</span></span>

<span data-ttu-id="787a1-413">**コンピューター**DBAnalyze は、Lync Server 2013 がインストールされているドメインに参加しているコンピューターからのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-413">**Computer** DBAnalyze can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span>

<span data-ttu-id="787a1-414">**ネットワーク** コンピューターは、バックエンド データベースに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-414">**Network** The computer should be able to connect to the back-end database.</span></span>

<span data-ttu-id="787a1-415">**ソフトウェア**DBAnalyze を実行する前に、Lync Server 2013 ソフトウェアコンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-415">**Software** Lync Server 2013 software components must be installed before running DBAnalyze.</span></span>

<span data-ttu-id="787a1-416">**ユーザー**次の表は、Lync Server 2013 データベースへのアクセスに必要な権限を持っている管理者を示しています。</span><span class="sxs-lookup"><span data-stu-id="787a1-416">**Users**The table below shows the administrators who have the necessary permissions to access Lync Server 2013 databases.</span></span>

<span data-ttu-id="787a1-417">![Dbanalyze.exe の権限のテーブル](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Dbanalyze.exe の権限のテーブル")</span><span class="sxs-lookup"><span data-stu-id="787a1-417">![Permissions table for Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Permissions table for Dbanalyze.exe.")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="787a1-418"><STRONG>/report:disk</STRONG> モードでは、ローカル管理者のアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="787a1-418">A local administrator account is required for <STRONG>/report:disk</STRONG> mode.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="787a1-419">例</span><span class="sxs-lookup"><span data-stu-id="787a1-419">Examples</span></span>

<span data-ttu-id="787a1-420">次に、有効な Dbanalyze.exe コマンドの例を示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-420">The following are examples of valid Dbanalyze.exe commands:</span></span>

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a><span data-ttu-id="787a1-421">概要</span><span class="sxs-lookup"><span data-stu-id="787a1-421">Summary</span></span>

<span data-ttu-id="787a1-422">DBAnalyzer を使用すると、管理者は Lync Server 2013 データベースの分析をすばやく簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-422">DBAnalyzer provides administrators a quick and easy to analyze Lync Server 2013 databases.</span></span>

</div>

</div>

<div>

## <a name="importstorageservicedata"></a><span data-ttu-id="787a1-423">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="787a1-423">ImportStorageServiceData</span></span>

<span data-ttu-id="787a1-424">ImportStorageServiceData リソース キット ツールを使用すると、Storage Service (LYSS) からフラッシュされたキューやエンドポイントのデータを、ストレージ サービスに再インポートできます。</span><span class="sxs-lookup"><span data-stu-id="787a1-424">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-425">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-425">Description</span></span>

<span data-ttu-id="787a1-426">Storage Service からのデータのフラッシュは、キュー アイテムの状態やデータベースのサイズに基づいて自動的 (定期的) に行われた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-426">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="787a1-427">また、プール フェールオーバー コマンドレット、またはそれによって呼び出される StorageServiceFullFlush コマンドレットの手動呼び出しによって行われた可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="787a1-427">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="787a1-428">フロントエンドのデータベースのサイズが通常のレベルよりも上にある場合は、データがより多くエクスポートされる可能性が高いため、データを再インポートしないことをお勧めします。さらに、ストレージサービスキューの増加を引き起こしたエラーの原因となった問題は、まず解決される必要があります (Exchange のエンドポイントエラー、ネットワークの問題、その他の問題など)。</span><span class="sxs-lookup"><span data-stu-id="787a1-428">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

<span data-ttu-id="787a1-429">**シナリオ 1:** プールのフェールオーバー中に、各フロントエンドのストレージ サービスからファイルがフラッシュされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-429">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="787a1-430">フェールオーバーが完了したら、ツールを実行してデータを再インポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-430">After failover is completed, the tool should be run to re-import the data.</span></span>

<span data-ttu-id="787a1-431">**シナリオ 2:** データは毎日自動的にフラッシュされます。または、特定のサイズのしきい値を超える記憶域サービスデータベースに対応しています (たとえば、60%、80%、90%)。</span><span class="sxs-lookup"><span data-stu-id="787a1-431">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="787a1-432">この自動フラッシュデータは、管理者によって定期的に再インポートされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-432">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="787a1-433">このような状況では、monitoring の SCOM パックが展開されていない場合、ストレージサービスからフラッシュされるデータに関連するイベントが Lync Server ストレージサービスにあります。</span><span class="sxs-lookup"><span data-stu-id="787a1-433">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Lync Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="787a1-434">32075のイベント Id (完全なフラッシュ操作が開始されます)、32076 (完全なフラッシュが完了しました)、32082 (メンテナンスレベルのフラッシュ開始)、32083 (メンテナンスレベルのフラッシュの完了)、32089 (データベースの書き込みによるフラッシュ発生)。</span><span class="sxs-lookup"><span data-stu-id="787a1-434">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="787a1-435">注: これらのイベント Id は、RTM リリースに対応しています。</span><span class="sxs-lookup"><span data-stu-id="787a1-435">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="787a1-436">管理者にこれらのイベントが表示される場合は、フラッシュアウトされたファイルがあることを意味します。このデータは定期的にこのツールを使ってインポートし直す必要があります。たとえば、週ごとに1回。</span><span class="sxs-lookup"><span data-stu-id="787a1-436">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="787a1-437">オンラインサービスリリースの場合、Lync Server 用の正常性監視 SCOM pack が展開されていると、管理者に対して、フラッシュされたデータを記憶域サービスに再インポートするように求める新しい通知が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="787a1-437">For the Online Service release, if health monitoring SCOM pack for Lync Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="787a1-438">警告の原因に対応するイベントは、フロントエンド サーバーのイベント ログに出されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-438">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="787a1-439">イベントの出力には、フラッシュされたデータ ファイルが置かれている親パスや、警告の条件に一致するファイルの個数などが記述されています。</span><span class="sxs-lookup"><span data-stu-id="787a1-439">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="787a1-440">警告の条件は、指定の親パスに Y 日以上前のファイルが X 個以上あることです (X と Y は StorageService 内に事前設定されていますが、APPCONFIG ファイルを変更して上書きできます)。</span><span class="sxs-lookup"><span data-stu-id="787a1-440">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="787a1-441">状態の警告が出されるイベントで、親パスが異なる場合の例を以下に 2 つ示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-441">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="787a1-442">(たとえば、c:\\programdata\\Microsoft\\Lync Server\\storageservice)。</span><span class="sxs-lookup"><span data-stu-id="787a1-442">( for example c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ).</span></span> <span data-ttu-id="787a1-443">その後、管理者はこの reskit ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="787a1-443">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="787a1-444">このツールは、ツールが実行されているフロントエンドでデータが所有されていない場合に、このツールが実行されているフロントエンドの CPU と IO の負荷を、他のフロントエンドと共に増やします。</span><span class="sxs-lookup"><span data-stu-id="787a1-444">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="787a1-445">このツールは、フロントエンドの CPU と IO の負荷が高くない場合 (ピーク時間以外の場合など) に、このツールを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="787a1-445">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="787a1-446">次に、このツールでは、1つのデータファイルをインポートするために 2 ~ 3 分間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="787a1-446">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="787a1-447">ツールの実行時間を見積もるときは、この点に注意してください。ツールによって生成される詳細ログファイルは、既定でファイルストアに表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-447">Keep this in mind when estimating how long tool will be running.The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="787a1-448">ログファイルの数が MB 以上である可能性があるため、エラーが報告されていない場合は削除します。</span><span class="sxs-lookup"><span data-stu-id="787a1-448">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

<span data-ttu-id="787a1-449">![記憶域サーバーのイベント ログのサンプル イベント](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "記憶域サーバーのイベント ログのサンプル イベント")</span><span class="sxs-lookup"><span data-stu-id="787a1-449">![Sample Storage Server event log events.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Sample Storage Server event log events.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="787a1-450">要件</span><span class="sxs-lookup"><span data-stu-id="787a1-450">Requirements</span></span>

<span data-ttu-id="787a1-451">Lync Server 2013 のリソースキットツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="787a1-451">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="787a1-452">このツールは、Lync Server および Lync Server 管理シェルがインストールされているドメインに参加しているコンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-452">The tool runs on domain-joined machines where Lync Server and Lync Server Management Shell are installed.</span></span> <span data-ttu-id="787a1-453">このツールは、管理シェルのコマンドレットを使用して、プール内のすべてのフロントエンドサーバーを特定します。</span><span class="sxs-lookup"><span data-stu-id="787a1-453">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="787a1-454">第二に、このツールは、 **Rtclocal**データベースがインストールされているプール内のコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-454">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="787a1-455">このデータベースは、ツールによって、プールの WEBSERVICE ファイル共有の場所を取得するために使用されます。さらに、このツールを使用する前に、各フロントエンドサーバーで、まず、各フロントエンドサーバーで**enable-PSRemoting**を使用して Windows PowerShell リモート処理を有効にする必要があります。また、このツールが実行されているコンピューターの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="787a1-455">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="787a1-456">そうしないと、このツールのリモート Windows PowerShell コマンドが失敗します。</span><span class="sxs-lookup"><span data-stu-id="787a1-456">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="787a1-457">Windows PowerShell リモート処理は、プールの終了後、すべてのフロントエンドサーバーで無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-457">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="787a1-458">最後に、ツールを呼び出すアカウントまたは資格情報に、このツールを実行しているプールの webservice ファイル共有への読み取り/書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="787a1-458">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="787a1-459">そうしないと、IO 権限のエラーでツールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="787a1-459">Otherwise the tool will fail with IO Permission errors.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="787a1-460">Windows Server 2012 では、windows PowerShell リモート処理は既定で有効になっていますが、Windows Server 2008 オペレーティングシステムでは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="787a1-460">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="787a1-461">例</span><span class="sxs-lookup"><span data-stu-id="787a1-461">Examples</span></span>

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

## <a name="lcssync"></a><span data-ttu-id="787a1-462">LCSSync</span><span class="sxs-lookup"><span data-stu-id="787a1-462">LCSSync</span></span>

<span data-ttu-id="787a1-463">LCSSync ツールを使用すると、複数のフォレスト環境に Lync Server 2013 通信ソフトウェアを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-463">The LCSSync tool helps to deploy Lync Server 2013 communications software in a multi-forest environment.</span></span> <span data-ttu-id="787a1-464">このツールは、さまざまなユーザーのフォレストのユーザーやグループを Active Directory ドメインサービスの連絡先オブジェクトとして、Lync Server 2013 がインストールされている中央フォレストに同期するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-464">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Lync Server 2013 is installed.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-465">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-465">Description</span></span>

<span data-ttu-id="787a1-466">LCSSync は、中央フォレストの同期された Active Directory ドメインサービスの連絡先オブジェクトを使用して、Lync Server のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="787a1-466">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Lync Server.</span></span> <span data-ttu-id="787a1-467">シングルサインインを提供するには、プライマリユーザーアカウントが、Lync Server 2013 の中央フォレストの Active Directory ドメインサービスの連絡先オブジェクトにマップされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-467">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Lync Server 2013.</span></span> <span data-ttu-id="787a1-468">このツールは、そのマッピングを支援します。</span><span class="sxs-lookup"><span data-stu-id="787a1-468">This tool helps perform that mapping.</span></span> <span data-ttu-id="787a1-469">このツールには、Microsoft Identity Integration Server で Management Agents を作成するためのテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="787a1-469">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="787a1-470">概要</span><span class="sxs-lookup"><span data-stu-id="787a1-470">Summary</span></span>

<span data-ttu-id="787a1-471">LCSSync ツールは、マルチフォレスト環境で Lync Server を展開するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="787a1-471">The LCSSync tool helps to deploy Lync Server in a multi-forest environment.</span></span>

</div>

</div>

<div>

## <a name="lookupuserconsole"></a><span data-ttu-id="787a1-472">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="787a1-472">LookupUserConsole</span></span>

<span data-ttu-id="787a1-473">LookupUserConsole ツールは、特定のユーザーに関する内部の Lync Server ルーティング情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-473">The LookupUserConsole tool displays internal Lync Server routing information about specific users.</span></span> <span data-ttu-id="787a1-474">この情報は、Microsoft のサポート担当者が展開やルーティングの問題を解決するのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-474">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-475">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-475">Description</span></span>

<span data-ttu-id="787a1-476">LookupUserConsole を実行すると、SIP アドレスを受け取り、Lync Server の内部ルーティング情報を表示しようとしているコマンドプロンプトが開きます。</span><span class="sxs-lookup"><span data-stu-id="787a1-476">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Lync Server routing information relating them.</span></span> <span data-ttu-id="787a1-477">LookupUserConsole ツールを終了するには、「**exit**」 と入力します。</span><span class="sxs-lookup"><span data-stu-id="787a1-477">Type **exit** to quit the LookupUserConsole tool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="787a1-478">要件</span><span class="sxs-lookup"><span data-stu-id="787a1-478">Requirements</span></span>

<span data-ttu-id="787a1-479">Lync Server 2013 のリソースキットツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="787a1-479">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="787a1-480">このツールは、Lync Server がインストールされているドメインに参加しているコンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-480">The tool runs on domain-joined machines where Lync Server is installed</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="787a1-481">例</span><span class="sxs-lookup"><span data-stu-id="787a1-481">Examples</span></span>

<span data-ttu-id="787a1-482">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>lookupuserconsole</span><span class="sxs-lookup"><span data-stu-id="787a1-482">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe</span></span>

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

## <a name="msturnping"></a><span data-ttu-id="787a1-483">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="787a1-483">MsTurnPing</span></span>

<span data-ttu-id="787a1-484">MSTurnPing ツールでは、Microsoft Lync Server 2013 通信ソフトウェアの管理者は、オーディオ/ビデオエッジとオーディオ/ビデオ認証サービスを実行しているサーバーと、トポロジで帯域幅ポリシーサービスを実行しているサーバーの状態を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-484">The MSTurnPing tool allows an administrator of Microsoft Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-485">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-485">Description</span></span>

<span data-ttu-id="787a1-486">MSTurnPing ツールを使用すると、Lync Server 2013 通信ソフトウェアの管理者は、オーディオ/ビデオエッジとオーディオ/ビデオ認証サービスを実行しているサーバーと、トポロジで帯域幅ポリシーサービスを実行しているサーバーの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-486">The MSTurnPing tool allows an administrator of Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="787a1-487">このツールを使用すると、管理者は次のテストを実行できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-487">The tool allows the administrator to perform the following tests:</span></span>

1.  <span data-ttu-id="787a1-488">音声ビデオ エッジ サーバー テスト: トポロジ内の音声ビデオ エッジ サーバーに対して次のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="787a1-488">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="787a1-489">Lync Server の音声/ビデオ認証サービスが開始されていて、適切な資格情報を発行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="787a1-489">Verifying that the Lync Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="787a1-490">Lync Server の音声/ビデオエッジサービスが開始されていることを確認し、外部境界にリソースを正常に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-490">Verifying that the Lync Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2.  <span data-ttu-id="787a1-491">帯域幅ポリシー サービス テスト: トポロジ内の帯域幅ポリシー サービスを実行しているすべてのサーバーに対して次のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="787a1-491">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="787a1-492">Lync Server 帯域幅ポリシーサービス (認証) が開始されていて、適切な資格情報を発行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="787a1-492">Verifying that the Lync Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="787a1-493">Lync Server 帯域幅ポリシーサービス (コア) が開始されていて、帯域幅の確認を正常に実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="787a1-493">Verifying that the Lync Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="787a1-494">このツールは、トポロジの一部でありローカル ストアがインストールされているコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-494">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="787a1-495">出力</span><span class="sxs-lookup"><span data-stu-id="787a1-495">Output</span></span>

<span data-ttu-id="787a1-496">このツールでは、各操作の結果が出力されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-496">The tool outputs the results of each of the operations.</span></span>

  - <span data-ttu-id="787a1-497">**AudioVideoEdgeServer** テストを実行した場合、ツールの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="787a1-497">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="787a1-498">トポロジで Lync Server の音声/ビデオ認証サービスを提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="787a1-498">The test results of the computers that provide the Lync Server Audio/Video Authentication service in the topology</span></span>
    
      - <span data-ttu-id="787a1-499">トポロジで Lync Server オーディオ/ビデオエッジサービスを提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="787a1-499">The test results of the computers that provide the Lync Server Audio/Video Edge service in the topology</span></span>

  - <span data-ttu-id="787a1-500">**BandwidthPolicyServer** テストを実行した場合、ツールの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="787a1-500">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="787a1-501">トポロジで Lync Server 帯域幅ポリシーサービス (認証) を提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="787a1-501">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Authentication) in the topology</span></span>
    
      - <span data-ttu-id="787a1-502">トポロジで Lync Server 帯域幅ポリシーサービス (コア) を提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="787a1-502">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Core) in the topology</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="787a1-503">要件</span><span class="sxs-lookup"><span data-stu-id="787a1-503">Requirements</span></span>

  - <span data-ttu-id="787a1-504">このツールは、トポロジ内のローカル ストアを持つコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-504">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

  - <span data-ttu-id="787a1-505">このツールは、ローカル ストアへのアクセス権のある管理者として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-505">The tool must be run as an administrator who has access to the local store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="787a1-506">例</span><span class="sxs-lookup"><span data-stu-id="787a1-506">Examples</span></span>

<span data-ttu-id="787a1-507">ツールの入力例は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="787a1-507">The following is an example of the tool input.</span></span>

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a><span data-ttu-id="787a1-508">概要</span><span class="sxs-lookup"><span data-stu-id="787a1-508">Summary</span></span>

<span data-ttu-id="787a1-509">このツールは、音声/ビデオおよび帯域幅ポリシーサービスを実行しているサーバーの状態を確認する、Lync Server 2013 管理者にとって有益なリソースになることがあります。</span><span class="sxs-lookup"><span data-stu-id="787a1-509">This tool can be a valuable resource to Lync Server 2013 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a><span data-ttu-id="787a1-510">Network Configuration Viewer</span><span class="sxs-lookup"><span data-stu-id="787a1-510">Network Configuration Viewer</span></span>

<span data-ttu-id="787a1-511">Microsoft Lync Server 2013 communication software 管理者は、ネットワーク構成ビューアーを使って、音声などのリアルタイム通信セッションを許可するようにプロビジョニングされている企業の通話受付制御 (CAC) ネットワークトポロジを表示できます。指定した帯域幅に基づいたビデオ通話。</span><span class="sxs-lookup"><span data-stu-id="787a1-511">Network Configuration Viewer can be used by Microsoft Lync Server 2013 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="787a1-512">Lync Server 2013 管理者は、Lync Server 2013 と共にインストールされている帯域幅ポリシーサービスによって適用される CAC ポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="787a1-512">Lync Server 2013 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Lync Server 2013.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-513">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-513">Description</span></span>

<span data-ttu-id="787a1-514">Network Configuration Viewer (NetworkConfigurationViewer.exe) を使用すると、管理者は次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-514">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

  - <span data-ttu-id="787a1-515">画像形式での Lync Server 2013 展開からの CAC ネットワークトポロジの読み込みと表示。</span><span class="sxs-lookup"><span data-stu-id="787a1-515">Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format.</span></span>

  - <span data-ttu-id="787a1-516">帯域幅ポリシー サーバー ログ ファイルの CAC ネットワーク トポロジを読み込み、図の形式で表示する。</span><span class="sxs-lookup"><span data-stu-id="787a1-516">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

  - <span data-ttu-id="787a1-517">CAC ネットワーク トポロジを XML 形式でディスクに保存、格納する。</span><span class="sxs-lookup"><span data-stu-id="787a1-517">Save and store CAC network topology in an XML format on the disk.</span></span>

  - <span data-ttu-id="787a1-518">CAC ネットワーク トポロジ図を JPG または BMP 形式で保存、格納する。</span><span class="sxs-lookup"><span data-stu-id="787a1-518">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

  - <span data-ttu-id="787a1-519">CAC ネットワーク トポロジ構成データを表示する。</span><span class="sxs-lookup"><span data-stu-id="787a1-519">View CAC network topology configuration data.</span></span>

  - <span data-ttu-id="787a1-520">CAC ネットワーク トポロジをツリー形式で表示する。</span><span class="sxs-lookup"><span data-stu-id="787a1-520">View CAC network topology in a tree-view style.</span></span>

  - <span data-ttu-id="787a1-521">CAC ネットワーク トポロジ リンク (サイトから地域、地域から地域、サイトからサイトの各リンクなど) のカスタム コネクタを定義する。</span><span class="sxs-lookup"><span data-stu-id="787a1-521">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

  - <span data-ttu-id="787a1-522">CAC ネットワーク トポロジのサイト情報、地域情報、プロビジョニングされた帯域幅ポリシーとネットワーク リンクを表示する。</span><span class="sxs-lookup"><span data-stu-id="787a1-522">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="787a1-523">用途</span><span class="sxs-lookup"><span data-stu-id="787a1-523">Purpose</span></span>

<span data-ttu-id="787a1-524">企業の CAC ネットワーク トポロジ リンクをグラフィカル インターフェイスで表示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-524">View enterprise CAC network topology links in a graphical interface.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="787a1-525">例</span><span class="sxs-lookup"><span data-stu-id="787a1-525">Examples</span></span>

<span data-ttu-id="787a1-526">**次のグラフィカルな形式の Lync Server 2013 展開からの CAC ネットワークトポロジの読み込みと表示を行います。** Lync Server 2013 管理者は、次の図に示すように、[**ネットワーク構成のダウンロード**] オプションを使用して、すべての lync server 2013 コンピューターで CAC ネットワークトポロジの構成を読み込んで表示することができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-526">**Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format:** Lync Server 2013 administrators can load and view CAC network topology configuration on any Lync Server 2013 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="787a1-527">このツールでは、Lync 構成ストアへの接続がないコンピューターに展開すると、このような構成がダウンロードまたは表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="787a1-527">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Lync configuration store.</span></span>

<span data-ttu-id="787a1-528">![ネットワーク構成のダウンロード](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "ネットワーク構成のダウンロード")</span><span class="sxs-lookup"><span data-stu-id="787a1-528">![Downloading the network configuration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Downloading the network configuration.")</span></span>

<span data-ttu-id="787a1-529">**帯域幅ポリシーサーバーログファイルからの CAC ネットワークトポロジを、グラフィカル形式で読み込み、表示します。** Lync Server 2013 帯域幅ポリシーサーバーは、CAC ネットワークトポロジを、Lync Server 2013 ファイル共有の場所にあるログメカニズムの一部として保存します。</span><span class="sxs-lookup"><span data-stu-id="787a1-529">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Lync Server 2013 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Lync Server 2013 file share location.</span></span> <span data-ttu-id="787a1-530">Lync Server の管理者は、次に示すように、 **[ネットワーク構成を開く**] オプションを使用して、このようなファイルをグラフィカルな形式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-530">Lync Server administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

<span data-ttu-id="787a1-531">![帯域幅ポリシー サーバーのログ ファイルを開く](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "帯域幅ポリシー サーバーのログ ファイルを開く")</span><span class="sxs-lookup"><span data-stu-id="787a1-531">![Opening a Bandwidth Policy Server log file.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Opening a Bandwidth Policy Server log file.")</span></span>

<span data-ttu-id="787a1-532">次に示すように、ディスク上の XML 形式で CAC ネットワークトポロジを保存して保存します。 Lync Server 2013 管理者は、次のように [**ネットワーク構成のコピーを保存**] オプションを使用して、cac ネットワークトポロジ構成ファイルを xml 形式で保存することができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-532">Save and store CAC network topology in an XML format on the disk: Lync Server 2013 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="787a1-533">保存した構成ファイルはオフラインでのグラフィカルな表示に使用できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-533">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

<span data-ttu-id="787a1-534">![ネットワーク構成の XML ファイルとしての保存](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "ネットワーク構成の XML ファイルとしての保存")</span><span class="sxs-lookup"><span data-stu-id="787a1-534">![Saving the network configuration as an XML file.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Saving the network configuration as an XML file.")</span></span>

<span data-ttu-id="787a1-535">CAC ネットワークトポロジ図を JPG または BMP 形式で保存して保存します。 Lync Server 2013 管理者は、次に示すように**ネットワーク構成ダイアグラムを [画像として保存**] オプションを使って、cac ネットワークトポロジ構成をグラフィカルな形式 (JPG と bmp ファイル形式) で保存できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-535">Save and Store CAC network topology diagram in JPG or BMP format: Lync Server 2013 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

<span data-ttu-id="787a1-536">![ネットワーク構成の画像としての保存](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "ネットワーク構成の画像としての保存")</span><span class="sxs-lookup"><span data-stu-id="787a1-536">![Saving the network configuration as a picture.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Saving the network configuration as a picture.")</span></span>

<span data-ttu-id="787a1-537">**CAC ネットワークトポロジ構成データを表示します。** Lync Server 2013 管理者は、以下に示すように [ネットワーク構成データの表示] オプションを使用して、ネットワーク領域、ネットワークサイト、帯域幅プロファイル、サイトサブネットの IP アドレスなどの関連ネットワーク構成データをテキスト形式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-537">**View CAC network topology configuration data:** Lync Server 2013 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

<span data-ttu-id="787a1-538">![ネットワーク構成データの表示](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "ネットワーク構成データの表示")</span><span class="sxs-lookup"><span data-stu-id="787a1-538">![Viewing network configuration data.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Viewing network configuration data.")</span></span>

<span data-ttu-id="787a1-539">**ツリービュー形式で CAC ネットワークトポロジを表示します。** Lync Server 2013 管理者は、次に示すように、ツールウィンドウの左側にあるコントロールパネルを使用して、関連するネットワーク構成データをグラフィカルなツリービュースタイルで表示できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-539">**View CAC network topology in a tree-view style:** Lync Server 2013 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

<span data-ttu-id="787a1-540">![ネットワーク構成データのツリー ビューでの表示](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "ネットワーク構成データのツリー ビューでの表示")</span><span class="sxs-lookup"><span data-stu-id="787a1-540">![Viewing network configuration data in a tree-view.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Viewing network configuration data in a tree-view.")</span></span>

<span data-ttu-id="787a1-541">**CAC ネットワークトポロジリンク (サイト間、地域間、サイト間リンクなど) 用のカスタムコネクタを定義します (例:** Lync Server 2013 管理者は、以下に示すように [設定] オプションを使用して、CAC ネットワーク構成の WAN リンク用のカスタムグラフィカルコネクタを定義できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-541">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Lync Server 2013 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="787a1-542">これは、ネットワーク構成にプロビジョニングされている各種ネットワーク リンクを区別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="787a1-542">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

<span data-ttu-id="787a1-543">![CAC ネットワークトポロジ用のカスタムコネクタを定義する](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "CAC ネットワークトポロジ用のカスタムコネクタを定義する")</span><span class="sxs-lookup"><span data-stu-id="787a1-543">![Define custom connectors for CAC network topology](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Define custom connectors for CAC network topology")</span></span>

<span data-ttu-id="787a1-544">**CAC ネットワークトポロジのサイト情報、地域情報、およびプロビジョニングされた帯域幅ポリシーを表示します。** Lync Server 2013 管理者は、以下に示すオプションを使用して、関連する CAC ネットワークの領域情報、サイト情報、および CAC 帯域幅プロビジョニングの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-544">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Lync Server 2013 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="787a1-545">(たとえば、ネットワーク領域またはネットワークサイトオブジェクトの [**情報**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="787a1-545">(For example, click **Info** in a network region or network site object.)</span></span>

<span data-ttu-id="787a1-546">![ネットワークのカスタム コネクタの定義](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "ネットワークのカスタム コネクタの定義")</span><span class="sxs-lookup"><span data-stu-id="787a1-546">![Defining custom connectors for your network.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Defining custom connectors for your network.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="787a1-547">概要</span><span class="sxs-lookup"><span data-stu-id="787a1-547">Summary</span></span>

<span data-ttu-id="787a1-548">このツールは、Lync Server 2013 管理者が、グラフィック形式で展開するための CAC ネットワークトポロジを表示したい場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="787a1-548">This tool can be a valuable resource to Lync Server 2013 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

</div>

</div>

<div>

## <a name="response-group-agent-live"></a><span data-ttu-id="787a1-549">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="787a1-549">Response Group Agent Live</span></span>

<span data-ttu-id="787a1-550">応答グループ アプリケーションによって、エージェントは組み込みの Web サービスを使用してリアルタイムの有効な情報にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="787a1-550">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="787a1-551">ただし、このデータのグラフィカル表示はアプリケーションの外部では使用できません。</span><span class="sxs-lookup"><span data-stu-id="787a1-551">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="787a1-552">応答グループエージェントのライブリソースキットツールでは、他のエージェントの存在など、リアルタイムの Microsoft Lync 2013 通信ソフトウェア情報を使用して、この情報に簡単かつグラフィカルな方法でアクセスできるため、この問題が解決されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-552">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Microsoft Lync 2013 communications software information such as the presence of other agents.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-553">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-553">Description</span></span>

<span data-ttu-id="787a1-554">Response Group Agent Live は、サインインやサインアウト機能、リアルタイム情報 (グループのメンバーシップや現在の通話数など) を応答グループ エージェントに提供する Windows アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="787a1-554">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="787a1-555">これは、[エージェントグループ] ページの拡張バージョン (Lync 2013 からアクセス可能) であることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="787a1-555">It is meant to be an enhanced version of the Agent Groups page (accessible from Lync 2013.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="787a1-556">用途</span><span class="sxs-lookup"><span data-stu-id="787a1-556">Purpose</span></span>

<span data-ttu-id="787a1-p165">着信通話は応答グループ アプリケーションによってキューに配置されてから、エージェント グループにルーティングされます。どの通話を処理するかについて十分な情報に基づいて判断するために、エージェントは他のエージェントの状態や各キューで待機中の通話数など、エージェント グループに関するリアルタイム情報にアクセスできます。このような情報は、当初は応答グループ サービスからのみアクセスが可能でしたが、Response Group Agent Live によって直感的な方法で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="787a1-p165">The Response Group application queues incoming calls, and then routes them to agent groups. To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue. This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

<div>

## <a name="features"></a><span data-ttu-id="787a1-560">機能</span><span class="sxs-lookup"><span data-stu-id="787a1-560">Features</span></span>

<span data-ttu-id="787a1-561">応答グループエージェント Live ツールは、応答グループサービスと Microsoft Lync 2013 SDK に基づいて構築されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-561">The Response Group Agent Live tool is built on the Response Group service and the Microsoft Lync 2013 SDK.</span></span> <span data-ttu-id="787a1-562">このツールは応答グループ サービスから利用できる情報や機能 (グループのメンバーシップ、他のエージェントのプレゼンス、待機中の通話数など) を応答グループ エージェントに提供します。</span><span class="sxs-lookup"><span data-stu-id="787a1-562">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="787a1-563">下の図は、Response Group Agent Live のメイン インターフェイスを示しています。</span><span class="sxs-lookup"><span data-stu-id="787a1-563">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

<span data-ttu-id="787a1-564">![Response Group Agent Live ツール](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "Response Group Agent Live ツール")</span><span class="sxs-lookup"><span data-stu-id="787a1-564">![The Response Group Agent Live tool.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "The Response Group Agent Live tool.")</span></span>

<span data-ttu-id="787a1-565">Response Group Agent Live では、エージェントは次の主な 3 つの機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-565">The following three main features are available for agents in Response Group Agent Live:</span></span>

  - <span data-ttu-id="787a1-566">**サインイン/チェックアウト:** Lync 2013 からアクセスできる [エージェントグループ] ページとは異なり、応答グループエージェントの Live では、エージェントのみが一度にサインインまたはサインアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-566">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Lync 2013), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="787a1-567">このアプリケーションでは、次の3つの簡単な方法でエージェントにサインインまたはサインアウトできます。</span><span class="sxs-lookup"><span data-stu-id="787a1-567">This application provides three quick ways for agents to sign in or out:</span></span>
    
      - <span data-ttu-id="787a1-568">アプリケーション内でサインイン/サインアウト (緑色と赤色) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="787a1-568">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
      - <span data-ttu-id="787a1-569">システム トレイ アイコンを右クリックし、サインインまたはサインアウトを選択します。</span><span class="sxs-lookup"><span data-stu-id="787a1-569">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
      - <span data-ttu-id="787a1-570">構成可能なキーボード ショートカットを使用します。</span><span class="sxs-lookup"><span data-stu-id="787a1-570">Using configurable keyboard shortcuts.</span></span>

  - <span data-ttu-id="787a1-571">**グループメンバーシップ:**[エージェント] グループが選択されている場合、[応答グループエージェント Live] は、右側のウィンドウにこのグループのエージェントの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-571">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="787a1-572">Lync 2013 がこのアプリケーションと同じコンピューターで実行されている場合、プレゼンス情報と連絡先カードが応答グループエージェントの Live に表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-572">If Lync 2013 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="787a1-573">担当者は、そこから直接 IM を送信したり、他のエージェントに直接通話を発信したりできます。</span><span class="sxs-lookup"><span data-stu-id="787a1-573">Agents can send an IM or call other agents directly from there.</span></span>

  - <span data-ttu-id="787a1-p169">**リアルタイム統計情報:** Response Group Agent Live ではすべてのエージェント グループのリアルタイム統計情報を使用できます。更新間隔は 1 分です。応答グループが通話に応答すると、グループ名の横に視覚的なインジケーターが追加され、キュー内の現在の通話数が表示されます。グループにマウスを合わせると、最長の待機時間も表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p169">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups. The update frequency is one minute. When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls. Pausing the pointer over a group also displays the longest waiting time.</span></span>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="787a1-578">要件</span><span class="sxs-lookup"><span data-stu-id="787a1-578">Requirements</span></span>

<span data-ttu-id="787a1-579">Response Group Agent Live には .NET Framework 4.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="787a1-579">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="787a1-580">さらに、プレゼンスと連絡先カードの機能を活用するには、Lync 2013 をローカルでインストールし (実行中) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-580">In addition, to take advantage of the presence and contact card features, Lync 2013 must be installed locally (and be running).</span></span>

<div>

## <a name="configuration"></a><span data-ttu-id="787a1-581">構成</span><span class="sxs-lookup"><span data-stu-id="787a1-581">Configuration</span></span>

<span data-ttu-id="787a1-p171">アプリケーションの [Options] ダイアログ ボックスを使用すると、Response Group Agent Live を個人の好みに合わせてカスタマイズできます。また、管理者は RGAgentLive.exe.config ファイルの defaultHostAddress プロパティを直接編集して既定のホスト アドレスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p171">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application. In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="787a1-p172">下の図は、エージェントがホスト アドレスやショートカット キーを構成できる [Options] ダイアログ ボックスを示しています。このダイアログを表示するには、メイン インターフェイスの右上にある [Options] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="787a1-p172">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys. This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

<span data-ttu-id="787a1-586">![[Response Group Agent Live Options] ダイアログ ボックス](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "[Response Group Agent Live Options] ダイアログ ボックス")</span><span class="sxs-lookup"><span data-stu-id="787a1-586">![The Response Group Agent Live Options dialog box.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "The Response Group Agent Live Options dialog box.")</span></span>

<span data-ttu-id="787a1-587">Response Group Agent Live の構成では次の 3 つの設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="787a1-587">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

  - <span data-ttu-id="787a1-p173">[Host address]: これは通常、エージェントのホーム プールに属する Web プール FQDN です。この情報から、正確な応答グループ サービス アドレスがバックグラウンドで自動的に取得されます (ホストの後に適切なパスが付加されます)。</span><span class="sxs-lookup"><span data-stu-id="787a1-p173">Host address: This is typically the web pool FQDN belonging to the agent’s home pool. The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

  - <span data-ttu-id="787a1-p174">[Shortcuts]: サインイン/サインアウト用の厳密なショートカットをカスタマイズできます。唯一の制約として、ショートカットでは 1 つ以上のキーのほかに "Windows ロゴ" キーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-p174">Shortcuts: The exact shortcuts to sign-in/out can be customized. The only limitation is that both shortcuts must contain the “Windows Logo” key (in addition to at least another key).</span></span>

  - <span data-ttu-id="787a1-592">[Start with Windows]: Windows と共に自動的に起動するようにアプリケーションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-592">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="787a1-593">例</span><span class="sxs-lookup"><span data-stu-id="787a1-593">Examples</span></span>

<span data-ttu-id="787a1-594">下の図は、右側のウィンドウで連絡先を右クリックして、他のエージェントに電話をかけたり IM を送信したりする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="787a1-594">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

<span data-ttu-id="787a1-595">![通話の発信または IM の送信](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "通話の発信または IM の送信")</span><span class="sxs-lookup"><span data-stu-id="787a1-595">![Making a call or sending an IM.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Making a call or sending an IM.")</span></span>

<span data-ttu-id="787a1-596">下の図は、Response Group Agent Live に表示されるキュー内の現在の通話数と全着信通話内での最長待機時間を示しています。</span><span class="sxs-lookup"><span data-stu-id="787a1-596">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

<span data-ttu-id="787a1-597">![キュー情報の表示](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "キュー情報の表示")</span><span class="sxs-lookup"><span data-stu-id="787a1-597">![Viewing queue information.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Viewing queue information.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="787a1-598">概要</span><span class="sxs-lookup"><span data-stu-id="787a1-598">Summary</span></span>

<span data-ttu-id="787a1-599">迅速なサインインとサインアウト、グループのメンバーシップ、基本的なリアルタイム統計情報は、アプリケーション外部でのみ利用できる、応答グループ サービスに基づいた便利な応答グループ エージェント機能です。</span><span class="sxs-lookup"><span data-stu-id="787a1-599">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="787a1-600">応答グループエージェントのライブリソースキットツールを使用すると、Lync 管理者は、迅速かつグラフィカルな方法でタスクを実行できる Windows アプリケーションでエージェントを提供できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-600">With the Response Group Agent Live Resource Kit tool, Lync administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

</div>

</div>

<div>

## <a name="sefautil"></a><span data-ttu-id="787a1-601">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="787a1-601">SEFAUtil</span></span>

<span data-ttu-id="787a1-602">SEFAUtil (セカンダリ拡張機能のアクティブ化) は、Microsoft Lync Server 2013 通信ソフトウェア管理者およびヘルプデスクエージェントが代理人の呼び出し、着信の転送、同時呼び出し、チーム呼び出しを構成できるようにするコマンドラインツールです。Lync Server 2013 ユーザーの代わりに、設定とグループの通話が集配されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-602">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Microsoft Lync Server 2013 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="787a1-603">このツールを使用すると、管理者は、特定のユーザーに対して公開されている通話ルーティング設定を照会することもできます。SEFAUtil ツールを使用すると、管理者は、ユーザーの代わりに着信の転送を有効または無効にしたり、変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-603">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="787a1-604">管理者は、(SIP URI の形式で) ターゲットを指定するか、またはユーザーによって既に公開されているターゲットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-604">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="787a1-605">このツールでは、管理者がユーザーに代わって代理人またはチーム呼び出しグループのメンバーを追加または削除することもできます。このツールは、Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 3.0 に基づいて構築されており、管理者が SEFAUtil の中央管理ストアで信頼済みアプリケーションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-605">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil</span></span>

<span data-ttu-id="787a1-606">SEFAUtil (セカンダリ拡張機能のアクティブ化) lync Server 2013 管理者およびヘルプデスクエージェントは、Lync Server 2013 ユーザーの代わりに、代理人、着信の転送、同時呼び出し、チーム呼び出しの設定、グループの通話ピックアップを構成することができます。.</span><span class="sxs-lookup"><span data-stu-id="787a1-606">SEFAUtil (secondary extension feature activation) enables Lync Server 2013 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="787a1-607">また、管理者は特定のユーザー向けに公開されているコール ルーティング設定のクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-607">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-608">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-608">Description</span></span>

<span data-ttu-id="787a1-609">SEFAUtil の現在のバージョンは、コマンドラインツールにすぎません。グラフィカルユーザーインターフェイスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="787a1-609">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="787a1-610">このツールは、Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 3.0 に基づいています。</span><span class="sxs-lookup"><span data-stu-id="787a1-610">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="787a1-611">このツールの機能により、管理者やヘルプデスクの担当者は次の作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-611">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

  - <span data-ttu-id="787a1-612">ユーザーのすべてのコール ルーティング設定を表示する (着信転送、代理人、同時呼び出し、チーム呼び出し、グループ通話ピックアップなど)</span><span class="sxs-lookup"><span data-stu-id="787a1-612">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

  - <span data-ttu-id="787a1-613">着信転送設定を有効化、無効化、変更する (宛先や無応答タイマーなど)</span><span class="sxs-lookup"><span data-stu-id="787a1-613">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

  - <span data-ttu-id="787a1-614">着信転送の即時構成を有効化、無効化、変更する</span><span class="sxs-lookup"><span data-stu-id="787a1-614">Enable/disable/modify call-forwarding immediate configurations</span></span>

  - <span data-ttu-id="787a1-615">代理人設定を有効化、無効化、変更する</span><span class="sxs-lookup"><span data-stu-id="787a1-615">Enable/disable/modify delegation settings</span></span>

  - <span data-ttu-id="787a1-616">チーム呼び出しグループ設定を有効化、無効化、変更する</span><span class="sxs-lookup"><span data-stu-id="787a1-616">Enable/disable/modify team-call group settings</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="787a1-617">Lync Server 2013 SEFAUtil の新ツール</span><span class="sxs-lookup"><span data-stu-id="787a1-617">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="787a1-618">同時呼び出し設定を有効化、無効化、変更する (宛先など)</span><span class="sxs-lookup"><span data-stu-id="787a1-618">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="787a1-619">Lync Server 2013 SEFAUtil の新ツール</span><span class="sxs-lookup"><span data-stu-id="787a1-619">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="787a1-620">グループ通話ピックアップ設定を有効化、無効化、変更する</span><span class="sxs-lookup"><span data-stu-id="787a1-620">Enable/disable/modify group call pickup settings</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="787a1-621">Lync Server 2013 SEFAUtil の新ツール</span><span class="sxs-lookup"><span data-stu-id="787a1-621">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

<span data-ttu-id="787a1-622">このツールの制約は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="787a1-622">This tool has the following limitations:</span></span>

  - <span data-ttu-id="787a1-623">Lync Server プールに所属しているユーザーのみがサポートされます</span><span class="sxs-lookup"><span data-stu-id="787a1-623">Supported only for users homed in a Lync Server pool</span></span>

  - <span data-ttu-id="787a1-624">複数ユーザーのコール ルーティング設定の一括編集はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="787a1-624">Bulk-edit of call routing settings for several users is not supported</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="787a1-625">出力</span><span class="sxs-lookup"><span data-stu-id="787a1-625">Output</span></span>

<span data-ttu-id="787a1-p179">ツールの現在のバージョンでは、[コマンド プロンプト] ウィンドウでのみ結果が表示されます。詳しくは、このドキュメント後半の「例」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="787a1-p179">The current version of this tool provides output only in the Command Prompt window. For details, see the Examples section later in this document.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="787a1-628">用途</span><span class="sxs-lookup"><span data-stu-id="787a1-628">Purpose</span></span>

<span data-ttu-id="787a1-629">このツールを使用するいくつかの主なシナリオを次に示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-629">Following are some of the key scenarios where this tool may be used:</span></span>

  - <span data-ttu-id="787a1-630">Bob は役員で、Lync Server テレフォニーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="787a1-630">Bob is an executive and has been moved to Lync Server telephony.</span></span> <span data-ttu-id="787a1-631">彼の既存の PBX システムには代理人が設定されています。</span><span class="sxs-lookup"><span data-stu-id="787a1-631">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="787a1-632">Lync への移行の一環として、管理者は、Bob のルーティングを構成して、既存の委任構成を反映させることができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-632">As part of the move to Lync, the administrator is able to configure Bob’s routing to reflect his pre-existing delegation configuration.</span></span>

  - <span data-ttu-id="787a1-p181">西村さんは旅行中で、顧客からの重要な連絡を待っています。しかし、ホテル滞在中はコンピューターを使うことができません。彼女はヘルプデスクに電話して、勤務先電話番号にかかってきたすべての電話を携帯電話の番号に転送してもらうよう頼みました。ヘルプデスク担当者は、彼女のためにこのような構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p181">Alice is travelling and realizes that she is expecting an important call from one of her customers. However, she is in a hotel and has no access to a computer. She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number. The helpdesk personnel are able to do the configuration on her behalf.</span></span>

  - <span data-ttu-id="787a1-p182">松本さんの勤務先電話番号にかかってくる電話は、勤務中は常に彼の携帯電話のボイスメールに送信されています。しかし、他の多くの場所では通話は問題なく機能しているようです。ヘルプデスクの技術者は松本さんのルーティング構成を確認できるので、彼の携帯電話に同時呼び出しが構成されていることを見つけます。技術者は松本さんにオフィスでの通信状態についてたずね、通信状態が良くない場合に着信通話を携帯電話のボイスメールへ送信しているのは同時呼び出しルールであることを特定できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p182">Joe’s calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations. The helpdesk technician is able to view Joe’s routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone. The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe’s mobile voicemail when his network coverage is poor.</span></span>

  - <span data-ttu-id="787a1-640">Mike は Contoso の新入社員で、新しいチームに参加して、すべてのメンバーがチーム呼び出し用に構成されています。 Microsoft Lync が有効になっている場合、管理者はチーム呼び出しグループ設定を設定して、すべての新しいチームメンバーを含めることができます。さらに、管理者は、チームのメンバー全員のチーム呼び出しグループメンバーとして Mike を追加します。</span><span class="sxs-lookup"><span data-stu-id="787a1-640">Mike is a new employee at Contoso and he’s joining a new team on which all members are configured for team-call, when being enabled for Microsoft Lync, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

  - <span data-ttu-id="787a1-641">Contoso の人事部門のカスタマー サービス プラクティスとは、すべての発信者に対して最初の電話から個人サービスを提供することです。</span><span class="sxs-lookup"><span data-stu-id="787a1-641">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="787a1-642">部門のメンバー全員がお互いのすぐそばに座っているとすれば、チーム呼び出しで全員の電話が一斉に鳴るのはチームにとって非常に混乱のもとになります。</span><span class="sxs-lookup"><span data-stu-id="787a1-642">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="787a1-643">チームメンバーを邪魔することなく最良のサービスを提供するために、Lync 管理者はグループ通話のピックアップ機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="787a1-643">To provide the best service without disrupting the team members, the Lync administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="787a1-644">管理者は部門の全員をピックアップ グループに追加して、ピックアップ グループ番号を伝えます。</span><span class="sxs-lookup"><span data-stu-id="787a1-644">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="787a1-645">原田さんが席を外している場合は、彼女の電話が鳴っていることに気付いた松本さんが自分の席から電話に応答します。</span><span class="sxs-lookup"><span data-stu-id="787a1-645">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="787a1-646">要件</span><span class="sxs-lookup"><span data-stu-id="787a1-646">Requirements</span></span>

<span data-ttu-id="787a1-p184">SEFAUtil ツールは信頼されたアプリケーション プールに属しているコンピューターでのみ実行できます。このコンピューターには UCMA 3.0 がインストールされている必要があります。ツールを実行するには、SEFAUtil アプリケーション ID を持つ新しい信頼されたアプリケーションをプール内に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-p184">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool. UCMA 3.0 must be installed on that computer. To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

<span data-ttu-id="787a1-650">**SEFAUtil ツール用の新しい信頼されたアプリケーションの作成**</span><span class="sxs-lookup"><span data-stu-id="787a1-650">**Creating a new Trusted Application for the SEFAUtil tool**</span></span>

1.  <span data-ttu-id="787a1-651">SEFAUTil ツールは信頼されたアプリケーション プールに属しているコンピューターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-651">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="787a1-652">必要に応じて、新しい信頼できるアプリケーションプールとしてプールを追加するには、次のコマンドレットを実行して、Lync Server 管理シェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="787a1-652">If needed, adding a pool as a new trusted application pool can be done via the Lync Server Management Shell with the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="787a1-653">SEFAUtil ツールを実行するコンピューターには UCMA 3.0 をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-653">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

    
    </div>

2.  <span data-ttu-id="787a1-654">信頼されたアプリケーションを SEFAUtil ツールのトポロジ内に定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-654">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="787a1-655">SEFAUtil を新しい信頼されたアプリケーションとして定義するには、Lync Server 管理シェルを使用して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="787a1-655">To define SEFAUtil as a new trusted application, use the Lync Server Management Shell and execute the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="787a1-656">必要に応じて、別のポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-656">A different port can be used if needed.</span></span>

    
    </div>

3.  <span data-ttu-id="787a1-657">トポロジの変更を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="787a1-658">トポロジの変更を有効にするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="787a1-658">Enabling the topology changes can be done via the Lync Server Management Shell by executing the following cmdlet:</span></span>
    
        Enable-CsToplogy

4.  <span data-ttu-id="787a1-659">必要に応じて、SEFAUtil ツールの実行に使用するサーバーに Lync Server 2013 リソースキットツールをインストールします (サーバーは、信頼されたアプリケーションプールの一部である必要があります)。</span><span class="sxs-lookup"><span data-stu-id="787a1-659">If needed, install the Lync Server 2013 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5.  <span data-ttu-id="787a1-660">SEFAUtil が正しく実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="787a1-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="787a1-661">そのためには、Windows コマンド プロンプトから管理者権限でツールを実行し、展開内のユーザーの着信転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="787a1-662">既定では、ツールは次の場所に配置されます: "...\\Program Files\\Microsoft Lync Server 2013\\Reskit "。</span><span class="sxs-lookup"><span data-stu-id="787a1-662">By default the tool will be located in: “…\\Program Files\\Microsoft Lync Server 2013\\Reskit”.</span></span> <span data-ttu-id="787a1-663">ユーザーの着信転送設定を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="787a1-663">To display the call forwarding settings of a user, use the following command:</span></span>
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    <span data-ttu-id="787a1-664">ユーザーの着信転送設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-664">The call forwarding settings of the user should be displayed.</span></span>

<div>

## <a name="group-call-pickup"></a><span data-ttu-id="787a1-665">グループ通話ピックアップ</span><span class="sxs-lookup"><span data-stu-id="787a1-665">Group Call Pickup</span></span>

<span data-ttu-id="787a1-666">グループ通話のピックアップ機能を完全に有効にするには、Lync Server で追加の構成を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-666">Group Call Pickup requires additional configuration in Lync Server for the capability to be fully enabled.</span></span> <span data-ttu-id="787a1-667">ユーザーにピックアップ グループを割り当てる前に、この機能の計画と展開の手順について、グループ通話ピックアップの製品ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="787a1-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="787a1-668">例</span><span class="sxs-lookup"><span data-stu-id="787a1-668">Examples</span></span>

<div>

## <a name="display-current-call-handling-settings"></a><span data-ttu-id="787a1-669">現在の通話処理設定の表示</span><span class="sxs-lookup"><span data-stu-id="787a1-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="787a1-670">次のコマンドでは、ユーザーの通話処理が表示されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-670">The following command displays the call handling for the user.</span></span> `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> <span data-ttu-id="787a1-671">この例では、 <STRONG>/server</STRONG>スイッチを使用して、接続先の Lync server を指定します。</span><span class="sxs-lookup"><span data-stu-id="787a1-671">This example uses the <STRONG>/server</STRONG> switch to specify the Lync Server to connect to.</span></span>



</div>

<span data-ttu-id="787a1-672">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-672">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="787a1-673">着信転送/応答なしの宛先の設定</span><span class="sxs-lookup"><span data-stu-id="787a1-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="787a1-674">この例では、着信転送/応答なしの宛先と呼び出しの遅延を設定します。</span><span class="sxs-lookup"><span data-stu-id="787a1-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="787a1-675">ここでは、/server スイッチは提供されません。SEFAUtil が Lync サーバーの自動検出を試みます。</span><span class="sxs-lookup"><span data-stu-id="787a1-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Lync Server.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

<span data-ttu-id="787a1-676">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-676">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="787a1-677">着信転送の即時有効化</span><span class="sxs-lookup"><span data-stu-id="787a1-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="787a1-678">この例では、別のユーザーへの着信転送をすぐに有効にします。</span><span class="sxs-lookup"><span data-stu-id="787a1-678">This example immediately enables call-forwarding to another user.</span></span>

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

<span data-ttu-id="787a1-679">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-679">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="787a1-680">着信転送の即時無効化</span><span class="sxs-lookup"><span data-stu-id="787a1-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="787a1-681">この例では、別のユーザーへの着信転送をすぐに無効にします。</span><span class="sxs-lookup"><span data-stu-id="787a1-681">This example immediately disables call forwarding.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

<span data-ttu-id="787a1-682">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-682">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="787a1-683">代理人としてのユーザーの追加と代理人の同時呼び出しの設定</span><span class="sxs-lookup"><span data-stu-id="787a1-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="787a1-684">この例では、ユーザーを代理人として追加し、代理人の同時呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="787a1-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

<span data-ttu-id="787a1-685">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-685">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="787a1-686">代理人の同時呼び出しルールの変更</span><span class="sxs-lookup"><span data-stu-id="787a1-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="787a1-687">この例では、前の例で設定した代理人の同時呼び出しルールを遅延呼び出しルールに変更します。</span><span class="sxs-lookup"><span data-stu-id="787a1-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

<span data-ttu-id="787a1-688">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-688">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a><span data-ttu-id="787a1-689">代理人の削除</span><span class="sxs-lookup"><span data-stu-id="787a1-689">Remove the Delegate</span></span>

<span data-ttu-id="787a1-690">この例では代理人を削除します。</span><span class="sxs-lookup"><span data-stu-id="787a1-690">This example removes the delegate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="787a1-691">最後の代理人が削除されると、代理人着信は自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="787a1-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

<span data-ttu-id="787a1-692">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-692">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="787a1-693">代理人の追加と代理人への着信転送ルールの設定</span><span class="sxs-lookup"><span data-stu-id="787a1-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="787a1-694">この例では、代理人を追加し、代理人への着信転送ルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="787a1-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

<span data-ttu-id="787a1-695">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-695">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="787a1-696">同時呼び出しの有効化と宛先番号の設定</span><span class="sxs-lookup"><span data-stu-id="787a1-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="787a1-697">この例では、同時呼び出しを有効にして、同時呼び出しの宛先番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="787a1-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> <span data-ttu-id="787a1-698">既に同時呼び出しを有効にしているユーザーの同時呼び出しの宛先番号を変更するには、コマンドに /enablesimulring スイッチを追加します。追加しない場合、宛先番号は変更されません。</span><span class="sxs-lookup"><span data-stu-id="787a1-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>



</div>

<span data-ttu-id="787a1-699">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-699">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a><span data-ttu-id="787a1-700">同時呼び出しの無効化</span><span class="sxs-lookup"><span data-stu-id="787a1-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="787a1-701">この例では、同時呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="787a1-701">This example disables simultaneous ringing.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

<span data-ttu-id="787a1-702">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-702">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="787a1-703">チーム呼び出しのチーム メンバーの追加とチーム呼び出しメンバー グループへの同時呼び出しの設定</span><span class="sxs-lookup"><span data-stu-id="787a1-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="787a1-704">この例では、ユーザーのチーム呼び出しグループにチーム メンバーを追加し、チーム呼び出しグループへの同時呼び出しを有効にします。</span><span class="sxs-lookup"><span data-stu-id="787a1-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="787a1-705">ユーザーのチーム呼び出しグループにチーム メンバーを追加すると、ユーザーの同時呼び出しの設定がチーム呼び出しグループを同時に呼び出すように自動的に切り替わります。</span><span class="sxs-lookup"><span data-stu-id="787a1-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>



</div>

<span data-ttu-id="787a1-706">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-706">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="787a1-707">チーム呼び出しグループからのメンバーの削除</span><span class="sxs-lookup"><span data-stu-id="787a1-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="787a1-708">この例では、ユーザーのチーム呼び出しグループからチーム メンバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="787a1-708">This example removes a team member of the team-call group of a user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> <span data-ttu-id="787a1-709">削除対象のメンバーがチーム呼び出しグループで唯一のメンバーである場合、チーム呼び出しグループの同時呼び出しは自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="787a1-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>



</div>

<span data-ttu-id="787a1-710">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-710">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="787a1-711">チーム呼び出しグループの遅延呼び出しの設定</span><span class="sxs-lookup"><span data-stu-id="787a1-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="787a1-712">この例では、チーム呼び出しグループの時間設定の遅延呼び出しを変更します。</span><span class="sxs-lookup"><span data-stu-id="787a1-712">This example changes the delayed ring to the team-call group time setting.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

<span data-ttu-id="787a1-713">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-713">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a><span data-ttu-id="787a1-714">チーム呼び出しの有効化</span><span class="sxs-lookup"><span data-stu-id="787a1-714">Enable Team-Call</span></span>

<span data-ttu-id="787a1-715">この例では、ユーザーのチーム呼び出しを有効にします。</span><span class="sxs-lookup"><span data-stu-id="787a1-715">This example enables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="787a1-716">ユーザーのチーム呼び出しグループにメンバーがいない場合、チーム呼び出しは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="787a1-716">If the team-call group of the user has no members, team-call won’t be enabled.</span></span>



</div>

<span data-ttu-id="787a1-717">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-717">**Output**</span></span>

</div>

<div>

## <a name="disable-team-call"></a><span data-ttu-id="787a1-718">チーム呼び出しの無効化</span><span class="sxs-lookup"><span data-stu-id="787a1-718">Disable Team-Call</span></span>

<span data-ttu-id="787a1-719">この例では、ユーザーのチーム呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="787a1-719">This example disables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

<span data-ttu-id="787a1-720">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-720">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="787a1-721">グループ通話ピックアップの有効化とユーザーへのピックアップ グループの割り当て</span><span class="sxs-lookup"><span data-stu-id="787a1-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="787a1-722">この例では、ユーザーにピックアップ グループを割り当て、グループ通話ピックアップを有効にします。</span><span class="sxs-lookup"><span data-stu-id="787a1-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

<span data-ttu-id="787a1-723">**出力**</span><span class="sxs-lookup"><span data-stu-id="787a1-723">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a><span data-ttu-id="787a1-724">グループ通話ピックアップの無効化</span><span class="sxs-lookup"><span data-stu-id="787a1-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="787a1-725">この例では、特定のユーザーのグループ通話ピックアップを無効にします。</span><span class="sxs-lookup"><span data-stu-id="787a1-725">This example disables Group Call Pickup for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> <span data-ttu-id="787a1-p191">ユーザーのグループ通話ピックアップを無効にした場合、ユーザーに割り当てられたグループ番号は保持されません。そのユーザーのグループ通話ピックアップを後からもう一度有効にする場合は、/enablegrouppickup スイッチでグループ番号をもう一度割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-p191">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained. If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a><span data-ttu-id="787a1-728">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="787a1-728">SYSPrep.ps1</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-729">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-729">Description</span></span>

<span data-ttu-id="787a1-730">Sysprep.inf は、Windows Server 2008 オペレーティングシステムコンピューターに次の Lync Server 2013 の前提条件をインストールする Windows PowerShell スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="787a1-730">SYSPrep.ps1 is a Windows PowerShell script that will install the following Lync Server 2013 prerequisites on your Windows Server 2008 operating system machine.</span></span>

  - <span data-ttu-id="787a1-731">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="787a1-731">Microsoft .Net Framework 4.5</span></span>

  - <span data-ttu-id="787a1-732">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="787a1-732">Microsoft SQL Server Express</span></span>

  - <span data-ttu-id="787a1-733">Windows Powershell バージョン 3.0</span><span class="sxs-lookup"><span data-stu-id="787a1-733">Windows Powershell version 3.0</span></span>

  - <span data-ttu-id="787a1-734">Visual C++ 2010 再頒布可能パッケージ</span><span class="sxs-lookup"><span data-stu-id="787a1-734">Visual C++ 2010 Redistributable</span></span>

  - <span data-ttu-id="787a1-735">Internet Information Server の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="787a1-735">Internet Information Server Updates</span></span>

  - <span data-ttu-id="787a1-736">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="787a1-736">Windows Identity Foundation</span></span>

  - <span data-ttu-id="787a1-737">Lync Server 2013 コアファイル</span><span class="sxs-lookup"><span data-stu-id="787a1-737">Lync Server 2013 Core files</span></span>

<span data-ttu-id="787a1-738">このスクリプトは Microsoft Windows オペレーティング システム用のシステム準備ツールと名前は似ていますが、別のツールです。</span><span class="sxs-lookup"><span data-stu-id="787a1-738">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="787a1-739">このスクリプトでは、Lync Server 2013 に必要な前提条件のみをインストールします。</span><span class="sxs-lookup"><span data-stu-id="787a1-739">This script will only install the required prerequisites for Lync Server 2013.</span></span> <span data-ttu-id="787a1-740">これらの必須コンポーネントをインストールしたら、Windows SYSPrep ツールを使用して、サーバーのイメージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-740">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="787a1-741">要件</span><span class="sxs-lookup"><span data-stu-id="787a1-741">Requirements</span></span>

<span data-ttu-id="787a1-742">Sysprep.inf スクリプトを実行する前に、必須ファイルを Windows Server 2008 オペレーティングシステムコンピューター上のローカルフォルダー (例 **: D:\\Setup)** にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-742">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\\Setup)**.</span></span> <span data-ttu-id="787a1-743">このフォルダーには、Lync Server 2013 ファイルのコピー **(具体的に**は setup.exe) も含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-743">This folder must also include a copy of the Lync Server 2013 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="787a1-744">必須ファイルは、次の場所からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="787a1-744">The prerequisite files can be downloaded from the following locations:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="787a1-745">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="787a1-745">Prerequisite</span></span></th>
<th><span data-ttu-id="787a1-746">場所</span><span class="sxs-lookup"><span data-stu-id="787a1-746">Location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="787a1-747">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="787a1-747">Microsoft .Net Framework 4.5</span></span></p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="787a1-748">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="787a1-748">Microsoft SQL Server Express 2008 R2</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="787a1-749">Windows Powershell バージョン 3.0</span><span class="sxs-lookup"><span data-stu-id="787a1-749">Windows Powershell version 3.0</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="787a1-750">Visual C++ 2010 再頒布可能パッケージ</span><span class="sxs-lookup"><span data-stu-id="787a1-750">Visual C++ 2010 Redistributable</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="787a1-751">Internet Information Server の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="787a1-751">Internet Information Server Updates</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="787a1-752">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="787a1-752">Windows Identity Foundation</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="787a1-753">Lync Server 2013 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="787a1-753">Lync Server 2013 Setup.exe</span></span></p></td>
<td><p><span data-ttu-id="787a1-754">Lync Server 2013 メディアからのコピー</span><span class="sxs-lookup"><span data-stu-id="787a1-754">Copy from Lync Server 2013 media</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a><span data-ttu-id="787a1-755">パラメーター</span><span class="sxs-lookup"><span data-stu-id="787a1-755">Parameter</span></span>

<span data-ttu-id="787a1-756">**–SetupFolder** パラメーターは必須コンポーネント ファイルのディレクトリの場所を引数として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="787a1-756">The **–SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="787a1-757">例</span><span class="sxs-lookup"><span data-stu-id="787a1-757">Examples</span></span>

<span data-ttu-id="787a1-758">Sysprep.inf スクリプトを実行して Lync Server 2013 の前提条件をインストールするには、管理者特権のコマンドプロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="787a1-758">To run the SYSPrep.ps1 script and install the Lync Server 2013 prerequisites, run the following command from an elevated command prompt:</span></span>

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="787a1-759">Unassigned Number Announcements Migration</span><span class="sxs-lookup"><span data-stu-id="787a1-759">Unassigned Number Announcements Migration</span></span>

<span data-ttu-id="787a1-760">未割り当ての番号のお知らせ移行ツールを使用すると、Lync 管理者は、アナウンスメントアプリケーションによって提供されている、割り当てられていない番号の構成を、ソースの Lync サーバーまたはプールから送信先の Lync サーバーまたはプールに移動できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-760">The Unassigned Number Announcements Migration tool enables a Lync administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Lync Server or Pool to a destination Lync Server or Pool.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-761">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-761">Description</span></span>

<span data-ttu-id="787a1-762">Unassigned Number Announcements Migration ツールは Windows PowerShell スクリプトであり、アナウンス アプリケーションによるサービスを受けている未使用の番号の構成を移行元のサーバーまたはプールから別のサーバーまたはプールに移行します。</span><span class="sxs-lookup"><span data-stu-id="787a1-762">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="787a1-763">Unassigned Number Announcements Migration スクリプトを実行すると、次の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="787a1-763">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1.  <span data-ttu-id="787a1-764">移行元のサーバーまたはプールでホストされているアナウンス アプリケーションの未使用の番号のアナウンスが使用しているすべての音声ファイルを、移行先のサーバーまたはプールのファイル ストアに移行します。</span><span class="sxs-lookup"><span data-stu-id="787a1-764">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="787a1-765">オーディオファイルは、移行先のプールにコピーされると、ソースプールから削除されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-765">the audio files are removed from the source pool once they’re copied to the destination pool.</span></span>

    
    </div>

2.  <span data-ttu-id="787a1-766">移行元のサーバーまたはプールでホストされているアナウンス アプリケーションに構成されているすべての未使用の番号のアナウンスを、移行先のサーバーまたはプールに移行します。</span><span class="sxs-lookup"><span data-stu-id="787a1-766">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3.  <span data-ttu-id="787a1-767">移行元のサーバーまたはプールでホストされているアナウンス アプリケーションによるサービスを受けているすべての未使用の番号の範囲を、移行先のサーバーまたはプールにもう一度割り当てます。</span><span class="sxs-lookup"><span data-stu-id="787a1-767">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="787a1-768">スクリプトの実行が成功すると、移行元のサーバーまたはプールでホストされているアナウンス アプリケーションによるサービスを受けていたすべての未使用の番号の範囲が、同じ構成を使用して移行先のサーバーまたはプールによるサービスを受けるようになります。</span><span class="sxs-lookup"><span data-stu-id="787a1-768">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="787a1-769">出力</span><span class="sxs-lookup"><span data-stu-id="787a1-769">Output</span></span>

<span data-ttu-id="787a1-770">**ムーブグループの移動 Ementconfiguration**スクリプトは、Lync 管理シェルウィンドウで、移行操作の成功または失敗を実行した場所を示します。</span><span class="sxs-lookup"><span data-stu-id="787a1-770">The **Move-CsAnnouncementConfiguration** script indicates in the Lync Management Shell window from where it’s executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="787a1-p194">エラーによって操作の実行が中断した場合、移行に成功した未使用の番号の範囲は稼動状態で移行先に残り、移行する予定の残りの未使用の番号の範囲も稼動状態で移行元に残ります。残りの構成を完全に移行するには、エラーを修正してからもう一度スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="787a1-p194">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form. To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="787a1-773">用途</span><span class="sxs-lookup"><span data-stu-id="787a1-773">Purpose</span></span>

<span data-ttu-id="787a1-774">Unassigned Number Announcements Migration スクリプトは、次の 3 つのシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-774">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

  - <span data-ttu-id="787a1-775">**構成設定を新しいバージョンの Lync Server に移行する:** Contoso は Lync Server 2013 への移行プロセス中であり、移行プロセスの一環として、lync server の管理者は、アナウンスメントアプリケーションによってサービスされている、割り当てられていない番号の構成を Lync Server 2010 の展開から新しい Lync Server 2013 の展開に移動することを希望しています。</span><span class="sxs-lookup"><span data-stu-id="787a1-775">**Migrating configuration settings to a new version of Lync Server:** Contoso is in the process of migrating to Lync Server 2013 and as part of the migration process the Lync Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2010 deployment to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="787a1-776">設定を移動するには、Lync Server の管理者が、割り当てられていない番号のお知らせ移行ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="787a1-776">To move the configuration settings, the Lync Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

  - <span data-ttu-id="787a1-777">**Lync server 2013 から Lync server 2010 に展開をロールバックする:** 予期しない問題が発生したため、Contoso は移行を新しい Lync Server 2013 展開にロールバックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-777">**Rolling back a deployment from Lync Server 2013 to Lync Server 2010:** Due unexpected factors, Contoso has to roll back the migration to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="787a1-778">サービスの中断を最小限に抑えるため、Lync Server 管理者は、割り当てられていない番号のお知らせ移行ツールを使用して、Lync Server 2013 の展開から Lync Server 2010 の展開に構成をロールバックします。</span><span class="sxs-lookup"><span data-stu-id="787a1-778">To minimize disruptions to the service, the Lync Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Lync Server 2013 deployment to the Lync Server 2010 deployment.</span></span>

  - <span data-ttu-id="787a1-779">**Lync の展開間でデータを移動する:** Contoso は、1つのプールのすべてのサーバーを新しいサーバーに置き換えるプロセスを進めています。</span><span class="sxs-lookup"><span data-stu-id="787a1-779">**Moving data between Lync deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="787a1-780">新しい Lync Server 2013 プールを展開し、古いプールから新しいプールにすべてのデータを移動して、古いプールを廃止するという戦略があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-780">Their strategy is to deploy a new Lync Server 2013 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="787a1-781">新しいプールを展開した後は、Unassigned Number Announcements Migration ツールを使用して、古いプールから新しいプールに構成を移行します。</span><span class="sxs-lookup"><span data-stu-id="787a1-781">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

<div>

## <a name="requirements"></a><span data-ttu-id="787a1-782">要件</span><span class="sxs-lookup"><span data-stu-id="787a1-782">Requirements</span></span>

<span data-ttu-id="787a1-783">ツールの正常な実行に必要な主な要件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="787a1-783">The following are the main requirements needed to successfully run the tool:</span></span>

1.  <span data-ttu-id="787a1-784">このスクリプトは、Lync Server 2013 管理シェルがインストールされているコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-784">The script must be run from a computer that has Lync Server 2013 Management Shell installed.</span></span>

2.  <span data-ttu-id="787a1-785">お知らせアプリケーションは、移行元と移行先の Lync サーバーまたはプールに正常に展開される必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-785">The announcement application has to be successfully deployed in the source and destination Lync Servers or Pools.</span></span>

<div>

## <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="787a1-786">Move-CsAnnouncementConfiguration スクリプト</span><span class="sxs-lookup"><span data-stu-id="787a1-786">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="787a1-787">Move-CsAnnouncementConfiguration スクリプトでは、下の表に示す 2 つのパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="787a1-787">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

<span data-ttu-id="787a1-788">![Move-CsAnnouncementConfiguration のパラメーター](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration のパラメーター")</span><span class="sxs-lookup"><span data-stu-id="787a1-788">![Move-CsAnnouncementConfiguration parameters.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parameters.")</span></span>

</div>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="787a1-789">例</span><span class="sxs-lookup"><span data-stu-id="787a1-789">Examples</span></span>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="787a1-790">割り当てられていない番号のお知らせの構成を Lync Server 2010 プールから Lync Server 2013 プールに移動する</span><span class="sxs-lookup"><span data-stu-id="787a1-790">Moving the Unassigned Number Announcements Configuration from a Lync Server 2010 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="787a1-791">この例では、割り当てられていない番号のアナウンスをソースプール (Lync Server 2010) から移行先プール (Lync Server 2013) に移動します。</span><span class="sxs-lookup"><span data-stu-id="787a1-791">This example moves the unassigned number announcements from the source pool (Lync Server 2010) to the destination pool (Lync Server 2013).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a><span data-ttu-id="787a1-792">割り当てられていない番号のお知らせの構成を Lync Server 2013 プールから Lync Server 2010 プールに移動する</span><span class="sxs-lookup"><span data-stu-id="787a1-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Lync Server 2010 Pool</span></span>

<span data-ttu-id="787a1-793">この例では、割り当てられていない番号のアナウンスをソースプール (Lync Server 2013) から移行先プール (Lync Server 2010) に移動します。</span><span class="sxs-lookup"><span data-stu-id="787a1-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Lync Server 2010).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a><span data-ttu-id="787a1-794">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="787a1-794">Web Conf Data</span></span>

<span data-ttu-id="787a1-795">Web Conf データツールを使用すると、Lync Server 2013 通信ソフトウェアの管理者は開催者の Web 会議に関連付けられたデータをより詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-795">The Web Conf Data Tool allows an administrator of Lync Server 2013 communications software to have more control over the data associated with an organizer’s Web conferences.</span></span> <span data-ttu-id="787a1-796">特定のユーザーの会議データをタイムスタンプの条件に基づいて削除する場合などのシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="787a1-796">Scenarios include the ability to delete a specific user’s meeting data based on a time stamp criteria.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="787a1-797">説明</span><span class="sxs-lookup"><span data-stu-id="787a1-797">Description</span></span>

<span data-ttu-id="787a1-798">このツールを使用すると、管理者は次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="787a1-798">This tool allows the administrator to perform the following operations:</span></span>

1.  <span data-ttu-id="787a1-799">1 人のユーザーに関連付けられているすべての Web 会議データを検索する。</span><span class="sxs-lookup"><span data-stu-id="787a1-799">Find all Web conferencing data associated with a single user.</span></span>

2.  <span data-ttu-id="787a1-800">1 人のユーザーに関連付けられているすべての Web 会議データを削除する。</span><span class="sxs-lookup"><span data-stu-id="787a1-800">Delete all Web conferencing data associated with a single user.</span></span>

3.  <span data-ttu-id="787a1-801">特定の日付よりも古い、1 人のユーザーに関連付けられているすべての Web 会議データを削除する。</span><span class="sxs-lookup"><span data-stu-id="787a1-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4.  <span data-ttu-id="787a1-802">ユーザーがあるプールから別のプールに移行した場合に、その 1 人のユーザーに関連付けられているすべての Web 会議データを移行する。</span><span class="sxs-lookup"><span data-stu-id="787a1-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="787a1-803">Lync Server 2010 用のリソースキットツールでは、1人のユーザーに関連付けられたすべての Web 会議データを別のプールに移動することができました。</span><span class="sxs-lookup"><span data-stu-id="787a1-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="787a1-804">このツールでは <STRONG>MoveConferenceData</STRONG> パラメーターのほうを優先して、この機能は現在廃止されています。</span><span class="sxs-lookup"><span data-stu-id="787a1-804">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span></span> <span data-ttu-id="787a1-805">このパラメーターの詳細については、「<A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">移動-CsUser</A>コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="787a1-805">For details about this parameter, see the <A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">Move-CsUser</A> cmdlet.</span></span>



</div>

<span data-ttu-id="787a1-p200">このツールでは、非アクティブな会議の会議データのみが削除されます。アクティブな会議 (開催中の会議) は削除できません。</span><span class="sxs-lookup"><span data-stu-id="787a1-p200">The tool deletes meeting data only for meetings that are inactive. Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="787a1-p201">このツールはターゲット ユーザーと同じプール内にあるコンピューターから実行する必要があります。会議コンテンツ データをこのツールで管理しているユーザーは同じユーザー プールに所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-p201">This tool must be run from a computer that is in the same pool as the target user. The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="787a1-810">出力</span><span class="sxs-lookup"><span data-stu-id="787a1-810">Output</span></span>

<span data-ttu-id="787a1-811">このツールでは、次の各操作の結果が出力されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-811">This tool outputs the results of each of the operations:</span></span>

  - <span data-ttu-id="787a1-812">クエリを実行した場合は、該当のユーザーを開催者とする、すべての非アクティブな会議のデータ フォルダーの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

  - <span data-ttu-id="787a1-813">削除を実行した場合は、削除対象のデータがあるすべての会議データ フォルダーの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="787a1-814">要件</span><span class="sxs-lookup"><span data-stu-id="787a1-814">Requirements</span></span>

<span data-ttu-id="787a1-815">このツールは、開催者が現在所属しているのと同じプール内で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="787a1-816">このツールは、コンテンツ ファイル ストアへのアクセス権を持つ管理者特権を使用して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="787a1-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="787a1-817">例</span><span class="sxs-lookup"><span data-stu-id="787a1-817">Examples</span></span>

<span data-ttu-id="787a1-818">下の表にパラメーターを示します (一部は例で使用されています)。</span><span class="sxs-lookup"><span data-stu-id="787a1-818">The following table describes the parameters, some of which are used in the examples.</span></span>

<span data-ttu-id="787a1-819">![Web Conf Data ツールのパラメーター](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data ツールのパラメーター")</span><span class="sxs-lookup"><span data-stu-id="787a1-819">![Web Conf Data Tool parameters.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data Tool parameters.")</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

<span data-ttu-id="787a1-p202">上の例は query コマンドの動作を示しています。このコマンドの出力は、ツールの影響を受けるすべての会議コンテンツ フォルダーの一覧になります。</span><span class="sxs-lookup"><span data-stu-id="787a1-p202">The preceding example shows how a query command would work. The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

<span data-ttu-id="787a1-p203">上の例は delete コマンドの動作を示しています。delete コマンドにより、このユーザーのすべての非アクティブな会議フォルダーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="787a1-p203">The preceding is an example of a delete command. The delete command will remove all inactive meeting folders from this user.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="787a1-824">概要</span><span class="sxs-lookup"><span data-stu-id="787a1-824">Summary</span></span>

<span data-ttu-id="787a1-825">このツールは、会議データをより正確に制御する必要のある管理者にとって役立つツールとなります。</span><span class="sxs-lookup"><span data-stu-id="787a1-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
