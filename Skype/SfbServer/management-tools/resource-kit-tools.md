---
title: Skype for Business Server 2015 リソース キット ツールのドキュメント
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: このトピックでは、Skype for Business Server 2015 リソースキットのツールについて説明します。各ツールの目的や使用例も記載されています。 Skype for Business Server 2015 リソースキットは、Skype for business Server 2015 を展開して管理する IT 管理者にとって、日常的なタスクを容易にするのに役立ちます。 たとえば、Web Conf Data ツールを使用すると、オンライン会議中にユーザーによってアップロードされたデータを簡単に制御できます。 SEFAUtil ツールを使用すると、ユーザーの問い合わせに対して自動転送や自動応答を設定できます。 IT 管理者はこれらのツールを使用して、より効率的に Skype for Business Server 2015 を管理することをお勧めします。
ms.openlocfilehash: c34998cf86de6bc85d384081c0db77f70edb68f9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289063"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="f0a90-107">Skype for Business Server 2015 リソース キット ツールのドキュメント</span><span class="sxs-lookup"><span data-stu-id="f0a90-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="f0a90-108">このトピックでは、Skype for Business Server 2015 リソースキットのツールについて説明します。各ツールの目的や使用例も記載されています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="f0a90-109">Skype for Business Server 2015 リソースキットは、Skype for business Server 2015 を展開して管理する IT 管理者にとって、日常的なタスクを容易にするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="f0a90-110">たとえば、**Web Conf Data** ツールを使用すると、オンライン会議中にユーザーによってアップロードされたデータを簡単に制御できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="f0a90-111">**SEFAUtil** ツールを使用すると、ユーザーの問い合わせに対して自動転送や自動応答を設定できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="f0a90-112">IT 管理者はこれらのツールを使用して、より効率的に Skype for Business Server 2015 を管理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="f0a90-113">リソース キット ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="f0a90-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="f0a90-114">Skype for Business Server 2015 リソースキットをインストールするには、ダウンロードセンターから[OCSReskit](https://www.microsoft.com/en-us/download/details.aspx?id=52631)をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="f0a90-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="f0a90-p103">**OCSResKit.msi** を実行すると、簡易インストールが行われます。.msi によって、**%Program Files%\Skype for Business Server 2015\ResKit** のパスにすべてのツールがインストールされます。このフォルダーには、自己完結型のツールの実行可能ファイルが格納されます。各ツールのサポート ファイルは、それぞれのサブフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p103">Run **OCSResKit.msi** to do a simple installation. The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**. Tools that are self-contained executables are in this folder. Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="f0a90-119">サポートされる環境</span><span class="sxs-lookup"><span data-stu-id="f0a90-119">Supported Environments</span></span>

<span data-ttu-id="f0a90-120">Skype for Business server 2015 リソースキットは、skype for business server 2015 に必要な仕様を満たしているサーバーにインストールする必要があります。通常は、Skype for business Server 2015 を実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="f0a90-121">リソース キット ツールの概要</span><span class="sxs-lookup"><span data-stu-id="f0a90-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="f0a90-122">以下は、Skype for Business Server 2015 リソースキットに用意されているツールの一覧です。</span><span class="sxs-lookup"><span data-stu-id="f0a90-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="f0a90-123">各ツールの要件や使用例については、以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="f0a90-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="f0a90-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="f0a90-125">Bandwidth Policy Service Monitor</span><span class="sxs-lookup"><span data-stu-id="f0a90-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="f0a90-126">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="f0a90-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="f0a90-127">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="f0a90-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="f0a90-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="f0a90-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="f0a90-129">Import Storage Service Data</span><span class="sxs-lookup"><span data-stu-id="f0a90-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="f0a90-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="f0a90-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="f0a90-131">Lookup User Console</span><span class="sxs-lookup"><span data-stu-id="f0a90-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="f0a90-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="f0a90-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="f0a90-133">Network Configuration Viewer</span><span class="sxs-lookup"><span data-stu-id="f0a90-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="f0a90-134">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="f0a90-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="f0a90-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="f0a90-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="f0a90-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="f0a90-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="f0a90-137">Unassigned Number Announcements Migration</span><span class="sxs-lookup"><span data-stu-id="f0a90-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="f0a90-138">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="f0a90-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="f0a90-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="f0a90-139">ABSConfig</span></span>
<span data-ttu-id="f0a90-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="f0a90-140"></span></span>

<span data-ttu-id="f0a90-141">アドレス帳サービス構成ツール (ABSConfig) は、管理者が Skype for Business Server 2015 のアドレス帳サービス構成をカスタマイズするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="f0a90-142">このツールでは、Skype for Business Server 2015 管理者が、既定のアドレス帳サービス設定を復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="f0a90-143">説明</span><span class="sxs-lookup"><span data-stu-id="f0a90-143">Description</span></span>

<span data-ttu-id="f0a90-144">ABSConfig は、管理者がアドレス帳サービスに関連する Active Directory ドメインサービスの属性を構成できるようにするグラフィカルユーザーインターフェイスアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="f0a90-145">このツールを使用する主なシナリオは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="f0a90-146">管理者が Active Directory ドメインサービスの属性を Skype for Business Server 2015 の属性にマッピングできるようにします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="f0a90-147">管理者が Active Directory ドメイン サービスの属性をアドレス帳サービスのファイルに含めるか、ファイルから除外できるようにする。</span><span class="sxs-lookup"><span data-stu-id="f0a90-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="f0a90-148">管理者がアドレス帳サービスの既定の設定を復元できるようにする。</span><span class="sxs-lookup"><span data-stu-id="f0a90-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="f0a90-149">ABSConfig ツールは、absConfig.exe ファイルから起動できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="f0a90-150">ツールが [属性の**構成**] タブに表示されます。この表には、Active Directory ドメインサービスの属性を Skype for Business Server 2015 の属性フィールドにマップし、特定の属性フィルターに基づいてアドレス帳サービスファイルに含めるか除外するかを指定するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="f0a90-151">また、アドレス帳ファイルに含める電話番号の値をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="f0a90-152">[**Restore Defaults**] オプションを使用すると、アドレス帳サービスの設定を既定の値に復元できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="f0a90-153">異なる OC フィールド名への AD 属性の再マッピングは、アドレス帳のファイルのダウンロードに対してのみ機能し、アドレス帳 Web クエリではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="f0a90-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="f0a90-154">出力</span><span class="sxs-lookup"><span data-stu-id="f0a90-154">Output</span></span>

<span data-ttu-id="f0a90-155">ABSConfig は、アドレス帳サービスの構成をデータベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="f0a90-156">用途</span><span class="sxs-lookup"><span data-stu-id="f0a90-156">Purpose</span></span>

<span data-ttu-id="f0a90-157">ABSConfig では、Skype for Business Server 2015 アドレス帳サービスをすばやく簡単にカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="f0a90-158">要件</span><span class="sxs-lookup"><span data-stu-id="f0a90-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="f0a90-159">コンピューター</span><span class="sxs-lookup"><span data-stu-id="f0a90-159">Computer</span></span>

<span data-ttu-id="f0a90-160">ABSConfig は、Skype for Business Server 2015 がインストールされているドメインに参加しているコンピューターからのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="f0a90-161">Skype for Business Server 2015 Enterprise Edition の場合、このツールは、セットアップ時にアドレス帳サービスが有効になっているすべてのフロントエンドサーバーで実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="f0a90-162">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="f0a90-162">Network</span></span>

<span data-ttu-id="f0a90-163">コンピューターは、フロントエンド プールとバックエンド データベースに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="f0a90-164">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="f0a90-164">Software</span></span>

<span data-ttu-id="f0a90-165">ABSConfig ツールを実行する前に、次のソフトウェア コンポーネントをインストールしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="f0a90-166">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f0a90-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="f0a90-167">ユーザー</span><span class="sxs-lookup"><span data-stu-id="f0a90-167">Users</span></span>

<span data-ttu-id="f0a90-168">Skype for Business Server 2015 の展開を更新するのに必要なアクセス許可を持つ管理者。</span><span class="sxs-lookup"><span data-stu-id="f0a90-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="f0a90-169">例</span><span class="sxs-lookup"><span data-stu-id="f0a90-169">Examples</span></span>

<span data-ttu-id="f0a90-p108">ABSConfig は、コマンド プロンプトで **ABSConfig.exe** と入力して起動することができます。ABSConfig ツールのユーザー インターフェイスを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p108">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt. Shown below is the ABSConfig tool user interface.</span></span>

