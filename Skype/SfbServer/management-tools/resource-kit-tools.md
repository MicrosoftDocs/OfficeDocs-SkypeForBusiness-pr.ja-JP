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
description: このトピックでは、Skype for Business Server 2015 リソース キットのツールについて、各ツールの目的と使用例を含めて説明します。 Skype for Business Server 2015 リソース キットは、Skype for Business Server 2015 を展開および管理する IT 管理者が日常的な作業を容易にするのに役立ちます。 たとえば、Web Conf Data ツールを使用すると、オンライン会議中にユーザーがアップロードしたデータを簡単に制御できます。 SEFAUtil ツールを使用して、ユーザーの代理呼び出しの転送と応答を設定できます。 IT 管理者は、これらのツールを使用して Skype for Business Server 2015 の管理を効果的に行う必要があります。
ms.openlocfilehash: bf1a1d946c998466b118e0ab2038044a48d90970
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822037"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="c9b18-107">Skype for Business Server 2015 リソース キット ツールのドキュメント</span><span class="sxs-lookup"><span data-stu-id="c9b18-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="c9b18-108">このトピックでは、Skype for Business Server 2015 リソース キットのツールについて、各ツールの目的と使用例を含めて説明します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="c9b18-109">Skype for Business Server 2015 リソース キットは、Skype for Business Server 2015 を展開および管理する IT 管理者が日常的な作業を容易にするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="c9b18-110">たとえば **、Web Conf Data** ツールを使用すると、オンライン会議中にユーザーがアップロードしたデータを簡単に制御できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="c9b18-111">**SEFAUtil ツールを** 使用して、ユーザーの代理呼び出しの転送と応答を設定できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="c9b18-112">IT 管理者は、これらのツールを使用して Skype for Business Server 2015 の管理を効果的に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="c9b18-113">リソース キット ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="c9b18-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="c9b18-114">Skype for Business Server 2015 リソース キットをインストールするには、ダウンロード [ センターから ](https://www.microsoft.com/download/details.aspx?id=52631)OCSReskit.msiをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="c9b18-115">この **OCSResKit.msi** を実行して、簡単なインストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="c9b18-116">.msi は **、%Program Files%\Skype for Business Server 2015\ResKit** というパスのすべてのツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="c9b18-117">自己格納型の実行可能ファイルであるツールは、このフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="c9b18-118">サポート ファイルも含むツールは、独自のサブフォルダーに含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="c9b18-119">サポートされる環境</span><span class="sxs-lookup"><span data-stu-id="c9b18-119">Supported Environments</span></span>

<span data-ttu-id="c9b18-120">Skype for Business Server 2015 リソース キットは、Skype for Business Server 2015 (通常は Skype for Business Server 2015 の実行に使用される) に必要な仕様を満たすサーバーにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="c9b18-121">リソース キット ツールの概要</span><span class="sxs-lookup"><span data-stu-id="c9b18-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="c9b18-122">Skype for Business Server 2015 リソース キットに用意されているツールの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="c9b18-123">要件や使用例など、各ツールの説明については、以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="c9b18-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="c9b18-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="c9b18-125">帯域幅ポリシー サービス モニター</span><span class="sxs-lookup"><span data-stu-id="c9b18-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="c9b18-126">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="c9b18-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="c9b18-127">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="c9b18-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="c9b18-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="c9b18-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="c9b18-129">ストレージ サービス データのインポート</span><span class="sxs-lookup"><span data-stu-id="c9b18-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="c9b18-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="c9b18-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="c9b18-131">ユーザー コンソールを参照する</span><span class="sxs-lookup"><span data-stu-id="c9b18-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="c9b18-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="c9b18-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="c9b18-133">ネットワーク構成ビューアー</span><span class="sxs-lookup"><span data-stu-id="c9b18-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="c9b18-134">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="c9b18-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="c9b18-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="c9b18-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="c9b18-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="c9b18-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="c9b18-137">割り当てられていない番号アナウンスの移行</span><span class="sxs-lookup"><span data-stu-id="c9b18-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="c9b18-138">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="c9b18-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="c9b18-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="c9b18-139">ABSConfig</span></span>
<span data-ttu-id="c9b18-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="c9b18-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="c9b18-141">アドレス帳サービス構成ツール (ABSConfig) は、管理者が Skype for Business Server 2015 のアドレス帳サービス構成をカスタマイズするのに役立つ管理ツールです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="c9b18-142">また、このツールを使用すると、Skype for Business Server 2015 管理者は既定のアドレス帳サービス設定を復元できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="c9b18-143">説明</span><span class="sxs-lookup"><span data-stu-id="c9b18-143">Description</span></span>

<span data-ttu-id="c9b18-144">ABSConfig は、管理者がアドレス帳サービスに関連する Active Directory ドメイン サービス属性を構成できるグラフィカル ユーザー インターフェイス アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="c9b18-145">このツールの主なシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="c9b18-146">管理者が Active Directory ドメイン サービスの属性を Skype for Business Server 2015 の属性にマップできる。</span><span class="sxs-lookup"><span data-stu-id="c9b18-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="c9b18-147">管理者がアドレス帳サービス ファイルに含める、または除外する Active Directory ドメイン サービス属性を指定する。</span><span class="sxs-lookup"><span data-stu-id="c9b18-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="c9b18-148">管理者が既定のアドレス帳サービスの設定を復元する。</span><span class="sxs-lookup"><span data-stu-id="c9b18-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="c9b18-149">ABSConfig ツールは、次のファイルを使用ABSConfig.exeできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="c9b18-150">ツールが開き、[属性の構成 **] タブが開** きます。この表には、Active Directory ドメイン サービスの属性を Skype for Business Server 2015 の属性フィールドにマップするオプションと、特定の属性フィルターに基づいてアドレス帳サービス ファイルに含めるユーザーまたは除外するユーザーを指定するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="c9b18-151">また、アドレス帳ファイルに含める電話番号の値をカスタマイズするオプションも用意されています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="c9b18-152">[ **既定値に戻す]** オプションを使用すると、管理者はアドレス帳サービスの設定を既定値に復元できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="c9b18-153">異なる OC フィールド名への AD 属性の再マッピングは、アドレス帳ファイルのダウンロードでのみ機能し、アドレス帳 Web クエリではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c9b18-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="c9b18-154">出力</span><span class="sxs-lookup"><span data-stu-id="c9b18-154">Output</span></span>

<span data-ttu-id="c9b18-155">ABSConfig は、アドレス帳サービス構成をデータベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="c9b18-156">用途</span><span class="sxs-lookup"><span data-stu-id="c9b18-156">Purpose</span></span>

<span data-ttu-id="c9b18-157">ABSConfig は、Skype for Business Server 2015 アドレス帳サービスをカスタマイズするための迅速かつ簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="c9b18-158">要件</span><span class="sxs-lookup"><span data-stu-id="c9b18-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="c9b18-159">コンピューター</span><span class="sxs-lookup"><span data-stu-id="c9b18-159">Computer</span></span>

<span data-ttu-id="c9b18-160">ABSConfig は、Skype for Business Server 2015 がインストールされているドメインに参加しているコンピューターからのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="c9b18-161">Skype for Business Server 2015 Enterprise Edition の場合、このツールは、セットアップ中にアドレス帳サービスが有効になっているフロントエンド サーバーで実行できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="c9b18-162">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="c9b18-162">Network</span></span>

<span data-ttu-id="c9b18-163">コンピューターは、フロントエンド プールとバック エンド データベースに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="c9b18-164">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="c9b18-164">Software</span></span>

<span data-ttu-id="c9b18-165">ABSConfig ツールを実行する前に、次のソフトウェア コンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="c9b18-166">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c9b18-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="c9b18-167">ユーザー</span><span class="sxs-lookup"><span data-stu-id="c9b18-167">Users</span></span>

<span data-ttu-id="c9b18-168">Skype for Business Server 2015 展開の更新に必要なアクセス許可を持つ管理者。</span><span class="sxs-lookup"><span data-stu-id="c9b18-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="c9b18-169">例</span><span class="sxs-lookup"><span data-stu-id="c9b18-169">Examples</span></span>

<span data-ttu-id="c9b18-170">ABSConfig を開始するには、コマンド プロンプト **でABSConfig.exe** 入力します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="c9b18-171">ABSConfig ツールのユーザー インターフェイスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-171">Shown below is the ABSConfig tool user interface.</span></span>

