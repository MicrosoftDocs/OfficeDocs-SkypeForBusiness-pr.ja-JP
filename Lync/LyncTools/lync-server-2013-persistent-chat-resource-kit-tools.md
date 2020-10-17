---
title: Lync Server 2013 常設チャットリソースキットツール
description: Lync Server 2013 常設チャットリソースキットツール。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 336e81c97da73da47eee654161a7d8d8956f9edb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542353"
---
# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="368aa-103">Lync Server 2013 常設チャットリソースキットツール</span><span class="sxs-lookup"><span data-stu-id="368aa-103">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="368aa-104">_**トピックの最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="368aa-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="368aa-105">Lync Server 2013 常設チャットリソースキットツールは、Lync Server 2013 常設チャットサーバーを展開して管理する IT 管理者にとって、日常的な作業を容易にするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="368aa-105">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="368aa-106">このトピックでは、インストール手順だけでなく、各ツールの目的と使用例についても説明します。</span><span class="sxs-lookup"><span data-stu-id="368aa-106">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="368aa-107">リソースキットツールのインストール</span><span class="sxs-lookup"><span data-stu-id="368aa-107">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="368aa-108">Lync Server 2013 のリソースキットツールをインストールするには、 **PersistentChatReskit.msi**をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="368aa-108">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="368aa-109">**PersistentChatReskit.msi**を実行して簡単なインストールを行います。</span><span class="sxs-lookup"><span data-stu-id="368aa-109">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="368aa-110">.Msi は、次のパスにあるすべてのツールをインストールします。 \\ **Program Files \\ Microsoft Lync Server 2013 \\ 常設チャットサーバーリソースキット**。</span><span class="sxs-lookup"><span data-stu-id="368aa-110">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="368aa-111">このフォルダーには、自己完結型の実行可能ファイルであるツールがあります。</span><span class="sxs-lookup"><span data-stu-id="368aa-111">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="368aa-112">ファイルが含まれているツールも、それぞれ独自のサブフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="368aa-112">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="368aa-113">Lync Server 2013 のリソースキットツールをインストールした後、 <STRONG>PsExec.exe</STRONG>をインストールし、 <STRONG>PsExec.exe</STRONG>を次のパスにコピーする必要があります。 \\ <STRONG>Program Files Kit\ChatStressTool The Microsoft Lync Server 2013 \ 常設 Chat server Resource</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="368aa-113">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="368aa-114"><STRONG>PsExec.exe</STRONG>をコピーしない場合、常設チャットストレスツールはエラー例外をスローし、正しく実行されません。</span><span class="sxs-lookup"><span data-stu-id="368aa-114">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="368aa-115">ツールを実行する前に、この前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="368aa-115">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="368aa-116"><STRONG>PsExec.exe</STRONG>のインストールの詳細については、「」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A> 。</span><span class="sxs-lookup"><span data-stu-id="368aa-116">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="368aa-117">サポートされる環境</span><span class="sxs-lookup"><span data-stu-id="368aa-117">Supported Environments</span></span>

<span data-ttu-id="368aa-118">最適なパフォーマンスを得るために、lync server 2013、リソースキットツールは、Lync Server 2013 に必要なものと同じ環境にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-118">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="368aa-119">リソースキットツールの概要</span><span class="sxs-lookup"><span data-stu-id="368aa-119">Resource Kit Tools Overview</span></span>

<span data-ttu-id="368aa-120">Lync Server 2013 常設チャットリソースキットには、次のツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="368aa-120">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="368aa-121">次のセクションでは、要件や使用例など、各ツールの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="368aa-121">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="368aa-122">影響チェック</span><span class="sxs-lookup"><span data-stu-id="368aa-122">AffCheck</span></span>

  - <span data-ttu-id="368aa-123">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="368aa-123">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="368aa-124">ChatStress ツール</span><span class="sxs-lookup"><span data-stu-id="368aa-124">ChatStress Tool</span></span>

  - <span data-ttu-id="368aa-125">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="368aa-125">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="368aa-126">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="368aa-126">ChatUsageReport</span></span>

  - <span data-ttu-id="368aa-127">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="368aa-127">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="368aa-128">影響チェック</span><span class="sxs-lookup"><span data-stu-id="368aa-128">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="368aa-129">説明</span><span class="sxs-lookup"><span data-stu-id="368aa-129">Description</span></span>