![ABSConfig.exe ツール](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="f0a90-173">概要</span><span class="sxs-lookup"><span data-stu-id="f0a90-173">Summary</span></span>

<span data-ttu-id="f0a90-174">ABSConfig ツールでは、管理者は、Skype for Business Server 2015 アドレス帳サービスをカスタマイズするための簡単で使いやすいツールを提供しています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="f0a90-175">Bandwidth Policy Service Monitor</span><span class="sxs-lookup"><span data-stu-id="f0a90-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="f0a90-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="f0a90-176"></span></span>

<span data-ttu-id="f0a90-177">Bandwidth Policy Service Monitor ツールを使用すると、管理者は以下のリストを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="f0a90-178">トポロジで構成されているすべての Skype for Business Server 2015 帯域幅ポリシーサービス (認証とコア)</span><span class="sxs-lookup"><span data-stu-id="f0a90-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="f0a90-179">各サービスの帯域幅ポリシー サービスとエッジ サーバーへの接続状況</span><span class="sxs-lookup"><span data-stu-id="f0a90-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="f0a90-180">ネットワーク構成ドキュメントで構成されたすべてのリンクと、各帯域幅ポリシー サービスから報告されたリアルタイムの帯域幅の使用状況</span><span class="sxs-lookup"><span data-stu-id="f0a90-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="f0a90-181">説明</span><span class="sxs-lookup"><span data-stu-id="f0a90-181">Description</span></span>

<span data-ttu-id="f0a90-p109">Bandwidth Policy Service Monitor ツールは、GUI ベースのアプリケーションとして実装されています。管理者は、PDPMonUI.exe を実行してツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p109">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application. Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="f0a90-p110">ツールを起動すると、ツールはトポロジ内の帯域幅ポリシー サービスの一覧を検索します。初期アップデートが完了すると、ウィンドウの左ペインに、所属するクラスターによってグループ分けされたサービスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p110">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology. After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="f0a90-p111">管理者が特定の帯域幅ポリシー サービスを選ぶと、右ペインにそのサービスの情報が表示されます。次の 2 つのメイン タブにそれぞれ情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p111">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service. That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="f0a90-188">[Machine Info] タブ</span><span class="sxs-lookup"><span data-stu-id="f0a90-188">Machine Info Tab</span></span>

<span data-ttu-id="f0a90-189">[**Machine Info**] タブには、選択した帯域幅ポリシー サービスの詳細と、選択した帯域幅ポリシー サービスから別のサービスへの接続の一覧と状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="f0a90-190">[Topology Info] タブ</span><span class="sxs-lookup"><span data-stu-id="f0a90-190">Topology Info Tab</span></span>

<span data-ttu-id="f0a90-p112">[**Topology Info**] タブには、ネットワーク構成設定で構成されたすべてのリンクの一覧が表示されます。各リンクには、音声とビデオの帯域幅容量が表示されます。さらに、現在使用されている帯域幅が、Kbps と容量に対する割合で表示されます。ツールでは色分けが使用され、容量の上限に近づいているリンクが強調表示されます。これにより、管理者は対象のリンクをすばやく分離できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p112">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings. For each link, the audio and video bandwidth capacity is displayed. Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity. The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="f0a90-195">構成済みの帯域幅ポリシーサービスに接続しているときに帯域幅ポリシーのサービスモニターで障害が発生した場合、[**コンピューター情報**] タブと [**トポロジ情報**] タブにある情報は設定されません。</span><span class="sxs-lookup"><span data-stu-id="f0a90-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="f0a90-196">ただし、最初は接続されたにもかかわらず、後にサービスへの接続が途切れることもあります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="f0a90-197">このような場合、管理者に古い情報が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="f0a90-198">各タブには [**Last Updated**] タイムスタンプが用意されているため、管理者は特定の帯域幅ポリシー サービスのデータが最後に更新された時間を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="f0a90-199">出力</span><span class="sxs-lookup"><span data-stu-id="f0a90-199">Output</span></span>

<span data-ttu-id="f0a90-200">コマンドラインの出力はありません。プログラムの出力は、メインのグラフィカル ユーザー インターフェイス (GUI) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="f0a90-201">用途</span><span class="sxs-lookup"><span data-stu-id="f0a90-201">Purpose</span></span>

<span data-ttu-id="f0a90-p114">Bandwidth Policy Service Monitor ツールを使用すると、管理者はトポロジに定義された各帯域幅ポリシー サービスの詳細を確認できます。さらに、管理者はネットワーク構成ドキュメントに定義されたすべてのリンクの帯域幅の使用状況を、リアルタイムで確認できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p114">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology. In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="f0a90-204">要件</span><span class="sxs-lookup"><span data-stu-id="f0a90-204">Requirements</span></span>

<span data-ttu-id="f0a90-205">帯域幅ポリシーのサービスモニターツールは、Skype for Business Server トポロジの一部であるコンピューターで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="f0a90-206">概要</span><span class="sxs-lookup"><span data-stu-id="f0a90-206">Summary</span></span>

<span data-ttu-id="f0a90-207">Bandwidth Policy Service Monitor ツールを使用すると、トポロジ内の帯域幅ポリシー サービスの状態を確認できます。さらに、ネットワーク構成設定で定義されたリンクの帯域幅のリアルタイムの使用状況を把握できるため、管理者にとって非常に重要なリソースです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="f0a90-208">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="f0a90-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="f0a90-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="f0a90-209"></span></span>

<span data-ttu-id="f0a90-p115">Bandwidth Utilization Analyzer は、エンタープライズ ネットワークの WAN リンク全体の UC エンドポイントで消費される帯域幅を、さまざまな観点から確認できるレポートを作成するツールです。これらのレポートを使用すると、現在の帯域幅の消費パターンを把握して、帯域幅の容量計画に活用できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p115">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network. These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="f0a90-212">説明</span><span class="sxs-lookup"><span data-stu-id="f0a90-212">Description</span></span>

<span data-ttu-id="f0a90-p116">Bandwidth Utilization Analyzer は、GUI ベースのアプリケーションとして実装されます。このツールは、ネットワーク全体音声に限定した使用状況に関するレポートを作成し、容量の計画に活用できます。また、さまざまなリンクに割り当てられた帯域幅容量を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p116">Bandwidth Utilization Analyzer is implemented as a GUI-based application. This tool generates reports specifically for audio utilization across the network and helps with capacity planning. It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="f0a90-216">出力</span><span class="sxs-lookup"><span data-stu-id="f0a90-216">Output</span></span>

<span data-ttu-id="f0a90-217">Bandwidth Utilization Analyzer には、システムで構成されたすべての WAN リンクにおける、音声の帯域幅容量と使用状況に関するグラフィカル プロットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="f0a90-218">用途</span><span class="sxs-lookup"><span data-stu-id="f0a90-218">Purpose</span></span>

<span data-ttu-id="f0a90-219">音声とビデオによる展開では、エンタープライズネットワーク全体でのメディアトラフィックの帯域幅使用率の傾向を監視し、理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="f0a90-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="f0a90-220">Bandwidth Utilization Analyzer ツールを使用すると、管理者はそれを把握できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="f0a90-221">このツールでは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-221">This tool does the following:</span></span>

- <span data-ttu-id="f0a90-222">ネットワーク全体にわたる音声の使用状況に関するレポートを生成する</span><span class="sxs-lookup"><span data-stu-id="f0a90-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="f0a90-223">より効果的な容量計画の立案と、さまざまなリンクに割り当てられた帯域幅容量の反復処理をサポートする</span><span class="sxs-lookup"><span data-stu-id="f0a90-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="f0a90-224">Bandwidth Utilization Analyzer では、帯域幅容量のグラフィカル プロットと使用状況レポートを作成できます。その範囲と実行可能な操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="f0a90-225">エンタープライズ ネットワーク内のすべての WAN リンク</span><span class="sxs-lookup"><span data-stu-id="f0a90-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="f0a90-226">事前に指定した WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="f0a90-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="f0a90-227">リンク容量を超過した WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="f0a90-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="f0a90-228">帯域幅の使用率が予測を下回る WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="f0a90-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="f0a90-229">重大レベル (WAN リンクの帯域幅使用率が容量の 90% を超過している) に達している WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="f0a90-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="f0a90-230">WAN リンクの種類 (ネットワーク サイト リンク、地域間リンク、サイト内リンク) でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="f0a90-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="f0a90-231">ネットワーク地域でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="f0a90-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="f0a90-232">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f0a90-232">Applications</span></span>

<span data-ttu-id="f0a90-233">Bandwidth Utilization Analyzer には、次の 2 つのアプリケーション (ツール) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="f0a90-234">**WanLinkLogCollector**このツールを使用すると、ユーザーは必要な情報を入力することができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="f0a90-235">**BandwidthUtilizationAnalyzer** Microsoft Excel スプレッドシートソフトウェアレポートは、WanLinkLogCollector によって自動的に起動されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="f0a90-236">このアプリケーションでは、レポートにフィルターを適用できます (この記事の後半で説明します)。</span><span class="sxs-lookup"><span data-stu-id="f0a90-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="f0a90-237">Bandwidth Utilization Analyzer の使用フェーズ</span><span class="sxs-lookup"><span data-stu-id="f0a90-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="f0a90-238">Bandwidth Utilization Analyzer の使用は、次の 2 つのフェーズに分けられます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="f0a90-239">ログの収集 (WanLinkLogCollector.exe を使用)</span><span class="sxs-lookup"><span data-stu-id="f0a90-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="f0a90-240">レポートのカスタマイズ (BandwidthUtilizationAnalyzer.xlsm を使用)</span><span class="sxs-lookup"><span data-stu-id="f0a90-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0a90-241">BandwidthUtilizationAnalyzer.xlsm はエンド ユーザーが手動で起動できないようにすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="f0a90-242">Bandwidth Utilization Analyzer の起動</span><span class="sxs-lookup"><span data-stu-id="f0a90-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="f0a90-243">コマンド プロンプトで WanLinkLogCollector.exe を実行するか、Windows エクスプローラーを使用して起動します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="f0a90-244">**WanLinkLogCollector.exe の使用**</span><span class="sxs-lookup"><span data-stu-id="f0a90-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="f0a90-245">WanLinkLogCollector.exe を使用するには、次の 3 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="f0a90-246">**タイムラインを記録する**レポートを生成する必要があるタイムラインを指定する</span><span class="sxs-lookup"><span data-stu-id="f0a90-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="f0a90-247">**ファイルディレクトリを指定**するファイルの場所情報を入力する</span><span class="sxs-lookup"><span data-stu-id="f0a90-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="f0a90-248">**ログを収集し、レポートビューアーを起動する**コマンドを実行してレポートを生成する</span><span class="sxs-lookup"><span data-stu-id="f0a90-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="f0a90-249">手順 1 - ログのタイムラインを指定する</span><span class="sxs-lookup"><span data-stu-id="f0a90-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="f0a90-250">タイムラインのログを記録するには、以下の図に示すように、次の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="f0a90-251">**Start date** レポートを生成するタイムラインの開始日 (例: 2010 年 8 月 1 日)。</span><span class="sxs-lookup"><span data-stu-id="f0a90-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="f0a90-252">**End date** レポートを生成するタイムラインの終了日 (例: 2010 年 9 月 30 日)。</span><span class="sxs-lookup"><span data-stu-id="f0a90-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![Bandwidth Utilization Analyzer の開始日/終了日](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="f0a90-254">手順 2 - ファイルのディレクトリを指定する</span><span class="sxs-lookup"><span data-stu-id="f0a90-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="f0a90-255">図に示すように、以下のファイル ディレクトリを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="f0a90-256">**サーバーのログファイルの場所**帯域幅ポリシーサーバーログが保存されているフォルダーの場所。</span><span class="sxs-lookup"><span data-stu-id="f0a90-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="f0a90-257">通常、これは\<、\>\\<choice の [\>FE \AppServerFiles\PDP. のにあります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="f0a90-258">**一時ファイルの保存場所**レポートの生成中に中間ファイルが保存される一時ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="f0a90-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

![Bandwidth Utilization Analyzer のファイル ディレクトリ](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

> [!NOTE]
> <span data-ttu-id="f0a90-260">サーバー ログや一時ファイルを格納するフォルダーにアクセスできる十分な権限をツールのユーザーに割り当てるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f0a90-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="f0a90-261">手順 3 - ログを収集してレポート ビューアーを起動する</span><span class="sxs-lookup"><span data-stu-id="f0a90-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="f0a90-p120">ログを収集してレポート ビューアーを起動するには、以下の図に示す [**Execute**] をクリックします。この手順により、必要なデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p120">To collect the logs and start the report viewer, click **Execute** as shown below. This step collects the required data.</span></span>

![Bandwidth Utilization Analyzer でのデータの収集](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="f0a90-265">入力の検証が正常に行われると、以下のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-265">When the input validation is successful, the message shown below is displayed.</span></span>

![BandwidthUtilizationAnalyzer でログに収集された通知](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="f0a90-p121">[**OK **] をクリックします。BandwidthUtilizationAnalyzer.xlsm は自動的に起動します。メッセージ ボックスの指示に従います。詳細については、次のセクション「**BandwidthUtilizationAnalyzer.xlsm の使用**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p121">Click **OK**. BandwidthUtilizationAnalyzer.xlsm is automatically started. Follow the instructions in the message box. For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="f0a90-271">BandwidthUtilizationAnalyzer.xlsm の使用</span><span class="sxs-lookup"><span data-stu-id="f0a90-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="f0a90-272">BandwidthUtilizationAnalyzer.xlsm が自動的に起動したら、以下の図に示す [**Refresh**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="f0a90-p122">ファイルのフォルダーが開いたら、メッセージ ボックスで指定した場所にある consolidated.csv を選びます。以下に示すように、場所は **C:\Temp** です。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p122">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below. It also shows the location as **C:\Temp**.</span></span>

     ![BandwidthUtilizationAnalyzer でフォルダーを開く](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="f0a90-277">[**Import**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-277">Click **Import**.</span></span>

4. <span data-ttu-id="f0a90-p123">グラフィカル プロットが自動的に生成されます。バックグラウンドで作業中のポインターが表示されなくなると、使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p123">The graphical plot is automatically generated. It is available when the working-in-the-background pointer disappears.</span></span>

     ![レポート ビューでのフィルターの適用](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="f0a90-281">レポート ビューにフィルターを適用する</span><span class="sxs-lookup"><span data-stu-id="f0a90-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="f0a90-282">レポート ビューに適用できるフィルター (以下の図を参照) は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![レポート ビューでのフィルターの適用](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="f0a90-284">**Name** WAN リンクでフィルター処理 (グラフの右側のフィルター)。プレフィックス (縦長の青いボックスを参照) は、次のようなリンクの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="f0a90-285">**S: Site** ネットワーク サイトからネットワーク地域への WAN リンク</span><span class="sxs-lookup"><span data-stu-id="f0a90-285">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="f0a90-286">**IS Inter-Site** 2 つのネットワーク サイト間の WAN リンク</span><span class="sxs-lookup"><span data-stu-id="f0a90-286">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="f0a90-287">**R Inter-Region** 2 つのネットワーク地域間の WAN リンク</span><span class="sxs-lookup"><span data-stu-id="f0a90-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="f0a90-288">**Exceeded limit** 帯域幅の使用率が帯域幅容量を超過している WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="f0a90-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="f0a90-289">**Critical levels** 帯域幅の使用率が帯域幅容量の 90% 以上に達した WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="f0a90-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="f0a90-290">**Under-utilized** 帯域幅の使用率が帯域幅容量の 25% に達していない WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="f0a90-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="f0a90-291">**Link type** 次に示す WAN リンクの種類でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-291">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="f0a90-292">**Network site** タイプ</span><span class="sxs-lookup"><span data-stu-id="f0a90-292">**Network site** type</span></span>

   - <span data-ttu-id="f0a90-293">**Inter-site** タイプ</span><span class="sxs-lookup"><span data-stu-id="f0a90-293">**Inter-site** type</span></span>

   - <span data-ttu-id="f0a90-294">**Inter-Region link** タイプ</span><span class="sxs-lookup"><span data-stu-id="f0a90-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="f0a90-295">**Region** ネットワーク地域でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="f0a90-295">**Region** Filter by network region</span></span>

<span data-ttu-id="f0a90-296">次の図は、これまでに紹介したフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="f0a90-p124">[**Name**] でフィルター処理します。グラフに表示するリンクのリストを選びます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p124">Filter by **Name**. Select the list of links that need to be displayed in the graph.</span></span>

![BandwidthUtilizationAnalyzer での [Name] でのフィルター処理](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="f0a90-300">[**Exceeded limit**] でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-300">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="f0a90-301">フィルターを適用するには、[**True**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-301">Select **True** to enforce the filter.</span></span>

![[Exceeded Limit] でのフィルター処理](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="f0a90-303">[\*\*Critical levels \*\*] でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-303">Filter by **Critical levels**.</span></span> <span data-ttu-id="f0a90-304">フィルターを適用するには、[\*\*TRUE \*\*] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-304">Select **True** to enforce the filter.</span></span>

![[Critical Levels] でのフィルター処理](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="f0a90-306">[\*\*Under-utilized \*\*] でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-306">Filter by **Under utilized**.</span></span> <span data-ttu-id="f0a90-307">フィルターを適用するには、[\*\*TRUE \*\*] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-307">Select **True** to enforce the filter.</span></span>

![[Under Utilized] でのフィルター処理](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="f0a90-309">[**Link Type**] でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-309">Filter by **Link Type**.</span></span> <span data-ttu-id="f0a90-310">表示する種類を 1 つ以上選びます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-310">Select the type or types that need to be displayed.</span></span>

![[Link Type] でのフィルター処理](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="f0a90-312">[**Region**] でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-312">Filter by **Region**.</span></span> <span data-ttu-id="f0a90-313">リンクを表示する地域のリストを選びます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-313">Select a list of regions whose links need to be displayed.</span></span>

![[Region] でのフィルター処理](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="f0a90-315">要件</span><span class="sxs-lookup"><span data-stu-id="f0a90-315">Requirements</span></span>

- <span data-ttu-id="f0a90-316">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="f0a90-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="f0a90-317">Microsoft Excel 2010 または Excel 2007</span><span class="sxs-lookup"><span data-stu-id="f0a90-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="f0a90-318">概要</span><span class="sxs-lookup"><span data-stu-id="f0a90-318">Summary</span></span>

<span data-ttu-id="f0a90-p130">Bandwidth Utilization Analyzer は、ネットワーク全体の UC トラフィックにおける音声の帯域幅の使用状況をプロットするために使用します。このツールは、ビデオの帯域幅の使用状況を報告する場合にも同様に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p130">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network. This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="f0a90-321">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="f0a90-321">Call Parkometer</span></span>
<span data-ttu-id="f0a90-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="f0a90-322"></span></span>

<span data-ttu-id="f0a90-323">Call Parkometer は、コール パーク オービット デバイスに簡単にアクセスできるコマンドライン アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="f0a90-324">説明</span><span class="sxs-lookup"><span data-stu-id="f0a90-324">Description</span></span>

<span data-ttu-id="f0a90-325">Call Parkometer は、現在パークされている通話を追跡するツールです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="f0a90-326">オービットやコール パーク サーバー (CPS) の使用状況に関する統計情報も収集します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="f0a90-327">このコマンドラインツールは、CPS への読み取りアクセスと書き込みアクセスの両方を提供します。これには、ローカルまたはリモート接続コンピューターからの SQL Server データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="f0a90-328">すべてのオプションは同時に使用できません。</span><span class="sxs-lookup"><span data-stu-id="f0a90-328">All options are mutually exclusive.</span></span> <span data-ttu-id="f0a90-329">コマンドライン構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-329">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="f0a90-330">**-o**パラメーター—このプールで構成されているすべてのオービット範囲を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="f0a90-331">**-n**パラメーター—このプールで現在使用されているすべての orbits を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="f0a90-332">情報は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="f0a90-333">パーク元とパーク先の SIP Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="f0a90-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="f0a90-334">通話のパーク先の CPS のホスト名。</span><span class="sxs-lookup"><span data-stu-id="f0a90-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="f0a90-335">通話がパークされた時点のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="f0a90-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="f0a90-336">**-f**パラメーター—プール内の現在の空き orbits の数を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="f0a90-337">\*\*-r \<n\> \*\*パラメーター—\>最終保留\<された通話の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="f0a90-338">情報は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="f0a90-339">パーク先の SIP URI。</span><span class="sxs-lookup"><span data-stu-id="f0a90-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="f0a90-340">パーク元の SIP URI。</span><span class="sxs-lookup"><span data-stu-id="f0a90-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="f0a90-341">通話のパーク先の CPS のホスト名。</span><span class="sxs-lookup"><span data-stu-id="f0a90-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="f0a90-342">通話が保留解除または切断された時点のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="f0a90-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="f0a90-343">\*\*-t\<n\> \*\*パラメーター-データベース内のオービットを予約して、割り当てられた値の乱数をランダムに表示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="f0a90-344">出力</span><span class="sxs-lookup"><span data-stu-id="f0a90-344">Output</span></span>

<span data-ttu-id="f0a90-345">コマンド プロンプトで指定された入力パラメーターによっては、Call Parkometer に次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="f0a90-346">このプールで構成されたすべてのオービット範囲</span><span class="sxs-lookup"><span data-stu-id="f0a90-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="f0a90-347">現在パークされている通話</span><span class="sxs-lookup"><span data-stu-id="f0a90-347">Currently parked calls</span></span>

- <span data-ttu-id="f0a90-348">有効な (使用可能な) オービットの数</span><span class="sxs-lookup"><span data-stu-id="f0a90-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="f0a90-349">最近パークされた通話</span><span class="sxs-lookup"><span data-stu-id="f0a90-349">Recently parked calls</span></span>

- <span data-ttu-id="f0a90-350">一定およびランダムなオービットの値をテストするために予約されたオービット</span><span class="sxs-lookup"><span data-stu-id="f0a90-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="f0a90-351">用途</span><span class="sxs-lookup"><span data-stu-id="f0a90-351">Purpose</span></span>

<span data-ttu-id="f0a90-p135">CPS ツールを使用すると、CPS データベースへのコマンドライン アクセスを確立できます。管理者は、CPS の使用状況を確認して、プールに割り当てられているオービットの数を把握できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p135">The purpose of the CPS tool is to provide command-line access to the CPS database. The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="f0a90-354">要件</span><span class="sxs-lookup"><span data-stu-id="f0a90-354">Requirements</span></span>

<span data-ttu-id="f0a90-355">CPS が実行されている同じコンピューターで実行する場合、このツールの使用に必要な条件はありません。</span><span class="sxs-lookup"><span data-stu-id="f0a90-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="f0a90-356">このツールがリモートコンピューターで実行される場合は、Skype for Business Server 2015 で使用される SQL Server データベースがリモートアクセスを許可するように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="f0a90-357">呼び出しの場合は、プールの SQL Server に接続するために SQL Server データベース接続文字列を使用して構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="f0a90-358">この SQL Server データベース接続文字列は構成ファイルで定義され\*\*\*\* ています。このファイルは、par・・・・・・・・ m の場所にあるのと同じディレクトリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="f0a90-359">次の XML ファイルは、par・メータの例です。構成が必要なパラメーターは、ユーザー名 (myの "管理者" など)、パスワード (mypassword など)、ホスト名 (たとえば、myserver) です。</span><span class="sxs-lookup"><span data-stu-id="f0a90-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

```
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

### <a name="examples"></a><span data-ttu-id="f0a90-360">例</span><span class="sxs-lookup"><span data-stu-id="f0a90-360">Examples</span></span>

<span data-ttu-id="f0a90-361">展開された軌道範囲:-o パラメーターは、このプール用に構成されているすべてのオービット範囲を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Call Parkometer のオービット範囲](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="f0a90-363">現在保留中の通話:-n パラメーターは、このプールで現在使用されているすべての orbits を示しています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Call Parkometer で現在保留されている通話](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="f0a90-365">無料 orbits の数:-f パラメーターには、プール内の現在の空き orbits の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Call Parkometer の使用されていないオービット](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="f0a90-367">最近の保留中の通話: \<-\> r n パラメーター \<は\> 、表示されている最後の保留中の通話を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Call Parkometer で最近保留された通話](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="f0a90-369">軌道予約をテストします。 \<-\> t n パラメーターテストでは、データベース内のオービットが次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Call Parkometer のオービット予約のテスト](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="f0a90-371">概要</span><span class="sxs-lookup"><span data-stu-id="f0a90-371">Summary</span></span>

<span data-ttu-id="f0a90-372">Call Parkometer は、コール パーク サーバーに関する詳しい情報を提供するコマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="f0a90-373">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="f0a90-373">DBAnalyze</span></span>
<span data-ttu-id="f0a90-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="f0a90-374"></span></span>

### <a name="description"></a><span data-ttu-id="f0a90-375">説明</span><span class="sxs-lookup"><span data-stu-id="f0a90-375">Description</span></span>

<span data-ttu-id="f0a90-376">DBAnalyze は、管理者が Skype for Business Server 2015 データベースに関する分析レポートを収集するのに役立つコマンドラインツールです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="f0a90-377">DBAnalyze には、診断モード、ユーザー データ モード、会議モード、MCU モード、ディスク断片化モードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="f0a90-378">**診断モード**テーブル (レコード数、断片化、データサイズ、インデックスサイズ)、データとログファイルのサイズ、最後のバックアップ時間、Microsoft Office Communications Server を実行しているサーバー間の連絡先配布に関する情報を含むレポートを作成します。アクセス許可の平均数、連絡先、コンテナー、サブスクリプション、文書、ユーザーあたりのエンドポイント、不適切にホームとなっているユーザー、ルーティングできない会議の平均数、スケジュールされた会議、アクティブな会議データベースのバージョン。</span><span class="sxs-lookup"><span data-stu-id="f0a90-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f0a90-379">診断モードを実行すると、サーバーのパフォーマンスに影響を与えることがあります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="f0a90-380">**ユーザーデータモード**指定したユーザーの連絡先、コンテナー、サブスクリプション、パブリケーション、アクセス許可、連絡先グループのデータ、またはそのユーザーを連絡先やアクセス許可の一覧に登録しているユーザーのレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="f0a90-381">このモードでは、ユーザーが開催する、または招待された会議の概要データもレポートします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="f0a90-382">**会議モード**会議のすべてのスケジュールの詳細、出席者リスト、会議で許可されているメディアの種類の一覧、アクティブな Mcu (multipoint control ユニット)、アクティブな参加者の一覧、各会議の詳細データをレポートします。参加者のシグナリングの状態。</span><span class="sxs-lookup"><span data-stu-id="f0a90-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="f0a90-383">**会議 ID のデコード\*\*\*\*/Pstnid**スイッチで指定されている公衆交換電話網 (PSTN) 会議 ID をデコードしますが、詳細情報についてはバックエンドに接続しません。</span><span class="sxs-lookup"><span data-stu-id="f0a90-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="f0a90-384">**会議の解決\*\*\*\*/Pstnid**スイッチで指定されている PSTN 会議 ID をデコードし、ID で示されている会議に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="f0a90-385">**Mcu モード**プール内の各 MCU の ID、メディアの種類、URL、ハートビートの状態、会議のロード、参加者の負荷をレポートします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="f0a90-386">**ディスクの最適化モード**すべてのディスクの断片化の状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="f0a90-p139">このツールは、さまざまな問題を診断し、管理者の容量計画を支援するために使用できます。たとえば、サーバー A に所属する大多数のユーザーが、サーバー B に所属するユーザーを連絡先として選択した場合、管理者はサーバー A のユーザーをサーバー B に移動して、サーバー間のトラフィックを削減できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p139">This tool can be used to diagnose various problems or to assist administrators with capacity planning. For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="f0a90-389">出力</span><span class="sxs-lookup"><span data-stu-id="f0a90-389">Output</span></span>

<span data-ttu-id="f0a90-390">このツールは、Skype for Business Server 2015 データベースに関する定義済みレポートを出力します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="f0a90-391">**パス**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span><span class="sxs-lookup"><span data-stu-id="f0a90-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="f0a90-392">用途</span><span class="sxs-lookup"><span data-stu-id="f0a90-392">Purpose</span></span>

<span data-ttu-id="f0a90-393">Dbanalyze .exe をインストールするには、ローカルフォルダーにコピーし、ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="f0a90-394">このツールを使用するには、コマンドラインから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="f0a90-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`コマンドラインオプションの説明を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Dbanalyze.exe のコマンド ライン オプション](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="f0a90-397">要件</span><span class="sxs-lookup"><span data-stu-id="f0a90-397">Requirements</span></span>

 <span data-ttu-id="f0a90-398">**コンピューター**DBAnalyze は、Skype for Business Server 2015 がインストールされているドメインに参加しているコンピューターからのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="f0a90-399">**ネットワーク** コンピューターは、バックエンド データベースに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="f0a90-400">**ソフトウェア**DBAnalyze を実行する前に、Skype for Business Server 2015 ソフトウェアコンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="f0a90-401">**ユーザー**次の表は、Skype for Business Server 2015 データベースへのアクセスに必要な権限を持っている管理者を示しています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-401">**Users**The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Dbanalyze.exe の権限のテーブル](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="f0a90-403">**/report:disk** モードでは、ローカル管理者のアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="f0a90-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="f0a90-404">例</span><span class="sxs-lookup"><span data-stu-id="f0a90-404">Examples</span></span>

<span data-ttu-id="f0a90-405">次に、有効な Dbanalyze.exe コマンドの例を示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="f0a90-406">概要</span><span class="sxs-lookup"><span data-stu-id="f0a90-406">Summary</span></span>

<span data-ttu-id="f0a90-407">DBAnalyzer を使用すると、管理者は Skype for Business Server 2015 データベースの分析をすばやく簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="f0a90-408">Import Storage Service Data</span><span class="sxs-lookup"><span data-stu-id="f0a90-408">Import Storage Service Data</span></span>
<span data-ttu-id="f0a90-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="f0a90-409"></span></span>

<span data-ttu-id="f0a90-410">ImportStorageServiceData リソース キット ツールを使用すると、Storage Service (LYSS) からフラッシュされたキューやエンドポイントのデータを、ストレージ サービスに再インポートできます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="f0a90-411">説明</span><span class="sxs-lookup"><span data-stu-id="f0a90-411">Description</span></span>

<span data-ttu-id="f0a90-412">Storage Service からのデータのフラッシュは、キュー アイテムの状態やデータベースのサイズに基づいて自動的 (定期的) に行われた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="f0a90-413">また、プール フェールオーバー コマンドレット、またはそれによって呼び出される StorageServiceFullFlush コマンドレットの手動呼び出しによって行われた可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="f0a90-414">フロントエンドのデータベースのサイズが通常のレベルよりも上にある場合は、データがより多くエクスポートされる可能性が高いため、データを再インポートしないことをお勧めします。さらに、ストレージサービスキューの増加を引き起こしたエラーの原因となった問題は、まず解決される必要があります (Exchange のエンドポイントエラー、ネットワークの問題、その他の問題など)。</span><span class="sxs-lookup"><span data-stu-id="f0a90-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="f0a90-415">**シナリオ 1:** プールのフェールオーバー中に、各フロントエンドのストレージ サービスからファイルがフラッシュされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="f0a90-416">フェールオーバーが完了したら、ツールを実行してデータを再インポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="f0a90-417">**シナリオ 2:** データは毎日自動的にフラッシュされます。または、特定のサイズのしきい値を超える記憶域サービスデータベースに対応しています (たとえば、60%、80%、90%)。</span><span class="sxs-lookup"><span data-stu-id="f0a90-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="f0a90-418">この自動フラッシュデータは、管理者によって定期的に再インポートされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="f0a90-419">このような状況では、monitoring SCOM pack が展開されていない場合、ストレージサービスからフラッシュされるデータに関連した Skype for Business Server ストレージサービスのイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="f0a90-420">32075のイベント Id (完全なフラッシュ操作が開始されます)、32076 (完全なフラッシュが完了しました)、32082 (メンテナンスレベルのフラッシュ開始)、32083 (メンテナンスレベルのフラッシュの完了)、32089 (データベースの書き込みによるフラッシュ発生)。</span><span class="sxs-lookup"><span data-stu-id="f0a90-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="f0a90-421">注: これらのイベント Id は、RTM リリースに対応しています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="f0a90-422">管理者にこれらのイベントが表示される場合は、フラッシュアウトされたファイルがあることを意味します。このデータは定期的にこのツールを使ってインポートし直す必要があります。たとえば、週ごとに1回。</span><span class="sxs-lookup"><span data-stu-id="f0a90-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="f0a90-423">オンラインサービスのリリースでは、Skype for Business Server 用の正常性監視 SCOM pack が展開されている場合は、管理者に対して、フラッシュされたデータを記憶域サービスに再インポートするように求める新しい通知が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="f0a90-424">警告の原因に対応するイベントは、フロントエンド サーバーのイベント ログに出されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="f0a90-425">イベントの出力には、フラッシュされたデータ ファイルが置かれている親パスや、警告の条件に一致するファイルの個数などが記述されています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="f0a90-426">警告の条件は、指定の親パスに Y 日以上前のファイルが X 個以上あることです (X と Y は StorageService 内に事前設定されていますが、APPCONFIG ファイルを変更して上書きできます)。</span><span class="sxs-lookup"><span data-stu-id="f0a90-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="f0a90-427">状態の警告が出されるイベントで、親パスが異なる場合の例を以下に 2 つ示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="f0a90-428">1 つは Web サービスのファイル共有で、もう 1 つは各フロントエンドのローカルの Application Data ディレクトリ (例: c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService) です。</span><span class="sxs-lookup"><span data-stu-id="f0a90-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="f0a90-429">その後、管理者はこの reskit ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="f0a90-430">このツールは、ツールが実行されているフロントエンドでデータが所有されていない場合に、このツールが実行されているフロントエンドの CPU と IO の負荷を、他のフロントエンドと共に増やします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="f0a90-431">このツールは、フロントエンドの CPU と IO の負荷が高くない場合 (ピーク時間以外の場合など) に、このツールを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="f0a90-432">次に、このツールでは、1つのデータファイルをインポートするために 2 ~ 3 分間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="f0a90-433">ツールの実行時間を見積もるときは、この点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="f0a90-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="f0a90-434">ツールによって生成される詳細ログファイルは、既定でファイルストアに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="f0a90-435">ログファイルの数が MB 以上である可能性があるため、エラーが報告されていない場合は削除します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![記憶域サーバーのイベント ログのサンプル イベント](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="f0a90-437">要件</span><span class="sxs-lookup"><span data-stu-id="f0a90-437">Requirements</span></span>

<span data-ttu-id="f0a90-438">Skype for Business Server 2015 リソースキットツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="f0a90-439">このツールは、Skype for Business Server と Skype for Business Server 管理シェルがインストールされているドメインに参加しているコンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="f0a90-440">このツールは、管理シェルのコマンドレットを使用して、プール内のすべてのフロントエンドサーバーを特定します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="f0a90-441">第二に、このツールは、 **Rtclocal**データベースがインストールされているプール内のコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="f0a90-442">このデータベースは、ツールによって、プールの WEBSERVICE ファイル共有の場所を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="f0a90-443">さらに、このツールを使用する前に、各フロントエンドサーバーで、まず、各フロントエンドサーバーで**enable-PSRemoting**を使用して Windows PowerShell リモート処理を有効にする必要があります。また、このツールが実行されているコンピューターの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="f0a90-444">そうしないと、このツールのリモート Windows PowerShell コマンドが失敗します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="f0a90-445">Windows PowerShell リモート処理は、プールの終了後、すべてのフロントエンドサーバーで無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="f0a90-446">最後に、ツールを呼び出すアカウントまたは資格情報に、このツールを実行しているプールの webservice ファイル共有への読み取り/書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f0a90-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="f0a90-447">そうしないと、IO 権限のエラーでツールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="f0a90-448">Windows Server 2012 では、windows PowerShell リモート処理は既定で有効になっていますが、Windows Server 2008 オペレーティングシステムでは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="f0a90-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="f0a90-449">例</span><span class="sxs-lookup"><span data-stu-id="f0a90-449">Examples</span></span>

```
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
```

## <a name="lcssync"></a><span data-ttu-id="f0a90-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="f0a90-450">LCSSync</span></span>
<span data-ttu-id="f0a90-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="f0a90-451"></span></span>

<span data-ttu-id="f0a90-452">LCSSync ツールを使用すると、複数のフォレスト環境に Skype for Business Server 2015 通信ソフトウェアを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="f0a90-453">このツールは、Skype for Business Server 2015 がインストールされている中央フォレストに、異なるユーザーフォレストのユーザーとグループを Active Directory ドメインサービスの連絡先オブジェクトとして同期するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="f0a90-454">説明</span><span class="sxs-lookup"><span data-stu-id="f0a90-454">Description</span></span>

 <span data-ttu-id="f0a90-455">LCSSync は、中央のフォレストの同期された Active Directory ドメインサービスの連絡先オブジェクトを使用して、Skype for Business Server のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="f0a90-456">シングルサインインを提供するには、プライマリユーザーアカウントが、Skype for Business Server 2015 の中央フォレストの Active Directory ドメインサービスの連絡先オブジェクトにマップされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="f0a90-457">このツールは、そのマッピングを支援します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="f0a90-458">このツールには、Microsoft Identity Integration Server で Management Agents を作成するためのテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="f0a90-459">概要</span><span class="sxs-lookup"><span data-stu-id="f0a90-459">Summary</span></span>

<span data-ttu-id="f0a90-460">LCSSync ツールを使用すると、複数のフォレスト環境に Skype for Business Server 2015 を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="f0a90-461">Lookup User Console</span><span class="sxs-lookup"><span data-stu-id="f0a90-461">Lookup User Console</span></span>
<span data-ttu-id="f0a90-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="f0a90-462"></span></span>

<span data-ttu-id="f0a90-463">LookupUserConsole ツールは、特定のユーザーに関する内部の Skype for Business Server ルーティング情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="f0a90-464">この情報は、Microsoft のサポート担当者が展開やルーティングの問題を解決するのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="f0a90-465">説明</span><span class="sxs-lookup"><span data-stu-id="f0a90-465">Description</span></span>

 <span data-ttu-id="f0a90-466">LookupUserConsole を実行すると、SIP アドレスを受け入れ、それに関連する内部の Skype for Business Server ルーティング情報を表示しようとするコマンドプロンプトが開きます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="f0a90-467">LookupUserConsole ツールを終了するには、「**exit**」 と入力します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="f0a90-468">要件</span><span class="sxs-lookup"><span data-stu-id="f0a90-468">Requirements</span></span>

<span data-ttu-id="f0a90-469">Skype for Business Server 2015 リソースキットをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="f0a90-470">このツールは、Skype for Business Server がインストールされているドメインに参加しているコンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="f0a90-471">例</span><span class="sxs-lookup"><span data-stu-id="f0a90-471">Examples</span></span>

<span data-ttu-id="f0a90-472">C:\Program Files\Skype for Business Server 2015 \ ResKit\>lookupuserconsole</span><span class="sxs-lookup"><span data-stu-id="f0a90-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

```
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
```

## <a name="msturnping"></a><span data-ttu-id="f0a90-473">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="f0a90-473">MsTurnPing</span></span>
<span data-ttu-id="f0a90-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="f0a90-474"></span></span>

<span data-ttu-id="f0a90-475">MSTurnPing ツールを使用すると、Skype for Business Server 2015 通信ソフトウェアの管理者は、オーディオ/ビデオエッジとオーディオ/ビデオ認証サービスを実行しているサーバーと、帯域幅ポリシーを実行しているサーバーの状態を確認することができます。トポロジ内のサービス。</span><span class="sxs-lookup"><span data-stu-id="f0a90-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="f0a90-476">説明</span><span class="sxs-lookup"><span data-stu-id="f0a90-476">Description</span></span>

<span data-ttu-id="f0a90-477">MSTurnPing ツールを使用すると、Skype for Business Server 2015 通信ソフトウェアの管理者は、オーディオ/ビデオエッジとオーディオ/ビデオ認証サービスを実行しているサーバーと、帯域幅ポリシーを実行しているサーバーの状態を確認することができます。トポロジ内のサービス。</span><span class="sxs-lookup"><span data-stu-id="f0a90-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="f0a90-478">このツールを使用すると、管理者は次のテストを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="f0a90-479">音声ビデオ エッジ サーバー テスト: トポロジ内の音声ビデオ エッジ サーバーに対して次のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="f0a90-480">Skype for Business Server の音声/ビデオ認証サービスが開始されていて、適切な資格情報を発行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="f0a90-481">Skype for Business Server のオーディオ/ビデオエッジサービスが開始されていることを確認し、外部境界にリソースを正常に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="f0a90-482">帯域幅ポリシー サービス テスト: トポロジ内の帯域幅ポリシー サービスを実行しているすべてのサーバーに対して次のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="f0a90-483">Skype for Business Server 帯域幅ポリシーサービス (認証) が開始されていて、適切な資格情報を発行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="f0a90-484">Skype for Business Server 帯域幅ポリシーサービス (コア) が開始されていて、帯域幅のチェックを正常に実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="f0a90-485">このツールは、トポロジの一部でありローカル ストアがインストールされているコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="f0a90-486">出力</span><span class="sxs-lookup"><span data-stu-id="f0a90-486">Output</span></span>

<span data-ttu-id="f0a90-487">このツールでは、各操作の結果が出力されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="f0a90-488">**AudioVideoEdgeServer** テストを実行した場合、ツールの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="f0a90-489">トポロジで Skype for Business Server 2015 Audio/Video Authentication service を提供しているコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="f0a90-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="f0a90-490">トポロジで Skype for Business Server 2015 オーディオ/ビデオエッジサービスを提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="f0a90-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="f0a90-491">**BandwidthPolicyServer** テストを実行した場合、ツールの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="f0a90-492">トポロジで Skype for Business Server 2015 帯域幅ポリシーサービス (Authentication) を提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="f0a90-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="f0a90-493">トポロジで Skype for Business Server 2015 帯域幅ポリシーサービス (コア) を提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="f0a90-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="f0a90-494">要件</span><span class="sxs-lookup"><span data-stu-id="f0a90-494">Requirements</span></span>

- <span data-ttu-id="f0a90-495">このツールは、トポロジ内のローカル ストアを持つコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="f0a90-496">このツールは、ローカル ストアへのアクセス権のある管理者として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="f0a90-497">例</span><span class="sxs-lookup"><span data-stu-id="f0a90-497">Examples</span></span>

<span data-ttu-id="f0a90-498">ツールの入力例は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-498">The following is an example of the tool input.</span></span>

```
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="f0a90-499">概要</span><span class="sxs-lookup"><span data-stu-id="f0a90-499">Summary</span></span>

<span data-ttu-id="f0a90-500">このツールは、音声/ビデオおよび帯域幅ポリシーサービスを実行しているサーバーの状態を確認する、Skype for Business Server 2015 管理者にとって有益なリソースになることがあります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="f0a90-501">Network Configuration Viewer</span><span class="sxs-lookup"><span data-stu-id="f0a90-501">Network Configuration Viewer</span></span>
<span data-ttu-id="f0a90-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="f0a90-502"></span></span>

<span data-ttu-id="f0a90-503">Network Configuration Viewer は、Skype for Business Server 2015 communications software 管理者が、リアルタイム通信セッションを許可するようにプロビジョニングされている企業の通話受付制御 (CAC) ネットワークトポロジを表示するために使うことができます。指定した帯域幅に基づいて、音声通話またはビデオ通話を行います。</span><span class="sxs-lookup"><span data-stu-id="f0a90-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="f0a90-504">Skype for Business Server 2015 管理者は、Skype for business Server 2015 と共にインストールされている帯域幅ポリシーサービスによって適用される CAC ポリシーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="f0a90-505">説明</span><span class="sxs-lookup"><span data-stu-id="f0a90-505">Description</span></span>

<span data-ttu-id="f0a90-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) を使用すると、管理者は次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="f0a90-507">Skype for Business Server 2015 の展開からの CAC ネットワークトポロジの読み込みと表示は、グラフィカル形式で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="f0a90-508">帯域幅ポリシー サーバー ログ ファイルの CAC ネットワーク トポロジを読み込み、図の形式で表示する。</span><span class="sxs-lookup"><span data-stu-id="f0a90-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="f0a90-509">CAC ネットワーク トポロジを XML 形式でディスクに保存、格納する。</span><span class="sxs-lookup"><span data-stu-id="f0a90-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="f0a90-510">CAC ネットワーク トポロジ図を JPG または BMP 形式で保存、格納する。</span><span class="sxs-lookup"><span data-stu-id="f0a90-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="f0a90-511">CAC ネットワーク トポロジ構成データを表示する。</span><span class="sxs-lookup"><span data-stu-id="f0a90-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="f0a90-512">CAC ネットワーク トポロジをツリー形式で表示する。</span><span class="sxs-lookup"><span data-stu-id="f0a90-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="f0a90-513">CAC ネットワーク トポロジ リンク (サイトから地域、地域から地域、サイトからサイトの各リンクなど) のカスタム コネクタを定義する。</span><span class="sxs-lookup"><span data-stu-id="f0a90-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="f0a90-514">CAC ネットワーク トポロジのサイト情報、地域情報、プロビジョニングされた帯域幅ポリシーとネットワーク リンクを表示する。</span><span class="sxs-lookup"><span data-stu-id="f0a90-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="f0a90-515">用途</span><span class="sxs-lookup"><span data-stu-id="f0a90-515">Purpose</span></span>

<span data-ttu-id="f0a90-516">企業の CAC ネットワーク トポロジ リンクをグラフィカル インターフェイスで表示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="f0a90-517">例</span><span class="sxs-lookup"><span data-stu-id="f0a90-517">Examples</span></span>

 <span data-ttu-id="f0a90-518">Skype for business server **2015 の展開からの cac ネットワークトポロジの読み込みと表示グラフィカル形式で**の操作: skype for business server 2015 管理者は、次の方法で、任意の Skype For business server 2015 コンピューター上の cac ネットワークトポロジ構成を読み込み、表示することができます。次の図に示すように、[**ネットワーク構成のダウンロード**] オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="f0a90-519">このツールでは、Skype for Business Server 2015 構成ストアへの接続がないコンピューターに展開された場合に、このような構成をダウンロードまたは表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="f0a90-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![ネットワーク構成のダウンロード](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="f0a90-521">**帯域幅ポリシーサーバーログファイルからの CAC ネットワークトポロジを、グラフィカル形式で読み込み、表示します。** Skype for Business Server 2015 帯域幅ポリシーサーバーは、CAC ネットワークトポロジを、Skype for Business Server 2015 ファイル共有の場所にあるログメカニズムの一部として保存します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="f0a90-522">Skype for Business Server 2015 管理者は、次に示すように、 **[ネットワーク構成を開く**] オプションを使用して、このようなファイルをグラフィカルな形式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![帯域幅ポリシー サーバーのログ ファイルを開く](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="f0a90-524">CAC ネットワークトポロジを保存して、ディスク上の XML 形式で保存します。 Skype for Business Server 2015 管理者は、次のように [**ネットワーク構成のコピーを保存**] オプションを使用して、cac ネットワークトポロジ構成ファイルを xml 形式で保存することができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="f0a90-525">保存した構成ファイルはオフラインでのグラフィカルな表示に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![ネットワーク構成の XML ファイルとしての保存](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="f0a90-527">CAC ネットワークトポロジ図を JPG または BMP 形式で保存して保存します。 Skype for Business Server 2015 管理者は、次の**ようにネットワーク構成ダイアグラムを保存することで、cac ネットワークトポロジ構成をグラフィカルな形式 (JPG と bmp ファイル形式) で保存できます。** 次に示すように、[図] オプション。</span><span class="sxs-lookup"><span data-stu-id="f0a90-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![ネットワーク構成の画像としての保存](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="f0a90-529"><strong>CAC ネットワークトポロジ構成データを表示します。</strong>Skype for Business Server 2015 管理者は、表示される [ネットワーク構成データの表示] オプションを使用して、ネットワーク領域、ネットワークサイト、帯域幅プロファイル、サイトサブネットの IP アドレスなどの関連ネットワーク構成データをテキスト形式で表示できます。以下に。</span><span class="sxs-lookup"><span data-stu-id="f0a90-529"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![ネットワーク構成データの表示](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="f0a90-531">**ツリービュー形式で CAC ネットワークトポロジを表示します。** Skype for Business Server 2015 管理者は、次に示すように、ツールウィンドウの左側にあるコントロールパネルを使用して、関連するネットワーク構成データをグラフィカルツリービュースタイルで表示できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![ネットワーク構成データのツリー ビューでの表示](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="f0a90-533">**CAC ネットワークトポロジリンク (サイト間、地域間、サイト間リンクなど) 用のカスタムコネクタを定義します (例:** Skype for Business Server 2015 管理者は、次に示すように設定オプションを使用して、CAC ネットワーク構成の WAN リンク用のカスタムグラフィカルコネクタを定義できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="f0a90-534">これは、ネットワーク構成にプロビジョニングされている各種ネットワーク リンクを区別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![ツール](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="f0a90-536">**CAC ネットワークトポロジのサイト情報、地域情報、およびプロビジョニングされた帯域幅ポリシーを表示します。** Skype for Business Server 2015 管理者は、以下に示すオプションを使用して、関連する CAC ネットワークの地域情報、サイト情報、および CAC 帯域幅プロビジョニングの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="f0a90-537">(たとえば、ネットワーク領域またはネットワークサイトオブジェクトの [**情報**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="f0a90-537">(For example, click **Info** in a network region or network site object.)</span></span>

![ネットワークのカスタム コネクタの定義](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="f0a90-539">概要</span><span class="sxs-lookup"><span data-stu-id="f0a90-539">Summary</span></span>

<span data-ttu-id="f0a90-540">このツールは、Skype for Business Server 2015 管理者が、グラフィック形式で展開するための CAC ネットワークトポロジを表示するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="f0a90-541">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="f0a90-541">Response Group Agent Live</span></span>
<span data-ttu-id="f0a90-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="f0a90-542"></span></span>

<span data-ttu-id="f0a90-543">応答グループ アプリケーションによって、エージェントは組み込みの Web サービスを使用してリアルタイムの有効な情報にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="f0a90-544">ただし、このデータのグラフィカル表示はアプリケーションの外部では使用できません。</span><span class="sxs-lookup"><span data-stu-id="f0a90-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="f0a90-545">応答グループエージェントのライブリソースキットツールは、この情報に簡単かつグラフィカルな方法でアクセスすることでこの問題を解決します。この問題は、他のエージェントの存在など、リアルタイムの Skype for Business 通信ソフトウェア情報を使用することで強化されています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="f0a90-546">説明</span><span class="sxs-lookup"><span data-stu-id="f0a90-546">Description</span></span>

<span data-ttu-id="f0a90-547">Response Group Agent Live は、サインインやサインアウト機能、リアルタイム情報 (グループのメンバーシップや現在の通話数など) を応答グループ エージェントに提供する Windows アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="f0a90-548">これは、[エージェントグループ] ページの拡張バージョン (Skype for Business からアクセス可能) であることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="f0a90-549">用途</span><span class="sxs-lookup"><span data-stu-id="f0a90-549">Purpose</span></span>

<span data-ttu-id="f0a90-p161">着信通話は応答グループ アプリケーションによってキューに配置されてから、エージェント グループにルーティングされます。どの通話を処理するかについて十分な情報に基づいて判断するために、エージェントは他のエージェントの状態や各キューで待機中の通話数など、エージェント グループに関するリアルタイム情報にアクセスできます。このような情報は、当初は応答グループ サービスからのみアクセスが可能でしたが、Response Group Agent Live によって直感的な方法で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p161">The Response Group application queues incoming calls, and then routes them to agent groups. To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue. This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="f0a90-553">機能</span><span class="sxs-lookup"><span data-stu-id="f0a90-553">Features</span></span>

<span data-ttu-id="f0a90-554">応答グループエージェントのライブツールは、応答グループサービスと Skype for Business Server 2015 SDK 上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="f0a90-555">このツールは応答グループ サービスから利用できる情報や機能 (グループのメンバーシップ、他のエージェントのプレゼンス、待機中の通話数など) を応答グループ エージェントに提供します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="f0a90-556">下の図は、Response Group Agent Live のメイン インターフェイスを示しています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![Response Group Agent Live ツール](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="f0a90-558">Response Group Agent Live では、エージェントは次の主な 3 つの機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="f0a90-559">**サインイン/チェックアウト:**[エージェントグループ] ページ (Skype for Business Server 2015 からアクセス可能) とは異なり、応答グループエージェントの Live では、エージェントのみが一度にサインインまたはサインアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="f0a90-560">このアプリケーションでは、次の3つの簡単な方法でエージェントにサインインまたはサインアウトできます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="f0a90-561">アプリケーション内でサインイン/サインアウト (緑色と赤色) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="f0a90-562">システム トレイ アイコンを右クリックし、サインインまたはサインアウトを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="f0a90-563">構成可能なキーボード ショートカットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="f0a90-564">**グループメンバーシップ:**[エージェント] グループが選択されている場合、[応答グループエージェント Live] は、右側のウィンドウにこのグループのエージェントの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="f0a90-565">Skype for Business Server 2015 がこのアプリケーションと同じコンピューターで実行されている場合、プレゼンス情報と連絡先カードが応答グループエージェントの Live に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="f0a90-566">担当者は、そこから直接 IM を送信したり、他のエージェントに直接通話を発信したりできます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="f0a90-p165">**リアルタイム統計情報:** Response Group Agent Live ではすべてのエージェント グループのリアルタイム統計情報を使用できます。更新間隔は 1 分です。応答グループが通話に応答すると、グループ名の横に視覚的なインジケーターが追加され、キュー内の現在の通話数が表示されます。グループにマウスを合わせると、最長の待機時間も表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p165">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups. The update frequency is one minute. When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls. Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="f0a90-571">要件</span><span class="sxs-lookup"><span data-stu-id="f0a90-571">Requirements</span></span>

<span data-ttu-id="f0a90-572">Response Group Agent Live には .NET Framework 4.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="f0a90-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="f0a90-573">さらに、プレゼンスと連絡先カードの機能を活用するには、Skype for Business をローカルでインストールし (実行中) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="f0a90-574">構成</span><span class="sxs-lookup"><span data-stu-id="f0a90-574">Configuration</span></span>

<span data-ttu-id="f0a90-p167">アプリケーションの [Options] ダイアログ ボックスを使用すると、Response Group Agent Live を個人の好みに合わせてカスタマイズできます。また、管理者は RGAgentLive.exe.config ファイルの defaultHostAddress プロパティを直接編集して既定のホスト アドレスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p167">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application. In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="f0a90-p168">下の図は、エージェントがホスト アドレスやショートカット キーを構成できる [Options] ダイアログ ボックスを示しています。このダイアログを表示するには、メイン インターフェイスの右上にある [Options] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p168">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys. This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![[Response Group Agent Live Options] ダイアログ ボックス](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="f0a90-580">Response Group Agent Live の構成では次の 3 つの設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="f0a90-581">[Host address (ホストアドレス) (通常は、エージェントのホームプールに属している web プールの FQDN)。</span><span class="sxs-lookup"><span data-stu-id="f0a90-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="f0a90-582">この情報から、正確な応答グループ サービス アドレスがバックグラウンドで自動的に取得されます (ホストの後に適切なパスが付加されます)。</span><span class="sxs-lookup"><span data-stu-id="f0a90-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="f0a90-583">[Shortcuts]: サインイン/サインアウト用の厳密なショートカットをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="f0a90-584">唯一の制限は、両方のショートカットに "Windows ロゴ" キーが含まれている必要があります (これには、少なくとも別のキーを使用する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="f0a90-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="f0a90-585">[Start with Windows]: Windows と共に自動的に起動するようにアプリケーションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="f0a90-586">例</span><span class="sxs-lookup"><span data-stu-id="f0a90-586">Examples</span></span>

<span data-ttu-id="f0a90-587">下の図は、右側のウィンドウで連絡先を右クリックして、他のエージェントに電話をかけたり IM を送信したりする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![通話の発信または IM の送信](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="f0a90-589">下の図は、Response Group Agent Live に表示されるキュー内の現在の通話数と全着信通話内での最長待機時間を示しています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![キュー情報の表示](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="f0a90-591">概要</span><span class="sxs-lookup"><span data-stu-id="f0a90-591">Summary</span></span>

<span data-ttu-id="f0a90-592">迅速なサインインとサインアウト、グループのメンバーシップ、基本的なリアルタイム統計情報は、アプリケーション外部でのみ利用できる、応答グループ サービスに基づいた便利な応答グループ エージェント機能です。</span><span class="sxs-lookup"><span data-stu-id="f0a90-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="f0a90-593">応答グループエージェントのライブリソースキットツールを使って、Skype for Business Server 2015 管理者は、迅速かつグラフィカルな方法でタスクを実行できる Windows アプリケーションでエージェントを提供できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="f0a90-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="f0a90-594">SEFAUtil</span></span>
<span data-ttu-id="f0a90-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="f0a90-595"></span></span>

<span data-ttu-id="f0a90-596">SEFAUtil (セカンダリ拡張機能のアクティブ化) は、Skype for Business Server 2015 通信ソフトウェア管理者およびヘルプデスクエージェントによる代理人の呼び出し、着信の転送、同時呼び出しの構成を可能にするコマンドラインツールです。Skype for Business Server 2015 ユーザーの代わりに、チーム呼び出しの設定とグループの通話が集配されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="f0a90-597">このツールを使用すると、管理者は、特定のユーザーに対して公開されている通話ルーティング設定を照会することもできます。SEFAUtil ツールを使用すると、管理者は、ユーザーの代わりに着信の転送を有効または無効にしたり、変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="f0a90-598">管理者は、(SIP URI の形式で) ターゲットを指定するか、またはユーザーによって既に公開されているターゲットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="f0a90-599">このツールでは、管理者がユーザーに代わって代理人またはチーム呼び出しグループのメンバーを追加または削除することもできます。このツールは、Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 3.0 に基づいて構築されており、管理者が SEFAUtil の中央管理ストアで信頼されたアプリケーションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="f0a90-600">SEFAUtil (セカンダリ拡張機能のアクティブ化) を有効にすると、Skype for Business Server 2015 管理者およびヘルプデスクエージェントは、Skype の代わりに代理人の呼び出し、着信の転送、同時呼び出し、チーム呼び出しの設定、グループ通話のピックアップを構成することができます。Business Server 2015 ユーザーの場合。</span><span class="sxs-lookup"><span data-stu-id="f0a90-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="f0a90-601">また、管理者は特定のユーザー向けに公開されているコール ルーティング設定のクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="f0a90-602">説明</span><span class="sxs-lookup"><span data-stu-id="f0a90-602">Description</span></span>

<span data-ttu-id="f0a90-603">SEFAUtil の現在のバージョンは、コマンドラインツールにすぎません。グラフィカルユーザーインターフェイスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f0a90-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="f0a90-604">このツールは、Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 3.0 に基づいています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="f0a90-605">このツールの機能により、管理者やヘルプデスクの担当者は次の作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="f0a90-606">ユーザーのすべてのコール ルーティング設定を表示する (着信転送、代理人、同時呼び出し、チーム呼び出し、グループ通話ピックアップなど)</span><span class="sxs-lookup"><span data-stu-id="f0a90-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="f0a90-607">着信転送設定を有効化、無効化、変更する (宛先や無応答タイマーなど)</span><span class="sxs-lookup"><span data-stu-id="f0a90-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="f0a90-608">着信転送の即時構成を有効化、無効化、変更する</span><span class="sxs-lookup"><span data-stu-id="f0a90-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="f0a90-609">代理人設定を有効化、無効化、変更する</span><span class="sxs-lookup"><span data-stu-id="f0a90-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="f0a90-610">チーム呼び出しグループ設定を有効化、無効化、変更する</span><span class="sxs-lookup"><span data-stu-id="f0a90-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="f0a90-611">Skype for Business Server 2015 SEFAUtil の新ツール</span><span class="sxs-lookup"><span data-stu-id="f0a90-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="f0a90-612">同時呼び出し設定を有効化、無効化、変更する (宛先など)</span><span class="sxs-lookup"><span data-stu-id="f0a90-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="f0a90-613">Skype for Business Server 2015 SEFAUtil の新ツール</span><span class="sxs-lookup"><span data-stu-id="f0a90-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="f0a90-614">グループ通話ピックアップ設定を有効化、無効化、変更する</span><span class="sxs-lookup"><span data-stu-id="f0a90-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="f0a90-615">Skype for Business Server 2015 SEFAUtil の新ツール</span><span class="sxs-lookup"><span data-stu-id="f0a90-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="f0a90-616">このツールの制約は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="f0a90-617">Skype for Business Server プールに所属しているユーザーのみがサポートされます</span><span class="sxs-lookup"><span data-stu-id="f0a90-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="f0a90-618">複数ユーザーのコール ルーティング設定の一括編集はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f0a90-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="f0a90-619">出力</span><span class="sxs-lookup"><span data-stu-id="f0a90-619">Output</span></span>

<span data-ttu-id="f0a90-p175">ツールの現在のバージョンでは、[コマンド プロンプト] ウィンドウでのみ結果が表示されます。詳しくは、このドキュメント後半の「例」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p175">The current version of this tool provides output only in the Command Prompt window. For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="f0a90-622">用途</span><span class="sxs-lookup"><span data-stu-id="f0a90-622">Purpose</span></span>

<span data-ttu-id="f0a90-623">このツールを使用するいくつかの主なシナリオを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="f0a90-624">Bob は役員で、Skype for Business Server テレフォニーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="f0a90-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="f0a90-625">彼の既存の PBX システムには代理人が設定されています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="f0a90-626">Skype for Business Server 2015 への移行の一部として、管理者は、Bob のルーティングを構成して、既存の委任構成を反映させることができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="f0a90-p177">西村さんは旅行中で、顧客からの重要な連絡を待っています。しかし、ホテル滞在中はコンピューターを使うことができません。彼女はヘルプデスクに電話して、勤務先電話番号にかかってきたすべての電話を携帯電話の番号に転送してもらうよう頼みました。ヘルプデスク担当者は、彼女のためにこのような構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p177">Alice is travelling and realizes that she is expecting an important call from one of her customers. However, she is in a hotel and has no access to a computer. She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number. The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="f0a90-631">Joe の勤務先の電話番号への通話は、勤務先の携帯電話のボイスメールに送られます。ただし、他のほとんどの場所で正常に動作しているように見えます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="f0a90-632">ヘルプデスクの技術者は、Joe のルーティング構成を表示して、Joe が自分の携帯電話に同時呼び出しを設定していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="f0a90-633">技術者は、自分のオフィスの携帯電話の範囲について Joe に質問し、自分のネットワークカバレージの品質が低いときに、通話が Joe の携帯電話のボイスメールに転送される原因と判断することができます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="f0a90-634">Mike は Contoso の新入社員で、新しいチームに参加して、メンバー全員がチーム呼び出し用に構成されています。 Skype for Business Server 2015 を有効にすると、管理者はチーム呼び出しグループ設定を設定して、すべての新しいチームメンバーを含めることができます。さらに、管理者は、チームのメンバー全員のチーム呼び出しグループメンバーとして Mike を追加します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="f0a90-635">Contoso の人事部門のカスタマー サービス プラクティスとは、すべての発信者に対して最初の電話から個人サービスを提供することです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="f0a90-636">部門のメンバー全員がお互いのすぐそばに座っているとすれば、チーム呼び出しで全員の電話が一斉に鳴るのはチームにとって非常に混乱のもとになります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="f0a90-637">Skype for Business Server 2015 管理者は、チームメンバーを中断することなく最良のサービスを提供するために、グループ通話のピックアップ機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="f0a90-638">管理者は部門の全員をピックアップ グループに追加して、ピックアップ グループ番号を伝えます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="f0a90-639">原田さんが席を外している場合は、彼女の電話が鳴っていることに気付いた松本さんが自分の席から電話に応答します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="f0a90-640">要件</span><span class="sxs-lookup"><span data-stu-id="f0a90-640">Requirements</span></span>

<span data-ttu-id="f0a90-p180">SEFAUtil ツールは信頼されたアプリケーション プールに属しているコンピューターでのみ実行できます。このコンピューターには UCMA 3.0 がインストールされている必要があります。ツールを実行するには、SEFAUtil アプリケーション ID を持つ新しい信頼されたアプリケーションをプール内に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p180">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool. UCMA 3.0 must be installed on that computer. To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="f0a90-644">SEFAUtil ツール用の新しい信頼されたアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="f0a90-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="f0a90-645">SEFAUTil ツールは信頼されたアプリケーション プールに属しているコンピューターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="f0a90-646">必要に応じて、新しい信頼できるアプリケーションプールとしてプールを追加するには、次のコマンドレットを実行して、Skype for Business Server 管理シェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="f0a90-647">SEFAUtil ツールを実行するコンピューターには UCMA 3.0 をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="f0a90-648">信頼されたアプリケーションを SEFAUtil ツールのトポロジ内に定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="f0a90-649">SEFAUtil を新しい信頼されたアプリケーションとして定義するには、Skype for Business Server 管理シェルを使用して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="f0a90-650">必要に応じて、別のポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-650">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f0a90-651">プール FQDN: SEFAUtil アプリケーションをホストするサーバーまたはプールの FQDN (通常は、Skype for Business フロントエンドサーバー > またはプール)。</span><span class="sxs-lookup"><span data-stu-id="f0a90-651">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="f0a90-652">プールレジストラー FQDN: このアプリケーションプールに関連付けられている Skype for Business フロントエンドサーバーまたはプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="f0a90-652">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="f0a90-653">プールサイト: このプールが所属しているサイトのサイト ID です。</span><span class="sxs-lookup"><span data-stu-id="f0a90-653">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="f0a90-654">トポロジの変更を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-654">The topology changes need to be enabled.</span></span> <span data-ttu-id="f0a90-655">トポロジの変更を有効にするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-655">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```
   Enable-CsToplogy
   ```

4. <span data-ttu-id="f0a90-656">必要に応じて、SEFAUtil ツールの実行に使用するサーバーに Skype for Business Server 2015 リソースキットツールをインストールします (サーバーは信頼されたアプリケーションプールの一部である必要があります)。</span><span class="sxs-lookup"><span data-stu-id="f0a90-656">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="f0a90-657">SEFAUtil が正しく実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-657">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="f0a90-658">そのためには、Windows コマンド プロンプトから管理者権限でツールを実行し、展開内のユーザーの着信転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-658">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="f0a90-659">既定では、ツールは "..\Program Files\Skype for Business Server 2015 \ Reskit" に保存されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-659">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="f0a90-660">ユーザーの着信転送設定を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-660">To display the call forwarding settings of a user, use the following command:</span></span>

   ```
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="f0a90-661">ユーザーの着信転送設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-661">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="f0a90-662">グループ通話ピックアップ</span><span class="sxs-lookup"><span data-stu-id="f0a90-662">Group Call Pickup</span></span>

<span data-ttu-id="f0a90-663">グループ通話のピックアップ機能を完全に有効にするには、Skype for Business Server 2015 で追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="f0a90-663">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="f0a90-664">ユーザーにピックアップ グループを割り当てる前に、この機能の計画と展開の手順について、グループ通話ピックアップの製品ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0a90-664">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="f0a90-665">例</span><span class="sxs-lookup"><span data-stu-id="f0a90-665">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="f0a90-666">現在の通話処理設定の表示</span><span class="sxs-lookup"><span data-stu-id="f0a90-666">Display Current Call Handling Settings</span></span>

<span data-ttu-id="f0a90-667">次のコマンドでは、ユーザーの通話処理が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-667">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="f0a90-668">この例では、 **/server**スイッチを使用して、接続先の Skype For business サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-668">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="f0a90-669">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-669">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="f0a90-670">着信転送/応答なしの宛先の設定</span><span class="sxs-lookup"><span data-stu-id="f0a90-670">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="f0a90-671">この例では、着信転送/応答なしの宛先と呼び出しの遅延を設定します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-671">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="f0a90-672">ここでは、/server スイッチは提供されません。SEFAUtil は、Skype for Business Server 2015 の自動検出を試みます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-672">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 <span data-ttu-id="f0a90-673">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-673">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="f0a90-674">着信転送の即時有効化</span><span class="sxs-lookup"><span data-stu-id="f0a90-674">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="f0a90-675">この例では、別のユーザーへの着信転送をすぐに有効にします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-675">This example immediately enables call-forwarding to another user.</span></span>

```
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="f0a90-676">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-676">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="f0a90-677">着信転送の即時無効化</span><span class="sxs-lookup"><span data-stu-id="f0a90-677">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="f0a90-678">この例では、別のユーザーへの着信転送をすぐに無効にします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-678">This example immediately disables call forwarding.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 <span data-ttu-id="f0a90-679">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-679">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="f0a90-680">代理人としてのユーザーの追加と代理人の同時呼び出しの設定</span><span class="sxs-lookup"><span data-stu-id="f0a90-680">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="f0a90-681">この例では、ユーザーを代理人として追加し、代理人の同時呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-681">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="f0a90-682">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-682">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="f0a90-683">代理人の同時呼び出しルールの変更</span><span class="sxs-lookup"><span data-stu-id="f0a90-683">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="f0a90-684">この例では、前の例で設定した代理人の同時呼び出しルールを遅延呼び出しルールに変更します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-684">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="f0a90-685">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-685">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="f0a90-686">代理人の削除</span><span class="sxs-lookup"><span data-stu-id="f0a90-686">Remove the Delegate</span></span>

<span data-ttu-id="f0a90-687">この例では代理人を削除します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-687">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="f0a90-688">最後の代理人が削除されると、代理人着信は自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-688">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="f0a90-689">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-689">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="f0a90-690">代理人の追加と代理人への着信転送ルールの設定</span><span class="sxs-lookup"><span data-stu-id="f0a90-690">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="f0a90-691">この例では、代理人を追加し、代理人への着信転送ルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-691">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="f0a90-692">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-692">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="f0a90-693">同時呼び出しの有効化と宛先番号の設定</span><span class="sxs-lookup"><span data-stu-id="f0a90-693">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="f0a90-694">この例では、同時呼び出しを有効にして、同時呼び出しの宛先番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-694">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="f0a90-695">既に同時呼び出しを有効にしているユーザーの同時呼び出しの宛先番号を変更するには、コマンドに /enablesimulring スイッチを追加します。追加しない場合、宛先番号は変更されません。</span><span class="sxs-lookup"><span data-stu-id="f0a90-695">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="f0a90-696">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-696">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="f0a90-697">同時呼び出しの無効化</span><span class="sxs-lookup"><span data-stu-id="f0a90-697">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="f0a90-698">この例では、同時呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-698">This example disables simultaneous ringing.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="f0a90-699">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-699">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="f0a90-700">チーム呼び出しのチーム メンバーの追加とチーム呼び出しメンバー グループへの同時呼び出しの設定</span><span class="sxs-lookup"><span data-stu-id="f0a90-700">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="f0a90-701">この例では、ユーザーのチーム呼び出しグループにチーム メンバーを追加し、チーム呼び出しグループへの同時呼び出しを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-701">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="f0a90-702">ユーザーのチーム呼び出しグループにチーム メンバーを追加すると、ユーザーの同時呼び出しの設定がチーム呼び出しグループを同時に呼び出すように自動的に切り替わります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-702">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="f0a90-703">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-703">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="f0a90-704">チーム呼び出しグループからのメンバーの削除</span><span class="sxs-lookup"><span data-stu-id="f0a90-704">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="f0a90-705">この例では、ユーザーのチーム呼び出しグループからチーム メンバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-705">This example removes a team member of the team-call group of a user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="f0a90-706">削除対象のメンバーがチーム呼び出しグループで唯一のメンバーである場合、チーム呼び出しグループの同時呼び出しは自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-706">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="f0a90-707">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-707">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="f0a90-708">チーム呼び出しグループの遅延呼び出しの設定</span><span class="sxs-lookup"><span data-stu-id="f0a90-708">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="f0a90-709">この例では、チーム呼び出しグループの時間設定の遅延呼び出しを変更します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-709">This example changes the delayed ring to the team-call group time setting.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="f0a90-710">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-710">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="f0a90-711">チーム呼び出しの有効化</span><span class="sxs-lookup"><span data-stu-id="f0a90-711">Enable Team-Call</span></span>

<span data-ttu-id="f0a90-712">この例では、ユーザーのチーム呼び出しを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-712">This example enables team-call for a given user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="f0a90-713">ユーザーのチーム呼び出しグループにメンバーがいない場合、チーム呼び出しは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="f0a90-713">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="f0a90-714">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-714">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="f0a90-715">チーム呼び出しの無効化</span><span class="sxs-lookup"><span data-stu-id="f0a90-715">Disable Team-Call</span></span>

<span data-ttu-id="f0a90-716">この例では、ユーザーのチーム呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-716">This example disables team-call for a given user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="f0a90-717">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-717">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="f0a90-718">グループ通話ピックアップの有効化とユーザーへのピックアップ グループの割り当て</span><span class="sxs-lookup"><span data-stu-id="f0a90-718">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="f0a90-719">この例では、ユーザーにピックアップ グループを割り当て、グループ通話ピックアップを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-719">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="f0a90-720">**出力**</span><span class="sxs-lookup"><span data-stu-id="f0a90-720">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="f0a90-721">グループ通話ピックアップの無効化</span><span class="sxs-lookup"><span data-stu-id="f0a90-721">Disable Group Call Pickup</span></span>

<span data-ttu-id="f0a90-722">この例では、特定のユーザーのグループ通話ピックアップを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-722">This example disables Group Call Pickup for a given user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="f0a90-p188">ユーザーのグループ通話ピックアップを無効にした場合、ユーザーに割り当てられたグループ番号は保持されません。そのユーザーのグループ通話ピックアップを後からもう一度有効にする場合は、/enablegrouppickup スイッチでグループ番号をもう一度割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p188">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained. If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="f0a90-725">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="f0a90-725">SYSPrep.ps1</span></span>
<span data-ttu-id="f0a90-726"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="f0a90-726"></span></span>

### <a name="description"></a><span data-ttu-id="f0a90-727">説明</span><span class="sxs-lookup"><span data-stu-id="f0a90-727">Description</span></span>

<span data-ttu-id="f0a90-728">Sysprep.inf は、Windows Server 2008 オペレーティングシステムコンピューターに次の Skype for Business Server 2015 の前提条件をインストールする Windows PowerShell スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-728">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="f0a90-729">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="f0a90-729">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="f0a90-730">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="f0a90-730">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="f0a90-731">Windows Powershell バージョン 3.0</span><span class="sxs-lookup"><span data-stu-id="f0a90-731">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="f0a90-732">Visual C++ 2010 再頒布可能パッケージ</span><span class="sxs-lookup"><span data-stu-id="f0a90-732">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="f0a90-733">Internet Information Server の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="f0a90-733">Internet Information Server Updates</span></span>

- <span data-ttu-id="f0a90-734">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="f0a90-734">Windows Identity Foundation</span></span>

- <span data-ttu-id="f0a90-735">Skype for Business Server 2015 コアファイル</span><span class="sxs-lookup"><span data-stu-id="f0a90-735">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="f0a90-736">このスクリプトは Microsoft Windows オペレーティング システム用のシステム準備ツールと名前は似ていますが、別のツールです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-736">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="f0a90-737">このスクリプトでは、Skype for Business Server 2015 に必要な前提条件のみをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-737">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="f0a90-738">これらの必須コンポーネントをインストールしたら、Windows SYSPrep ツールを使用して、サーバーのイメージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-738">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="f0a90-739">要件</span><span class="sxs-lookup"><span data-stu-id="f0a90-739">Requirements</span></span>

<span data-ttu-id="f0a90-740">Sysprep.inf スクリプトを実行する前に、必須ファイルを Windows Server 2008 オペレーティングシステムコンピューター上のローカルフォルダー ( **D:\Setup など)** にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-740">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="f0a90-741">このフォルダーには、特定の**setup.exe**のように、Skype For business Server 2015 ファイルのコピーも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-741">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="f0a90-742">必須ファイルは、次の場所からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-742">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="f0a90-743">**必須コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="f0a90-743">**Prerequisite**</span></span>                                | <span data-ttu-id="f0a90-744">**場所**</span><span class="sxs-lookup"><span data-stu-id="f0a90-744">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="f0a90-745">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="f0a90-745">Microsoft .Net Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="f0a90-746">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="f0a90-746">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/en-us/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="f0a90-747">Windows Powershell バージョン 3.0</span><span class="sxs-lookup"><span data-stu-id="f0a90-747">Windows Powershell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/en-us/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="f0a90-748">Visual C++ 2010 再頒布可能パッケージ</span><span class="sxs-lookup"><span data-stu-id="f0a90-748">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/en-us/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="f0a90-749">Internet Information Server の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="f0a90-749">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/en-us/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="f0a90-750">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="f0a90-750">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/en-us/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="f0a90-751">Skype for Business Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="f0a90-751">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="f0a90-752">Skype for Business Server 2015 メディアからのコピー</span><span class="sxs-lookup"><span data-stu-id="f0a90-752">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="f0a90-753">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f0a90-753">Parameter</span></span>

<span data-ttu-id="f0a90-754">**-Setupfolder**パラメーターは、必須ファイルのディレクトリの場所を引数として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-754">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="f0a90-755">例</span><span class="sxs-lookup"><span data-stu-id="f0a90-755">Examples</span></span>

<span data-ttu-id="f0a90-756">Sysprep.inf スクリプトを実行して、Skype for Business Server 2015 の前提条件をインストールするには、管理者特権のコマンドプロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-756">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="f0a90-757">Unassigned Number Announcements Migration</span><span class="sxs-lookup"><span data-stu-id="f0a90-757">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="f0a90-758"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="f0a90-758"></span></span>

<span data-ttu-id="f0a90-759">未割り当て番号のお知らせ移行ツールを使用すると、Skype for Business Server 2015 管理者は、アナウンスメントアプリケーションによって提供されている、割り当てられていない番号の設定をソース Skype for Business サーバーまたはプールから a に移動することができます。接続先の Skype for Business サーバーまたはプール。</span><span class="sxs-lookup"><span data-stu-id="f0a90-759">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="f0a90-760">説明</span><span class="sxs-lookup"><span data-stu-id="f0a90-760">Description</span></span>

<span data-ttu-id="f0a90-761">Unassigned Number Announcements Migration ツールは Windows PowerShell スクリプトであり、アナウンス アプリケーションによるサービスを受けている未使用の番号の構成を移行元のサーバーまたはプールから別のサーバーまたはプールに移行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-761">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="f0a90-762">Unassigned Number Announcements Migration スクリプトを実行すると、次の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-762">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="f0a90-763">移行元のサーバーまたはプールでホストされているアナウンス アプリケーションの未使用の番号のアナウンスが使用しているすべての音声ファイルを、移行先のサーバーまたはプールのファイル ストアに移行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-763">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f0a90-764">オーディオファイルは、移行先のプールにコピーされると、ソースプールから削除されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-764">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="f0a90-765">移行元のサーバーまたはプールでホストされているアナウンス アプリケーションに構成されているすべての未使用の番号のアナウンスを、移行先のサーバーまたはプールに移行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-765">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="f0a90-766">移行元のサーバーまたはプールでホストされているアナウンス アプリケーションによるサービスを受けているすべての未使用の番号の範囲を、移行先のサーバーまたはプールにもう一度割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-766">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="f0a90-767">スクリプトの実行が成功すると、移行元のサーバーまたはプールでホストされているアナウンス アプリケーションによるサービスを受けていたすべての未使用の番号の範囲が、同じ構成を使用して移行先のサーバーまたはプールによるサービスを受けるようになります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-767">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="f0a90-768">出力</span><span class="sxs-lookup"><span data-stu-id="f0a90-768">Output</span></span>

<span data-ttu-id="f0a90-769">**ムーブグループの移動 Ementconfiguration**スクリプトは、Skype For Business Server 管理シェルウィンドウで、移行操作の成功または失敗を実行した場所を示します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-769">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="f0a90-p191">エラーによって操作の実行が中断した場合、移行に成功した未使用の番号の範囲は稼動状態で移行先に残り、移行する予定の残りの未使用の番号の範囲も稼動状態で移行元に残ります。残りの構成を完全に移行するには、エラーを修正してからもう一度スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p191">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form. To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="f0a90-772">用途</span><span class="sxs-lookup"><span data-stu-id="f0a90-772">Purpose</span></span>

<span data-ttu-id="f0a90-773">Unassigned Number Announcements Migration スクリプトは、次の 3 つのシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-773">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="f0a90-774">**新しいバージョンの Skype For Business Server に構成設定を移行する:** Contoso は、Skype for Business Server 2015 への移行プロセス中で、移行プロセスの一環として、Skype for Business Server の管理者が、Lync からのアナウンスメントアプリケーションによって提供されている割り当てられていない番号の設定を移動することを希望しています。新しい Skype for Business Server 2015 の展開へのサーバー2013の展開。</span><span class="sxs-lookup"><span data-stu-id="f0a90-774">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="f0a90-775">設定を移動するには、Skype for Business Server の管理者は、割り当てられていない番号のお知らせ移行ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-775">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="f0a90-776">**Skype For Business server 2015 から Lync server 2013 に展開をロールバックする:** 予期しない問題が発生したため、Contoso は移行をロールバックして、新しい Skype for Business Server 2015 の展開に移行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-776">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="f0a90-777">サービスの中断を最小限に抑えるため、Skype for Business Server の管理者は、割り当てられていない番号のお知らせ移行ツールを使用して、Skype for Business Server 2015 の展開から Lync Server 2013 の展開に構成をロールバックします。</span><span class="sxs-lookup"><span data-stu-id="f0a90-777">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="f0a90-778">**展開間でのデータの移動:** Contoso は、1つのプールのすべてのサーバーを新しいサーバーに置き換えるプロセスを進めています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-778">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="f0a90-779">この戦略は、新しい Skype for Business Server 2015 プールを展開して、古いプールから新しいプールにすべてのデータを移動し、古いプールを廃止することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-779">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="f0a90-780">新しいプールを展開した後は、Unassigned Number Announcements Migration ツールを使用して、古いプールから新しいプールに構成を移行します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-780">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="f0a90-781">要件</span><span class="sxs-lookup"><span data-stu-id="f0a90-781">Requirements</span></span>

<span data-ttu-id="f0a90-782">ツールの正常な実行に必要な主な要件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f0a90-782">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="f0a90-783">このスクリプトは、Skype for Business Server 管理シェルがインストールされているコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-783">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="f0a90-784">お知らせアプリケーションは、移行元と移行先の Skype for Business サーバーまたはプールに正常に展開される必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-784">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="f0a90-785">Move-CsAnnouncementConfiguration スクリプト</span><span class="sxs-lookup"><span data-stu-id="f0a90-785">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="f0a90-786">Move-CsAnnouncementConfiguration スクリプトでは、下の表に示す 2 つのパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="f0a90-786">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Move-CsAnnouncementConfiguration のパラメーター](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="f0a90-788">例</span><span class="sxs-lookup"><span data-stu-id="f0a90-788">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="f0a90-789">割り当てられていない番号のお知らせの構成を Lync Server 2013 プールから Skype for Business Server 2015 プールに移動する</span><span class="sxs-lookup"><span data-stu-id="f0a90-789">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="f0a90-790">この例では、割り当てられていない番号のアナウンスをソースプール (Lync Server 2013) から移行先プール (Skype for Business Server 2015) に移動します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-790">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="f0a90-791">割り当てられていない番号のお知らせの構成を Skype for Business Server 2015 プールから Lync Server 2013 プールに移動する</span><span class="sxs-lookup"><span data-stu-id="f0a90-791">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="f0a90-792">この例では、ソースプール (Skype for Business Server 2015) から割り当てられていない番号のアナウンスを移行先のプール (Lync Server 2013) に移動します。</span><span class="sxs-lookup"><span data-stu-id="f0a90-792">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="f0a90-793">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="f0a90-793">Web Conf Data</span></span>
<span data-ttu-id="f0a90-794"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="f0a90-794"></span></span>

<span data-ttu-id="f0a90-795">Web Conf データツールを使用すると、Skype for Business Server 2015 通信ソフトウェアの管理者は開催者の Web 会議に関連付けられたデータをより詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-795">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="f0a90-796">シナリオには、タイムスタンプ条件に基づいて特定のユーザーの会議データを削除する機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-796">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="f0a90-797">説明</span><span class="sxs-lookup"><span data-stu-id="f0a90-797">Description</span></span>

<span data-ttu-id="f0a90-798">このツールを使用すると、管理者は次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-798">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="f0a90-799">1 人のユーザーに関連付けられているすべての Web 会議データを検索する。</span><span class="sxs-lookup"><span data-stu-id="f0a90-799">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="f0a90-800">1 人のユーザーに関連付けられているすべての Web 会議データを削除する。</span><span class="sxs-lookup"><span data-stu-id="f0a90-800">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="f0a90-801">特定の日付よりも古い、1 人のユーザーに関連付けられているすべての Web 会議データを削除する。</span><span class="sxs-lookup"><span data-stu-id="f0a90-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="f0a90-802">ユーザーがあるプールから別のプールに移行した場合に、その 1 人のユーザーに関連付けられているすべての Web 会議データを移行する。</span><span class="sxs-lookup"><span data-stu-id="f0a90-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

> [!NOTE]
> <span data-ttu-id="f0a90-803">Lync Server 2010 用のリソースキットツールでは、1人のユーザーに関連付けられたすべての Web 会議データを別のプールに移動することができました。</span><span class="sxs-lookup"><span data-stu-id="f0a90-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="f0a90-804">このツールでは **MoveConferenceData** パラメーターのほうを優先して、この機能は現在廃止されています。</span><span class="sxs-lookup"><span data-stu-id="f0a90-804">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="f0a90-805">このパラメーターの詳細については、「[移動-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps)コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0a90-805">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="f0a90-p197">このツールでは、非アクティブな会議の会議データのみが削除されます。アクティブな会議 (開催中の会議) は削除できません。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p197">The tool deletes meeting data only for meetings that are inactive. Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="f0a90-p198">このツールはターゲット ユーザーと同じプール内にあるコンピューターから実行する必要があります。会議コンテンツ データをこのツールで管理しているユーザーは同じユーザー プールに所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p198">This tool must be run from a computer that is in the same pool as the target user. The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="f0a90-810">出力</span><span class="sxs-lookup"><span data-stu-id="f0a90-810">Output</span></span>

<span data-ttu-id="f0a90-811">このツールでは、次の各操作の結果が出力されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-811">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="f0a90-812">クエリを実行した場合は、該当のユーザーを開催者とする、すべての非アクティブな会議のデータ フォルダーの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="f0a90-813">削除を実行した場合は、削除対象のデータがあるすべての会議データ フォルダーの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="f0a90-814">要件</span><span class="sxs-lookup"><span data-stu-id="f0a90-814">Requirements</span></span>

<span data-ttu-id="f0a90-815">このツールは、開催者が現在所属しているのと同じプール内で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="f0a90-816">このツールは、コンテンツ ファイル ストアへのアクセス権を持つ管理者特権を使用して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="f0a90-817">例</span><span class="sxs-lookup"><span data-stu-id="f0a90-817">Examples</span></span>

<span data-ttu-id="f0a90-818">下の表にパラメーターを示します (一部は例で使用されています)。</span><span class="sxs-lookup"><span data-stu-id="f0a90-818">The following table describes the parameters, some of which are used in the examples.</span></span>

![Web Conf Data ツールのパラメーター](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="f0a90-p199">上の例は query コマンドの動作を示しています。このコマンドの出力は、ツールの影響を受けるすべての会議コンテンツ フォルダーの一覧になります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p199">The preceding example shows how a query command would work. The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="f0a90-p200">上の例は delete コマンドの動作を示しています。delete コマンドにより、このユーザーのすべての非アクティブな会議フォルダーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="f0a90-p200">The preceding is an example of a delete command. The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="f0a90-824">概要</span><span class="sxs-lookup"><span data-stu-id="f0a90-824">Summary</span></span>

<span data-ttu-id="f0a90-825">このツールは、会議データをより正確に制御する必要のある管理者にとって役立つツールとなります。</span><span class="sxs-lookup"><span data-stu-id="f0a90-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>