![次ABSConfig.exeツール。](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="c9b18-173">概要</span><span class="sxs-lookup"><span data-stu-id="c9b18-173">Summary</span></span>

<span data-ttu-id="c9b18-174">ABSConfig ツールを使用すると、管理者は Skype for Business Server 2015 アドレス帳サービスを迅速かつ簡単にカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="c9b18-175">帯域幅ポリシー サービス モニター</span><span class="sxs-lookup"><span data-stu-id="c9b18-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="c9b18-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="c9b18-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="c9b18-177">Bandwidth Policy Service Monitor ツールは、管理者が次の一覧を表示することを目的とします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="c9b18-178">トポロジで構成済みのすべての Skype for Business Server 2015 帯域幅ポリシー サービス (認証とコア)</span><span class="sxs-lookup"><span data-stu-id="c9b18-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="c9b18-179">各サービスが他の帯域幅ポリシー サービスおよびエッジ サーバーに対して行う接続</span><span class="sxs-lookup"><span data-stu-id="c9b18-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="c9b18-180">ネットワーク構成ドキュメントで構成されているリンクすべてと、各帯域幅ポリシー サービスによって報告されるリアルタイムの帯域幅使用量</span><span class="sxs-lookup"><span data-stu-id="c9b18-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="c9b18-181">説明</span><span class="sxs-lookup"><span data-stu-id="c9b18-181">Description</span></span>

<span data-ttu-id="c9b18-182">Bandwidth Policy Service Monitor ツールは、GUI ベースのアプリケーションとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="c9b18-183">管理者は、次のコマンドを実行してツールPDPMonUI.exe。</span><span class="sxs-lookup"><span data-stu-id="c9b18-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="c9b18-184">ツールが起動すると、トポロジ内の帯域幅ポリシー サービスの一覧の検出が試行されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="c9b18-185">最初の更新が完了すると、ウィンドウの左側のウィンドウに、属するクラスターによってグループ化されたサービスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="c9b18-186">管理者が特定の帯域幅ポリシー サービスを選択すると、右側のウィンドウに特定のサービスに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="c9b18-187">このウィンドウには、情報を表示する 2 つのメイン タブがあります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="c9b18-188">[コンピューター情報] タブ</span><span class="sxs-lookup"><span data-stu-id="c9b18-188">Machine Info Tab</span></span>

<span data-ttu-id="c9b18-189">[ **コンピューター情報** ] タブには、選択されている帯域幅ポリシー サービスの詳細と、選択した帯域幅ポリシー サービスが他のサービスに対して行ったすべての接続の一覧と状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="c9b18-190">[トポロジ情報] タブ</span><span class="sxs-lookup"><span data-stu-id="c9b18-190">Topology Info Tab</span></span>

<span data-ttu-id="c9b18-191">[ **トポロジ情報] タブ** には、ネットワーク構成設定で構成されているリンクの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="c9b18-192">各リンクについて、音声とビデオの帯域幅容量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="c9b18-193">さらに、現在利用されている帯域幅は、Kbps と容量の割合の両方で表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="c9b18-194">ツールは、容量に近い使用率を持つリンクを強調表示するために色分け機能を使用します。これにより、管理者はこのようなリンクをすばやく分離できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="c9b18-195">帯域幅ポリシー サービス モニター ツールが構成済みの帯域幅ポリシー サービスに接続するときに障害が発生した場合、[コンピューター情報]タブと [トポロジ情報] タブの情報は入力されません。</span><span class="sxs-lookup"><span data-stu-id="c9b18-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="c9b18-196">ただし、ツールが最初に接続した後にサービスへの接続が失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="c9b18-197">このような場合、管理者には古い情報が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="c9b18-198">各タブ **には、** 特定の帯域幅ポリシー サービスのデータが最後に更新された時刻を管理者が確認できる最終更新タイム スタンプがあります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="c9b18-199">出力</span><span class="sxs-lookup"><span data-stu-id="c9b18-199">Output</span></span>

<span data-ttu-id="c9b18-200">コマンド ライン出力はありません。プログラム出力は、メインのグラフィカル ユーザー インターフェイス (GUI) に含まれる。</span><span class="sxs-lookup"><span data-stu-id="c9b18-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="c9b18-201">用途</span><span class="sxs-lookup"><span data-stu-id="c9b18-201">Purpose</span></span>

<span data-ttu-id="c9b18-202">Bandwidth Policy Service Monitor ツールの目的は、管理者がトポロジで定義されている各帯域幅ポリシー サービスの状態を確認できるようです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="c9b18-203">また、管理者は、ネットワーク構成ドキュメントで定義されているリンクすべてについて、リアルタイムの帯域幅の使用状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="c9b18-204">要件</span><span class="sxs-lookup"><span data-stu-id="c9b18-204">Requirements</span></span>

<span data-ttu-id="c9b18-205">Bandwidth Policy Service Monitor ツールは、Skype for Business Server トポロジの一部であるコンピューターで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="c9b18-206">概要</span><span class="sxs-lookup"><span data-stu-id="c9b18-206">Summary</span></span>

<span data-ttu-id="c9b18-207">帯域幅ポリシー サービス モニター ツールは、管理者がトポロジ内のすべての帯域幅ポリシー サービスの状態を検査し、さらに重要な点として、ネットワーク構成設定で定義されているリンクの帯域幅使用率をリアルタイムで取得できるような、重要なリソースです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="c9b18-208">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="c9b18-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="c9b18-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="c9b18-209"><a name="bua"> </a></span></span>

<span data-ttu-id="c9b18-210">Bandwidth Utilization Analyzer は、エンタープライズ ネットワーク内の WAN リンクを通して UC エンドポイントによる帯域幅消費のさまざまなビューに関するレポートを作成するツールです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="c9b18-211">これらのレポートは、現在の帯域幅消費パターンを理解し、帯域幅容量の計画を支援するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="c9b18-212">説明</span><span class="sxs-lookup"><span data-stu-id="c9b18-212">Description</span></span>

<span data-ttu-id="c9b18-213">Bandwidth Utilization Analyzer は、GUI ベースのアプリケーションとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="c9b18-214">このツールは、ネットワーク全体の音声使用率に関するレポートを生成し、容量計画に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="c9b18-215">また、さまざまなリンクに割り当てられている帯域幅容量に対して反復処理も行います。</span><span class="sxs-lookup"><span data-stu-id="c9b18-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="c9b18-216">出力</span><span class="sxs-lookup"><span data-stu-id="c9b18-216">Output</span></span>

<span data-ttu-id="c9b18-217">Bandwidth Utilization Analyzer は、システムで構成されている WAN リンクすべてについて、帯域幅容量と音声の使用率のグラフィック プロットを提供します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="c9b18-218">用途</span><span class="sxs-lookup"><span data-stu-id="c9b18-218">Purpose</span></span>

<span data-ttu-id="c9b18-219">音声およびビデオの展開では、エンタープライズ ネットワーク全体のメディア トラフィックの帯域幅使用率の傾向を監視し、把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="c9b18-220">Bandwidth Utilization Analyzer ツールを使用すると、管理者はこれを実現できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="c9b18-221">このツールは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-221">This tool does the following:</span></span>

- <span data-ttu-id="c9b18-222">ネットワーク全体の音声使用率に関する特定のレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="c9b18-223">より効果的な容量計画と、さまざまなリンクに割り当てられた帯域幅容量の反復に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="c9b18-224">Bandwidth Utilization Analyzer は、帯域幅容量と使用率レポートのグラフィカル プロットを生成できます。これらは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="c9b18-225">エンタープライズ ネットワーク内のすべての WAN リンク</span><span class="sxs-lookup"><span data-stu-id="c9b18-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="c9b18-226">選択された WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="c9b18-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="c9b18-227">リンク容量を超えた WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="c9b18-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="c9b18-228">プロビジョニングされた帯域幅の利用が低い WAN リンクでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="c9b18-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="c9b18-229">重要なレベルに達している WAN リンク (WAN リンクの帯域幅容量の 90% を超える帯域幅使用率) でフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c9b18-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="c9b18-230">WAN リンクの種類 (ネットワーク サイト リンク、エリア間リンク、サイト内のリンク) でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="c9b18-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="c9b18-231">ネットワーク地域でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="c9b18-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="c9b18-232">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c9b18-232">Applications</span></span>

<span data-ttu-id="c9b18-233">Bandwidth Utilization Analyzer には、次の 2 つのアプリケーション (ツール) があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="c9b18-234">**WanLinkLogCollector.exe** このツールを使用すると、ユーザーは必要な情報を入力できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="c9b18-235">**BandwidthUtilizationAnalyzer.xlsm** Microsoft Excel スプレッドシート ソフトウェア レポートは、ユーザーが自動的に起動WanLinkLogCollector.exe。</span><span class="sxs-lookup"><span data-stu-id="c9b18-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="c9b18-236">このアプリケーションを使用すると、ユーザーは後で示すようにレポートにフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="c9b18-237">Bandwidth Utilization Analyzer の使用のフェーズ</span><span class="sxs-lookup"><span data-stu-id="c9b18-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="c9b18-238">Bandwidth Utilization Analyzer を使用する場合、次の 2 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="c9b18-239">ログを収集します。ログは、このログを使用してWanLinkLogCollector.exe</span><span class="sxs-lookup"><span data-stu-id="c9b18-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="c9b18-240">m を使用して実行されるレポートをBandwidthUtilizationAnalyzer.xlsする</span><span class="sxs-lookup"><span data-stu-id="c9b18-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c9b18-241">エンド ユーザーが手動BandwidthUtilizationAnalyzer.xls起動しない方法を強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="c9b18-242">帯域幅使用率アナライザーの開始</span><span class="sxs-lookup"><span data-stu-id="c9b18-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="c9b18-243">コマンド WanLinkLogCollector.exeエクスプローラーを使用して、コマンド を起動します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="c9b18-244">**ユーザー設定WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="c9b18-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="c9b18-245">この機能を使用するには、次の 3 つのWanLinkLogCollector.exe。</span><span class="sxs-lookup"><span data-stu-id="c9b18-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="c9b18-246">**タイムラインをログに記録する** レポートの生成に必要なタイムラインを指定する</span><span class="sxs-lookup"><span data-stu-id="c9b18-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="c9b18-247">**ファイル ディレクトリを指定する** ファイルの場所情報を提供する</span><span class="sxs-lookup"><span data-stu-id="c9b18-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="c9b18-248">**ログを収集してレポート ビューアーを起動する** コマンドを実行してレポートを生成する</span><span class="sxs-lookup"><span data-stu-id="c9b18-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="c9b18-249">手順 1 - タイムラインをログに記録する</span><span class="sxs-lookup"><span data-stu-id="c9b18-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="c9b18-250">タイムラインをログに記録すると、ツール ユーザーは、次の図に示すように次を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="c9b18-251">**開始日** これは、レポートが生成されるタイムラインの開始日です。たとえば、2010 年 8 月 1 日です。</span><span class="sxs-lookup"><span data-stu-id="c9b18-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="c9b18-252">**終了日** これは、レポートが生成されるタイムラインの終了日です。たとえば、2010 年 9 月 30 日です。</span><span class="sxs-lookup"><span data-stu-id="c9b18-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![帯域幅使用率 A の開始日と終了日](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="c9b18-254">手順 2 - ファイル ディレクトリを指定する</span><span class="sxs-lookup"><span data-stu-id="c9b18-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="c9b18-255">次に示すように、ユーザーは次のファイル ディレクトリを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="c9b18-256">**サーバー ログ ファイルの場所** 帯域幅ポリシー サーバー ログが格納されるフォルダーの場所。</span><span class="sxs-lookup"><span data-stu-id="c9b18-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="c9b18-257">これは通常、FE \<fileserver\> \\ \> \AppServerFiles\PDP<選択する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="c9b18-258">**一時ファイルの保存場所** レポートの生成中に中間ファイルが保存される一時ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="c9b18-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![Bandwidth Utilization Utilization Utilization のファイル ディレクトリ](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="c9b18-260">サーバー ログと一時ファイル ストア フォルダーへの十分なファイル アクセスがツール ユーザーに提供されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="c9b18-261">手順 3 - ログを収集し、レポート ビューアーを起動する</span><span class="sxs-lookup"><span data-stu-id="c9b18-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="c9b18-262">ログを収集してレポート ビューアーを起動するには、次に示すように **[実行** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="c9b18-263">この手順では、必要なデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-263">This step collects the required data.</span></span>

![Bandwidth Utilization Utilization Utilizationy のデータを収集する](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="c9b18-265">入力検証に成功すると、次に示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-265">When the input validation is successful, the message shown below is displayed.</span></span>

![帯域幅 Utili で収集された通知をログに記録する](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="c9b18-267">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-267">Click **OK**.</span></span> <span data-ttu-id="c9b18-268">BandwidthUtilizationAnalyzer.xlsm が自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="c9b18-269">メッセージ ボックスの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="c9b18-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="c9b18-270">詳細については、次 **のセクションBandwidthUtilizationAnalyzer.xlsm** を使用するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9b18-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="c9b18-271">BandwidthUtilizationAnalyzer.xlsm の使用</span><span class="sxs-lookup"><span data-stu-id="c9b18-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="c9b18-272">m BandwidthUtilizationAnalyzer.xlsが自動的に開始された場合は、次に示すように **[最新** の情報に更新] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="c9b18-274">ファイル フォルダーを開いた後、次consolidated.csvメッセージ ボックスで指定されている場所からファイル フォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="c9b18-275">また、場所は **C:\Temp として表示されます**。</span><span class="sxs-lookup"><span data-stu-id="c9b18-275">It also shows the location as **C:\Temp**.</span></span>

     ![BandwidthUtilizationAnalyzer でフォルダーを開く。](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="c9b18-277">[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-277">Click **Import**.</span></span>

4. <span data-ttu-id="c9b18-278">グラフィカル プロットは自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="c9b18-279">これは、バックグラウンドでの作業ポインターが消えたときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![レポート ビューでのフィルターの適用。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="c9b18-281">レポート ビューにフィルターを適用する</span><span class="sxs-lookup"><span data-stu-id="c9b18-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="c9b18-282">以下に示すように、レポート ビューに適用できるフィルターを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![レポート ビューでのフィルターの適用。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="c9b18-284">**名前** WAN リンクでフィルター処理します (フィルターはグラフの右側にあります)。プレフィックスは、次のリンクの種類を表します。垂直 (青) ボックスを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="c9b18-285">**S サイト** ネットワーク サイトからネットワーク地域への WAN リンク</span><span class="sxs-lookup"><span data-stu-id="c9b18-285">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="c9b18-286">**IS Inter-Site** 2 つのネットワーク サイト間の WAN リンク</span><span class="sxs-lookup"><span data-stu-id="c9b18-286">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="c9b18-287">**R 地域間** 2 つのネットワーク地域間の WAN リンク</span><span class="sxs-lookup"><span data-stu-id="c9b18-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="c9b18-288">**制限を超えました** 帯域幅の使用率が帯域幅容量を超える WAN リンクでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c9b18-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="c9b18-289">**重要なレベル** 帯域幅使用率が帯域幅容量の 90% 以上に達した WAN リンクでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c9b18-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="c9b18-290">**利用が多い** 帯域幅使用率が帯域幅容量の 25% 未満である WAN リンクでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c9b18-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="c9b18-291">**リンクの種類** 次の WAN リンクの種類でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-291">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="c9b18-292">**ネットワーク サイトの** 種類</span><span class="sxs-lookup"><span data-stu-id="c9b18-292">**Network site** type</span></span>

   - <span data-ttu-id="c9b18-293">**サイト間の** 種類</span><span class="sxs-lookup"><span data-stu-id="c9b18-293">**Inter-site** type</span></span>

   - <span data-ttu-id="c9b18-294">**地域間リンクの** 種類</span><span class="sxs-lookup"><span data-stu-id="c9b18-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="c9b18-295">**地域** ネットワーク地域でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="c9b18-295">**Region** Filter by network region</span></span>

<span data-ttu-id="c9b18-296">次の図は、前述のフィルターを示しています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="c9b18-297">名前で **フィルター処理します**。</span><span class="sxs-lookup"><span data-stu-id="c9b18-297">Filter by **Name**.</span></span> <span data-ttu-id="c9b18-298">グラフに表示する必要があるリンクの一覧を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-298">Select the list of links that need to be displayed in the graph.</span></span>

![BandwidthUtilizationAnalyzer での名前によるフィルター。](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="c9b18-300">制限を **超えてフィルター処理します**。</span><span class="sxs-lookup"><span data-stu-id="c9b18-300">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="c9b18-301">True **を選択** してフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-301">Select **True** to enforce the filter.</span></span>

![制限を超えてフィルター処理します。](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="c9b18-303">クリティカル レベル **でフィルター処理します**。</span><span class="sxs-lookup"><span data-stu-id="c9b18-303">Filter by **Critical levels**.</span></span> <span data-ttu-id="c9b18-304">True **を選択** してフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-304">Select **True** to enforce the filter.</span></span>

![クリティカル レベルによるフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="c9b18-306">Under で **フィルター処理**</span><span class="sxs-lookup"><span data-stu-id="c9b18-306">Filter by **Under utilized**.</span></span> <span data-ttu-id="c9b18-307">True **を選択** してフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-307">Select **True** to enforce the filter.</span></span>

![Under Utilized によるフィルター。](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="c9b18-309">リンクの種類 **でフィルター処理します**。</span><span class="sxs-lookup"><span data-stu-id="c9b18-309">Filter by **Link Type**.</span></span> <span data-ttu-id="c9b18-310">表示する必要がある種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-310">Select the type or types that need to be displayed.</span></span>

![リンクの種類によるフィルター。](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="c9b18-312">地域で **フィルター処理します**。</span><span class="sxs-lookup"><span data-stu-id="c9b18-312">Filter by **Region**.</span></span> <span data-ttu-id="c9b18-313">リンクを表示する必要がある地域の一覧を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-313">Select a list of regions whose links need to be displayed.</span></span>

![地域によるフィルター。](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="c9b18-315">要件</span><span class="sxs-lookup"><span data-stu-id="c9b18-315">Requirements</span></span>

- <span data-ttu-id="c9b18-316">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="c9b18-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="c9b18-317">Microsoft Excel 2010 または Excel 2007</span><span class="sxs-lookup"><span data-stu-id="c9b18-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="c9b18-318">概要</span><span class="sxs-lookup"><span data-stu-id="c9b18-318">Summary</span></span>

<span data-ttu-id="c9b18-319">Bandwidth Utilization Analyzer は、ネットワーク全体の UC トラフィックの音声帯域幅使用率をプロットするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-319">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="c9b18-320">このツールを使用して、ネットワーク上のビデオ帯域幅の使用状況を報告することもできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-320">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="c9b18-321">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="c9b18-321">Call Parkometer</span></span>
<span data-ttu-id="c9b18-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="c9b18-322"><a name="callpark"> </a></span></span>

<span data-ttu-id="c9b18-323">Call Parkometer は、コール パーク オービット データベースに簡単にアクセスできるコマンドライン アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="c9b18-324">説明</span><span class="sxs-lookup"><span data-stu-id="c9b18-324">Description</span></span>

<span data-ttu-id="c9b18-325">Call Parkometer は、現在パークされている通話を追跡するツールです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="c9b18-326">また、オービットとコール パーク サーバー (CPS) の使用状況に関する統計情報も収集します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="c9b18-327">このコマンド ライン ツールは、ローカルまたはリモート接続されたコンピューターから CPS オービット SQL Serverに対する読み取りおよび書き込みアクセスの両方を提供します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="c9b18-328">すべてのオプションは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="c9b18-328">All options are mutually exclusive.</span></span> <span data-ttu-id="c9b18-329">コマンド ライン構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-329">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="c9b18-330">**-o パラメーター** - このプールに構成されているオービット範囲の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="c9b18-331">**-n パラメーター** - このプールで現在使用されているオービットの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="c9b18-332">表示される情報は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="c9b18-333">パークインとパークの SIP Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="c9b18-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="c9b18-334">通話がパークされる CPS のホスト名。</span><span class="sxs-lookup"><span data-stu-id="c9b18-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="c9b18-335">通話がパークされた時刻のタイム スタンプ。</span><span class="sxs-lookup"><span data-stu-id="c9b18-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="c9b18-336">**-f パラメーター** - プール内の現在空きオービットの数を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="c9b18-337">**-r \<n\>** パラメーター — 最後にパーク \<n\> された通話を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="c9b18-338">表示される情報は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="c9b18-339">パーク先 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="c9b18-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="c9b18-340">Parker SIP URI。</span><span class="sxs-lookup"><span data-stu-id="c9b18-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="c9b18-341">通話がパークされた CPS のホスト名。</span><span class="sxs-lookup"><span data-stu-id="c9b18-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="c9b18-342">呼び出しが取得または破棄された時刻のタイム スタンプ。</span><span class="sxs-lookup"><span data-stu-id="c9b18-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="c9b18-343">**-t \<n\>** パラメーター - 割り当てられたオービット番号のランダム性を示す、データベース内のオービットの予約をテストします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="c9b18-344">出力</span><span class="sxs-lookup"><span data-stu-id="c9b18-344">Output</span></span>

<span data-ttu-id="c9b18-345">Call Parkometer は、コマンド プロンプトで指定された入力パラメーターに応じて、次の出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="c9b18-346">このプールに対して構成されているオービット範囲すべて</span><span class="sxs-lookup"><span data-stu-id="c9b18-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="c9b18-347">現在パーク中の通話</span><span class="sxs-lookup"><span data-stu-id="c9b18-347">Currently parked calls</span></span>

- <span data-ttu-id="c9b18-348">空き (使用可能な) オービットの数</span><span class="sxs-lookup"><span data-stu-id="c9b18-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="c9b18-349">最近パークされた通話</span><span class="sxs-lookup"><span data-stu-id="c9b18-349">Recently parked calls</span></span>

- <span data-ttu-id="c9b18-350">均一なオービット値とランダム オービット値をテストする目的で予約されたオービット</span><span class="sxs-lookup"><span data-stu-id="c9b18-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="c9b18-351">用途</span><span class="sxs-lookup"><span data-stu-id="c9b18-351">Purpose</span></span>

<span data-ttu-id="c9b18-352">CPS ツールの目的は、CPS データベースへのコマンド ライン アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-352">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="c9b18-353">管理者は、CPS の使用状況を表示し、プールに割り当てられているオービットの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-353">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="c9b18-354">要件</span><span class="sxs-lookup"><span data-stu-id="c9b18-354">Requirements</span></span>

<span data-ttu-id="c9b18-355">CPS を実行しているのと同じコンピューターでこのツールを実行する場合、要件はありません。</span><span class="sxs-lookup"><span data-stu-id="c9b18-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="c9b18-356">このツールをリモート コンピューターで実行する場合は、Skype for Business Server 2015 で使用される SQL Server データベースがリモート アクセスを許可するように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="c9b18-357">Call Parkometer は、プールのSQL Server接続するためのデータベース接続文字列を使用して構成する必要SQL Server。</span><span class="sxs-lookup"><span data-stu-id="c9b18-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="c9b18-358">このSQL Serverデータベース接続文字列は、構成ファイルで定義されています。parkometer.exe.config。 \*\*\*\* このディレクトリは、このディレクトリと同じディレクトリparkometer.exe配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="c9b18-359">次の XML ファイルは、次の例parkometer.exe.config。構成する必要があるパラメーターは、ユーザー名 (mydomain\Administrator など)、パスワード (mypassword など)、ホスト名 (myserver など) です。</span><span class="sxs-lookup"><span data-stu-id="c9b18-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

### <a name="examples"></a><span data-ttu-id="c9b18-360">例</span><span class="sxs-lookup"><span data-stu-id="c9b18-360">Examples</span></span>

<span data-ttu-id="c9b18-361">展開されたオービット範囲: -o パラメーターは、次に示すように、このプールに構成されているオービット範囲の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Call Parkometer のオービット範囲。](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="c9b18-363">現在パークされている通話: -n パラメーターは、次に示すように、このプールで現在使用されているオービットの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Call Parkometer で現在パークされている通話。](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="c9b18-365">空きオービットの数: -f パラメーターは、プール内で現在空きオービットの数を次のように一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Call Parkometer のフリー オービット。](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="c9b18-367">最近パークされた通話: -r パラメーターは、次に示すように、最後にパーク \<n\> \<n\> された通話を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Call Parkometer で最近パークされた通話。](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="c9b18-369">オービット予約のテスト: -t パラメーターは、次に示すようにデータベース内のオービット \<n\> の予約をテストします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Call Parkometer でオービット予約をテストします。](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="c9b18-371">概要</span><span class="sxs-lookup"><span data-stu-id="c9b18-371">Summary</span></span>

<span data-ttu-id="c9b18-372">Call Parkometer は、コール パーク サーバーに関する詳細情報を提供するコマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="c9b18-373">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="c9b18-373">DBAnalyze</span></span>
<span data-ttu-id="c9b18-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="c9b18-374"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="c9b18-375">説明</span><span class="sxs-lookup"><span data-stu-id="c9b18-375">Description</span></span>

<span data-ttu-id="c9b18-376">DBAnalyze は、管理者が Skype for Business Server 2015 データベースに関する分析レポートを収集するのに役立つコマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="c9b18-377">DBAnalyze には、診断、ユーザー データ、会議、MCUs、ディスク断片化のモードがあります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="c9b18-378">**診断モード** テーブルに関する情報を含むレポートを作成します (レコード数、 断片化、データ サイズ、およびログ ファイルのサイズ、データとログ ファイルのサイズ、最後のバックアップ時間、Microsoft Office Communications Server を実行しているサーバー間の連絡先の分散、アクセス許可の平均数、連絡先、コンテナー、サブスクリプション、公開、ユーザーごとのエンドポイント、不適切にホームに入っているユーザー、ルーティングできないユーザー、ユーザーごとに開催された会議の平均数、スケジュールされた会議、アクティブな会議、およびデータベース のバージョン。</span><span class="sxs-lookup"><span data-stu-id="c9b18-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9b18-379">診断モードを実行すると、サーバーのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="c9b18-380">**ユーザー データ モード** 指定したユーザーの連絡先、コンテナー、サブスクリプション、発行、アクセス許可、および連絡先グループのデータ、または連絡先リストとアクセス許可リストにそのユーザーを持つユーザーのデータを報告します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="c9b18-381">このモードでは、ユーザーが開催または招待された会議の概要データも報告されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="c9b18-382">**会議モード** 特定の電話会議の詳細データを報告します。たとえば、会議のすべてのスケジュール時の詳細、招待者リスト、会議で許可されるメディアの種類のリスト、アクティブな MCUs (マルチポイントコントロール ユニット)、アクティブな参加者リスト、各参加者の信号状態が含されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="c9b18-383">**会議 ID のデコード\*\*\*\*/pstnid** スイッチで指定されているが、詳細情報についてはバック エンドに接続しない公衆交換電話網 (PSTN) 会議 ID をデコードします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="c9b18-384">**会議を解決する\*\*\*\*/pstnid** スイッチで指定された PSTN 会議 ID をデコードし、ID で示される会議に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="c9b18-385">**MCUs モード** プール内の各 MCU の ID、メディアの種類、URL、ハートビートの状態、会議の負荷、および参加者の負荷を報告します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="c9b18-386">**ディスク断片化モード** すべてのディスクの断片化状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="c9b18-387">このツールは、さまざまな問題を診断したり、管理者が容量計画を行うのを支援したりするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-387">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="c9b18-388">たとえば、サーバー A にホームを持つユーザーのほとんどが、サーバー B にホームのユーザーを連絡先として選択した場合、管理者はサーバー A のユーザーをサーバー B に移動して、サーバー間のトラフィックを削減できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-388">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="c9b18-389">出力</span><span class="sxs-lookup"><span data-stu-id="c9b18-389">Output</span></span>

<span data-ttu-id="c9b18-390">このツールは、Skype for Business Server 2015 データベースに関する定義済みのレポートを出力します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="c9b18-391">**パス**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span><span class="sxs-lookup"><span data-stu-id="c9b18-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="c9b18-392">用途</span><span class="sxs-lookup"><span data-stu-id="c9b18-392">Purpose</span></span>

<span data-ttu-id="c9b18-393">このファイルDbanalyze.exeローカル フォルダーにコピーし、ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="c9b18-394">ツールを使用するには、コマンド ラインから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="c9b18-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` コマンド ライン オプションの説明を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![コマンド ライン オプションDbanalyze.exe。](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="c9b18-397">要件</span><span class="sxs-lookup"><span data-stu-id="c9b18-397">Requirements</span></span>

 <span data-ttu-id="c9b18-398">**コンピューター** DBAnalyze は、Skype for Business Server 2015 がインストールされているドメインに参加しているコンピューターからのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="c9b18-399">**ネットワーク** コンピューターは、バック エンド データベースに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="c9b18-400">**ソフトウェア** DBAnalyze を実行する前に、Skype for Business Server 2015 ソフトウェア コンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="c9b18-401">**ユーザー** 次の表に、Skype for Business Server 2015 データベースにアクセスするために必要なアクセス許可を持つ管理者を示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-401">**Users** The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![アクセス許可の表Dbanalyze.exe。](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="c9b18-403">**/report:disk モードにはローカル管理者アカウントが必要** です。</span><span class="sxs-lookup"><span data-stu-id="c9b18-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="c9b18-404">例</span><span class="sxs-lookup"><span data-stu-id="c9b18-404">Examples</span></span>

<span data-ttu-id="c9b18-405">有効なコマンドの例を次Dbanalyze.exeします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="c9b18-406">概要</span><span class="sxs-lookup"><span data-stu-id="c9b18-406">Summary</span></span>

<span data-ttu-id="c9b18-407">DBAnalyzer を使用すると、管理者は Skype for Business Server 2015 データベースを迅速かつ簡単に分析できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="c9b18-408">ストレージ サービス データのインポート</span><span class="sxs-lookup"><span data-stu-id="c9b18-408">Import Storage Service Data</span></span>
<span data-ttu-id="c9b18-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="c9b18-409"><a name="Issd"> </a></span></span>

<span data-ttu-id="c9b18-410">ImportStorageServiceData リソース キット ツールを使用すると、記憶域サービス (LYSS) からフラッシュされたキューとエンドポイントのデータをストレージ サービスに再インポートできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="c9b18-411">説明</span><span class="sxs-lookup"><span data-stu-id="c9b18-411">Description</span></span>

<span data-ttu-id="c9b18-412">記憶域サービスからフラッシュされたデータは、キュー アイテムの状態またはデータベース サイズに基づいて自動 (定期的) に実行された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="c9b18-413">これは、プール フェールオーバー コマンドレットの手動呼び出し、または StorageServiceFullFlush コマンドレット (プール フェールオーバー コマンドレットが呼び出すコマンドレット) が原因で発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="c9b18-414">フロントエンドのストレージ サービス (LYSS) データベース のサイズが通常のレベルを超える場合は、データを再インポートしない方が理想的です。そうすると、エクスポートされるデータが多いだけなので注意してください。さらに、記憶域サービス キューの拡大の原因となるエラーの原因となる可能性がある問題は、最初に解決する必要があります (Exchange エンドポイントエラー、ネットワークの問題、その他の問題など)。</span><span class="sxs-lookup"><span data-stu-id="c9b18-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="c9b18-415">**シナリオ 1:** プールのフェールオーバー中に、各フロントエンドのストレージ サービスからファイルがフラッシュされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="c9b18-416">フェールオーバーが完了したら、ツールを実行してデータを再インポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="c9b18-417">**シナリオ 2:** データが毎日自動的にフラッシュされる、または記憶域サービス データベースが特定のサイズしきい値を超えた場合 (たとえば、60%、80%、90% いっぱい)。</span><span class="sxs-lookup"><span data-stu-id="c9b18-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="c9b18-418">この自動フラッシュされたデータは、管理者が定期的に再インポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="c9b18-419">上記の状況では、監視 SCOM パックが展開されていない場合、ストレージ サービスからフラッシュされるデータに関連する Skype for Business Server Storage Service のイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="c9b18-420">32075 (フル フラッシュ操作が開始)、32076 (完全フラッシュが完了)、32082 (メンテナンス レベルフラッシュが開始)、32083 (メンテナンス レベルフラッシュが完了)、32089 (データベースの満たのためにフラッシュが発生しました) のイベント ID。</span><span class="sxs-lookup"><span data-stu-id="c9b18-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="c9b18-421">これらのイベント ID は RTM リリースに対応しています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="c9b18-422">管理者がこれらのイベントを見た場合、フラッシュされたファイルがあるという意味です。このデータは、このツールを使用して定期的にインポートし戻す必要があります (たとえば、1 週間に 1 回)。</span><span class="sxs-lookup"><span data-stu-id="c9b18-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="c9b18-423">Online Service リリースでは、Skype for Business Server の正常性監視 SCOM パックが展開されている場合、フラッシュされたデータを記憶域サービスに再インポートする必要がある新しいアラートが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="c9b18-424">通知をトリガーしたフロントエンド サーバーのイベント ログに、対応するイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="c9b18-425">このイベントには、フラッシュされたデータ ファイルが置かれる親パスの説明と、警告条件を満たすファイルの数が示されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="c9b18-426">警告の条件は、特定の親パスの下に、少なくとも Y 日間の古い X 以上のファイルが含まれます (ここで、X と Y は StorageService 内で事前に設定されますが、APPCONFIG ファイルを変更することで上書きできます)。正常性アラートをトリガーできるイベントの 2 つの例を以下に示します。違いは親パスです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="c9b18-427">1 つの可能性は Web サービス ファイル共有の下にありますが、もう 1 つの可能性は各フロントエンドのローカル アプリケーション データ ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="c9b18-428">( c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService など)。</span><span class="sxs-lookup"><span data-stu-id="c9b18-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="c9b18-429">管理者は、この再キット ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="c9b18-430">このツールは、ツールが実行されるフロントエンドによってデータが所有されていない場合に、実行中のフロントエンドと他のフロントエンドの CPU と IO の負荷を増加します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="c9b18-431">このツールは、フロントエンドの CPU 負荷と IO 負荷が高くない場合 (ピーク時間外など) に実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="c9b18-432">2 番目に、このツールは 2 ~ 3 分で 1 つのデータ ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="c9b18-433">ツールの実行時間を見積もる場合は、この問題に念頭に置いておきます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="c9b18-434">ツールによって生成された詳細ログ ファイルは、既定でファイル ストアに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="c9b18-435">ログ ファイルには数十 MB 以上のエラーが報告されていない場合に削除します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![記憶域サーバーのイベント ログ イベントのサンプル。](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="c9b18-437">要件</span><span class="sxs-lookup"><span data-stu-id="c9b18-437">Requirements</span></span>

<span data-ttu-id="c9b18-438">Skype for Business Server 2015 リソース キット ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="c9b18-439">このツールは、Skype for Business Server と Skype for Business Server 管理シェルがインストールされているドメインに参加しているコンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="c9b18-440">このツールは、管理シェルのコマンドレットを使用して、プール内のすべてのフロントエンド サーバーを識別します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="c9b18-441">次に **、RtcLocal** データベースがインストールされているプール内のコンピューターからツールを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="c9b18-442">このデータベースは、プールの WEBSERVICE ファイル共有の場所を取得するためにツールによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="c9b18-443">さらに、このツールを使用する前に、各フロントエンド サーバーは、まず、各フロントエンド サーバーと、ツールの実行に使用するコンピューターで **Enable-PSRemoting** を使用して Windows PowerShell リモート処理を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="c9b18-444">そうしないと、このWindows PowerShellのリモート コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="c9b18-445">Windows PowerShell後、プール内のすべてのフロントエンド サーバーでリモート処理をオフにできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="c9b18-446">最後に、ツールを呼び出すアカウントまたは資格情報に、このツールを実行しているプールの Web サービス ファイル共有に対する読み取り/書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="c9b18-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="c9b18-447">そうしないと、ツールは IO アクセス許可エラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="c9b18-448">Windows Server 2008 Windows Server 2012ではWindows PowerShellリモート処理は既定で有効になっていますが、Windows Server 2008 オペレーティング システムでは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="c9b18-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="c9b18-449">例</span><span class="sxs-lookup"><span data-stu-id="c9b18-449">Examples</span></span>

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

## <a name="lcssync"></a><span data-ttu-id="c9b18-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="c9b18-450">LCSSync</span></span>
<span data-ttu-id="c9b18-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="c9b18-451"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="c9b18-452">LCSSync ツールは、複数フォレスト環境に Skype for Business Server 2015 通信ソフトウェアを展開するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="c9b18-453">このツールは、Active Directory ドメイン サービス連絡先オブジェクトとして、異なるユーザー フォレストのユーザーとグループを、Skype for Business Server 2015 がインストールされている中央フォレストに同期するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="c9b18-454">説明</span><span class="sxs-lookup"><span data-stu-id="c9b18-454">Description</span></span>

 <span data-ttu-id="c9b18-455">LCSSync は、中央フォレスト内の同期された Active Directory ドメイン サービス連絡先オブジェクトを使用して、Skype for Business Server のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="c9b18-456">シングル サインインを提供するには、プライマリ ユーザー アカウントを、Skype for Business Server 2015 の中央フォレストの Active Directory ドメイン サービス連絡先オブジェクトにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="c9b18-457">このツールは、そのマッピングの実行に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="c9b18-458">このツールは、Microsoft Identity Integration Server で管理エージェントを作成するためのテンプレートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="c9b18-459">概要</span><span class="sxs-lookup"><span data-stu-id="c9b18-459">Summary</span></span>

<span data-ttu-id="c9b18-460">LCSSync ツールは、複数フォレスト環境に Skype for Business Server 2015 を展開するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="c9b18-461">ユーザー コンソールを参照する</span><span class="sxs-lookup"><span data-stu-id="c9b18-461">Lookup User Console</span></span>
<span data-ttu-id="c9b18-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="c9b18-462"><a name="LUC"> </a></span></span>

<span data-ttu-id="c9b18-463">LookupUserConsole ツールは、特定のユーザーに関する内部 Skype for Business Server ルーティング情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="c9b18-464">この情報は、展開とルーティングの問題を診断する際に、Microsoft が個人をサポートする際に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="c9b18-465">説明</span><span class="sxs-lookup"><span data-stu-id="c9b18-465">Description</span></span>

 <span data-ttu-id="c9b18-466">このLookupUserConsole.exe、SIP アドレスを受け入れ、関連する内部 Skype for Business Server ルーティング情報の表示を試みるコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="c9b18-467">Exit **と入力** して LookupUserConsole ツールを終了します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="c9b18-468">要件</span><span class="sxs-lookup"><span data-stu-id="c9b18-468">Requirements</span></span>

<span data-ttu-id="c9b18-469">Skype for Business Server 2015 リソース キットをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="c9b18-470">このツールは、Skype for Business Server がインストールされているドメインに参加しているコンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="c9b18-471">例</span><span class="sxs-lookup"><span data-stu-id="c9b18-471">Examples</span></span>

<span data-ttu-id="c9b18-472">C:\Program Files\Skype for Business Server 2015\ResKit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="c9b18-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

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

## <a name="msturnping"></a><span data-ttu-id="c9b18-473">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="c9b18-473">MsTurnPing</span></span>
<span data-ttu-id="c9b18-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="c9b18-474"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="c9b18-475">MSTurnPing ツールを使用すると、Skype for Business Server 2015 通信ソフトウェアの管理者は、音声ビデオ エッジサービスと音声ビデオ認証サービスを実行しているサーバー、およびトポロジ内で帯域幅ポリシー サービスを実行しているサーバーの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="c9b18-476">説明</span><span class="sxs-lookup"><span data-stu-id="c9b18-476">Description</span></span>

<span data-ttu-id="c9b18-477">MSTurnPing ツールを使用すると、Skype for Business Server 2015 通信ソフトウェアの管理者は、音声ビデオ エッジサービスと音声ビデオ認証サービスを実行しているサーバー、およびトポロジ内で帯域幅ポリシー サービスを実行しているサーバーの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="c9b18-478">このツールを使用すると、管理者は次のテストを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="c9b18-479">A/V エッジ サーバー テスト: このツールは、次の手順を実行して、トポロジ内のすべての A/V エッジ サーバーに対してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="c9b18-480">Skype for Business Server 音声ビデオ認証サービスが開始され、適切な資格情報を発行できるの確認。</span><span class="sxs-lookup"><span data-stu-id="c9b18-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="c9b18-481">Skype for Business Server 音声ビデオ エッジ サービスが開始され、外部エッジにリソースを正常に割り当て可能な場合の確認。</span><span class="sxs-lookup"><span data-stu-id="c9b18-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="c9b18-482">帯域幅ポリシー サービス のテスト: このツールは、トポロジ内で帯域幅ポリシー サービスを実行しているすべてのサーバーに対して、次の操作を実行してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="c9b18-483">Skype for Business Server 帯域幅ポリシー サービス (認証) が開始され、適切な資格情報を発行できる確認。</span><span class="sxs-lookup"><span data-stu-id="c9b18-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="c9b18-484">Skype for Business Server 帯域幅ポリシー サービス (コア) が開始され、帯域幅チェックが正常に実行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="c9b18-485">このツールは、トポロジの一部であり、ローカル ストアがインストールされているコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="c9b18-486">出力</span><span class="sxs-lookup"><span data-stu-id="c9b18-486">Output</span></span>

<span data-ttu-id="c9b18-487">ツールは、各操作の結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="c9b18-488">**AudioVideoEdgeServer テストを実行** すると、ツールの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="c9b18-489">トポロジで Skype for Business Server 2015 音声ビデオ認証サービスを提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="c9b18-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="c9b18-490">トポロジで Skype for Business Server 2015 音声ビデオ エッジ サービスを提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="c9b18-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="c9b18-491">**BandwidthPolicyServer テストを実行** すると、ツールの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="c9b18-492">トポロジで Skype for Business Server 2015 帯域幅ポリシー サービス (認証) を提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="c9b18-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="c9b18-493">トポロジで Skype for Business Server 2015 帯域幅ポリシー サービス (コア) を提供するコンピューターのテスト結果</span><span class="sxs-lookup"><span data-stu-id="c9b18-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="c9b18-494">要件</span><span class="sxs-lookup"><span data-stu-id="c9b18-494">Requirements</span></span>

- <span data-ttu-id="c9b18-495">このツールは、トポロジ内にローカル ストアがあるコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="c9b18-496">このツールは、ローカル ストアにアクセスできる管理者として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="c9b18-497">例</span><span class="sxs-lookup"><span data-stu-id="c9b18-497">Examples</span></span>

<span data-ttu-id="c9b18-498">ツール入力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-498">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="c9b18-499">概要</span><span class="sxs-lookup"><span data-stu-id="c9b18-499">Summary</span></span>

<span data-ttu-id="c9b18-500">このツールは、音声/ビデオおよび帯域幅ポリシー サービスを実行しているサーバーの状態を確認する Skype for Business Server 2015 管理者にとって有益なリソースです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="c9b18-501">ネットワーク構成ビューアー</span><span class="sxs-lookup"><span data-stu-id="c9b18-501">Network Configuration Viewer</span></span>
<span data-ttu-id="c9b18-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="c9b18-502"><a name="NCV"> </a></span></span>

<span data-ttu-id="c9b18-503">ネットワーク構成ビューアーは、Skype for Business Server 2015 通信ソフトウェア管理者が、指定された帯域幅容量に基づく音声通話やビデオ通話などのリアルタイム通信セッションを許可するためにプロビジョニングされた企業の通話受付管理 (CAC) ネットワーク トポロジを表示するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="c9b18-504">Skype for Business Server 2015 管理者は CAC ポリシーを定義します。CAC ポリシーは、Skype for Business Server 2015 と一緒にインストールされる帯域幅ポリシー サービスによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="c9b18-505">説明</span><span class="sxs-lookup"><span data-stu-id="c9b18-505">Description</span></span>

<span data-ttu-id="c9b18-506">ネットワーク構成ビューアー (NetworkConfigurationViewer.exe) を使用すると、管理者は次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="c9b18-507">Skype for Business Server 2015 展開の CAC ネットワーク トポロジをグラフィカル形式で読み込み、表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="c9b18-508">帯域幅ポリシー サーバー ログ ファイルから CAC ネットワーク トポロジを読み込み、グラフィカル形式で表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="c9b18-509">CAC ネットワーク トポロジを XML 形式でディスクに保存して保存します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="c9b18-510">CAC ネットワーク トポロジ図を JPG または BMP 形式で保存および保存します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="c9b18-511">CAC ネットワーク トポロジ構成データを表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="c9b18-512">CAC ネットワーク トポロジをツリー ビュー スタイルで表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="c9b18-513">CAC ネットワーク トポロジ リンク (サイト間、地域間、サイト間リンクなど) のカスタム コネクタを定義します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="c9b18-514">CAC ネットワーク トポロジ サイト情報、地域情報、プロビジョニングされた帯域幅ポリシーとネットワーク リンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="c9b18-515">用途</span><span class="sxs-lookup"><span data-stu-id="c9b18-515">Purpose</span></span>

<span data-ttu-id="c9b18-516">エンタープライズ CAC ネットワーク トポロジ リンクをグラフィカル インターフェイスで表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="c9b18-517">例</span><span class="sxs-lookup"><span data-stu-id="c9b18-517">Examples</span></span>

 <span data-ttu-id="c9b18-518">**Skype for Business Server 2015** 展開からの CAC ネットワーク トポロジの読み込みと表示をグラフィカル形式で行います。Skype for Business Server 2015 管理者は、次の図に示すように、[ネットワーク構成のダウンロード] オプションを使用して、任意の Skype for Business Server 2015 コンピューターに CAC ネットワーク トポロジ構成を読み込み、表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="c9b18-519">Skype for Business Server 2015 構成ストアに接続できないコンピューターに展開すると、ツールはこのような構成をダウンロードまたは表示できません。</span><span class="sxs-lookup"><span data-stu-id="c9b18-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![ネットワーク構成のダウンロード。](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="c9b18-521">帯域幅ポリシー サーバー ログ ファイルから CAC ネットワーク トポロジを読み込み **、グラフィカル形式で表示します。** Skype for Business Server 2015 帯域幅ポリシー サーバーは、CAC ネットワーク トポロジを Skype for Business Server 2015 ファイル共有の場所の下のログ メカニズムの一部として保存します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="c9b18-522">Skype for Business Server 2015 の管理者は、次に示すように [Open **Network Configuration]** オプションを使用して、このようなファイルをグラフィカル形式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![帯域幅ポリシー サーバー ログ ファイルを開く。](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="c9b18-524">CAC ネットワーク トポロジを XML 形式でディスクに保存して保存します。Skype for Business Server 2015 管理者は、以下に示すように [ネットワーク構成のコピーを保存する] オプションを使用して、CAC ネットワーク トポロジ構成ファイルを XML 形式で保存できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="c9b18-525">保存した構成ファイルは、グラフィカル表示のためにオフラインで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![ネットワーク構成を XML ファイルとして保存する。](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="c9b18-527">CAC ネットワーク トポロジ図を JPG または BMP 形式で保存および保存する: Skype for Business Server 2015 管理者は、下に示すように 、[ネットワーク構成の保存] 図を画像として保存オプションを使用して、CAC ネットワーク トポロジ構成をグラフィカル形式 (JPG および BMP ファイル形式) で保存できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![ネットワーク構成を画像として保存する。](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="c9b18-529"><strong>CAC ネットワーク トポロジ構成データを表示します。</strong>Skype for Business Server 2015 管理者は、以下に示すように [ネットワーク構成データの表示] オプションを使用して、ネットワーク地域、ネットワーク サイト、帯域幅プロファイル、サイト サブネット IP アドレスなどの関連するネットワーク構成データをテキスト形式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-529"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![ネットワーク構成データの表示。](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="c9b18-531">**CAC ネットワーク トポロジをツリー ビュー スタイルで表示します。** Skype for Business Server 2015 管理者は、以下に示すように、ツール ウィンドウの左側にあるコントロール パネルを使用して、関連するネットワーク構成データをグラフィカル ツリー ビュー スタイルで表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![ツリー ビューでのネットワーク構成データの表示。](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="c9b18-533">CAC ネットワーク トポロジ リンク (サイト間、地域間、サイト間リンクなど) のカスタム コネクタ **を定義します。** Skype for Business Server 2015 管理者は、以下に示すように[設定] オプションを使用して、CAC ネットワーク構成 WAN リンクのカスタム グラフィカル コネクタを定義できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="c9b18-534">これにより、ネットワーク構成でプロビジョニングされたさまざまな種類のネットワーク リンクを区別できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![ツール](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="c9b18-536">**CAC ネットワーク トポロジ サイト情報、地域情報、プロビジョニングされた帯域幅ポリシーを表示します。** Skype for Business Server 2015 管理者は、以下に示すオプションを使用して、関連する CAC ネットワーク地域情報、サイト情報、CAC 帯域幅プロビジョニング情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="c9b18-537">(たとえば、ネットワーク地域 **またはネットワーク** サイト オブジェクトの [情報] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="c9b18-537">(For example, click **Info** in a network region or network site object.)</span></span>

![ネットワークのカスタム コネクタの定義。](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="c9b18-539">概要</span><span class="sxs-lookup"><span data-stu-id="c9b18-539">Summary</span></span>

<span data-ttu-id="c9b18-540">このツールは、展開用の CAC ネットワーク トポロジをグラフィカル形式で表示する Skype for Business Server 2015 管理者にとって有益なリソースです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="c9b18-541">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="c9b18-541">Response Group Agent Live</span></span>
<span data-ttu-id="c9b18-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="c9b18-542"><a name="RGAL"> </a></span></span>

<span data-ttu-id="c9b18-543">応答グループ アプリケーションを使用すると、エージェントは組み込みの Web サービスを使用して有用なリアルタイム情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="c9b18-544">残念ながら、このデータのグラフィカルビューはアプリケーションの外部では使用できません。</span><span class="sxs-lookup"><span data-stu-id="c9b18-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="c9b18-545">Response Group Agent Live Resource Kit ツールは、他のエージェントの存在など、リアルタイムの Skype for Business 通信ソフトウェア情報によって強化された、この情報にアクセスするためのシンプルでグラフィカルな方法を提供することで、この問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="c9b18-546">説明</span><span class="sxs-lookup"><span data-stu-id="c9b18-546">Description</span></span>

<span data-ttu-id="c9b18-547">応答グループ エージェント Live は、サインインおよびサインアウト機能と、応答グループ エージェントにリアルタイム情報 (グループ メンバーシップや現在の通話数など) を提供する Windows アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="c9b18-548">これは、(Skype for Business からアクセス可能な) [エージェント グループ] ページの拡張バージョンを意図しています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="c9b18-549">用途</span><span class="sxs-lookup"><span data-stu-id="c9b18-549">Purpose</span></span>

<span data-ttu-id="c9b18-550">応答グループ アプリケーションは着信呼び出しをキューに入れ、エージェント グループにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-550">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="c9b18-551">サービスへの呼び出しに関する情報に基づいた決定を行う場合、エージェントは、エージェント グループに関するリアルタイムの情報 (使用可能な他のエージェントや各キューで待機している通話の数など) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-551">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="c9b18-552">この情報は、最初は応答グループ サービスを通じてのみアクセス可能で、Response Group Agent Live によって直感的な方法で利用できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-552">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="c9b18-553">機能</span><span class="sxs-lookup"><span data-stu-id="c9b18-553">Features</span></span>

<span data-ttu-id="c9b18-554">応答グループ エージェント Live ツールは、応答グループ サービスと Skype for Business Server 2015 SDK 上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="c9b18-555">応答グループ エージェントは、応答グループ サービスから利用できる情報と機能 (グループ メンバーシップ、他のエージェントの存在、待機中の通話数など) を提供します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="c9b18-556">次の図は、Response Group Agent Live のメイン インターフェイスを示しています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![応答グループ エージェント Live ツール。](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="c9b18-558">Response Group Agent Live のエージェントには、次の 3 つの主な機能があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="c9b18-559">**サインイン/サインアウト:** [エージェント グループ] ページ (Skype for Business Server 2015 からアクセス可能) とは異なって、Response Group Agent Live では、エージェントだけが一度にすべてのエージェント グループにサインインまたはサインアウトできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="c9b18-560">このアプリケーションは、エージェントがサインインまたはサインアウトするための 3 つの簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="c9b18-561">アプリケーション内の [サインイン/サインアウト] (緑と赤) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="c9b18-562">システム トレイ アイコンを右クリックし、サインインまたはサインアウトを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="c9b18-563">構成可能なキーボード ショートカットの使用。</span><span class="sxs-lookup"><span data-stu-id="c9b18-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="c9b18-564">**グループ メンバーシップ:** エージェント グループが選択されている場合、Response Group Agent Live は、このグループ内のエージェントの一覧を右側のウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="c9b18-565">このアプリケーションと同じコンピューター上で Skype for Business Server 2015 を実行している場合、プレゼンス情報と連絡先カードが Response Group Agent Live に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="c9b18-566">エージェントは、IM を送信したり、そこから直接他のエージェントを呼び出したりできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="c9b18-567">**リアルタイム統計情報:** Response Group Agent Live は、すべてのエージェント グループのリアルタイム統計情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-567">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="c9b18-568">更新頻度は 1 分です。</span><span class="sxs-lookup"><span data-stu-id="c9b18-568">The update frequency is one minute.</span></span> <span data-ttu-id="c9b18-569">応答グループが通話に応答すると、現在キューに入っている通話数のグループ名の横に視覚的なインジケーターが追加されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-569">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="c9b18-570">ポインターをグループの上に一時停止すると、最長の待機時間も表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-570">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="c9b18-571">要件</span><span class="sxs-lookup"><span data-stu-id="c9b18-571">Requirements</span></span>

<span data-ttu-id="c9b18-572">Response Group Agent Live には .NET Framework 4.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="c9b18-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="c9b18-573">さらに、プレゼンスと連絡先カードの機能を利用するには、Skype for Business をローカルにインストール (および実行中) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="c9b18-574">構成</span><span class="sxs-lookup"><span data-stu-id="c9b18-574">Configuration</span></span>

<span data-ttu-id="c9b18-575">Response Group Agent Live は、アプリケーションの [オプション] ダイアログ ボックスを使用して、個々のユーザー設定に合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-575">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="c9b18-576">さらに、管理者は、既定のホスト アドレスを直接編集して、既定のホスト アドレスを定義RGAgentLive.exe.configできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-576">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="c9b18-577">次の図は、エージェントがホスト アドレスとショートカット キーの構成に使用できる [オプション] ダイアログ ボックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-577">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="c9b18-578">このダイアログにアクセスするには、メイン インターフェイスの上部にある [オプション] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-578">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![[応答グループ エージェントのライブ オプション] ダイアログ ボックス。](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="c9b18-580">応答グループ エージェント Live 構成では、次の 3 つの異なる設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="c9b18-581">ホスト アドレス: これは通常、エージェントのホーム プールに属する Web プールの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="c9b18-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="c9b18-582">正確な応答グループ サービス アドレスは、この情報からバックグラウンドで自動的に派生します (ホストの後に正しいパスを追加します)。</span><span class="sxs-lookup"><span data-stu-id="c9b18-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="c9b18-583">ショートカット: サインイン/サインアウトの正確なショートカットをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="c9b18-584">唯一の制限は、両方のショートカットに (少なくとも別のキーに加えて) "Windows ロゴ" キーを含む必要があるという制限です。</span><span class="sxs-lookup"><span data-stu-id="c9b18-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="c9b18-585">Windows から開始: Windows で自動的に起動するようにアプリケーションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="c9b18-586">例</span><span class="sxs-lookup"><span data-stu-id="c9b18-586">Examples</span></span>

<span data-ttu-id="c9b18-587">次の図は、右側のウィンドウで連絡先を右クリックして、IM を呼び出す方法または別のエージェントに送信する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![電話を発信する、または IM を送信する。](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="c9b18-589">次の図は、Response Group Agent Live がキュー内の現在の通話数と、これらすべての着信呼び出しの中で最も長い待ち時間を表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![キュー情報の表示。](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="c9b18-591">概要</span><span class="sxs-lookup"><span data-stu-id="c9b18-591">Summary</span></span>

<span data-ttu-id="c9b18-592">迅速なサインインとサインアウト、グループ メンバーシップ、基本的なリアルタイム統計情報は、応答グループ サービスからアプリケーションの外部でのみ使用できる、興味深い応答グループ エージェント機能です。</span><span class="sxs-lookup"><span data-stu-id="c9b18-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="c9b18-593">応答グループ エージェント Live リソース キット ツールを使用すると、Skype for Business Server 2015 管理者は、迅速かつグラフィカルな方法でタスクを実行できる Windows アプリケーションをエージェントに提供できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="c9b18-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="c9b18-594">SEFAUtil</span></span>
<span data-ttu-id="c9b18-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="c9b18-595"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="c9b18-596">SEFAUtil (セカンダリ内線機能のアクティブ化) は、Skype for Business Server 2015 通信ソフトウェア管理者およびヘルプデスク エージェントが、Skype for Business Server 2015 ユーザーの代わりに委任呼び出し、呼び出し転送、同時呼び出し、チーム呼び出し設定、およびグループ通話ピックアップを構成できるコマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="c9b18-597">また、管理者は、このツールを使用して、特定のユーザーに対して公開されている通話ルーティング設定を照会することもできます。SEFAUtil ツールを使用すると、管理者は、ユーザーに代わって、呼び出しの転送または同時呼び出しを有効/無効/変更できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="c9b18-598">管理者は、(SIP URI の形式で) ターゲットを指定するか、ユーザーによって既に公開されているターゲットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="c9b18-599">管理者は、このツールを使用して、ユーザーに代わって代理人またはチーム呼び出しグループ のメンバーを追加または削除することもできます。このツールは Microsoft Unified Communications Managed API (UCMA) 3.0 を基に構築され、管理者は SEFAUtil の中央管理ストアに信頼されたアプリケーションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="c9b18-600">SEFAUtil (セカンダリ内線機能のアクティブ化) を使用すると、Skype for Business Server 2015 管理者とヘルプデスク エージェントは、Skype for Business Server 2015 ユーザーの代わりに、代理呼び出し、呼び出し転送、同時呼び出し、チーム呼び出しの設定、およびグループ通話ピックアップを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="c9b18-601">また、管理者は、このツールを使用して、特定のユーザーに対して公開されている通話ルーティング設定を照会することもできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="c9b18-602">説明</span><span class="sxs-lookup"><span data-stu-id="c9b18-602">Description</span></span>

<span data-ttu-id="c9b18-603">現在のバージョンの SEFAUtil は、コマンド ライン ツールのみです。サポートされているグラフィカル ユーザー インターフェイスはありません。</span><span class="sxs-lookup"><span data-stu-id="c9b18-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="c9b18-604">このツールは、Microsoft Unified Communications Managed API (UCMA) 3.0 に基づいて作成されています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="c9b18-605">このツールの機能を使用すると、管理者とヘルプデスク エージェントは次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="c9b18-606">ユーザーのすべての通話ルーティング設定を表示する (呼び出し転送、委任、同時呼び出し、チーム通話、グループ通話ピックアップを含む)</span><span class="sxs-lookup"><span data-stu-id="c9b18-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="c9b18-607">転送設定の有効化/無効化/変更 (宛先と応答なしタイマーを含む)</span><span class="sxs-lookup"><span data-stu-id="c9b18-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="c9b18-608">呼び出し転送の即時構成を有効/無効/変更する</span><span class="sxs-lookup"><span data-stu-id="c9b18-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="c9b18-609">委任設定を有効/無効/変更する</span><span class="sxs-lookup"><span data-stu-id="c9b18-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="c9b18-610">チーム呼び出しグループの設定を有効/無効/変更する</span><span class="sxs-lookup"><span data-stu-id="c9b18-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9b18-611">Skype for Business Server 2015 SEFAUtil ツールの新機能</span><span class="sxs-lookup"><span data-stu-id="c9b18-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="c9b18-612">同時呼び出し設定の有効化/無効化/変更 (宛先を含む)</span><span class="sxs-lookup"><span data-stu-id="c9b18-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9b18-613">Skype for Business Server 2015 SEFAUtil ツールの新機能</span><span class="sxs-lookup"><span data-stu-id="c9b18-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="c9b18-614">グループ通話ピックアップ設定の有効化/無効化/変更</span><span class="sxs-lookup"><span data-stu-id="c9b18-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="c9b18-615">Skype for Business Server 2015 SEFAUtil ツールの新機能</span><span class="sxs-lookup"><span data-stu-id="c9b18-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="c9b18-616">このツールには、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="c9b18-617">Skype for Business Server プールにホームしているユーザーにのみサポートされます</span><span class="sxs-lookup"><span data-stu-id="c9b18-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="c9b18-618">複数のユーザーの通話ルーティング設定の一括編集はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="c9b18-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="c9b18-619">出力</span><span class="sxs-lookup"><span data-stu-id="c9b18-619">Output</span></span>

<span data-ttu-id="c9b18-620">このツールの現在のバージョンは、コマンド プロンプト ウィンドウでのみ出力を提供します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-620">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="c9b18-621">詳細については、このドキュメントの後半の「例」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9b18-621">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="c9b18-622">用途</span><span class="sxs-lookup"><span data-stu-id="c9b18-622">Purpose</span></span>

<span data-ttu-id="c9b18-623">このツールを使用する主なシナリオの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="c9b18-624">Bob は経営幹部であり、Skype for Business Server テレフォニーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="c9b18-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="c9b18-625">彼は既存の PBX システムに委任を持っています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="c9b18-626">Skype for Business Server 2015 への移行の一環として、管理者は既存の委任構成を反映するように Bob のルーティングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="c9b18-627">アリスは旅行中で、あるお客様からの重要な電話を期待しているという実感を持っています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-627">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="c9b18-628">しかし、彼女はホテルにいて、コンピューターにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="c9b18-628">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="c9b18-629">彼女はヘルプデスクに電話をかけ、仕事番号に対して行われたすべての通話を携帯電話番号に転送する要求を行います。</span><span class="sxs-lookup"><span data-stu-id="c9b18-629">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="c9b18-630">ヘルプデスク担当者は、彼女の代わりに構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-630">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="c9b18-631">Joe の仕事番号への電話は、仕事中は常にモバイル ボイスメールに移動します。ただし、他のほとんどの場所では正しく動作するように見える。</span><span class="sxs-lookup"><span data-stu-id="c9b18-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="c9b18-632">ヘルプデスク技術者は Joe のルーティング構成を表示し、Joe が携帯電話に同時呼び出しを構成しているのを検出できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="c9b18-633">技術者は Joe にオフィスでのモバイル対応について尋ね、同時呼び出しルールが原因で、ネットワークのカバレッジが低いときに Joe のモバイル ボイスメールに通話が行き届くと判断できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="c9b18-634">Mike は Contoso の新入社員で、Skype for Business Server 2015 が有効になっているときに、すべてのメンバーがチーム呼び出し用に構成されている新しいチームに参加しています。管理者は、チーム呼び出しグループ設定を設定して、新しいチーム メンバー全員を含め、さらに、チーム内の各メンバーのチーム呼び出しグループ メンバーとして Mike を追加できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="c9b18-635">Contoso 社の人事部のカスタマー サービス プラクティスは、最初の呼び出し以降のすべての発信者に対して個人サービスを提供する方法です。</span><span class="sxs-lookup"><span data-stu-id="c9b18-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="c9b18-636">部門のすべてのメンバーが互いに非常に近い場所に座っている場合、チーム呼び出しですべての電話が同時に呼び出されるのは、チームに非常に混乱を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="c9b18-637">チーム メンバーを混乱させずに最適なサービスを提供するために、Skype for Business Server 2015 管理者はグループ通話ピックアップ機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="c9b18-638">管理者は、すべての部門メンバーをピックアップ グループに追加し、その部門にピックアップ グループ番号と通信します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="c9b18-639">Samantha が自分のデスクを不在にした場合、Joe は自分の電話が鳴っているのを見て、自分のデスクから電話に応答します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="c9b18-640">要件</span><span class="sxs-lookup"><span data-stu-id="c9b18-640">Requirements</span></span>

<span data-ttu-id="c9b18-641">SEFAUtil ツールは、信頼されたアプリケーション プールの一部であるコンピューターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-641">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="c9b18-642">UCMA 3.0 をそのコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-642">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="c9b18-643">このツールを実行するには、SEFAUtil アプリケーション ID を持つ新しい信頼済みアプリケーションをそのプールに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-643">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="c9b18-644">SEFAUtil ツール用の新しい信頼済みアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="c9b18-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="c9b18-645">SEFAUTil ツールは、信頼されたアプリケーション プールの一部であるコンピューターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="c9b18-646">必要に応じて、新しい信頼されたアプリケーション プールとしてプールを追加するには、次のコマンドレットを使用して Skype for Business Server 管理シェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="c9b18-647">UCMA 3.0 は、SEFAUtil ツールの実行に使用するコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="c9b18-648">信頼されたアプリケーションは、SEFAUtil ツールのトポロジで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="c9b18-649">SEFAUtil を新しい信頼されたアプリケーションとして定義するには、Skype for Business Server 管理シェルを使用して次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="c9b18-650">必要に応じて、別のポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-650">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c9b18-651">プールの FQDN: SEFAUtil アプリケーションをホストするサーバーまたはプールの FQDN (通常、Skype for Business フロントエンド サーバーまたはプール>します)。</span><span class="sxs-lookup"><span data-stu-id="c9b18-651">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="c9b18-652">プール レジストラー FQDN: このアプリケーション プールに関連付けられている Skype for Business フロントエンド サーバーまたはプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="c9b18-652">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="c9b18-653">プール サイト: このプールがホームであるサイトのサイト ID。</span><span class="sxs-lookup"><span data-stu-id="c9b18-653">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="c9b18-654">トポロジの変更を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-654">The topology changes need to be enabled.</span></span> <span data-ttu-id="c9b18-655">トポロジの変更を有効にする場合は、次のコマンドレットを実行して Skype for Business Server 管理シェルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-655">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="c9b18-656">必要に応じて、SEFAUtil ツールの実行に使用するサーバーに Skype for Business Server 2015 リソース キット ツールをインストールします (サーバーは信頼されたアプリケーション プールの一部である必要があります)。</span><span class="sxs-lookup"><span data-stu-id="c9b18-656">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="c9b18-657">SEFAUtil が正しく実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-657">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="c9b18-658">これを行うには、管理者特権で Windows コマンド プロンプトからツールを実行し、展開内のユーザーの呼び出し転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-658">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="c9b18-659">既定では、ツールは "...\Program Files\Skype for Business Server 2015\Reskit" にあります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-659">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="c9b18-660">ユーザーの転送設定を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-660">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="c9b18-661">ユーザーの呼び出し転送設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-661">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="c9b18-662">グループ通話ピックアップ</span><span class="sxs-lookup"><span data-stu-id="c9b18-662">Group Call Pickup</span></span>

<span data-ttu-id="c9b18-663">グループ通話ピックアップでは、機能を完全に有効にするためには、Skype for Business Server 2015 で追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="c9b18-663">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="c9b18-664">ピックアップ グループをユーザーに割り当てる前に、この機能の計画と展開の手順について、グループ通話ピックアップ製品のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9b18-664">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="c9b18-665">例</span><span class="sxs-lookup"><span data-stu-id="c9b18-665">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="c9b18-666">現在の通話処理の設定を表示する</span><span class="sxs-lookup"><span data-stu-id="c9b18-666">Display Current Call Handling Settings</span></span>

<span data-ttu-id="c9b18-667">次のコマンドは、ユーザーの呼び出し処理を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-667">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="c9b18-668">この例では **、/server スイッチを使用** して、接続する Skype for Business Server を指定します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-668">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="c9b18-669">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-669">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="c9b18-670">通話転送/応答なし宛先を設定する</span><span class="sxs-lookup"><span data-stu-id="c9b18-670">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="c9b18-671">この例では、通話転送/応答なし宛先と呼び出しの遅延を設定します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-671">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="c9b18-672">ここでは、/server スイッチは提供されません。SEFAUtil は、Skype for Business Server 2015 の自動検出を試行します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-672">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 <span data-ttu-id="c9b18-673">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-673">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="c9b18-674">通話転送を直ちに有効にする</span><span class="sxs-lookup"><span data-stu-id="c9b18-674">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="c9b18-675">この例では、別のユーザーへの転送を直ちに有効にします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-675">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="c9b18-676">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="c9b18-677">直ちに呼び出し転送を無効にする</span><span class="sxs-lookup"><span data-stu-id="c9b18-677">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="c9b18-678">この例では、直ちに呼び出し転送を無効にします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-678">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 <span data-ttu-id="c9b18-679">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="c9b18-680">ユーザーを代理人として追加し、代理人の同時呼び出しを設定する</span><span class="sxs-lookup"><span data-stu-id="c9b18-680">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="c9b18-681">この例では、ユーザーを代理人として追加し、代理人の同時呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-681">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="c9b18-682">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="c9b18-683">代理人の同時呼び出しルールを変更する</span><span class="sxs-lookup"><span data-stu-id="c9b18-683">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="c9b18-684">この例では、前の例で設定した同時呼び出しルールを遅延呼び出しルールに変更します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-684">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="c9b18-685">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="c9b18-686">代理人を削除する</span><span class="sxs-lookup"><span data-stu-id="c9b18-686">Remove the Delegate</span></span>

<span data-ttu-id="c9b18-687">この例では、代理人を削除します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-687">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="c9b18-688">最後の代理人が削除されると、代理人呼び出しは自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-688">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="c9b18-689">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-689">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="c9b18-690">代理人を追加し、委任ルールにCall-Forwardを設定する</span><span class="sxs-lookup"><span data-stu-id="c9b18-690">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="c9b18-691">この例では、代理人を追加し、委任ルールへの転送を設定します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-691">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="c9b18-692">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="c9b18-693">同時呼び出しを有効にして宛先番号を設定する</span><span class="sxs-lookup"><span data-stu-id="c9b18-693">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="c9b18-694">この例では、同時呼び出しを有効にし、同時呼び出し先番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-694">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="c9b18-695">既に同時呼び出しが有効になっているユーザーの同時呼び出し先番号を変更するには、コマンドに /enablesimulring スイッチを付け続ける必要があります。そうしないと、宛先番号は変更されません。</span><span class="sxs-lookup"><span data-stu-id="c9b18-695">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="c9b18-696">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-696">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="c9b18-697">同時呼び出しを無効にする</span><span class="sxs-lookup"><span data-stu-id="c9b18-697">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="c9b18-698">この例では、同時呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-698">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="c9b18-699">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="c9b18-700">チーム メンバーを追加してTeam-Callメンバー グループに同時呼び出しTeam-Call設定する</span><span class="sxs-lookup"><span data-stu-id="c9b18-700">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="c9b18-701">この例では、ユーザーのチーム呼び出しグループにチーム メンバーを追加し、チーム呼び出しグループへの同時呼び出しを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-701">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="c9b18-702">ユーザーのチーム呼び出しグループにメンバーを追加すると、ユーザーの同時呼び出し設定が自動的にチーム呼び出しグループを同じに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-702">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="c9b18-703">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-703">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="c9b18-704">グループからメンバーをTeam-Callする</span><span class="sxs-lookup"><span data-stu-id="c9b18-704">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="c9b18-705">この例では、ユーザーのチーム呼び出しグループのチーム メンバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-705">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="c9b18-706">削除されるメンバーがチーム呼び出しグループの唯一のメンバーである場合、チーム呼び出しグループへの同時呼び出しは自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-706">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="c9b18-707">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-707">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="c9b18-708">Delayed Ring をグループにTeam-Callする</span><span class="sxs-lookup"><span data-stu-id="c9b18-708">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="c9b18-709">この例では、遅延リングをチーム呼び出しグループの時間設定に変更します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-709">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="c9b18-710">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="c9b18-711">有効Team-Call</span><span class="sxs-lookup"><span data-stu-id="c9b18-711">Enable Team-Call</span></span>

<span data-ttu-id="c9b18-712">この例では、特定のユーザーのチーム呼び出しを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-712">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="c9b18-713">ユーザーのチーム呼び出しグループにメンバーがない場合、チーム呼び出しは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="c9b18-713">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="c9b18-714">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-714">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="c9b18-715">無効Team-Call</span><span class="sxs-lookup"><span data-stu-id="c9b18-715">Disable Team-Call</span></span>

<span data-ttu-id="c9b18-716">この例では、特定のユーザーのチーム呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-716">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="c9b18-717">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-717">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="c9b18-718">グループ通話ピックアップを有効にし、ピックアップ グループをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c9b18-718">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="c9b18-719">この例では、ユーザーにピックアップ グループを割り当て、グループ通話ピックアップを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-719">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="c9b18-720">**出力**</span><span class="sxs-lookup"><span data-stu-id="c9b18-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="c9b18-721">グループ通話ピックアップを無効にする</span><span class="sxs-lookup"><span data-stu-id="c9b18-721">Disable Group Call Pickup</span></span>

<span data-ttu-id="c9b18-722">この例では、特定のユーザーのグループ通話ピックアップを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-722">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="c9b18-723">ユーザーのグループ通話ピックアップを無効にした場合、ユーザーに割り当てられたグループ番号は保持されません。</span><span class="sxs-lookup"><span data-stu-id="c9b18-723">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="c9b18-724">その後、そのユーザーのグループ通話ピックアップを再度有効にする場合は、/enablegrouppickup スイッチを使用してグループ番号を再び割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-724">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="c9b18-725">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="c9b18-725">SYSPrep.ps1</span></span>
<span data-ttu-id="c9b18-726"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="c9b18-726"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="c9b18-727">説明</span><span class="sxs-lookup"><span data-stu-id="c9b18-727">Description</span></span>

<span data-ttu-id="c9b18-728">SYSPrep.ps1は、Windows Server 2008 Windows PowerShellコンピューターに次の Skype for Business Server 2015 の前提条件をインストールするスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-728">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="c9b18-729">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="c9b18-729">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="c9b18-730">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="c9b18-730">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="c9b18-731">Windows Powershell バージョン 3.0</span><span class="sxs-lookup"><span data-stu-id="c9b18-731">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="c9b18-732">Visual C++ 2010 再頒布可能パッケージ</span><span class="sxs-lookup"><span data-stu-id="c9b18-732">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="c9b18-733">インターネット インフォメーション サーバーの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="c9b18-733">Internet Information Server Updates</span></span>

- <span data-ttu-id="c9b18-734">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="c9b18-734">Windows Identity Foundation</span></span>

- <span data-ttu-id="c9b18-735">Skype for Business Server 2015 Core ファイル</span><span class="sxs-lookup"><span data-stu-id="c9b18-735">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="c9b18-736">スクリプト名は Microsoft Windows オペレーティング システムのシステム準備ツールに似ていますが、異なります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-736">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="c9b18-737">このスクリプトは、Skype for Business Server 2015 に必要な前提条件のみをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-737">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="c9b18-738">これらの前提条件をインストールすると、Windows SYSPrep ツールを使用してサーバーのイメージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-738">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="c9b18-739">要件</span><span class="sxs-lookup"><span data-stu-id="c9b18-739">Requirements</span></span>

<span data-ttu-id="c9b18-740">SYSPrep.ps1 スクリプトを実行する前に、必要なファイルを Windows Server 2008 オペレーティング システム コンピューターのローカル フォルダー **(D:\Setup など)** にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-740">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="c9b18-741">このフォルダーには、Skype for Business Server 2015 ファイルのコピーも含める必要があります。具体的には、次の **Setup.exe。**</span><span class="sxs-lookup"><span data-stu-id="c9b18-741">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="c9b18-742">必須コンポーネント ファイルは、次の場所からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-742">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="c9b18-743">**前提条件**</span><span class="sxs-lookup"><span data-stu-id="c9b18-743">**Prerequisite**</span></span>                                | <span data-ttu-id="c9b18-744">**Location**</span><span class="sxs-lookup"><span data-stu-id="c9b18-744">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="c9b18-745">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="c9b18-745">Microsoft .Net Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="c9b18-746">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="c9b18-746">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="c9b18-747">Windows Powershell バージョン 3.0</span><span class="sxs-lookup"><span data-stu-id="c9b18-747">Windows Powershell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="c9b18-748">Visual C++ 2010 再頒布可能パッケージ</span><span class="sxs-lookup"><span data-stu-id="c9b18-748">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="c9b18-749">インターネット インフォメーション サーバーの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="c9b18-749">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="c9b18-750">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="c9b18-750">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="c9b18-751">Skype for Business Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="c9b18-751">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="c9b18-752">Skype for Business Server 2015 メディアからのコピー</span><span class="sxs-lookup"><span data-stu-id="c9b18-752">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="c9b18-753">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9b18-753">Parameter</span></span>

<span data-ttu-id="c9b18-754">**-SetupFolder パラメーターは**、必須コンポーネント ファイルのディレクトリの場所を引数として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-754">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="c9b18-755">例</span><span class="sxs-lookup"><span data-stu-id="c9b18-755">Examples</span></span>

<span data-ttu-id="c9b18-756">このスクリプトSYSPrep.ps1実行し、Skype for Business Server 2015 の前提条件をインストールするには、管理者特権のコマンド プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-756">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="c9b18-757">割り当てられていない番号アナウンスの移行</span><span class="sxs-lookup"><span data-stu-id="c9b18-757">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="c9b18-758"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="c9b18-758"><a name="UNAM"> </a></span></span>

<span data-ttu-id="c9b18-759">割り当てられていない番号アナウンス移行ツールを使用すると、Skype for Business Server 2015 管理者は、アナウンス アプリケーションがサービスを提供する割り当てられていない番号の構成を、移行元の Skype for Business Server またはプールから移行先の Skype for Business Server またはプールに移動できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-759">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="c9b18-760">説明</span><span class="sxs-lookup"><span data-stu-id="c9b18-760">Description</span></span>

<span data-ttu-id="c9b18-761">割り当てられていない番号アナウンス移行ツールは、移行元サーバーまたはプールのアナウンス アプリケーションによってサービスされる割り当てられていない番号の構成を別のサーバーまたはプールに移動する Windows PowerShell スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-761">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="c9b18-762">Unassigned Number Announcements Migration スクリプトを実行すると、次の操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-762">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="c9b18-763">送信元サーバーまたはプールでホストされているアナウンス アプリケーションの割り当てられていない番号のアナウンスによって使用されるオーディオ ファイルを、移動先のサーバーまたはプールのファイル ストアに移動します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-763">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9b18-764">オーディオ ファイルは、コピー先のプールにコピーされると、ソース プールから削除されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-764">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="c9b18-765">送信元サーバーまたはプールでホストされているアナウンス アプリケーション用に構成された割り当てられていないすべてのアナウンスを、送信先サーバーまたはプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-765">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="c9b18-766">送信元サーバーまたはプールでホストされているアナウンス アプリケーションによってサービスが提供される割り当てられていない番号範囲を、送信先サーバーまたはプールに再割り当てします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-766">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="c9b18-767">スクリプトを正常に実行すると、移動元のサーバーまたはプールでホストされているアナウンス アプリケーションによってサービスが提供された割り当てられていない番号範囲はすべて、移動先のサーバーまたはプールによって同じ構成で処理されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-767">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="c9b18-768">出力</span><span class="sxs-lookup"><span data-stu-id="c9b18-768">Output</span></span>

<span data-ttu-id="c9b18-769">**Move-CsAnnouncementConfiguration** スクリプトは、Skype for Business Server 管理シェル ウィンドウで、移行操作の成功または失敗を実行した場所を示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-769">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="c9b18-770">エラーによって操作の実行が中断された場合、移行先に正常に移動された割り当てられていない番号の範囲は、移行先の運用フォームに残り、移行する残りの割り当てられていない番号の範囲も運用フォームのソースに残ります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-770">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="c9b18-771">構成の残りの部分を完全に移行するには、エラーに対処した後、スクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-771">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="c9b18-772">用途</span><span class="sxs-lookup"><span data-stu-id="c9b18-772">Purpose</span></span>

<span data-ttu-id="c9b18-773">Unassigned Number Announcements Migration スクリプトは、次の 3 つのシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-773">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="c9b18-774">**Skype for Business Server の新しいバージョンへの構成設定の移行:** Contoso 社は Skype for Business Server 2015 に移行中であり、移行プロセスの一環として、Skype for Business Server 管理者は、アナウンス アプリケーションがサービスを提供する割り当てられていない番号の構成を Lync Server 2013 展開から新しい Skype for Business Server 2015 展開に移行します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-774">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="c9b18-775">構成設定を移動するために、Skype for Business Server 管理者は割り当てられていない番号アナウンス移行ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-775">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="c9b18-776">**Skype for Business Server 2015 から Lync Server 2013** への展開のロールバック:予期しない要因により、Contoso 社は移行を新しい Skype for Business Server 2015 展開にロールバックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-776">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="c9b18-777">サービスの中断を最小限に抑えるために、Skype for Business Server 管理者は、割り当てられていない番号アナウンス移行ツールを使用して、構成を Skype for Business Server 2015 展開から Lync Server 2013 展開にロールバックします。</span><span class="sxs-lookup"><span data-stu-id="c9b18-777">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="c9b18-778">**展開間でのデータの移動:** Contoso 社は、1 つのプールのすべてのサーバーを新しいサーバーに置き換える処理を行っています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-778">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="c9b18-779">その戦略は、新しい Skype for Business Server 2015 プールを展開し、すべてのデータを古いプールから新しいプールに移動し、古いプールを廃止することです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-779">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="c9b18-780">新しいプールを展開すると、割り当てられていない番号アナウンス移行ツールを使用して、構成を古いプールから新しいプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-780">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="c9b18-781">要件</span><span class="sxs-lookup"><span data-stu-id="c9b18-781">Requirements</span></span>

<span data-ttu-id="c9b18-782">ツールを正常に実行するために必要な主な要件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-782">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="c9b18-783">このスクリプトは、Skype for Business Server 管理シェルがインストールされているコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-783">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="c9b18-784">アナウンス アプリケーションは、送信元と送信先の Skype for Business サーバーまたはプールに正常に展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-784">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="c9b18-785">Move-CsAnnouncementConfiguration スクリプト</span><span class="sxs-lookup"><span data-stu-id="c9b18-785">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="c9b18-786">次Move-CsAnnouncementConfigurationスクリプトには、次の表に示す 2 つのパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="c9b18-786">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Move-CsAnnouncementConfigurationパラメーター。](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="c9b18-788">例</span><span class="sxs-lookup"><span data-stu-id="c9b18-788">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="c9b18-789">Lync Server 2013 プールから Skype for Business Server 2015 プールへの割り当てられていない番号アナウンス構成の移動</span><span class="sxs-lookup"><span data-stu-id="c9b18-789">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="c9b18-790">この例では、割り当てられていない番号のアナウンスを送信元プール (Lync Server 2013) から送信先プール (Skype for Business Server 2015) に移動します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-790">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="c9b18-791">Skype for Business Server 2015 プールから Lync Server 2013 プールへの割り当てられていない番号アナウンス構成の移動</span><span class="sxs-lookup"><span data-stu-id="c9b18-791">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="c9b18-792">この例では、割り当てられていない番号のアナウンスを送信元プール (Skype for Business Server 2015) から送信先プール (Lync Server 2013) に移動します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-792">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="c9b18-793">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="c9b18-793">Web Conf Data</span></span>
<span data-ttu-id="c9b18-794"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="c9b18-794"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="c9b18-795">Web Conf Data Tool を使用すると、Skype for Business Server 2015 通信ソフトウェアの管理者は、開催者の Web 会議に関連付けられているデータを詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-795">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="c9b18-796">シナリオには、タイム スタンプ条件に基づいて特定のユーザーの会議データを削除する機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-796">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="c9b18-797">説明</span><span class="sxs-lookup"><span data-stu-id="c9b18-797">Description</span></span>

<span data-ttu-id="c9b18-798">このツールを使用すると、管理者は次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-798">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="c9b18-799">1 人のユーザーに関連付けられているすべての Web 会議データを検索します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-799">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="c9b18-800">1 人のユーザーに関連付けられているすべての Web 会議データを削除します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-800">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="c9b18-801">特定の日付より古い 1 人のユーザーに関連付けられているすべての Web 会議データを削除します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="c9b18-802">1 人のユーザーがプールから別のプールに移動するときに、そのユーザーに関連付けられているすべての Web 会議データを移動します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9b18-803">Lync Server 2010 のリソース キット ツールでは、そのユーザーがあるプールから別のプールに移動するときに、1 人のユーザーに関連付けられているすべての Web 会議データの移動がサポートされました。</span><span class="sxs-lookup"><span data-stu-id="c9b18-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="c9b18-804">この機能は **、MoveConferenceData** パラメーターを優先してこのツールから廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c9b18-804">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="c9b18-805">このパラメーターの詳細については [、Move-CsUser コマンドレットを参照](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) してください。</span><span class="sxs-lookup"><span data-stu-id="c9b18-805">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="c9b18-806">ツールは、非アクティブな会議の会議データのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="c9b18-807">アクティブな会議 (またはセッション内の会議) は削除できません。</span><span class="sxs-lookup"><span data-stu-id="c9b18-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="c9b18-808">このツールは、ターゲット ユーザーと同じプール内にあるコンピューターから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="c9b18-809">このツールによって管理されている会議コンテンツ データを持つユーザーは、同じユーザー プールに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="c9b18-810">出力</span><span class="sxs-lookup"><span data-stu-id="c9b18-810">Output</span></span>

<span data-ttu-id="c9b18-811">このツールは、各操作の結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-811">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="c9b18-812">クエリが実行された場合、ツールは、そのユーザーが開催者である非アクティブなすべての会議データ フォルダーの一覧を出力します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="c9b18-813">削除を実行すると、データが削除される会議データ フォルダーの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="c9b18-814">要件</span><span class="sxs-lookup"><span data-stu-id="c9b18-814">Requirements</span></span>

<span data-ttu-id="c9b18-815">このツールは、開催者が現在ホームに設定されているのと同じプールで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="c9b18-816">このツールは、コンテンツ ファイル ストアへのアクセス権を持つ管理者特権を使用して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="c9b18-817">例</span><span class="sxs-lookup"><span data-stu-id="c9b18-817">Examples</span></span>

<span data-ttu-id="c9b18-818">次の表に、パラメーターの一部を例で示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-818">The following table describes the parameters, some of which are used in the examples.</span></span>

![Web Conf Data Tool のパラメーター。](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="c9b18-820">上の例は、クエリ コマンドがどのように機能するのか示しています。</span><span class="sxs-lookup"><span data-stu-id="c9b18-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="c9b18-821">このようなコマンドの出力は、このツールの影響を受けるすべての会議コンテンツ フォルダーの一覧になります。</span><span class="sxs-lookup"><span data-stu-id="c9b18-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="c9b18-822">削除コマンドの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c9b18-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="c9b18-823">削除コマンドを実行すると、このユーザーからすべての非アクティブな会議フォルダーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c9b18-823">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="c9b18-824">概要</span><span class="sxs-lookup"><span data-stu-id="c9b18-824">Summary</span></span>

<span data-ttu-id="c9b18-825">このツールは、会議の会議データを正確に制御する必要がある管理者にとって有益なリソースです。</span><span class="sxs-lookup"><span data-stu-id="c9b18-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>