<span data-ttu-id="368aa-130">このツールは、常設チャットのバックエンドデータベースユーザーとグループの所属レコードが Active Directory ドメインサービスのものと一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="368aa-130">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="368aa-131">要件</span><span class="sxs-lookup"><span data-stu-id="368aa-131">Requirements</span></span>

<span data-ttu-id="368aa-132">このツールは、PersistentChatResKit インストーラーを使用してドメインに参加しているコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="368aa-132">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="368aa-133">このツールを実行するユーザーアカウントには、常設チャットのバックエンドデータベースと Active Directory ドメインサービスへの読み取りアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="368aa-133">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="368aa-134">使用方法</span><span class="sxs-lookup"><span data-stu-id="368aa-134">Usage</span></span>

<span data-ttu-id="368aa-135">構成ファイルの指示に従って AffCheck.exe.config ファイルを構成し、コマンドラインパラメーターを指定せずに、影響チェックツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="368aa-135">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="368aa-136">既定の AffCheck.exe.config の内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="368aa-136">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="368aa-137">**AffCheck.exe.config:**</span><span class="sxs-lookup"><span data-stu-id="368aa-137">**AffCheck.exe.config:**</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a><span data-ttu-id="368aa-138">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="368aa-138">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="368aa-139">説明</span><span class="sxs-lookup"><span data-stu-id="368aa-139">Description</span></span>

<span data-ttu-id="368aa-140">PersistentChatMonitoringSummary ツールは、永続的なチャットの監視情報を監視データベースから、指定された CSV ログファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="368aa-140">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="368aa-141">CSV ファイルには、セッション数の合計、成功したセッション、予期しないエラー、予期されたエラー、診断 ID、エラーの数、エラーの説明による予期しないエラーの内訳による、常設チャットセッションの内訳が含まれています。</span><span class="sxs-lookup"><span data-stu-id="368aa-141">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="368aa-142">要件</span><span class="sxs-lookup"><span data-stu-id="368aa-142">Requirements</span></span>

<span data-ttu-id="368aa-143">監視データベースにアクセスできるドメインに参加しているコンピューターに常設チャットリソースキットツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="368aa-143">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="368aa-144">ツールを実行するユーザーアカウントは、監視データベースに対する読み取りアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-144">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="368aa-145">ファイル (PersistentChatMonitoringSummary.exe.config) には、 \<connectionStrings\> 監視データベースへの接続文字列を定義するセクションを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-145">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="368aa-146">また、監視データが収集される PersistentChatEndpointUri のキーと、生成される CSV ファイルの場所へのファイルパスも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-146">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="368aa-147">インストールされている構成ファイルで例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="368aa-147">Refer to the installed config file for examples.</span></span> <span data-ttu-id="368aa-148">このファイルは、ツールと同じディレクトリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-148">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="368aa-149">使用方法</span><span class="sxs-lookup"><span data-stu-id="368aa-149">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="368aa-150">これらのパラメーターは、データの選択を定義します。</span><span class="sxs-lookup"><span data-stu-id="368aa-150">These parameters define the selection of data:</span></span>

<span data-ttu-id="368aa-151">**StartDateTime:** オプションで、選択期間の開始日を指定します。</span><span class="sxs-lookup"><span data-stu-id="368aa-151">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="368aa-152">既定値: 1/1/1753 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="368aa-152">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="368aa-153">**Enddatetime:** オプションで、選択期間の最後の日付を指定します。</span><span class="sxs-lookup"><span data-stu-id="368aa-153">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="368aa-154">既定値: Now</span><span class="sxs-lookup"><span data-stu-id="368aa-154">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="368aa-155">例</span><span class="sxs-lookup"><span data-stu-id="368aa-155">Example</span></span>

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="368aa-156">常設チャットストレスツール</span><span class="sxs-lookup"><span data-stu-id="368aa-156">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="368aa-157">説明</span><span class="sxs-lookup"><span data-stu-id="368aa-157">Description</span></span>

<span data-ttu-id="368aa-158">常設チャットストレスツールは、永続的なチャットの使用をシミュレートする簡単な方法を提供します。これにより、さまざまなユーザーモデルを含めて、予想される使用シナリオに合わせて、現実的なパフォーマンスをテストできます。</span><span class="sxs-lookup"><span data-stu-id="368aa-158">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="368aa-159">要件</span><span class="sxs-lookup"><span data-stu-id="368aa-159">Requirements</span></span>

