---
title: Skype for Business Server 2015 リソース キット ツールのドキュメント
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: このトピックでは、Skype for Business Server 2015 リソース キットのツールについて説明します。各ツールの目的とその使用例を含む。 Skype for Business Server 2015 リソース キットは、Skype for Business Server 2015 を展開および管理する IT 管理者が日常的なタスクを容易にするのに役立ちます。 たとえば、Web Conf Data ツールを使用して、オンライン会議中にユーザーがアップロードしたデータを簡単に制御できます。 SEFAUtil ツールを使用して、ユーザーの代理通話の転送と応答を設定できます。 IT 管理者は、これらのツールを使用して Skype for Business Server 2015 のより効果的な管理を行います。
ms.openlocfilehash: c09aa7c21e90a1783c0819a0877ecb87ff250d16
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114083"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="df9b0-107">Skype for Business Server 2015 リソース キット ツールのドキュメント</span><span class="sxs-lookup"><span data-stu-id="df9b0-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="df9b0-108">このトピックでは、Skype for Business Server 2015 リソース キットのツールについて説明します。各ツールの目的とその使用例を含む。</span><span class="sxs-lookup"><span data-stu-id="df9b0-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="df9b0-109">Skype for Business Server 2015 リソース キットは、Skype for Business Server 2015 を展開および管理する IT 管理者が日常的なタスクを容易にするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="df9b0-110">たとえば **、Web Conf Data ツール** を使用して、オンライン会議中にユーザーがアップロードしたデータを簡単に制御できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="df9b0-111">**SEFAUtil ツールを** 使用して、ユーザーの代理通話の転送と応答を設定できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="df9b0-112">IT 管理者は、これらのツールを使用して Skype for Business Server 2015 のより効果的な管理を行います。</span><span class="sxs-lookup"><span data-stu-id="df9b0-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="df9b0-113">リソース キット ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="df9b0-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="df9b0-114">Skype for Business Server 2015 リソース キットをインストールするには、ダウンロード [ センター ](https://www.microsoft.com/download/details.aspx?id=52631)OCSReskit.msiをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="df9b0-115">簡単 **OCSResKit.msi** を実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="df9b0-116">.msi は **、%Program Files%\Skype for Business Server 2015\ResKit** のすべてのツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="df9b0-117">自己格納型の実行可能ファイルであるツールは、このフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="df9b0-118">サポート ファイルも含むツールは、独自のサブフォルダーに含まれています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="df9b0-119">サポートされている環境</span><span class="sxs-lookup"><span data-stu-id="df9b0-119">Supported Environments</span></span>

<span data-ttu-id="df9b0-120">Skype for Business Server 2015 リソース キットは、Skype for Business Server 2015 に必要な仕様を満たすサーバー (通常は Skype for Business Server 2015 の実行に使用される) にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="df9b0-121">リソース キット ツールの概要</span><span class="sxs-lookup"><span data-stu-id="df9b0-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="df9b0-122">Skype for Business Server 2015 リソース キットで提供されるツールの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="df9b0-123">要件と使用例を含む各ツールの説明については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="df9b0-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="df9b0-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="df9b0-125">帯域幅ポリシー サービス モニター</span><span class="sxs-lookup"><span data-stu-id="df9b0-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="df9b0-126">帯域幅使用率アナライザー</span><span class="sxs-lookup"><span data-stu-id="df9b0-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="df9b0-127">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="df9b0-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="df9b0-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="df9b0-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="df9b0-129">ストレージ サービス データのインポート</span><span class="sxs-lookup"><span data-stu-id="df9b0-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="df9b0-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="df9b0-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="df9b0-131">ユーザー コンソールの参照</span><span class="sxs-lookup"><span data-stu-id="df9b0-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="df9b0-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="df9b0-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="df9b0-133">ネットワーク構成ビューアー</span><span class="sxs-lookup"><span data-stu-id="df9b0-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="df9b0-134">応答グループ エージェント Live</span><span class="sxs-lookup"><span data-stu-id="df9b0-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="df9b0-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="df9b0-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="df9b0-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="df9b0-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="df9b0-137">割り当てられていない番号のお知らせの移行</span><span class="sxs-lookup"><span data-stu-id="df9b0-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="df9b0-138">Web Conf データ</span><span class="sxs-lookup"><span data-stu-id="df9b0-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="df9b0-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="df9b0-139">ABSConfig</span></span>
<span data-ttu-id="df9b0-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="df9b0-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="df9b0-141">アドレス帳サービス構成ツール (ABSConfig) は、管理者が Skype for Business Server 2015 のアドレス帳サービス構成をカスタマイズするのに役立つ管理ツールです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="df9b0-142">また、このツールを使用すると、Skype for Business Server 2015 管理者は既定のアドレス帳サービス設定を復元できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="df9b0-143">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-143">Description</span></span>

<span data-ttu-id="df9b0-144">ABSConfig は、管理者がアドレス帳サービスに関連する Active Directory ドメイン サービス属性を構成できるグラフィカル ユーザー インターフェイス アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="df9b0-145">ツールの主なシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="df9b0-146">管理者が Active Directory ドメイン サービスの属性を Skype for Business Server 2015 の属性にマップできる。</span><span class="sxs-lookup"><span data-stu-id="df9b0-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="df9b0-147">管理者が、アドレス帳サービス ファイルに含めるか除外する Active Directory ドメイン サービス属性を指定できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="df9b0-148">管理者が既定のアドレス帳サービス設定を復元するには。</span><span class="sxs-lookup"><span data-stu-id="df9b0-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="df9b0-149">ABSConfig ツールは、このファイルを使用してABSConfig.exeできます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="df9b0-150">ツールが開き、[属性の構成 **] タブが開** きます。この表には、Active Directory ドメイン サービス属性を Skype for Business Server 2015 の属性フィールドにマップし、特定の属性フィルターに基づいてアドレス帳サービス ファイルに含めるか除外するユーザーを指定するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="df9b0-151">また、アドレス帳ファイルに含める電話番号の値をカスタマイズするオプションも用意されています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="df9b0-152">[ **既定値の復元]** オプションを使用すると、管理者はアドレス帳サービスの設定を既定値に復元できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="df9b0-153">異なる OC フィールドAD属性の再マッピングは、アドレス帳ファイルのダウンロードでのみ機能し、アドレス帳 Web クエリではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="df9b0-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="df9b0-154">出力</span><span class="sxs-lookup"><span data-stu-id="df9b0-154">Output</span></span>

<span data-ttu-id="df9b0-155">ABSConfig は、アドレス帳サービス構成をデータベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="df9b0-156">用途</span><span class="sxs-lookup"><span data-stu-id="df9b0-156">Purpose</span></span>

<span data-ttu-id="df9b0-157">ABSConfig は、Skype for Business Server 2015 アドレス帳サービスを迅速かつ簡単にカスタマイズする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="df9b0-158">要件</span><span class="sxs-lookup"><span data-stu-id="df9b0-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="df9b0-159">コンピューター</span><span class="sxs-lookup"><span data-stu-id="df9b0-159">Computer</span></span>

<span data-ttu-id="df9b0-160">ABSConfig は、Skype for Business Server 2015 がインストールされているドメインに参加しているコンピューターからのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="df9b0-161">Skype for Business Server 2015 Enterprise Edition の場合、このツールは、セットアップ中にアドレス帳サービスが有効になっているフロントエンド サーバーで実行できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="df9b0-162">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="df9b0-162">Network</span></span>

<span data-ttu-id="df9b0-163">コンピューターがフロントエンド プールとバック エンド データベースに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="df9b0-164">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="df9b0-164">Software</span></span>

<span data-ttu-id="df9b0-165">ABSConfig ツールを実行する前に、次のソフトウェア コンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="df9b0-166">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="df9b0-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="df9b0-167">ユーザー</span><span class="sxs-lookup"><span data-stu-id="df9b0-167">Users</span></span>

<span data-ttu-id="df9b0-168">Skype for Business Server 2015 展開を更新するために必要なアクセス許可を持つ管理者。</span><span class="sxs-lookup"><span data-stu-id="df9b0-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="df9b0-169">例</span><span class="sxs-lookup"><span data-stu-id="df9b0-169">Examples</span></span>

<span data-ttu-id="df9b0-170">ABSConfig は、コマンド **プロンプトにABSConfig.exe** 入力して開始できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="df9b0-171">以下に、ABSConfig ツールのユーザー インターフェイスを示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-171">Shown below is the ABSConfig tool user interface.</span></span>