<span data-ttu-id="368aa-160">常設チャットリソースキットツールを、常設チャットバックエンドデータベースにアクセスできるドメインに参加しているコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="368aa-160">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="368aa-161">この *コントローラー* コンピューターに加えて、いくつかの *ローダー* マシンが必要になります。</span><span class="sxs-lookup"><span data-stu-id="368aa-161">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="368aa-162">ユーザーモデルの10,000 ユーザーごとに、少なくとも 4 GB の空き RAM がローダーコンピューターに必要になります。</span><span class="sxs-lookup"><span data-stu-id="368aa-162">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="368aa-163">たとえば、80K を使用して実行すると、すべてのローダーコンピューターにまたがる RAM の 32 GB について必要になります。</span><span class="sxs-lookup"><span data-stu-id="368aa-163">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="368aa-164">予想される負荷に関係なく、少なくとも3台のローダーコンピューターを用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="368aa-164">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="368aa-165">ローダーコンピューターには、.NET 4.5 Framework に加えて、Visual C++ 2012 再頒布可能パッケージがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-165">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="368aa-166">構成</span><span class="sxs-lookup"><span data-stu-id="368aa-166">Configuration</span></span>

<span data-ttu-id="368aa-167">ChatStressTool ファイルをすべてのローダーコンピューターからアクセス可能な共有フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="368aa-167">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="368aa-168">ストレス実行で使用するユーザーとチャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="368aa-168">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="368aa-169">ユーザーモデルからの呼び出しを行うユーザー数だけ作成し、Lync で有効にして、常設チャットポリシーを有効に設定します。</span><span class="sxs-lookup"><span data-stu-id="368aa-169">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="368aa-170">ストレスチャネルのカテゴリを作成し、そのカテゴリで必要なだけのルームを作成します。</span><span class="sxs-lookup"><span data-stu-id="368aa-170">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="368aa-171">カテゴリには、すべてのストレスユーザーが **許可され** たリストに含まれている必要があります (OU を追加することによって)。また、ストレスルームには、プライバシー設定を **開く**必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-171">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="368aa-172">特別なストレスルームを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="368aa-172">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="368aa-173">5万ルームは、次の Windows PowerShell コマンドラインインターフェイスコマンドを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="368aa-173">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="368aa-174">トポロジに合わせて構成ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="368aa-174">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="368aa-175">**LoaderProcess.exe.config**で、"controller.contoso.com" をコントローラーのコンピューターの完全修飾ドメイン名 (FQDN) に変更します。</span><span class="sxs-lookup"><span data-stu-id="368aa-175">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="368aa-176">StressLauncher.exe.config の場合 \*\* :\*\*</span><span class="sxs-lookup"><span data-stu-id="368aa-176">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="368aa-177">"LoaderBinary" 設定値を共有フォルダーのパスに変更します。</span><span class="sxs-lookup"><span data-stu-id="368aa-177">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="368aa-178">ローダーコンピューターに対する管理者アクセス権を持つ資格情報に、"AdminUser"/"Adminuser" を変更します。</span><span class="sxs-lookup"><span data-stu-id="368aa-178">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="368aa-179">"ChannelCategory" を、ストレスチャネルが作成されたカテゴリの名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="368aa-179">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="368aa-180">ストレスユーザーの資格情報に一致するテンプレートに "UserNamePattern" と "UserPasswordPattern" を変更します。</span><span class="sxs-lookup"><span data-stu-id="368aa-180">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="368aa-181">{0} は、ユーザーのインデックス番号に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="368aa-181">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="368aa-182">テストトポロジの SIP ドメインに "Domain" を変更します。</span><span class="sxs-lookup"><span data-stu-id="368aa-182">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="368aa-183">常設チャットバックエンドデータベースの接続文字列に "ConnectionString" を変更します。</span><span class="sxs-lookup"><span data-stu-id="368aa-183">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="368aa-184">"UserIndexStart" を最初のストレスユーザーのインデックスに変更します。</span><span class="sxs-lookup"><span data-stu-id="368aa-184">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="368aa-185">"LyncFQDN" をフロントエンドプールの FQDN に変更します。</span><span class="sxs-lookup"><span data-stu-id="368aa-185">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="368aa-186">すべてのローダーコンピューターのコンピューター名を含めるように、"Machines" リストを変更します。</span><span class="sxs-lookup"><span data-stu-id="368aa-186">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="368aa-187">サービスエンドポイントの baseAddress (既定値は "controller.contoso.com") を、使用しているコントローラーコンピューターの FQDN に変更します。</span><span class="sxs-lookup"><span data-stu-id="368aa-187">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="368aa-188">使用方法</span><span class="sxs-lookup"><span data-stu-id="368aa-188">Usage</span></span>

<span data-ttu-id="368aa-189">構成が完了したら、コントローラマシンの StressLauncher.exe を開きます。</span><span class="sxs-lookup"><span data-stu-id="368aa-189">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="368aa-190">StressLauncher は、任意のユーザーとして起動できます。</span><span class="sxs-lookup"><span data-stu-id="368aa-190">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="368aa-191">ローダーコンピューターでのローダープロセスの開始に使用する資格情報は、構成ファイルで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-191">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="368aa-192">また、常設チャットバックエンドデータベースへの読み取りアクセス権を持つ接続文字列も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-192">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="368aa-193">この接続文字列が統合 Windows 認証を使用している場合は、このアクセス権を持つユーザーとして StressLauncher を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-193">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="368aa-194">必要に応じて、ユーザーモデルの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="368aa-194">Alter the user model settings as needed.</span></span> <span data-ttu-id="368aa-195">[ **読み込み開始** ] をクリックして、実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="368aa-195">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="368aa-196">1分以上経過すると、ユーザーはサインインし始め、進行状況バーがいっぱいになります。</span><span class="sxs-lookup"><span data-stu-id="368aa-196">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="368aa-197">この時点で、コントローラーマシンは動作し、パフォーマンスの測定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="368aa-197">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="368aa-198">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="368aa-198">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="368aa-199">説明</span><span class="sxs-lookup"><span data-stu-id="368aa-199">Description</span></span>

<span data-ttu-id="368aa-200">ChatUpgradeVerifier は、常設チャット固有のデータベース比較ツールです。</span><span class="sxs-lookup"><span data-stu-id="368aa-200">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="368aa-201">このツールでは、グループチャット 2007 R2 またはグループチャット2010データベース (2007/2010Db) を常設チャット2013データベース (2010Db) に比較します。</span><span class="sxs-lookup"><span data-stu-id="368aa-201">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="368aa-202">ツールは、1つずつ、それぞれカテゴリ、常設チャットルーム、および 2007/2010Db のアドインをチェックして、2010Db に表示されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="368aa-202">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="368aa-203">この比較には、カテゴリ、チャットルーム、またはアドインのすべての設定、カテゴリのスコープ内のプリンシパル、およびカテゴリまたはチャットルームのいずれかのロールのプリンシパルがすべてチェックされます。</span><span class="sxs-lookup"><span data-stu-id="368aa-203">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="368aa-204">カテゴリまたはチャットルームが2013Db で正しく表示されない場合は、競合ファイルにその違いが出力されます。</span><span class="sxs-lookup"><span data-stu-id="368aa-204">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="368aa-205">アップグレードが行われた後、2007/2010Db が変更された後、このツールが実行されると、競合ファイルへの相違が出力されます。</span><span class="sxs-lookup"><span data-stu-id="368aa-205">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="368aa-206">このアプリケーションはデータベース比較ツールにのみ適用され、アップグレードプロセスは検証されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="368aa-206">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="368aa-207">要件</span><span class="sxs-lookup"><span data-stu-id="368aa-207">Requirements</span></span>

<span data-ttu-id="368aa-208">常設チャットリソースキットツールを、常設チャットバックエンドデータベース (常設チャットの場合は以前のバージョンと現在のバージョン) にアクセスできるドメインに参加しているコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="368aa-208">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="368aa-209">ツールを実行するユーザーアカウントは、常設チャットデータベースへの読み取りアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-209">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="368aa-210">ChatUpgradeVerifier.exe.config ファイルには、適切なグループチャットデータベース (Groupchat 2007R2 または 2010) への接続文字列を含む GroupChat2007R2Db パラメーターまたは GroupChat2010Db パラメーターのいずれかが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-210">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="368aa-211">また、常設チャット2013データベースへの接続文字列を含む PersistentChat2013Db パラメーターも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-211">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="368aa-212">使用方法</span><span class="sxs-lookup"><span data-stu-id="368aa-212">Usage</span></span>