![[ABSConfig.exe] ツール。](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="df9b0-173">概要</span><span class="sxs-lookup"><span data-stu-id="df9b0-173">Summary</span></span>

<span data-ttu-id="df9b0-174">ABSConfig ツールは、管理者が Skype for Business Server 2015 アドレス帳サービスをカスタマイズするための迅速かつ簡単なツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="df9b0-175">帯域幅ポリシー サービス モニター</span><span class="sxs-lookup"><span data-stu-id="df9b0-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="df9b0-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="df9b0-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="df9b0-177">帯域幅ポリシー サービス モニター ツールは、管理者が次のリストを表示することを目的とします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="df9b0-178">トポロジで構成されている Skype for Business Server 2015 帯域幅ポリシー サービス (認証とコア)</span><span class="sxs-lookup"><span data-stu-id="df9b0-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="df9b0-179">各サービスが他の帯域幅ポリシー サービスおよびエッジ サーバーに対して行う接続</span><span class="sxs-lookup"><span data-stu-id="df9b0-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="df9b0-180">ネットワーク構成ドキュメントで構成されているすべてのリンクと、各帯域幅ポリシー サービスによって報告されるリアルタイム帯域幅の使用状況</span><span class="sxs-lookup"><span data-stu-id="df9b0-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="df9b0-181">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-181">Description</span></span>

<span data-ttu-id="df9b0-182">帯域幅ポリシー サービス モニター ツールは、GUI ベースのアプリケーションとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="df9b0-183">管理者は、ツールを起動するには、次のPDPMonUI.exe。</span><span class="sxs-lookup"><span data-stu-id="df9b0-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="df9b0-184">ツールが起動すると、トポロジ内の帯域幅ポリシー サービスの一覧を検出します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="df9b0-185">最初の更新が完了すると、ウィンドウの左側のウィンドウに、所属するクラスターによってグループ化されたサービスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="df9b0-186">管理者が特定の帯域幅ポリシー サービスを選択すると、右側のウィンドウに、その特定のサービスに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="df9b0-187">このウィンドウには、情報を表示する 2 つのメイン タブがあります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="df9b0-188">[コンピューター情報] タブ</span><span class="sxs-lookup"><span data-stu-id="df9b0-188">Machine Info Tab</span></span>

<span data-ttu-id="df9b0-189">[ **コンピューター情報]** タブには、選択した帯域幅ポリシー サービスの詳細と、選択した帯域幅ポリシー サービスによって他のサービスに対して行われたすべての接続の一覧と状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="df9b0-190">[トポロジ情報] タブ</span><span class="sxs-lookup"><span data-stu-id="df9b0-190">Topology Info Tab</span></span>

<span data-ttu-id="df9b0-191">[ **トポロジ情報] タブ** には、ネットワーク構成設定で構成されているすべてのリンクの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="df9b0-192">各リンクについて、オーディオとビデオの帯域幅容量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="df9b0-193">さらに、現在使用されている帯域幅は、Kbps と容量の割合の両方で表示されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="df9b0-194">このツールでは、色分けを使用して、容量に近い使用率を持つリンクを強調表示します。これにより、管理者はそのようなリンクをすばやく分離できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="df9b0-195">帯域幅ポリシー サービス モニター ツールが構成済みの帯域幅ポリシー サービスに接続するときにエラーが発生した場合、[コンピューター **情報**]タブと [トポロジ情報] タブの情報は入力されません。</span><span class="sxs-lookup"><span data-stu-id="df9b0-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="df9b0-196">ただし、ツールが最初に接続した後、サービスへの接続が失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="df9b0-197">このような場合、管理者に古い情報が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="df9b0-198">各タブ **には、特定** の帯域幅ポリシー サービスのデータが最後に更新された時刻を管理者が確認できる最終更新タイムスタンプがあります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="df9b0-199">出力</span><span class="sxs-lookup"><span data-stu-id="df9b0-199">Output</span></span>

<span data-ttu-id="df9b0-200">コマンド ライン出力はありません。プログラム出力は、メインのグラフィカル ユーザー インターフェイス (GUI) 内に含まれる。</span><span class="sxs-lookup"><span data-stu-id="df9b0-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="df9b0-201">用途</span><span class="sxs-lookup"><span data-stu-id="df9b0-201">Purpose</span></span>

<span data-ttu-id="df9b0-202">帯域幅ポリシー サービス モニター ツールの目的は、管理者がトポロジで定義されている各帯域幅ポリシー サービスの状態を表示できる目的です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="df9b0-203">さらに、管理者は、ネットワーク構成ドキュメントで定義されているリンクすべてについて、リアルタイムの帯域幅の使用状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="df9b0-204">要件</span><span class="sxs-lookup"><span data-stu-id="df9b0-204">Requirements</span></span>

<span data-ttu-id="df9b0-205">帯域幅ポリシー サービス モニター ツールは、Skype for Business Server トポロジの一部であるコンピューターで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="df9b0-206">概要</span><span class="sxs-lookup"><span data-stu-id="df9b0-206">Summary</span></span>

<span data-ttu-id="df9b0-207">帯域幅ポリシー サービス モニター ツールは、管理者にとって貴重なリソースであり、トポロジ内のすべての帯域幅ポリシー サービスの状態を検査し、さらに重要なことに、ネットワーク構成設定で定義されているリンクのリアルタイム帯域幅使用率を取得できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="df9b0-208">帯域幅使用率アナライザー</span><span class="sxs-lookup"><span data-stu-id="df9b0-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="df9b0-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="df9b0-209"><a name="bua"> </a></span></span>

<span data-ttu-id="df9b0-210">帯域幅使用率アナライザーは、エンタープライズ ネットワーク内の WAN リンク間の UC エンドポイントによる帯域幅消費のさまざまなビューに関するレポートを作成するツールです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="df9b0-211">これらのレポートは、現在の帯域幅消費パターンを理解し、帯域幅の容量計画を支援するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="df9b0-212">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-212">Description</span></span>

<span data-ttu-id="df9b0-213">帯域幅使用率アナライザーは、GUI ベースのアプリケーションとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="df9b0-214">このツールは、ネットワーク全体のオーディオ使用率専用のレポートを生成し、容量計画に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="df9b0-215">また、さまざまなリンクに割り当てられている帯域幅の容量を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="df9b0-216">出力</span><span class="sxs-lookup"><span data-stu-id="df9b0-216">Output</span></span>

<span data-ttu-id="df9b0-217">帯域幅使用率アナライザーは、システムで構成されているすべての WAN リンクに対して、オーディオの帯域幅容量と使用率のグラフィック プロットを提供します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="df9b0-218">用途</span><span class="sxs-lookup"><span data-stu-id="df9b0-218">Purpose</span></span>

<span data-ttu-id="df9b0-219">音声およびビデオの展開では、エンタープライズ ネットワーク全体のメディア トラフィックの帯域幅使用率の傾向を監視し、理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="df9b0-220">帯域幅使用率アナライザー ツールを使用すると、管理者はこれを実現できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="df9b0-221">このツールは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-221">This tool does the following:</span></span>

- <span data-ttu-id="df9b0-222">ネットワーク全体のオーディオ使用率に関する特定のレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="df9b0-223">さまざまなリンクに割り当てられている帯域幅の容量に対する、より効果的な容量計画と反復処理に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="df9b0-224">帯域幅使用率アナライザーは、帯域幅の容量と使用率レポートのグラフ プロットを生成できます。これらは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="df9b0-225">エンタープライズ ネットワーク内のすべての WAN リンク</span><span class="sxs-lookup"><span data-stu-id="df9b0-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="df9b0-226">選択されている選択された WAN リンクによってフィルター処理される</span><span class="sxs-lookup"><span data-stu-id="df9b0-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="df9b0-227">リンク容量を超えた WAN リンクによってフィルター処理される</span><span class="sxs-lookup"><span data-stu-id="df9b0-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="df9b0-228">プロビジョニングされた帯域幅を過小利用している WAN リンクによってフィルター処理される</span><span class="sxs-lookup"><span data-stu-id="df9b0-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="df9b0-229">重要なレベルに達している WAN リンクによるフィルター処理 (WAN リンクの帯域幅容量の 90% を超える帯域幅使用率)</span><span class="sxs-lookup"><span data-stu-id="df9b0-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="df9b0-230">WAN リンクの種類 (ネットワーク サイトリンク、エリア間リンク、サイト内のリンク) でフィルター処理される</span><span class="sxs-lookup"><span data-stu-id="df9b0-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="df9b0-231">ネットワーク地域でフィルター処理される</span><span class="sxs-lookup"><span data-stu-id="df9b0-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="df9b0-232">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="df9b0-232">Applications</span></span>

<span data-ttu-id="df9b0-233">帯域幅使用率アナライザーには、次の 2 つのアプリケーション (ツール) があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="df9b0-234">**WanLinkLogCollector.exe** このツールを使用すると、ユーザーは必要な情報を入力できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="df9b0-235">**BandwidthUtilizationAnalyzer.xlsm** Microsoft Excel スプレッドシート ソフトウェア レポートは、ユーザーが自動的にWanLinkLogCollector.exe。</span><span class="sxs-lookup"><span data-stu-id="df9b0-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="df9b0-236">このアプリケーションを使用すると、この記事の後半で示すように、ユーザーはレポートにフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="df9b0-237">帯域幅使用率アナライザーの使用のフェーズ</span><span class="sxs-lookup"><span data-stu-id="df9b0-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="df9b0-238">帯域幅使用率アナライザーを使用する場合は、次の 2 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="df9b0-239">ログを収集します。これは、ログを使用して実行WanLinkLogCollector.exe</span><span class="sxs-lookup"><span data-stu-id="df9b0-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="df9b0-240">m を使用して実行されるレポートをBandwidthUtilizationAnalyzer.xlsする</span><span class="sxs-lookup"><span data-stu-id="df9b0-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="df9b0-241">エンド ユーザーが手動BandwidthUtilizationAnalyzer.xls起動しない方法を強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="df9b0-242">帯域幅使用率アナライザーの開始</span><span class="sxs-lookup"><span data-stu-id="df9b0-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="df9b0-243">コマンド プロンプトWanLinkLogCollector.exe Windows エクスプローラーを使用して、コマンド を開始します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="df9b0-244">**ユーザー設定WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="df9b0-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="df9b0-245">次の 3 つの手順を使用WanLinkLogCollector.exe。</span><span class="sxs-lookup"><span data-stu-id="df9b0-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="df9b0-246">**タイムラインをログに記録する** レポートを生成する必要があるタイムラインを指定する</span><span class="sxs-lookup"><span data-stu-id="df9b0-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="df9b0-247">**ファイル ディレクトリを指定する** ファイルの場所情報を提供する</span><span class="sxs-lookup"><span data-stu-id="df9b0-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="df9b0-248">**ログを収集し、レポート ビューアーを起動する** コマンドを実行してレポートを生成する</span><span class="sxs-lookup"><span data-stu-id="df9b0-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="df9b0-249">手順 1 - タイムラインをログに記録する</span><span class="sxs-lookup"><span data-stu-id="df9b0-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="df9b0-250">タイムラインをログに記録すると、ツール ユーザーは、次の図に示すように、次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="df9b0-251">**開始日** これは、レポートを生成する予定のタイムラインの開始日です。たとえば、2010 年 8 月 1 日です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="df9b0-252">**終了日** これは、レポートが生成される予定のタイムラインの終了日です。たとえば、2010 年 9 月 30 日です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![帯域幅使用率 A の開始日と終了日](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="df9b0-254">手順 2 - ファイル ディレクトリを指定する</span><span class="sxs-lookup"><span data-stu-id="df9b0-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="df9b0-255">次のファイル ディレクトリは、ユーザーが示すように指定できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="df9b0-256">**サーバー ログ ファイルの場所** 帯域幅ポリシー サーバー ログが格納されているフォルダーの場所。</span><span class="sxs-lookup"><span data-stu-id="df9b0-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="df9b0-257">これは通常、FE \<fileserver\> \\ \> \AppServerFiles\PDP<選択する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="df9b0-258">**一時ファイルの保存場所** レポートの生成中に中間ファイルが保存される一時ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="df9b0-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![帯域幅使用率の分析のファイル ディレクトリ](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="df9b0-260">サーバー ログと一時ファイル ストア フォルダーへの十分なファイル アクセスがツール ユーザーに提供されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="df9b0-261">手順 3 - ログを収集し、レポート ビューアーを起動する</span><span class="sxs-lookup"><span data-stu-id="df9b0-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="df9b0-262">ログを収集してレポート ビューアーを起動するには、次に示すように **[実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="df9b0-263">この手順では、必要なデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-263">This step collects the required data.</span></span>

![帯域幅使用率分析でのデータの収集](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="df9b0-265">入力の検証が成功すると、次に示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-265">When the input validation is successful, the message shown below is displayed.</span></span>

![帯域幅 Utili で収集された通知のログ](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="df9b0-267">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-267">Click **OK**.</span></span> <span data-ttu-id="df9b0-268">BandwidthUtilizationAnalyzer.xlsm が自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="df9b0-269">メッセージ ボックスの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="df9b0-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="df9b0-270">詳細については、次の **セクションBandwidthUtilizationAnalyzer.xlsm** を使用するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df9b0-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="df9b0-271">m のBandwidthUtilizationAnalyzer.xls使用</span><span class="sxs-lookup"><span data-stu-id="df9b0-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="df9b0-272">m BandwidthUtilizationAnalyzer.xlsが自動的に開始された場合は、次に示すように **[更新** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="df9b0-274">ファイル フォルダーを開いた場合は、consolidated.csvメッセージ ボックスで指定された場所からファイル フォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="df9b0-275">また、場所は **C:\Temp として表示されます**。</span><span class="sxs-lookup"><span data-stu-id="df9b0-275">It also shows the location as **C:\Temp**.</span></span>

     ![BandwidthUtilizationAnalyzer でフォルダーを開きます。](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="df9b0-277">[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-277">Click **Import**.</span></span>

4. <span data-ttu-id="df9b0-278">グラフィカル プロットが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="df9b0-279">これは、作業中の背景ポインターが消えたときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![レポート ビューでフィルターを適用する。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="df9b0-281">レポート ビューへのフィルターの適用</span><span class="sxs-lookup"><span data-stu-id="df9b0-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="df9b0-282">次に示すように、レポート ビューに適用できるフィルターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![レポート ビューでフィルターを適用する。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="df9b0-284">**名前** WAN リンクによるフィルター (フィルターはグラフの右側にあります)。プレフィックスは、次のリンクの種類を示します。垂直 (青) ボックスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df9b0-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="df9b0-285">**S サイト** ネットワーク サイトからネットワーク地域への WAN リンク</span><span class="sxs-lookup"><span data-stu-id="df9b0-285">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="df9b0-286">**IS サイト間** 2 つのネットワーク サイト間の WAN リンク</span><span class="sxs-lookup"><span data-stu-id="df9b0-286">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="df9b0-287">**R 地域間** 2 つのネットワーク領域間の WAN リンク</span><span class="sxs-lookup"><span data-stu-id="df9b0-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="df9b0-288">**制限を超えた** 帯域幅使用率が帯域幅容量を超える WAN リンクによるフィルター処理</span><span class="sxs-lookup"><span data-stu-id="df9b0-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="df9b0-289">**重要なレベル** 帯域幅使用率が帯域幅容量の 90% 以上に達した WAN リンクによるフィルター</span><span class="sxs-lookup"><span data-stu-id="df9b0-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="df9b0-290">**利用が過小** 帯域幅使用率が帯域幅容量の 25% 未満である WAN リンクによるフィルター処理</span><span class="sxs-lookup"><span data-stu-id="df9b0-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="df9b0-291">**リンクの種類** 次の WAN リンクの種類でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-291">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="df9b0-292">**ネットワーク サイトの** 種類</span><span class="sxs-lookup"><span data-stu-id="df9b0-292">**Network site** type</span></span>

   - <span data-ttu-id="df9b0-293">**サイト間の** 種類</span><span class="sxs-lookup"><span data-stu-id="df9b0-293">**Inter-site** type</span></span>

   - <span data-ttu-id="df9b0-294">**地域間リンクの** 種類</span><span class="sxs-lookup"><span data-stu-id="df9b0-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="df9b0-295">**地域** ネットワーク地域でフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="df9b0-295">**Region** Filter by network region</span></span>

<span data-ttu-id="df9b0-296">次の図は、前述のフィルターを示しています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="df9b0-297">名前でフィルター **処理します**。</span><span class="sxs-lookup"><span data-stu-id="df9b0-297">Filter by **Name**.</span></span> <span data-ttu-id="df9b0-298">グラフに表示する必要があるリンクの一覧を選択します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-298">Select the list of links that need to be displayed in the graph.</span></span>

![BandwidthUtilizationAnalyzer の名前によるフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="df9b0-300">制限を超 **えてフィルターを適用します**。</span><span class="sxs-lookup"><span data-stu-id="df9b0-300">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="df9b0-301">**[True] を** 選択してフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-301">Select **True** to enforce the filter.</span></span>

![超過制限によるフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="df9b0-303">クリティカル レベル **でフィルター処理します**。</span><span class="sxs-lookup"><span data-stu-id="df9b0-303">Filter by **Critical levels**.</span></span> <span data-ttu-id="df9b0-304">**[True] を** 選択してフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-304">Select **True** to enforce the filter.</span></span>

![クリティカル レベルによるフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="df9b0-306">[使用 **されているアンダー] でフィルターを適用します**。</span><span class="sxs-lookup"><span data-stu-id="df9b0-306">Filter by **Under utilized**.</span></span> <span data-ttu-id="df9b0-307">**[True] を** 選択してフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-307">Select **True** to enforce the filter.</span></span>

![[使用] でフィルター処理します。](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="df9b0-309">[リンクの **種類でフィルター] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="df9b0-309">Filter by **Link Type**.</span></span> <span data-ttu-id="df9b0-310">表示する必要がある種類または種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-310">Select the type or types that need to be displayed.</span></span>

![リンクの種類によるフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="df9b0-312">地域で **フィルターを適用します**。</span><span class="sxs-lookup"><span data-stu-id="df9b0-312">Filter by **Region**.</span></span> <span data-ttu-id="df9b0-313">リンクを表示する必要がある地域の一覧を選択します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-313">Select a list of regions whose links need to be displayed.</span></span>

![地域によるフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="df9b0-315">要件</span><span class="sxs-lookup"><span data-stu-id="df9b0-315">Requirements</span></span>

- <span data-ttu-id="df9b0-316">3.5 .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="df9b0-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="df9b0-317">Microsoft Excel 2010 または Excel 2007</span><span class="sxs-lookup"><span data-stu-id="df9b0-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="df9b0-318">概要</span><span class="sxs-lookup"><span data-stu-id="df9b0-318">Summary</span></span>

<span data-ttu-id="df9b0-319">帯域幅使用率アナライザーは、ネットワーク全体の UC トラフィックのオーディオ帯域幅使用率をプロットするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-319">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="df9b0-320">このツールを使用して、ネットワーク上のビデオ帯域幅の使用率も報告できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-320">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="df9b0-321">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="df9b0-321">Call Parkometer</span></span>
<span data-ttu-id="df9b0-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="df9b0-322"><a name="callpark"> </a></span></span>

<span data-ttu-id="df9b0-323">Call Parkometer は、コール パーク オービット データベースに簡単にアクセスできるコマンド ライン アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="df9b0-324">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-324">Description</span></span>

<span data-ttu-id="df9b0-325">Call Parkometer は、現在パークされている通話を追跡するツールです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="df9b0-326">また、オービットとコール パーク サーバー (CPS) の使用状況に関する統計情報も収集します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="df9b0-327">このコマンド ライン ツールは、ローカルまたはリモート接続されたコンピューターから、CPS オービット SQL Serverに読み取りおよび書き込みアクセスの両方を提供します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="df9b0-328">すべてのオプションは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-328">All options are mutually exclusive.</span></span> <span data-ttu-id="df9b0-329">コマンド ライン構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-329">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="df9b0-330">**-o** パラメーター: このプールに構成されているオービット範囲の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="df9b0-331">**-n** パラメーター : このプールで現在使用されているオービットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="df9b0-332">表示される情報は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="df9b0-333">パークリーとパーカーの SIP ユニフォーム リソース識別子 (URI)。</span><span class="sxs-lookup"><span data-stu-id="df9b0-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="df9b0-334">呼び出しがパークされている CPS のホスト名。</span><span class="sxs-lookup"><span data-stu-id="df9b0-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="df9b0-335">通話がパークされた時刻のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="df9b0-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="df9b0-336">**-f** パラメーター : プール内の現在空きオービットの数を示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="df9b0-337">**-r \<n\>** parameter - 最後にパーク \<n\> された呼び出しの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="df9b0-338">表示される情報は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="df9b0-339">PARKEE SIP URI。</span><span class="sxs-lookup"><span data-stu-id="df9b0-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="df9b0-340">パーカー SIP URI。</span><span class="sxs-lookup"><span data-stu-id="df9b0-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="df9b0-341">呼び出しがパークされた CPS のホスト名。</span><span class="sxs-lookup"><span data-stu-id="df9b0-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="df9b0-342">呼び出しが取得または削除された時刻のタイム スタンプ。</span><span class="sxs-lookup"><span data-stu-id="df9b0-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="df9b0-343">**-t \<n\>** parameter - データベース内のオービットを予約し、割り当てられたオービット番号のランダム性を示すテストを行います。</span><span class="sxs-lookup"><span data-stu-id="df9b0-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="df9b0-344">出力</span><span class="sxs-lookup"><span data-stu-id="df9b0-344">Output</span></span>

<span data-ttu-id="df9b0-345">コマンド プロンプトで指定された入力パラメーターに応じて、Call Parkometer は次の出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="df9b0-346">このプール用に構成されているすべてのオービット範囲</span><span class="sxs-lookup"><span data-stu-id="df9b0-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="df9b0-347">現在、パークされている通話</span><span class="sxs-lookup"><span data-stu-id="df9b0-347">Currently parked calls</span></span>

- <span data-ttu-id="df9b0-348">無料の (使用可能な) オービットの数</span><span class="sxs-lookup"><span data-stu-id="df9b0-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="df9b0-349">最近パークされた通話</span><span class="sxs-lookup"><span data-stu-id="df9b0-349">Recently parked calls</span></span>

- <span data-ttu-id="df9b0-350">均一なオービット値とランダムオービット値をテストする予約済みのオービット</span><span class="sxs-lookup"><span data-stu-id="df9b0-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="df9b0-351">用途</span><span class="sxs-lookup"><span data-stu-id="df9b0-351">Purpose</span></span>

<span data-ttu-id="df9b0-352">CPS ツールの目的は、CPS データベースへのコマンド ライン アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-352">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="df9b0-353">管理者は、CPS 使用状況を表示し、プールに割り当てられたオービットの数を決定できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-353">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="df9b0-354">要件</span><span class="sxs-lookup"><span data-stu-id="df9b0-354">Requirements</span></span>

<span data-ttu-id="df9b0-355">このツールが CPS を実行しているのと同じコンピューターで実行される場合、要件はありません。</span><span class="sxs-lookup"><span data-stu-id="df9b0-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="df9b0-356">このツールをリモート コンピューターで実行する場合は、Skype for Business Server 2015 で使用SQL Serverデータベースをリモート アクセスを許可するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="df9b0-357">Call Parkometer は、プールのSQL Server接続するために、データベース接続文字列を使用して構成する必要SQL Server。</span><span class="sxs-lookup"><span data-stu-id="df9b0-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="df9b0-358">このSQL Serverデータベース接続文字列は、構成ファイルで定義されます。parkometer.exe.config。 \*\*\*\* このディレクトリは、そのディレクトリと同じディレクトリparkometer.exe必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="df9b0-359">次の XML ファイルは、次の XML ファイルの例parkometer.exe.config。構成する必要があるパラメーターは、ユーザー名 (mydomain\Administrator など)、パスワード (mypassword など)、ホスト名 (myserver など) です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

### <a name="examples"></a><span data-ttu-id="df9b0-360">例</span><span class="sxs-lookup"><span data-stu-id="df9b0-360">Examples</span></span>

<span data-ttu-id="df9b0-361">展開されたオービット範囲: -o パラメーターは、このプール用に構成されているすべてのオービット範囲を示すように一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Call Parkometer のオービット範囲。](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="df9b0-363">現在パークされている呼び出し: -n パラメーターは、このプールで現在使用されているオービットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Call Parkometer で現在パークされている呼び出し。](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="df9b0-365">空きオービットの数: -f パラメーターは、プール内の現在空きオービットの数を示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Call Parkometer の無料オービット。](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="df9b0-367">最近パークされた呼び出し: -r パラメーターは、次に示すように、最後 \<n\> \<n\> にパークされた呼び出しを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![コール パークメーターで最近パークされた呼び出し。](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="df9b0-369">軌道予約のテスト: -t パラメーターは、次に示すように、データベース内のオービット \<n\> を予約するテストを行います。</span><span class="sxs-lookup"><span data-stu-id="df9b0-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Call Parkometer でオービット予約をテストします。](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="df9b0-371">概要</span><span class="sxs-lookup"><span data-stu-id="df9b0-371">Summary</span></span>

<span data-ttu-id="df9b0-372">Call Parkometer は、コール パーク サーバーに関する詳細情報を提供するコマンド ライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="df9b0-373">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="df9b0-373">DBAnalyze</span></span>
<span data-ttu-id="df9b0-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="df9b0-374"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="df9b0-375">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-375">Description</span></span>

<span data-ttu-id="df9b0-376">DBAnalyze は、管理者が Skype for Business Server 2015 データベースに関する分析レポートを収集するのに役立つコマンド ライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="df9b0-377">DBAnalyze には、診断モード、ユーザー データモード、会議モード、MCUs モード、ディスク断片化モードがあります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="df9b0-378">**診断モード** テーブルに関する情報を含むレポートを作成します (レコード数、 断片化、データ サイズ、ログ ファイル サイズ、データ ファイルサイズ、最後のバックアップ時間、Microsoft Office Communications Server を実行しているサーバー間の連絡先配布、アクセス許可の平均数、連絡先、コンテナー、サブスクリプション、パブリケーション、ユーザーごとのエンドポイント、不適切にホームユーザー、ルーティングできないユーザー、ユーザーごとの組織化された会議の平均数、スケジュールされた会議、アクティブな会議、およびデータベース バージョン。</span><span class="sxs-lookup"><span data-stu-id="df9b0-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df9b0-379">診断モードを実行すると、サーバーのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="df9b0-380">**ユーザー データ モード** 指定したユーザーの連絡先、コンテナー、サブスクリプション、パブリケーション、アクセス許可、および連絡先グループのデータ、または連絡先とアクセス許可リストにそのユーザーを持つユーザーを報告します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="df9b0-381">また、このモードでは、ユーザーが開催または招待された会議の概要データも報告されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="df9b0-382">**会議モード** 会議のすべてのスケジュール時間の詳細、招待者リスト、会議に許可されているメディアの種類の一覧、アクティブな MCUs (マルチポイントコントロール ユニット)、アクティブな参加者リスト、各参加者のシグナリング状態など、特定の会議の詳細なデータをレポートします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="df9b0-383">**会議 ID のデコード** /pstnid スイッチで指定されているが、詳細についてはバック エンドに接続しない公衆交換電話網 **(PSTN)** 会議 ID をデコードします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="df9b0-384">**会議の解決\*\*\*\*/pstnid** スイッチで指定された PSTN 会議 ID をデコードし、ID で示された会議に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="df9b0-385">**MCUs モード** プール内の各 MCU の ID、メディアの種類、URL、ハートビートの状態、会議の負荷、および参加者の負荷を報告します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="df9b0-386">**ディスクの断片化モード** すべてのディスクの断片化状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="df9b0-387">このツールは、さまざまな問題を診断したり、管理者が容量計画を支援したりするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-387">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="df9b0-388">たとえば、サーバー A にホームされているユーザーのほとんどが、サーバー B のユーザーを連絡先として選択した場合、管理者はサーバー A のユーザーをサーバー B に移動して、サーバー間のトラフィックを削減できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-388">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="df9b0-389">出力</span><span class="sxs-lookup"><span data-stu-id="df9b0-389">Output</span></span>

<span data-ttu-id="df9b0-390">このツールは、Skype for Business Server 2015 データベースに関する定義済みのレポートを出力します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="df9b0-391">**パス**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span><span class="sxs-lookup"><span data-stu-id="df9b0-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="df9b0-392">用途</span><span class="sxs-lookup"><span data-stu-id="df9b0-392">Purpose</span></span>

<span data-ttu-id="df9b0-393">ファイルをインストールDbanalyze.exeローカル フォルダーにコピーし、ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="df9b0-394">ツールを使用するには、コマンド ラインから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="df9b0-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` コマンド ライン オプションの説明を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![コマンド ライン オプションを使用Dbanalyze.exe。](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="df9b0-397">要件</span><span class="sxs-lookup"><span data-stu-id="df9b0-397">Requirements</span></span>

 <span data-ttu-id="df9b0-398">**コンピューター** DBAnalyze は、Skype for Business Server 2015 がインストールされているドメインに参加しているコンピューターからのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="df9b0-399">**ネットワーク** コンピューターは、バック エンド データベースに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="df9b0-400">**ソフトウェア** DBAnalyze を実行する前に、Skype for Business Server 2015 ソフトウェア コンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="df9b0-401">**ユーザー** 次の表に、Skype for Business Server 2015 データベースにアクセスするために必要なアクセス許可を持つ管理者を示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-401">**Users** The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![ユーザーのアクセス許可Dbanalyze.exe。](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="df9b0-403">**/report:disk モードでは、ローカル管理者アカウントが必要** です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="df9b0-404">例</span><span class="sxs-lookup"><span data-stu-id="df9b0-404">Examples</span></span>

<span data-ttu-id="df9b0-405">有効なコマンドの例を次にDbanalyze.exeします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="df9b0-406">概要</span><span class="sxs-lookup"><span data-stu-id="df9b0-406">Summary</span></span>

<span data-ttu-id="df9b0-407">DBAnalyzer は、管理者が Skype for Business Server 2015 データベースを迅速かつ簡単に分析できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="df9b0-408">ストレージ サービス データのインポート</span><span class="sxs-lookup"><span data-stu-id="df9b0-408">Import Storage Service Data</span></span>
<span data-ttu-id="df9b0-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="df9b0-409"><a name="Issd"> </a></span></span>

<span data-ttu-id="df9b0-410">ImportStorageServiceData リソース キット ツールを使用すると、記憶域サービス (LYSS) からフラッシュされたキューデータとエンドポイント データをストレージ サービスに再インポートできます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="df9b0-411">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-411">Description</span></span>

<span data-ttu-id="df9b0-412">記憶域サービスからフラッシュされたデータは、キュー アイテムの状態またはデータベース サイズに基づいて自動 (定期的) に実行されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="df9b0-413">これは、プール フェールオーバー コマンドレットの手動呼び出し、または StorageServiceFullFlush コマンドレット (プール フェールオーバー コマンドレットが呼び出す) が原因で発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="df9b0-414">フロントエンドのストレージ サービス (LYSS) データベース サイズが通常のレベルを超える場合は、データを再インポートしない方が理想的です。さらに、記憶域サービス キューの拡大を引き起こしたエラーの原因となる可能性がある問題は、最初に解決する必要があります (Exchange エンドポイントのエラー、ネットワークの問題、その他の問題など)。</span><span class="sxs-lookup"><span data-stu-id="df9b0-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="df9b0-415">**シナリオ 1:** プールのフェールオーバー中に、ファイルが各フロントエンドのストレージ サービスからフラッシュアウトされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="df9b0-416">フェールオーバーが完了したら、ツールを実行してデータを再インポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="df9b0-417">**シナリオ 2:** データが毎日自動的にフラッシュされる、または特定のサイズのしきい値を超える記憶域サービス データベースに応答します (たとえば、60%、80%、90% 満値)。</span><span class="sxs-lookup"><span data-stu-id="df9b0-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="df9b0-418">この自動的にフラッシュされたデータは、管理者が定期的に再インポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="df9b0-419">上記の状況では、監視 SCOM パックが展開されていない場合、ストレージ サービスからフラッシュされるデータに関連する Skype for Business Server Storage Service のイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="df9b0-420">32075 のイベント ID (フル フラッシュ操作が開始されました)、32076 (フル フラッシュが完了しました)、32082 (メンテナンス レベルフラッシュが開始されました)、32083 (メンテナンス レベルフラッシュが完了)、32089 (データベースの満たされた原因でフラッシュが発生しました)。</span><span class="sxs-lookup"><span data-stu-id="df9b0-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="df9b0-421">これらのイベント Id は RTM リリースに対応しています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="df9b0-422">管理者がこれらのイベントを見た場合は、フラッシュされたファイルがあるという意味です。このデータは、このツールを使用して定期的にインポートバックする必要があります (たとえば、週に 1 回)。</span><span class="sxs-lookup"><span data-stu-id="df9b0-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="df9b0-423">Online Service リリースの場合、Skype for Business Server 用の正常性監視 SCOM パックが展開されている場合、新しいアラートが発生し、管理者はフラッシュされたデータをストレージ サービスに再インポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="df9b0-424">フロント エンド サーバーのイベント ログに対応するイベントが発生し、アラートがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="df9b0-425">イベントでは、フラッシュされたデータ ファイルが置かれる親パスと、アラート条件を満たすファイルの数について説明します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="df9b0-426">警告の条件は、特定の親パスの下に、少なくとも Y 日前の X 以上のファイルが含まれます (ここで、X と Y は StorageService 内で事前に設定されますが、APPCONFIG ファイルを変更することで上書きできます)。正常性アラートをトリガーできるイベントの 2 つの例を以下に示します。その違いは親パスです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="df9b0-427">1 つの可能性は Web サービス ファイル共有の下にありますが、もう 1 つの可能性は、各フロントエンドのローカル アプリケーション データ ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="df9b0-428">( c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService など)。</span><span class="sxs-lookup"><span data-stu-id="df9b0-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="df9b0-429">管理者は、この reskit ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="df9b0-430">このツールは、ツールが実行されるフロントエンドによってデータが所有されていない場合に、実行中のフロントエンドと他のフロントエンドの CPU と IO 負荷を増加します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="df9b0-431">フロント エンドが CPU と IO の負荷が高い (ピーク時外など) 場合は、このツールを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="df9b0-432">次に、このツールは 2 ~ 3 分で 1 つのデータ ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="df9b0-433">ツールの実行時間を見積もる場合は、この問題に気を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="df9b0-434">ツールによって生成された詳細ログ ファイルは、既定でファイル ストアに表示されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="df9b0-435">ログ ファイルには数十 MB 以上のエラーが報告されていない場合は削除します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![ストレージ サーバーのイベント ログ イベントのサンプル。](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="df9b0-437">要件</span><span class="sxs-lookup"><span data-stu-id="df9b0-437">Requirements</span></span>

<span data-ttu-id="df9b0-438">Skype for Business Server 2015 リソース キット ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="df9b0-439">このツールは、Skype for Business Server と Skype for Business Server 管理シェルがインストールされているドメインに参加しているコンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="df9b0-440">このツールは、管理シェルのコマンドレットを使用して、プール内のすべてのフロントエンド サーバーを識別します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="df9b0-441">次に **、RtcLocal** データベースがインストールされているプール内のコンピューターからツールを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="df9b0-442">このデータベースは、プールの WEBSERVICE ファイル共有の場所を取得するためにツールによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="df9b0-443">さらに、ツールを使用する前に、各フロントエンド サーバーで、各フロントエンド サーバーで **Enable-PSRemoting** を使用して Windows PowerShell リモート処理を有効にする必要があります。また、ツールが実行されるコンピューターも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="df9b0-444">それ以外の場合、Windows PowerShellリモート コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="df9b0-445">Windows PowerShell後、プール内のすべてのフロントエンド サーバーでリモート処理をオフにできます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="df9b0-446">最後に、ツールを呼び出すアカウントまたは資格情報に、このツールを実行しているプールの Web サービス ファイル共有に対する読み取り/書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="df9b0-447">それ以外の場合、ツールは IO アクセス許可エラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="df9b0-448">このWindows Server 2012、Windows PowerShellリモート処理は既定で有効になっていますが、Windows Server 2008 オペレーティング システムでは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="df9b0-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="df9b0-449">例</span><span class="sxs-lookup"><span data-stu-id="df9b0-449">Examples</span></span>

```console
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

## <a name="lcssync"></a><span data-ttu-id="df9b0-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="df9b0-450">LCSSync</span></span>
<span data-ttu-id="df9b0-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="df9b0-451"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="df9b0-452">LCSSync ツールは、Skype for Business Server 2015 コミュニケーション ソフトウェアを複数フォレスト環境に展開するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="df9b0-453">このツールは、異なるユーザー フォレストのユーザーとグループを Active Directory ドメイン サービス連絡先オブジェクトとして、Skype for Business Server 2015 がインストールされている中央フォレストに同期するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="df9b0-454">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-454">Description</span></span>

 <span data-ttu-id="df9b0-455">LCSSync は、中央フォレスト内の同期された Active Directory ドメイン サービス連絡先オブジェクトを使用して、Skype for Business Server のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="df9b0-456">シングル サインインを提供するには、プライマリ ユーザー アカウントを、Skype for Business Server 2015 の中央フォレストの Active Directory ドメイン サービス連絡先オブジェクトにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="df9b0-457">このツールは、そのマッピングを実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="df9b0-458">このツールは、Microsoft Identity Integration Server で管理エージェントを作成するためのテンプレートを提供します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="df9b0-459">概要</span><span class="sxs-lookup"><span data-stu-id="df9b0-459">Summary</span></span>

<span data-ttu-id="df9b0-460">LCSSync ツールは、複数フォレスト環境に Skype for Business Server 2015 を展開するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="df9b0-461">ユーザー コンソールの参照</span><span class="sxs-lookup"><span data-stu-id="df9b0-461">Lookup User Console</span></span>
<span data-ttu-id="df9b0-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="df9b0-462"><a name="LUC"> </a></span></span>

<span data-ttu-id="df9b0-463">LookupUserConsole ツールは、特定のユーザーに関する内部 Skype for Business Server ルーティング情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="df9b0-464">この情報は、展開とルーティングの問題を診断する際に Microsoft が個人をサポートする場合に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="df9b0-465">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-465">Description</span></span>

 <span data-ttu-id="df9b0-466">このLookupUserConsole.exeを実行すると、SIP アドレスを受け入れ、内部 Skype for Business Server ルーティング情報を表示しようとするコマンド プロンプトが開きます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="df9b0-467">Exit **と入力** して LookupUserConsole ツールを終了します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="df9b0-468">要件</span><span class="sxs-lookup"><span data-stu-id="df9b0-468">Requirements</span></span>

<span data-ttu-id="df9b0-469">Skype for Business Server 2015 リソース キットをインストールします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="df9b0-470">このツールは、Skype for Business Server がインストールされているドメインに参加しているコンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="df9b0-471">例</span><span class="sxs-lookup"><span data-stu-id="df9b0-471">Examples</span></span>

<span data-ttu-id="df9b0-472">C:\Program Files\Skype for Business Server 2015\ResKit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="df9b0-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

```console
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

## <a name="msturnping"></a><span data-ttu-id="df9b0-473">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="df9b0-473">MsTurnPing</span></span>
<span data-ttu-id="df9b0-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="df9b0-474"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="df9b0-475">MSTurnPing ツールを使用すると、Skype for Business Server 2015 コミュニケーション ソフトウェアの管理者は、オーディオ/ビデオ エッジおよびオーディオ/ビデオ認証サービスを実行しているサーバーと、トポロジで帯域幅ポリシー サービスを実行しているサーバーの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="df9b0-476">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-476">Description</span></span>

<span data-ttu-id="df9b0-477">MSTurnPing ツールを使用すると、Skype for Business Server 2015 コミュニケーション ソフトウェアの管理者は、オーディオ/ビデオ エッジおよびオーディオ/ビデオ認証サービスを実行しているサーバーと、トポロジで帯域幅ポリシー サービスを実行しているサーバーの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="df9b0-478">このツールを使用すると、管理者は次のテストを実行できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="df9b0-479">A/V エッジ サーバー テスト: このツールは、トポロジ内のすべての A/V エッジ サーバーに対して、次の操作を実行してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="df9b0-480">Skype for Business Server オーディオ/ビデオ認証サービスが開始され、適切な資格情報を発行できると確認します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="df9b0-481">Skype for Business Server Audio/Video Edge サービスが開始され、外部エッジにリソースを正常に割り当て可能な場合の確認。</span><span class="sxs-lookup"><span data-stu-id="df9b0-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="df9b0-482">帯域幅ポリシー サービス テスト: このツールは、トポロジで帯域幅ポリシー サービスを実行しているすべてのサーバーに対して、次の操作を実行してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="df9b0-483">Skype for Business Server 帯域幅ポリシー サービス (認証) が開始され、適切な資格情報を発行できるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="df9b0-484">Skype for Business Server 帯域幅ポリシー サービス (Core) が開始され、帯域幅チェックが正常に実行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="df9b0-485">このツールは、トポロジの一部であり、ローカル ストアがインストールされているコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="df9b0-486">出力</span><span class="sxs-lookup"><span data-stu-id="df9b0-486">Output</span></span>

<span data-ttu-id="df9b0-487">ツールは、各操作の結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="df9b0-488">**AudioVideoEdgeServer テストを実行** すると、ツールの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="df9b0-489">トポロジで Skype for Business Server 2015 オーディオ/ビデオ認証サービスを提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="df9b0-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="df9b0-490">トポロジで Skype for Business Server 2015 Audio/Video Edge サービスを提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="df9b0-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="df9b0-491">**BandwidthPolicyServer テストを実行** すると、ツールの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="df9b0-492">トポロジで Skype for Business Server 2015 帯域幅ポリシー サービス (認証) を提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="df9b0-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="df9b0-493">トポロジで Skype for Business Server 2015 帯域幅ポリシー サービス (Core) を提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="df9b0-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="df9b0-494">要件</span><span class="sxs-lookup"><span data-stu-id="df9b0-494">Requirements</span></span>

- <span data-ttu-id="df9b0-495">このツールは、トポロジ内でローカル ストアを持つコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="df9b0-496">このツールは、ローカル ストアにアクセスできる管理者として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="df9b0-497">例</span><span class="sxs-lookup"><span data-stu-id="df9b0-497">Examples</span></span>

<span data-ttu-id="df9b0-498">ツール入力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-498">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="df9b0-499">概要</span><span class="sxs-lookup"><span data-stu-id="df9b0-499">Summary</span></span>

<span data-ttu-id="df9b0-500">このツールは、オーディオ/ビデオおよび帯域幅ポリシー サービスを実行しているサーバーの状態を確認する Skype for Business Server 2015 管理者にとって貴重なリソースになります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="df9b0-501">ネットワーク構成ビューアー</span><span class="sxs-lookup"><span data-stu-id="df9b0-501">Network Configuration Viewer</span></span>
<span data-ttu-id="df9b0-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="df9b0-502"><a name="NCV"> </a></span></span>

<span data-ttu-id="df9b0-503">ネットワーク構成ビューアーは、Skype for Business Server 2015 コミュニケーション ソフトウェア管理者が、指定された帯域幅容量に基づく音声通話やビデオ通話などのリアルタイム通信セッションを許可するために準備されている企業の通話受付制御 (CAC) ネットワーク トポロジを表示するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="df9b0-504">Skype for Business Server 2015 管理者は CAC ポリシーを定義します。これは、Skype for Business Server 2015 にインストールされている帯域幅ポリシー サービスによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="df9b0-505">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-505">Description</span></span>

<span data-ttu-id="df9b0-506">ネットワーク構成ビューアー (NetworkConfigurationViewer.exe) を使用すると、管理者は次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="df9b0-507">Skype for Business Server 2015 展開から CAC ネットワーク トポロジをグラフィカル形式で読み込み、表示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="df9b0-508">帯域幅ポリシー サーバー ログ ファイルから CAC ネットワーク トポロジをグラフィカルな形式で読み込み、表示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="df9b0-509">CAC ネットワーク トポロジを XML 形式でディスクに保存して保存します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="df9b0-510">CAC ネットワーク トポロジ図を JPG または BMP 形式で保存して保存します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="df9b0-511">CAC ネットワーク トポロジ構成データを表示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="df9b0-512">ツリー ビュー スタイルで CAC ネットワーク トポロジを表示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="df9b0-513">CAC ネットワーク トポロジ リンクのカスタム コネクタ (サイト間リンク、地域間リンク、サイト間リンクなど) を定義します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="df9b0-514">CAC ネットワーク トポロジ サイト情報、地域情報、およびプロビジョニングされた帯域幅ポリシーとネットワーク リンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="df9b0-515">用途</span><span class="sxs-lookup"><span data-stu-id="df9b0-515">Purpose</span></span>

<span data-ttu-id="df9b0-516">グラフィカル インターフェイスでエンタープライズ CAC ネットワーク トポロジ リンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="df9b0-517">例</span><span class="sxs-lookup"><span data-stu-id="df9b0-517">Examples</span></span>

 <span data-ttu-id="df9b0-518">**Skype for Business Server 2015** の展開から CAC ネットワーク トポロジをグラフィカルな形式で読み込み、表示します。Skype for Business Server 2015 管理者は、下の図に示すように、[ネットワーク構成のダウンロード] オプションを使用して、すべての Skype for Business Server 2015 コンピューターで CAC ネットワーク トポロジ構成を読み込み、表示できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="df9b0-519">Skype for Business Server 2015 構成ストアに接続していないコンピューターに展開すると、このツールはこのような構成をダウンロードまたは表示できません。</span><span class="sxs-lookup"><span data-stu-id="df9b0-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![ネットワーク構成のダウンロード。](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="df9b0-521">帯域幅ポリシー サーバー ログ ファイルから CAC ネットワーク トポロジをグラフィカル形式 **で読み込み、表示します。** Skype for Business Server 2015 帯域幅ポリシー サーバーは、SKYPE for Business Server 2015 ファイル共有場所の下のログメカニズムの一部として CAC ネットワーク トポロジを保存します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="df9b0-522">Skype for Business Server 2015 管理者は、次に示すように [ネットワーク構成を開く] オプションを使用して、このようなファイルをグラフィカル形式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![帯域幅ポリシー サーバー ログ ファイルを開く。](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="df9b0-524">CAC ネットワーク トポロジをディスクに XML 形式で保存して保存します。Skype for Business Server 2015 管理者は、次に示すように [ネットワーク構成のコピーを保存する] オプションを使用して、CAC ネットワーク トポロジ構成ファイルを XML 形式で保存できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="df9b0-525">保存された構成ファイルは、グラフィカル表示の目的でオフラインで使用できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![ネットワーク構成を XML ファイルとして保存します。](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="df9b0-527">CAC ネットワーク トポロジ図を JPG または BMP 形式で保存および保存する: Skype for Business Server 2015 管理者は、以下に示すように [ネットワーク構成の保存] 図をピクチャ オプションとして使用して、CAC ネットワーク トポロジ構成をグラフィカル形式 (JPG および BMP ファイル形式) で保存できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![ネットワーク構成を図として保存します。](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="df9b0-529"><strong>CAC ネットワーク トポロジ構成データの表示:</strong>Skype for Business Server 2015 管理者は、以下に示す [ネットワーク構成データの表示] オプションを使用して、ネットワーク領域、ネットワーク サイト、帯域幅プロファイル、サイト サブネット IP アドレスなどの関連するネットワーク構成データをテキスト形式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-529"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![ネットワーク構成データの表示。](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="df9b0-531">**ツリー ビュー スタイルで CAC ネットワーク トポロジを表示する:** Skype for Business Server 2015 管理者は、以下に示すように、ツール ウィンドウの左側にあるコントロール パネルを使用して、関連するネットワーク構成データをグラフィカル ツリー ビュー スタイルで表示できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![ツリー ビューでのネットワーク構成データの表示。](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="df9b0-533">CAC ネットワーク トポロジ リンクのカスタム コネクタ (サイト間、地域間リンク、サイト間リンクなど **) を定義します。** Skype for Business Server 2015 管理者は、以下に示すように [設定] オプションを使用して、CAC ネットワーク構成 WAN リンクのカスタム グラフィカル コネクタを定義できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="df9b0-534">これにより、ネットワーク構成でプロビジョニングされたさまざまな種類のネットワーク リンクを区別できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![ツール](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="df9b0-536">**CAC ネットワーク トポロジ サイト情報、地域情報、およびプロビジョニングされた帯域幅ポリシーを表示します。** Skype for Business Server 2015 管理者は、以下に示すオプションを使用して、関連する CAC ネットワーク地域情報、サイト情報、CAC 帯域幅プロビジョニング情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="df9b0-537">(たとえば、ネットワーク領域 **またはネットワーク** サイト オブジェクトの [情報] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="df9b0-537">(For example, click **Info** in a network region or network site object.)</span></span>

![ネットワークのカスタム コネクタを定義する。](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="df9b0-539">概要</span><span class="sxs-lookup"><span data-stu-id="df9b0-539">Summary</span></span>

<span data-ttu-id="df9b0-540">このツールは、展開の CAC ネットワーク トポロジをグラフィカルな形式で表示する Skype for Business Server 2015 管理者にとって貴重なリソースになります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="df9b0-541">応答グループ エージェント Live</span><span class="sxs-lookup"><span data-stu-id="df9b0-541">Response Group Agent Live</span></span>
<span data-ttu-id="df9b0-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="df9b0-542"><a name="RGAL"> </a></span></span>

<span data-ttu-id="df9b0-543">応答グループ アプリケーションを使用すると、エージェントは組み込みの Web サービスを使用して有用なリアルタイム情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="df9b0-544">残念ながら、このデータのグラフィカル ビューはアプリケーションの外部で使用できません。</span><span class="sxs-lookup"><span data-stu-id="df9b0-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="df9b0-545">Response Group Agent Live Resource Kit ツールは、他のエージェントの存在などのリアルタイムの Skype for Business 通信ソフトウェア情報で強化された、この情報にアクセスするための簡単でグラフィカルな方法を提供することで、この問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="df9b0-546">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-546">Description</span></span>

<span data-ttu-id="df9b0-547">応答グループ エージェント Live は、サインインおよびサインアウト機能と、応答グループ エージェントに対してリアルタイムの情報 (グループ メンバーシップや現在の通話数など) を提供する Windows アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="df9b0-548">これは、エージェント グループ ページの拡張バージョン (Skype for Business からアクセス可能) を意図しています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="df9b0-549">用途</span><span class="sxs-lookup"><span data-stu-id="df9b0-549">Purpose</span></span>

<span data-ttu-id="df9b0-550">応答グループ アプリケーションは、着信呼び出しをキューに入れ、エージェント グループにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-550">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="df9b0-551">サービスへの呼び出しに関する情報に基づいた意思決定を行う場合、エージェントは、エージェント グループに関するリアルタイムの情報 (他のエージェントが利用できるもの、各キューで待機している呼び出しの数など) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-551">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="df9b0-552">この情報は、最初は応答グループ サービスを通じてのみアクセス可能ですが、応答グループ エージェント Live によって直感的に利用できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-552">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="df9b0-553">機能</span><span class="sxs-lookup"><span data-stu-id="df9b0-553">Features</span></span>

<span data-ttu-id="df9b0-554">応答グループ エージェント のライブ ツールは、応答グループ サービスと Skype for Business Server 2015 SDK に構築されています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="df9b0-555">応答グループ エージェントは、応答グループ サービスから利用できる情報と機能 (グループ メンバーシップ、他のエージェントの存在、待機中の通話数など) を提供します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="df9b0-556">次の図は、応答グループ エージェント Live のメイン インターフェイスを示しています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![応答グループ エージェントのライブ ツール。](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="df9b0-558">次の 3 つの主な機能は、応答グループ エージェント Live のエージェントで使用できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="df9b0-559">**サインイン/サインアウト:** [エージェント グループ] ページ (Skype for Business Server 2015 からアクセス可能) とは異なって、応答グループ エージェント Live では、エージェントだけがすべてのエージェント グループに一度にサインインまたはサインアウトできます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="df9b0-560">このアプリケーションは、エージェントがサインインまたはサインアウトするための 3 つの簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="df9b0-561">アプリケーション内の [サインイン/アウト] (緑と赤) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="df9b0-562">システム トレイ アイコンを右クリックし、[サインイン] または [サインアウト] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="df9b0-563">構成可能なキーボード ショートカットの使用。</span><span class="sxs-lookup"><span data-stu-id="df9b0-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="df9b0-564">**グループ メンバーシップ:** エージェント グループが選択されている場合、応答グループ エージェント Live は、このグループ内のエージェントの一覧を右側のウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="df9b0-565">Skype for Business Server 2015 が、このアプリケーションと同じコンピューターで実行されている場合、プレゼンス情報と連絡先カードが応答グループ エージェント Live に表示されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="df9b0-566">エージェントは、IM を送信したり、そこから他のエージェントを直接呼び出したりできます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="df9b0-567">**リアルタイム統計:** 応答グループ エージェント Live は、すべてのエージェント グループのリアルタイム統計を提供します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-567">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="df9b0-568">更新頻度は 1 分です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-568">The update frequency is one minute.</span></span> <span data-ttu-id="df9b0-569">応答グループから通話に応答すると、現在のキューに入っている呼び出し数を持つグループ名の横に視覚的インジケーターが追加されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-569">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="df9b0-570">ポインターをグループの上に一時停止すると、最も長い待機時間も表示されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-570">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="df9b0-571">要件</span><span class="sxs-lookup"><span data-stu-id="df9b0-571">Requirements</span></span>

<span data-ttu-id="df9b0-572">応答グループ エージェント Live には、.NET Framework 4.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="df9b0-573">さらに、プレゼンス カード機能と連絡先カード機能を利用するには、Skype for Business をローカルにインストール (および実行中) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="df9b0-574">構成</span><span class="sxs-lookup"><span data-stu-id="df9b0-574">Configuration</span></span>

<span data-ttu-id="df9b0-575">応答グループ エージェント Live は、アプリケーションの [オプション] ダイアログ ボックスを使用して、個々の基本設定に合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-575">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="df9b0-576">さらに、管理者は、既定のホスト アドレスを直接編集することで、既定のホスト アドレスを定義できます。既定のホスト アドレスファイルの defaultHostAddress プロパティRGAgentLive.exe.configできます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-576">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="df9b0-577">次の図は、エージェントがホスト アドレスとショートカット キーを構成するために使用できる [オプション] ダイアログ ボックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-577">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="df9b0-578">このダイアログにアクセスするには、メイン インターフェイスの上部右側にある [オプション] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-578">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![[応答グループ エージェントのライブ オプション] ダイアログ ボックス。](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="df9b0-580">応答グループ エージェントの Live 構成では、次の 3 つの異なる設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="df9b0-581">ホスト アドレス: これは通常、エージェントのホーム プールに属する Web プールの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="df9b0-582">正確な応答グループ サービス アドレスは、この情報からバックグラウンドで自動的に派生します (ホストの後に正しいパスを追加します)。</span><span class="sxs-lookup"><span data-stu-id="df9b0-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="df9b0-583">ショートカット: サインイン/サインアウトの正確なショートカットをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="df9b0-584">唯一の制限は、両方のショートカットに "Windows ロゴ" キー (少なくとも別のキーに加えて) が含まれている必要がある場合です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="df9b0-585">Windows から開始: アプリケーションは、Windows で自動的に開始するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="df9b0-586">例</span><span class="sxs-lookup"><span data-stu-id="df9b0-586">Examples</span></span>

<span data-ttu-id="df9b0-587">次の図は、右側のウィンドウで連絡先を右クリックして IM を呼び出す方法または別のエージェントに送信する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![呼び出しを行う、または IM を送信する。](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="df9b0-589">次の図は、応答グループ エージェント Live がキュー内の現在の通話数と、これらすべての着信呼び出しの中で最も長い待機時間を表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![キュー情報の表示。](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="df9b0-591">概要</span><span class="sxs-lookup"><span data-stu-id="df9b0-591">Summary</span></span>

<span data-ttu-id="df9b0-592">高速サインインとサインアウト、グループ メンバーシップ、および基本的なリアルタイム統計は、応答グループ サービスからアプリケーションの外部でのみ利用できる興味深い応答グループ エージェント機能です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="df9b0-593">応答グループ エージェント のライブ リソース キット ツールを使用すると、Skype for Business Server 2015 管理者は、エージェントに Windows アプリケーションを提供して、より迅速かつグラフィカルな方法でタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="df9b0-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="df9b0-594">SEFAUtil</span></span>
<span data-ttu-id="df9b0-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="df9b0-595"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="df9b0-596">SEFAUtil (セカンダリ拡張機能機能のアクティブ化) は、Skype for Business Server 2015 コミュニケーション ソフトウェア管理者およびヘルプデスク エージェントが、Skype for Business Server 2015 ユーザーに代わって代理呼び出し、通話転送、同時呼び出し、チーム通話設定、およびグループ通話ピックアップを構成できるコマンド ライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="df9b0-597">また、このツールを使用すると、管理者は特定のユーザーに対して発行された通話ルーティング設定を照会できます。SEFAUtil ツールを使用すると、管理者はユーザーの代わりに通話転送または同時呼び出しを有効/無効/変更できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="df9b0-598">管理者は、(SIP URI の形式で) ターゲットを指定するか、ユーザーによって既に公開されているターゲットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="df9b0-599">また、このツールを使用すると、管理者はユーザーの代わりに代理人またはチーム通話グループ メンバーを追加または削除できます。このツールは、Microsoft Unified Communications Managed API (UCMA) 3.0 上に構築され、管理者が SEFAUtil の中央管理ストアで信頼できるアプリケーションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="df9b0-600">SEFAUtil (セカンダリ拡張機能機能のアクティブ化) を使用すると、Skype for Business Server 2015 管理者およびヘルプデスク エージェントは、Skype for Business Server 2015 ユーザーに代わって、代理人呼び出し、通話転送、同時呼び出し、チーム通話の設定、グループ通話ピックアップを構成できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="df9b0-601">また、このツールを使用すると、管理者は特定のユーザーに対して発行された通話ルーティング設定を照会できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="df9b0-602">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-602">Description</span></span>

<span data-ttu-id="df9b0-603">現在のバージョンの SEFAUtil はコマンド ライン ツールのみです。グラフィカル ユーザー インターフェイスはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="df9b0-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="df9b0-604">このツールは、Microsoft Unified Communications マネージ API (UCMA) 3.0 に基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="df9b0-605">このツールの機能を使用すると、管理者とヘルプデスク エージェントは次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="df9b0-606">ユーザーのすべての通話ルーティング設定を表示する (通話転送、委任、同時呼び出し、チーム通話、グループ通話ピックアップを含む)</span><span class="sxs-lookup"><span data-stu-id="df9b0-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="df9b0-607">通話転送の設定を有効/無効/変更する (宛先と応答なしタイマーを含む)</span><span class="sxs-lookup"><span data-stu-id="df9b0-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="df9b0-608">通話転送の即時構成を有効/無効/変更する</span><span class="sxs-lookup"><span data-stu-id="df9b0-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="df9b0-609">委任設定を有効/無効/変更する</span><span class="sxs-lookup"><span data-stu-id="df9b0-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="df9b0-610">チーム通話グループの設定を有効/無効/変更する</span><span class="sxs-lookup"><span data-stu-id="df9b0-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="df9b0-611">Skype for Business Server 2015 SEFAUtil ツールの新機能</span><span class="sxs-lookup"><span data-stu-id="df9b0-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="df9b0-612">同時呼び出し設定の有効化/無効化/変更 (宛先を含む)</span><span class="sxs-lookup"><span data-stu-id="df9b0-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="df9b0-613">Skype for Business Server 2015 SEFAUtil ツールの新機能</span><span class="sxs-lookup"><span data-stu-id="df9b0-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="df9b0-614">グループ通話ピックアップの設定を有効/無効/変更する</span><span class="sxs-lookup"><span data-stu-id="df9b0-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="df9b0-615">Skype for Business Server 2015 SEFAUtil ツールの新機能</span><span class="sxs-lookup"><span data-stu-id="df9b0-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="df9b0-616">このツールには、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="df9b0-617">Skype for Business Server プールに含むユーザーにのみサポート</span><span class="sxs-lookup"><span data-stu-id="df9b0-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="df9b0-618">複数のユーザーの通話ルーティング設定の一括編集はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="df9b0-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="df9b0-619">出力</span><span class="sxs-lookup"><span data-stu-id="df9b0-619">Output</span></span>

<span data-ttu-id="df9b0-620">このツールの現在のバージョンでは、コマンド プロンプト ウィンドウでのみ出力が提供されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-620">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="df9b0-621">詳細については、このドキュメントの「例」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df9b0-621">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="df9b0-622">用途</span><span class="sxs-lookup"><span data-stu-id="df9b0-622">Purpose</span></span>

<span data-ttu-id="df9b0-623">このツールを使用できる主なシナリオの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="df9b0-624">Bob はエグゼクティブであり、Skype for Business Server テレフォニーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="df9b0-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="df9b0-625">彼は既存の PBX システムに委任を持っています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="df9b0-626">Skype for Business Server 2015 への移行の一環として、管理者は、既存の委任構成を反映するように Bob のルーティングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="df9b0-627">Alice は旅行中で、顧客の 1 人からの重要な呼び出しを期待しているという認識を持っています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-627">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="df9b0-628">ただし、彼女はホテルにいて、コンピューターにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="df9b0-628">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="df9b0-629">ヘルプデスクを呼び出し、自分の携帯電話番号に転送し、自分の電話番号に対して行われたすべての呼び出しを要求します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-629">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="df9b0-630">ヘルプデスク担当者は、自分の代わりに構成を実行できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-630">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="df9b0-631">仕事の番号に対する Joe の呼び出しは、仕事中にモバイル ボイスメールに送信されます。ただし、他のほとんどの場所では正常に動作している場合があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="df9b0-632">ヘルプデスクの技術者は、Joe のルーティング構成を表示し、Joe が携帯電話に同時呼び出しを構成しているのを検出できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="df9b0-633">技術者は、Joe に自分のオフィスでのモバイル カバレッジについて尋ね、同時呼び出しルールが原因で、ネットワークのカバレッジが悪いときに Joe のモバイル ボイスメールに通話が送信される原因と判断できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="df9b0-634">マイクは Contoso の新入社員で、すべてのメンバーがチーム通話用に構成されている新しいチームに参加しています。Skype for Business Server 2015 が有効になっている場合、管理者はチーム通話グループ設定を設定して、新しいチーム メンバー全員を含め、さらに、管理者はチーム内の各メンバーのチーム通話グループ メンバーとしてマイクを追加します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="df9b0-635">Contoso の人事部門のカスタマー サービスプラクティスは、最初の呼び出し以降のすべての発信者に対して個人サービスを提供する方法です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="df9b0-636">部門のすべてのメンバーが互いに非常に近い場所に座っているので、チーム通話と同時にすべての電話が鳴り出すのは、チームの非常に破壊的です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="df9b0-637">チーム メンバーを中断することなく最高のサービスを提供するために、Skype for Business Server 2015 管理者はグループ通話ピックアップ機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="df9b0-638">管理者は、すべての部署メンバーをピックアップ グループに追加し、ピックアップ グループ番号を部署に伝達します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="df9b0-639">サマンサが机から不在の場合、ジョーは自分の電話が鳴っているのに気づき、机から電話に出る。</span><span class="sxs-lookup"><span data-stu-id="df9b0-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="df9b0-640">要件</span><span class="sxs-lookup"><span data-stu-id="df9b0-640">Requirements</span></span>

<span data-ttu-id="df9b0-641">SEFAUtil ツールは、信頼されたアプリケーション プールの一部であるコンピューターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-641">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="df9b0-642">UCMA 3.0 は、そのコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-642">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="df9b0-643">このツールを実行するには、SEFAUtil アプリケーション ID を持つ新しい信頼済みアプリケーションをそのプールに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-643">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="df9b0-644">SEFAUtil ツール用の新しい信頼済みアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="df9b0-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="df9b0-645">SEFAUTil ツールは、信頼できるアプリケーション プールの一部であるコンピューターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="df9b0-646">必要に応じて、新しい信頼できるアプリケーション プールとしてプールを追加するには、次のコマンドレットを使用して Skype for Business Server 管理シェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="df9b0-647">UCMA 3.0 は、SEFAUtil ツールの実行に使用するコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="df9b0-648">信頼できるアプリケーションは、SEFAUtil ツールのトポロジで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="df9b0-649">SEFAUtil を新しい信頼済みアプリケーションとして定義するには、Skype for Business Server 管理シェルを使用し、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="df9b0-650">必要に応じて、別のポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-650">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="df9b0-651">プール FQDN: SEFAUtil アプリケーションをホストするサーバーまたはプールの FQDN (通常は Skype for Business フロントエンド サーバーまたはプール>です)。</span><span class="sxs-lookup"><span data-stu-id="df9b0-651">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="df9b0-652">プール レジストラー FQDN: このアプリケーション プールに関連付けられている Skype for Business フロントエンド サーバーまたはプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="df9b0-652">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="df9b0-653">プール サイト: このプールがホームであるサイトのサイト ID。</span><span class="sxs-lookup"><span data-stu-id="df9b0-653">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="df9b0-654">トポロジの変更を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-654">The topology changes need to be enabled.</span></span> <span data-ttu-id="df9b0-655">トポロジの変更を有効にするには、次のコマンドレットを実行して Skype for Business Server 管理シェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-655">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="df9b0-656">必要に応じて、SEFAUtil ツールの実行に使用するサーバーに Skype for Business Server 2015 リソース キット ツールをインストールします (サーバーは信頼できるアプリケーション プールの一部である必要があります)。</span><span class="sxs-lookup"><span data-stu-id="df9b0-656">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="df9b0-657">SEFAUtil が正しく実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-657">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="df9b0-658">これを行うには、管理者特権を持つ Windows コマンド プロンプトからツールを実行して、展開でユーザーの通話転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-658">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="df9b0-659">既定では、ツールは "...\Program Files\Skype for Business Server 2015\Reskit" にあります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-659">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="df9b0-660">ユーザーの通話転送設定を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-660">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="df9b0-661">ユーザーの通話転送設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-661">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="df9b0-662">グループ通話ピックアップ</span><span class="sxs-lookup"><span data-stu-id="df9b0-662">Group Call Pickup</span></span>

<span data-ttu-id="df9b0-663">グループ通話ピックアップでは、機能を完全に有効にするためには、Skype for Business Server 2015 で追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-663">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="df9b0-664">ピックアップ グループをユーザーに割り当てる前に、この機能の計画と展開の手順については、グループ通話ピックアップ製品のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df9b0-664">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="df9b0-665">例</span><span class="sxs-lookup"><span data-stu-id="df9b0-665">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="df9b0-666">現在の通話処理の設定を表示する</span><span class="sxs-lookup"><span data-stu-id="df9b0-666">Display Current Call Handling Settings</span></span>

<span data-ttu-id="df9b0-667">次のコマンドは、ユーザーの呼び出し処理を表示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-667">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="df9b0-668">この例では **、/server スイッチを** 使用して、接続する Skype for Business Server を指定します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-668">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="df9b0-669">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-669">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="df9b0-670">[転送/ 応答なし] の宛先を設定する</span><span class="sxs-lookup"><span data-stu-id="df9b0-670">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="df9b0-671">次の使用例は、通話転送/応答先なしと呼び出し遅延を設定します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-671">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="df9b0-672">ここでは、/server スイッチは提供されません。SEFAUtil は、Skype for Business Server 2015 の自動検出を試行します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-672">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 <span data-ttu-id="df9b0-673">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-673">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="df9b0-674">通話転送をすぐに有効にする</span><span class="sxs-lookup"><span data-stu-id="df9b0-674">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="df9b0-675">この例では、別のユーザーへの通話転送を直ちに有効にします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-675">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="df9b0-676">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="df9b0-677">通話転送を直ちに無効にする</span><span class="sxs-lookup"><span data-stu-id="df9b0-677">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="df9b0-678">この例では、通話転送を直ちに無効にします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-678">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 <span data-ttu-id="df9b0-679">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="df9b0-680">代理人としてユーザーを追加し、代理人の同時呼び出しを設定する</span><span class="sxs-lookup"><span data-stu-id="df9b0-680">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="df9b0-681">この例では、ユーザーを代理人として追加し、代理人の同時呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-681">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="df9b0-682">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="df9b0-683">代理人の同時呼び出しルールの変更</span><span class="sxs-lookup"><span data-stu-id="df9b0-683">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="df9b0-684">次の使用例は、前の例で設定した同時呼び出しルールを遅延呼び出しルールに変更します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-684">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="df9b0-685">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="df9b0-686">代理人を削除する</span><span class="sxs-lookup"><span data-stu-id="df9b0-686">Remove the Delegate</span></span>

<span data-ttu-id="df9b0-687">次の使用例は、代理人を削除します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-687">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="df9b0-688">最後の代理人が削除されると、代理人の呼び出しは自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-688">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="df9b0-689">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-689">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="df9b0-690">代理人を追加し、委任ルールにCall-Forwardを設定する</span><span class="sxs-lookup"><span data-stu-id="df9b0-690">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="df9b0-691">次の使用例は、代理人を追加し、代理人ルールへの呼び出し転送を設定します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-691">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="df9b0-692">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="df9b0-693">同時呼び出しを有効にして宛先番号を設定する</span><span class="sxs-lookup"><span data-stu-id="df9b0-693">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="df9b0-694">この例では、同時呼び出しを有効にし、同時呼び出し先番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-694">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="df9b0-695">同時呼び出しが有効になっているユーザーの同時呼び出し先番号を変更するには、/enabledimulring スイッチを使用してコマンドを保持し、それ以外の場合は宛先番号は変更されません。</span><span class="sxs-lookup"><span data-stu-id="df9b0-695">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="df9b0-696">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-696">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="df9b0-697">同時呼び出しを無効にする</span><span class="sxs-lookup"><span data-stu-id="df9b0-697">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="df9b0-698">次の使用例は、同時呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-698">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="df9b0-699">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="df9b0-700">グループのチーム メンバーを追加Team-Callメンバー グループに同時呼び出しTeam-Call設定する</span><span class="sxs-lookup"><span data-stu-id="df9b0-700">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="df9b0-701">次の使用例は、チーム メンバーをユーザーのチーム通話グループに追加し、チーム通話グループへの同時呼び出しを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-701">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="df9b0-702">ユーザーのチーム通話グループにメンバーを追加すると、ユーザーの同時呼び出し設定が自動的に切り替えて、チーム通話グループを同一化します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-702">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="df9b0-703">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-703">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="df9b0-704">グループからメンバーをTeam-Callする</span><span class="sxs-lookup"><span data-stu-id="df9b0-704">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="df9b0-705">次の使用例は、ユーザーのチーム通話グループのチーム メンバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-705">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="df9b0-706">削除するメンバーがチーム通話グループの唯一のメンバーである場合は、同時にチーム通話グループに呼び出し音が自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-706">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="df9b0-707">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-707">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="df9b0-708">遅延リングをグループにTeam-Callする</span><span class="sxs-lookup"><span data-stu-id="df9b0-708">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="df9b0-709">次の使用例は、遅延リングをチーム通話グループの時間設定に変更します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-709">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="df9b0-710">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="df9b0-711">[有効Team-Call</span><span class="sxs-lookup"><span data-stu-id="df9b0-711">Enable Team-Call</span></span>

<span data-ttu-id="df9b0-712">この例では、特定のユーザーに対してチーム呼び出しを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-712">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="df9b0-713">ユーザーのチーム通話グループにメンバーがない場合、チーム通話は有効になりません。</span><span class="sxs-lookup"><span data-stu-id="df9b0-713">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="df9b0-714">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-714">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="df9b0-715">無効にするTeam-Call</span><span class="sxs-lookup"><span data-stu-id="df9b0-715">Disable Team-Call</span></span>

<span data-ttu-id="df9b0-716">この例では、特定のユーザーのチーム呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-716">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="df9b0-717">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-717">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="df9b0-718">グループ通話ピックアップの有効化とピックアップ グループのユーザーへの割り当て</span><span class="sxs-lookup"><span data-stu-id="df9b0-718">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="df9b0-719">次の使用例は、ピックアップ グループをユーザーに割り当て、グループ通話ピックアップを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-719">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="df9b0-720">**出力**</span><span class="sxs-lookup"><span data-stu-id="df9b0-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="df9b0-721">グループ通話ピックアップを無効にする</span><span class="sxs-lookup"><span data-stu-id="df9b0-721">Disable Group Call Pickup</span></span>

<span data-ttu-id="df9b0-722">この例では、特定のユーザーのグループ通話ピックアップを無効にします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-722">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="df9b0-723">ユーザーのグループ通話ピックアップを無効にすると、ユーザーに割り当てられたグループ番号は保持されません。</span><span class="sxs-lookup"><span data-stu-id="df9b0-723">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="df9b0-724">その後、そのユーザーのグループ通話ピックアップを再度有効にする場合は、/enablegrouppickup スイッチでグループ番号を再度割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-724">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="df9b0-725">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="df9b0-725">SYSPrep.ps1</span></span>
<span data-ttu-id="df9b0-726"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="df9b0-726"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="df9b0-727">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-727">Description</span></span>

<span data-ttu-id="df9b0-728">SYSPrep.ps1は、次Windows PowerShell Skype for Business Server 2015 の前提条件を Windows Server 2008 オペレーティング システム コンピューターにインストールするスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-728">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="df9b0-729">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="df9b0-729">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="df9b0-730">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="df9b0-730">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="df9b0-731">Windows Powershell バージョン 3.0</span><span class="sxs-lookup"><span data-stu-id="df9b0-731">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="df9b0-732">Visual C++ 2010 再頒布可能</span><span class="sxs-lookup"><span data-stu-id="df9b0-732">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="df9b0-733">インターネット インフォメーション サーバーの更新</span><span class="sxs-lookup"><span data-stu-id="df9b0-733">Internet Information Server Updates</span></span>

- <span data-ttu-id="df9b0-734">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="df9b0-734">Windows Identity Foundation</span></span>

- <span data-ttu-id="df9b0-735">Skype for Business Server 2015 Core ファイル</span><span class="sxs-lookup"><span data-stu-id="df9b0-735">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="df9b0-736">スクリプト名は Microsoft Windows オペレーティング システムのシステム準備ツールに似ていますが、異なります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-736">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="df9b0-737">このスクリプトは、Skype for Business Server 2015 に必要な前提条件のみをインストールします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-737">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="df9b0-738">これらの前提条件がインストールされた後、Windows SYSPrep ツールを使用してサーバーのイメージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-738">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="df9b0-739">要件</span><span class="sxs-lookup"><span data-stu-id="df9b0-739">Requirements</span></span>

<span data-ttu-id="df9b0-740">SYSPrep.ps1 スクリプトを実行する前に、前提条件ファイルを Windows Server 2008 オペレーティング システム コンピューターのローカル フォルダー **(D:\Setup など) にコピーする必要があります**。</span><span class="sxs-lookup"><span data-stu-id="df9b0-740">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="df9b0-741">このフォルダーには、Skype for Business Server 2015 ファイルのコピーも含 **める必要Setup.exe。**</span><span class="sxs-lookup"><span data-stu-id="df9b0-741">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="df9b0-742">前提条件ファイルは、次の場所からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-742">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="df9b0-743">**前提条件**</span><span class="sxs-lookup"><span data-stu-id="df9b0-743">**Prerequisite**</span></span>                                | <span data-ttu-id="df9b0-744">**Location**</span><span class="sxs-lookup"><span data-stu-id="df9b0-744">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="df9b0-745">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="df9b0-745">Microsoft .Net Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="df9b0-746">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="df9b0-746">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="df9b0-747">Windows Powershell バージョン 3.0</span><span class="sxs-lookup"><span data-stu-id="df9b0-747">Windows Powershell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="df9b0-748">Visual C++ 2010 再頒布可能</span><span class="sxs-lookup"><span data-stu-id="df9b0-748">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="df9b0-749">インターネット インフォメーション サーバーの更新</span><span class="sxs-lookup"><span data-stu-id="df9b0-749">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="df9b0-750">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="df9b0-750">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="df9b0-751">Skype for Business Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="df9b0-751">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="df9b0-752">Skype for Business Server 2015 メディアからのコピー</span><span class="sxs-lookup"><span data-stu-id="df9b0-752">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="df9b0-753">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df9b0-753">Parameter</span></span>

<span data-ttu-id="df9b0-754">**-SetupFolder パラメーターは**、必須ファイルのディレクトリの場所を引数として受け取ります</span><span class="sxs-lookup"><span data-stu-id="df9b0-754">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="df9b0-755">例</span><span class="sxs-lookup"><span data-stu-id="df9b0-755">Examples</span></span>

<span data-ttu-id="df9b0-756">このスクリプトをSYSPrep.ps1し、Skype for Business Server 2015 の前提条件をインストールするには、管理者特権でコマンド プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-756">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="df9b0-757">割り当てられていない番号のお知らせの移行</span><span class="sxs-lookup"><span data-stu-id="df9b0-757">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="df9b0-758"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="df9b0-758"><a name="UNAM"> </a></span></span>

<span data-ttu-id="df9b0-759">[割り当てられていない番号のお知らせの移行] ツールを使用すると、Skype for Business Server 2015 管理者は、アナウンス アプリケーションによってサービスされる割り当てられていない番号構成を、送信元の Skype for Business Server または Pool から宛先 Skype for Business Server または Pool に移動できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-759">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="df9b0-760">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-760">Description</span></span>

<span data-ttu-id="df9b0-761">[割り当てられていない番号のお知らせ] 移行ツールは、ソース サーバーまたはプールのアナウンス アプリケーションによってサービスされる割り当てられていない番号構成を別のサーバーまたはプールに移動する Windows PowerShell スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-761">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="df9b0-762">実行すると、[割り当てられていない番号のお知らせ] 移行スクリプトは、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-762">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="df9b0-763">ソース サーバーまたはプールでホストされているアナウンス アプリケーションの割り当てられていない番号アナウンスで使用されるオーディオ ファイルを、移行先サーバーまたはプールのファイル ストアに移動します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-763">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df9b0-764">オーディオ ファイルは、コピー先プールにコピーされると、ソース プールから削除されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-764">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="df9b0-765">送信元サーバーまたはプールでホストされているアナウンス アプリケーション用に構成された割り当てられていない番号アナウンスを、すべて移行先のサーバーまたはプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-765">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="df9b0-766">送信元サーバーまたはプールでホストされているアナウンス アプリケーションによってサービスされる割り当てられていない番号範囲を、宛先サーバーまたはプールに再割り当てします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-766">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="df9b0-767">スクリプトを正常に実行すると、ソース サーバーまたはプールでホストされているアナウンス アプリケーションによってサービスされた割り当てられていない番号範囲はすべて、宛先サーバーまたはプールによって同じ構成で処理されます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-767">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="df9b0-768">出力</span><span class="sxs-lookup"><span data-stu-id="df9b0-768">Output</span></span>

<span data-ttu-id="df9b0-769">**Move-CsAnnouncementConfiguration** スクリプトは、Skype for Business Server 管理シェル ウィンドウで、移行操作の成功または失敗を実行した場所を示します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-769">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="df9b0-770">操作の実行がエラーによって中断された場合、宛先に正常に移動された割り当てられていない番号範囲は、運用フォーム内の移動先に残り、移行する割り当てられていない番号範囲の残りの部分は、運用フォームのソースにも残ります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-770">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="df9b0-771">構成の残りの部分を完全に移行するには、エラーに対処した後、スクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-771">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="df9b0-772">用途</span><span class="sxs-lookup"><span data-stu-id="df9b0-772">Purpose</span></span>

<span data-ttu-id="df9b0-773">[割り当てられていない番号のお知らせ] 移行スクリプトは、次の 3 つのシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-773">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="df9b0-774">**Skype for Business Server の新しいバージョンへの構成設定の移行:** Contoso は Skype for Business Server 2015 に移行中であり、移行プロセスの一環として、Skype for Business Server 管理者はアナウンス アプリケーションによってサービスされる割り当てられていない番号構成を Lync Server 2013 展開から新しい Skype for Business Server 2015 展開に移動します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-774">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="df9b0-775">構成設定を移動するには、Skype for Business Server 管理者が割り当てられていない番号アナウンス移行ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-775">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="df9b0-776">**Skype for Business Server 2015 から Lync Server 2013** への展開のロールバック:予期しない要因により、Contoso 社は新しい Skype for Business Server 2015 展開への移行をロールバックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-776">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="df9b0-777">サービスの中断を最小限に抑えるために、Skype for Business Server 管理者は、割り当てられていない番号アナウンス移行ツールを使用して、構成を Skype for Business Server 2015 展開から Lync Server 2013 展開にロールバックします。</span><span class="sxs-lookup"><span data-stu-id="df9b0-777">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="df9b0-778">**展開間でのデータの移動:** Contoso は、1 つのプールのすべてのサーバーを新しいサーバーに置き換える過程にいます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-778">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="df9b0-779">その戦略は、新しい Skype for Business Server 2015 プールを展開し、すべてのデータを古いプールから新しいプールに移動してから、古いプールを非推奨にすることです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-779">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="df9b0-780">新しいプールを展開すると、[割り当てられていない番号のお知らせの移行] ツールを使用して、構成を古いプールから新しいプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-780">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="df9b0-781">要件</span><span class="sxs-lookup"><span data-stu-id="df9b0-781">Requirements</span></span>

<span data-ttu-id="df9b0-782">ツールを正常に実行するために必要な主な要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df9b0-782">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="df9b0-783">このスクリプトは、Skype for Business Server 管理シェルがインストールされているコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-783">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="df9b0-784">アナウンス アプリケーションは、送信元と送信先の Skype for Business Servers またはプールに正常に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-784">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="df9b0-785">Move-CsAnnouncementConfiguration スクリプト</span><span class="sxs-lookup"><span data-stu-id="df9b0-785">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="df9b0-786">次Move-CsAnnouncementConfigurationスクリプトには、次の表に示す 2 つのパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-786">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Move-CsAnnouncementConfigurationパラメーター。](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="df9b0-788">例</span><span class="sxs-lookup"><span data-stu-id="df9b0-788">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="df9b0-789">割り当てられていない番号アナウンス構成を Lync Server 2013 プールから Skype for Business Server 2015 プールに移動する</span><span class="sxs-lookup"><span data-stu-id="df9b0-789">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="df9b0-790">次の使用例は、割り当てられていない番号アナウンスをソース プール (Lync Server 2013) から宛先プール (Skype for Business Server 2015) に移動します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-790">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="df9b0-791">割り当てられていない番号アナウンス構成を Skype for Business Server 2015 プールから Lync Server 2013 プールに移動する</span><span class="sxs-lookup"><span data-stu-id="df9b0-791">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="df9b0-792">次の使用例は、割り当てられていない番号アナウンスをソース プール (Skype for Business Server 2015) から宛先プール (Lync Server 2013) に移動します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-792">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="df9b0-793">Web Conf データ</span><span class="sxs-lookup"><span data-stu-id="df9b0-793">Web Conf Data</span></span>
<span data-ttu-id="df9b0-794"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="df9b0-794"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="df9b0-795">Web Conf Data Tool を使用すると、Skype for Business Server 2015 コミュニケーション ソフトウェアの管理者は、オーガナイザーの Web 会議に関連付けられたデータを詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-795">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="df9b0-796">シナリオには、タイム スタンプ条件に基づいて特定のユーザーの会議データを削除する機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-796">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="df9b0-797">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-797">Description</span></span>

<span data-ttu-id="df9b0-798">このツールを使用すると、管理者は次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="df9b0-798">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="df9b0-799">1 人のユーザーに関連付けられているすべての Web 会議データを検索します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-799">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="df9b0-800">1 人のユーザーに関連付けられているすべての Web 会議データを削除します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-800">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="df9b0-801">特定の日付より古い単一のユーザーに関連付けられているすべての Web 会議データを削除します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="df9b0-802">1 人のユーザーに関連付けられているすべての Web 会議データを、そのユーザーがプール間で移動するときに移動します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df9b0-803">Lync Server 2010 のリソース キット ツールでは、そのユーザーがプール間で移動するときに、1 人のユーザーに関連付けられているすべての Web 会議データの移動がサポートされました。</span><span class="sxs-lookup"><span data-stu-id="df9b0-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="df9b0-804">この機能は **、MoveConferenceData** パラメーターを優先して、このツールから廃止されました。</span><span class="sxs-lookup"><span data-stu-id="df9b0-804">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="df9b0-805">このパラメーターの詳細については [、Move-CsUser コマンドレットを参照](/powershell/module/skype/move-csuser.md?view=skype-ps) してください。</span><span class="sxs-lookup"><span data-stu-id="df9b0-805">For details about this parameter, see the [Move-CsUser](/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="df9b0-806">ツールは、非アクティブな会議の会議データのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="df9b0-807">アクティブな会議 (またはセッション内の会議) は削除できません。</span><span class="sxs-lookup"><span data-stu-id="df9b0-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="df9b0-808">このツールは、ターゲット ユーザーと同じプール内にあるコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="df9b0-809">このツールによって会議コンテンツ データが管理されているユーザーは、同じユーザー プールに保存されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="df9b0-810">出力</span><span class="sxs-lookup"><span data-stu-id="df9b0-810">Output</span></span>

<span data-ttu-id="df9b0-811">このツールは、各操作の結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-811">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="df9b0-812">クエリが実行された場合、このツールは、そのユーザーをオーガナイザーとして持つすべての非アクティブな会議データ フォルダーの一覧を出力します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="df9b0-813">削除が実行された場合、ツールは、データが削除されるすべての会議データ フォルダーの一覧を出力します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="df9b0-814">要件</span><span class="sxs-lookup"><span data-stu-id="df9b0-814">Requirements</span></span>

<span data-ttu-id="df9b0-815">このツールは、現在開催者が参加している同じプールで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="df9b0-816">このツールは、コンテンツ ファイル ストアへのアクセス権を持つ管理者特権を使用して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="df9b0-817">例</span><span class="sxs-lookup"><span data-stu-id="df9b0-817">Examples</span></span>

<span data-ttu-id="df9b0-818">次の表では、パラメーターについて説明します。その一部は例で使用されています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-818">The following table describes the parameters, some of which are used in the examples.</span></span>

![Web Conf データ ツールのパラメーター。](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="df9b0-820">前の例は、クエリ コマンドの動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="df9b0-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="df9b0-821">このようなコマンドの出力は、このツールの影響を受けるすべての会議コンテンツ フォルダーの一覧になります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="df9b0-822">前の例は、削除コマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="df9b0-823">削除コマンドは、このユーザーから非アクティブなすべての会議フォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="df9b0-823">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="df9b0-824">概要</span><span class="sxs-lookup"><span data-stu-id="df9b0-824">Summary</span></span>

<span data-ttu-id="df9b0-825">このツールは、会議の会議データを正確に制御する必要がある管理者にとって貴重なリソースになります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>