<span data-ttu-id="368aa-213">**Chatupgradeverifier**をパラメーターなしで実行します。</span><span class="sxs-lookup"><span data-stu-id="368aa-213">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="368aa-214">例</span><span class="sxs-lookup"><span data-stu-id="368aa-214">Example</span></span>

<span data-ttu-id="368aa-215">![ChatUpgradeVerifier.exe を実行しています。](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "ChatUpgradeVerifier.exe を実行しています。")</span><span class="sxs-lookup"><span data-stu-id="368aa-215">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="368aa-216">常設チャットの使用レポート</span><span class="sxs-lookup"><span data-stu-id="368aa-216">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="368aa-217">説明</span><span class="sxs-lookup"><span data-stu-id="368aa-217">Description</span></span>

<span data-ttu-id="368aa-218">ChatUsageReport ツールは、常設チャットサービスの利用状況の HTML レポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="368aa-218">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="368aa-219">要件</span><span class="sxs-lookup"><span data-stu-id="368aa-219">Requirements</span></span>

<span data-ttu-id="368aa-220">常設チャットリソースキットツールを、常設チャットバックエンドデータベースにアクセスできるドメインに参加しているコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="368aa-220">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="368aa-221">ツールを実行するユーザーアカウントは、常設チャットのバックエンドデータベースに対する読み取りアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-221">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="368aa-222">ファイル (ChatUsageReport.exe.config) には、 \<connectionStrings\> 常設チャットバックエンドデータベースへの接続文字列を定義するセクションを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-222">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="368aa-223">既定の構成ファイルの内容は、参照用にここに記載されています。</span><span class="sxs-lookup"><span data-stu-id="368aa-223">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="368aa-224">使用方法</span><span class="sxs-lookup"><span data-stu-id="368aa-224">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="368aa-225">これらのパラメーターは、データの選択を定義します。</span><span class="sxs-lookup"><span data-stu-id="368aa-225">These parameters define the selection of data:</span></span>

<span data-ttu-id="368aa-226">**StartDate:** オプションで、選択期間の UTC 開始日を指定します。</span><span class="sxs-lookup"><span data-stu-id="368aa-226">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="368aa-227">既定値: 最も早い日付</span><span class="sxs-lookup"><span data-stu-id="368aa-227">Default: Earliest Date</span></span>

<span data-ttu-id="368aa-228">**EndDate:** オプションで、選択期間の UTC 終了日を指定します。</span><span class="sxs-lookup"><span data-stu-id="368aa-228">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="368aa-229">既定値: Now</span><span class="sxs-lookup"><span data-stu-id="368aa-229">Default: Now</span></span>

<span data-ttu-id="368aa-230">これらのパラメーターは、どのデータをどのように表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="368aa-230">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="368aa-231">**Topactiveusers:** この値を指定すると、ユーザーが選択した期間のチャットルームに投稿したメッセージ数に関して、最もアクティブな n 人のユーザーがレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="368aa-231">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="368aa-232">既定値: 10</span><span class="sxs-lookup"><span data-stu-id="368aa-232">Default: 10</span></span>

<span data-ttu-id="368aa-233">**TopActiveRooms:** この値が指定されている場合、選択された期間の会議室に投稿されたメッセージの数に関して、最もアクティブなチャットルームがレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="368aa-233">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="368aa-234">既定値: 10</span><span class="sxs-lookup"><span data-stu-id="368aa-234">Default: 10</span></span>

<span data-ttu-id="368aa-235">**LeastActiveRooms:** この値が指定されている場合、選択した期間のチャットルームに投稿されたメッセージ数に関して、少なくとも1個のアクティブなチャットルームがレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="368aa-235">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="368aa-236">ルームには、少なくとも1つのメッセージが投稿されます。</span><span class="sxs-lookup"><span data-stu-id="368aa-236">Rooms will have at least one message posted.</span></span> <span data-ttu-id="368aa-237">既定値: 10</span><span class="sxs-lookup"><span data-stu-id="368aa-237">Default: 10</span></span>

<span data-ttu-id="368aa-238">**RoomsInactiveSince:** この指定を指定すると、指定された日付以降に非アクティブになったチャットルームの一覧がレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="368aa-238">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="368aa-239">既定値: 時間全体</span><span class="sxs-lookup"><span data-stu-id="368aa-239">Default: Entire Time</span></span>

<span data-ttu-id="368aa-240">**Outputfolder:** ChatUsageReport.html およびグラフ画像が配置されるフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="368aa-240">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="368aa-241">これは、config ファイルまたはコマンドラインで定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-241">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="368aa-242">すべてのコマンドラインパラメーター値は、ツールと同じディレクトリにある ChatUsageReport.exe.config ファイルでも指定できます。</span><span class="sxs-lookup"><span data-stu-id="368aa-242">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="368aa-243">構成ファイルとコマンドラインの両方でいずれかの値が指定されている場合、コマンドラインの値は構成ファイルの値より優先されます。</span><span class="sxs-lookup"><span data-stu-id="368aa-243">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="368aa-244">出力</span><span class="sxs-lookup"><span data-stu-id="368aa-244">Output</span></span>

<span data-ttu-id="368aa-245">レポートには、常に次の出力が含まれます。</span><span class="sxs-lookup"><span data-stu-id="368aa-245">The report will always include the following output:</span></span>

  - <span data-ttu-id="368aa-246">選択した期間のメッセージ投稿数ごとの最もアクティブなチャットルームの上位 n 個。</span><span class="sxs-lookup"><span data-stu-id="368aa-246">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="368aa-247">選択した期間のメッセージ投稿数ごとの上位 n 個のアクティブユーザー。</span><span class="sxs-lookup"><span data-stu-id="368aa-247">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="368aa-248">選択した期間のメッセージ投稿数ごとの、最もアクティブでないチャットルームの上位 n 個。</span><span class="sxs-lookup"><span data-stu-id="368aa-248">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="368aa-249">データベースの全期間または指定された日付以降に非アクティブなチャットルーム。</span><span class="sxs-lookup"><span data-stu-id="368aa-249">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="368aa-250">選択した期間の毎日のメッセージ投稿の傾向。</span><span class="sxs-lookup"><span data-stu-id="368aa-250">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="368aa-251">選択した期間の週単位のメッセージ投稿の傾向。</span><span class="sxs-lookup"><span data-stu-id="368aa-251">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="368aa-252">選択された期間のメッセージ投稿の月単位の傾向。</span><span class="sxs-lookup"><span data-stu-id="368aa-252">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="368aa-253">選択した期間のメッセージ投稿の合計数。</span><span class="sxs-lookup"><span data-stu-id="368aa-253">Total message posts for selected period.</span></span>

  - <span data-ttu-id="368aa-254">有効になっているルームの合計数。</span><span class="sxs-lookup"><span data-stu-id="368aa-254">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="368aa-255">例</span><span class="sxs-lookup"><span data-stu-id="368aa-255">Example</span></span>

<span data-ttu-id="368aa-256">次の例では、2001年全体の利用状況レポートを生成し、ChatUsageReport.exe.config で指定されている OutputFolder にレポートを配置します。</span><span class="sxs-lookup"><span data-stu-id="368aa-256">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="368aa-257">ChatUsageReport.exe.config:</span><span class="sxs-lookup"><span data-stu-id="368aa-257">ChatUsageReport.exe.config:</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="368aa-258">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="368aa-258">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="368aa-259">説明</span><span class="sxs-lookup"><span data-stu-id="368aa-259">Description</span></span>

<span data-ttu-id="368aa-260">ScheduleADSyncForPrincipal は、常設チャットバックエンドデータベースに接続されている場合に SQL Server Management Studio 内から直接実行する必要がある Microsoft SQL Server 2012 スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="368aa-260">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="368aa-261">このスクリプトを使用すると、永続的なチャットを強制して、スケジュールされた同期時間を待つのではなく、ユーザーのレコードを Active Directory ドメインサービスのレコードと同期させることができます。</span><span class="sxs-lookup"><span data-stu-id="368aa-261">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="368aa-262">要件</span><span class="sxs-lookup"><span data-stu-id="368aa-262">Requirements</span></span>

<span data-ttu-id="368aa-263">スクリプトを実行するユーザーアカウントは、常設チャットのバックエンドデータベースに対する所有者アクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="368aa-263">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="368aa-264">使用方法</span><span class="sxs-lookup"><span data-stu-id="368aa-264">Usage</span></span>

<span data-ttu-id="368aa-265">既定のスクリプトの内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="368aa-265">Following are the contents of the default script:</span></span>

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

