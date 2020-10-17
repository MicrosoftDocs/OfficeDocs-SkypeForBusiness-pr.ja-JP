---
title: Lync Server 2013 常設チャットリソースキットツール
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
ms.openlocfilehash: 80a9116374914c212d305ef2e55d0b8c4fecb782
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533674"
---
# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="10662-102">Lync Server 2013 常設チャットリソースキットツール</span><span class="sxs-lookup"><span data-stu-id="10662-102">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10662-103">_**トピックの最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="10662-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="10662-104">Lync Server 2013 常設チャットリソースキットツールは、Lync Server 2013 常設チャットサーバーを展開して管理する IT 管理者にとって、日常的な作業を容易にするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="10662-104">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="10662-105">このトピックでは、インストール手順だけでなく、各ツールの目的と使用例についても説明します。</span><span class="sxs-lookup"><span data-stu-id="10662-105">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="10662-106">リソースキットツールのインストール</span><span class="sxs-lookup"><span data-stu-id="10662-106">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="10662-107">Lync Server 2013 のリソースキットツールをインストールするには、 **PersistentChatReskit.msi**をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="10662-107">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="10662-108">**PersistentChatReskit.msi**を実行して簡単なインストールを行います。</span><span class="sxs-lookup"><span data-stu-id="10662-108">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="10662-109">.Msi は、次のパスにあるすべてのツールをインストールします。 \\ **Program Files \\ Microsoft Lync Server 2013 \\ 常設チャットサーバーリソースキット**。</span><span class="sxs-lookup"><span data-stu-id="10662-109">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="10662-110">このフォルダーには、自己完結型の実行可能ファイルであるツールがあります。</span><span class="sxs-lookup"><span data-stu-id="10662-110">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="10662-111">ファイルが含まれているツールも、それぞれ独自のサブフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="10662-111">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="10662-112">Lync Server 2013 のリソースキットツールをインストールした後、 <STRONG>PsExec.exe</STRONG>をインストールし、 <STRONG>PsExec.exe</STRONG>を次のパスにコピーする必要があります。 \\ <STRONG>Program Files Kit\ChatStressTool The Microsoft Lync Server 2013 \ 常設 Chat server Resource</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="10662-112">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="10662-113"><STRONG>PsExec.exe</STRONG>をコピーしない場合、常設チャットストレスツールはエラー例外をスローし、正しく実行されません。</span><span class="sxs-lookup"><span data-stu-id="10662-113">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="10662-114">ツールを実行する前に、この前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="10662-114">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="10662-115"><STRONG>PsExec.exe</STRONG>のインストールの詳細については、「」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A> 。</span><span class="sxs-lookup"><span data-stu-id="10662-115">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="10662-116">サポートされる環境</span><span class="sxs-lookup"><span data-stu-id="10662-116">Supported Environments</span></span>

<span data-ttu-id="10662-117">最適なパフォーマンスを得るために、lync server 2013、リソースキットツールは、Lync Server 2013 に必要なものと同じ環境にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-117">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="10662-118">リソースキットツールの概要</span><span class="sxs-lookup"><span data-stu-id="10662-118">Resource Kit Tools Overview</span></span>

<span data-ttu-id="10662-119">Lync Server 2013 常設チャットリソースキットには、次のツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="10662-119">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="10662-120">次のセクションでは、要件や使用例など、各ツールの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="10662-120">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="10662-121">影響チェック</span><span class="sxs-lookup"><span data-stu-id="10662-121">AffCheck</span></span>

  - <span data-ttu-id="10662-122">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="10662-122">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="10662-123">ChatStress ツール</span><span class="sxs-lookup"><span data-stu-id="10662-123">ChatStress Tool</span></span>

  - <span data-ttu-id="10662-124">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="10662-124">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="10662-125">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="10662-125">ChatUsageReport</span></span>

  - <span data-ttu-id="10662-126">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="10662-126">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="10662-127">影響チェック</span><span class="sxs-lookup"><span data-stu-id="10662-127">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="10662-128">説明</span><span class="sxs-lookup"><span data-stu-id="10662-128">Description</span></span>

<span data-ttu-id="10662-129">このツールは、常設チャットのバックエンドデータベースユーザーとグループの所属レコードが Active Directory ドメインサービスのものと一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="10662-129">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="10662-130">要件</span><span class="sxs-lookup"><span data-stu-id="10662-130">Requirements</span></span>

<span data-ttu-id="10662-131">このツールは、PersistentChatResKit インストーラーを使用してドメインに参加しているコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="10662-131">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="10662-132">このツールを実行するユーザーアカウントには、常設チャットのバックエンドデータベースと Active Directory ドメインサービスへの読み取りアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="10662-132">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="10662-133">使用方法</span><span class="sxs-lookup"><span data-stu-id="10662-133">Usage</span></span>

<span data-ttu-id="10662-134">構成ファイルの指示に従って AffCheck.exe.config ファイルを構成し、コマンドラインパラメーターを指定せずに、影響チェックツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="10662-134">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="10662-135">既定の AffCheck.exe.config の内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="10662-135">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="10662-136">**AffCheck.exe.config:**</span><span class="sxs-lookup"><span data-stu-id="10662-136">**AffCheck.exe.config:**</span></span>

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

## <a name="chatmonitoringsummary"></a><span data-ttu-id="10662-137">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="10662-137">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="10662-138">説明</span><span class="sxs-lookup"><span data-stu-id="10662-138">Description</span></span>

<span data-ttu-id="10662-139">PersistentChatMonitoringSummary ツールは、永続的なチャットの監視情報を監視データベースから、指定された CSV ログファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="10662-139">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="10662-140">CSV ファイルには、セッション数の合計、成功したセッション、予期しないエラー、予期されたエラー、診断 ID、エラーの数、エラーの説明による予期しないエラーの内訳による、常設チャットセッションの内訳が含まれています。</span><span class="sxs-lookup"><span data-stu-id="10662-140">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="10662-141">要件</span><span class="sxs-lookup"><span data-stu-id="10662-141">Requirements</span></span>

<span data-ttu-id="10662-142">監視データベースにアクセスできるドメインに参加しているコンピューターに常設チャットリソースキットツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="10662-142">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="10662-143">ツールを実行するユーザーアカウントは、監視データベースに対する読み取りアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-143">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="10662-144">ファイル (PersistentChatMonitoringSummary.exe.config) には、 \<connectionStrings\> 監視データベースへの接続文字列を定義するセクションを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-144">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="10662-145">また、監視データが収集される PersistentChatEndpointUri のキーと、生成される CSV ファイルの場所へのファイルパスも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-145">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="10662-146">インストールされている構成ファイルで例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10662-146">Refer to the installed config file for examples.</span></span> <span data-ttu-id="10662-147">このファイルは、ツールと同じディレクトリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-147">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="10662-148">使用方法</span><span class="sxs-lookup"><span data-stu-id="10662-148">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="10662-149">これらのパラメーターは、データの選択を定義します。</span><span class="sxs-lookup"><span data-stu-id="10662-149">These parameters define the selection of data:</span></span>

<span data-ttu-id="10662-150">**StartDateTime:** オプションで、選択期間の開始日を指定します。</span><span class="sxs-lookup"><span data-stu-id="10662-150">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="10662-151">既定値: 1/1/1753 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="10662-151">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="10662-152">**Enddatetime:** オプションで、選択期間の最後の日付を指定します。</span><span class="sxs-lookup"><span data-stu-id="10662-152">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="10662-153">既定値: Now</span><span class="sxs-lookup"><span data-stu-id="10662-153">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="10662-154">例</span><span class="sxs-lookup"><span data-stu-id="10662-154">Example</span></span>

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

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="10662-155">常設チャットストレスツール</span><span class="sxs-lookup"><span data-stu-id="10662-155">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="10662-156">説明</span><span class="sxs-lookup"><span data-stu-id="10662-156">Description</span></span>

<span data-ttu-id="10662-157">常設チャットストレスツールは、永続的なチャットの使用をシミュレートする簡単な方法を提供します。これにより、さまざまなユーザーモデルを含めて、予想される使用シナリオに合わせて、現実的なパフォーマンスをテストできます。</span><span class="sxs-lookup"><span data-stu-id="10662-157">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="10662-158">要件</span><span class="sxs-lookup"><span data-stu-id="10662-158">Requirements</span></span>

<span data-ttu-id="10662-159">常設チャットリソースキットツールを、常設チャットバックエンドデータベースにアクセスできるドメインに参加しているコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="10662-159">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="10662-160">この *コントローラー* コンピューターに加えて、いくつかの *ローダー* マシンが必要になります。</span><span class="sxs-lookup"><span data-stu-id="10662-160">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="10662-161">ユーザーモデルの10,000 ユーザーごとに、少なくとも 4 GB の空き RAM がローダーコンピューターに必要になります。</span><span class="sxs-lookup"><span data-stu-id="10662-161">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="10662-162">たとえば、80K を使用して実行すると、すべてのローダーコンピューターにまたがる RAM の 32 GB について必要になります。</span><span class="sxs-lookup"><span data-stu-id="10662-162">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="10662-163">予想される負荷に関係なく、少なくとも3台のローダーコンピューターを用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="10662-163">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="10662-164">ローダーコンピューターには、.NET 4.5 Framework に加えて、Visual C++ 2012 再頒布可能パッケージがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-164">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="10662-165">構成</span><span class="sxs-lookup"><span data-stu-id="10662-165">Configuration</span></span>

<span data-ttu-id="10662-166">ChatStressTool ファイルをすべてのローダーコンピューターからアクセス可能な共有フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="10662-166">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="10662-167">ストレス実行で使用するユーザーとチャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="10662-167">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="10662-168">ユーザーモデルからの呼び出しを行うユーザー数だけ作成し、Lync で有効にして、常設チャットポリシーを有効に設定します。</span><span class="sxs-lookup"><span data-stu-id="10662-168">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="10662-169">ストレスチャネルのカテゴリを作成し、そのカテゴリで必要なだけのルームを作成します。</span><span class="sxs-lookup"><span data-stu-id="10662-169">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="10662-170">カテゴリには、すべてのストレスユーザーが **許可され** たリストに含まれている必要があります (OU を追加することによって)。また、ストレスルームには、プライバシー設定を **開く**必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-170">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="10662-171">特別なストレスルームを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="10662-171">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="10662-172">5万ルームは、次の Windows PowerShell コマンドラインインターフェイスコマンドを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="10662-172">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="10662-173">トポロジに合わせて構成ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="10662-173">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="10662-174">**LoaderProcess.exe.config**で、"controller.contoso.com" をコントローラーのコンピューターの完全修飾ドメイン名 (FQDN) に変更します。</span><span class="sxs-lookup"><span data-stu-id="10662-174">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="10662-175">StressLauncher.exe.config の場合 \*\* :\*\*</span><span class="sxs-lookup"><span data-stu-id="10662-175">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="10662-176">"LoaderBinary" 設定値を共有フォルダーのパスに変更します。</span><span class="sxs-lookup"><span data-stu-id="10662-176">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="10662-177">ローダーコンピューターに対する管理者アクセス権を持つ資格情報に、"AdminUser"/"Adminuser" を変更します。</span><span class="sxs-lookup"><span data-stu-id="10662-177">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="10662-178">"ChannelCategory" を、ストレスチャネルが作成されたカテゴリの名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="10662-178">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="10662-179">ストレスユーザーの資格情報に一致するテンプレートに "UserNamePattern" と "UserPasswordPattern" を変更します。</span><span class="sxs-lookup"><span data-stu-id="10662-179">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="10662-180">{0} は、ユーザーのインデックス番号に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="10662-180">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="10662-181">テストトポロジの SIP ドメインに "Domain" を変更します。</span><span class="sxs-lookup"><span data-stu-id="10662-181">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="10662-182">常設チャットバックエンドデータベースの接続文字列に "ConnectionString" を変更します。</span><span class="sxs-lookup"><span data-stu-id="10662-182">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="10662-183">"UserIndexStart" を最初のストレスユーザーのインデックスに変更します。</span><span class="sxs-lookup"><span data-stu-id="10662-183">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="10662-184">"LyncFQDN" をフロントエンドプールの FQDN に変更します。</span><span class="sxs-lookup"><span data-stu-id="10662-184">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="10662-185">すべてのローダーコンピューターのコンピューター名を含めるように、"Machines" リストを変更します。</span><span class="sxs-lookup"><span data-stu-id="10662-185">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="10662-186">サービスエンドポイントの baseAddress (既定値は "controller.contoso.com") を、使用しているコントローラーコンピューターの FQDN に変更します。</span><span class="sxs-lookup"><span data-stu-id="10662-186">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="10662-187">使用方法</span><span class="sxs-lookup"><span data-stu-id="10662-187">Usage</span></span>

<span data-ttu-id="10662-188">構成が完了したら、コントローラマシンの StressLauncher.exe を開きます。</span><span class="sxs-lookup"><span data-stu-id="10662-188">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="10662-189">StressLauncher は、任意のユーザーとして起動できます。</span><span class="sxs-lookup"><span data-stu-id="10662-189">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="10662-190">ローダーコンピューターでのローダープロセスの開始に使用する資格情報は、構成ファイルで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-190">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="10662-191">また、常設チャットバックエンドデータベースへの読み取りアクセス権を持つ接続文字列も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-191">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="10662-192">この接続文字列が統合 Windows 認証を使用している場合は、このアクセス権を持つユーザーとして StressLauncher を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-192">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="10662-193">必要に応じて、ユーザーモデルの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="10662-193">Alter the user model settings as needed.</span></span> <span data-ttu-id="10662-194">[ **読み込み開始** ] をクリックして、実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="10662-194">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="10662-195">1分以上経過すると、ユーザーはサインインし始め、進行状況バーがいっぱいになります。</span><span class="sxs-lookup"><span data-stu-id="10662-195">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="10662-196">この時点で、コントローラーマシンは動作し、パフォーマンスの測定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="10662-196">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="10662-197">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="10662-197">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="10662-198">説明</span><span class="sxs-lookup"><span data-stu-id="10662-198">Description</span></span>

<span data-ttu-id="10662-199">ChatUpgradeVerifier は、常設チャット固有のデータベース比較ツールです。</span><span class="sxs-lookup"><span data-stu-id="10662-199">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="10662-200">このツールでは、グループチャット 2007 R2 またはグループチャット2010データベース (2007/2010Db) を常設チャット2013データベース (2010Db) に比較します。</span><span class="sxs-lookup"><span data-stu-id="10662-200">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="10662-201">ツールは、1つずつ、それぞれカテゴリ、常設チャットルーム、および 2007/2010Db のアドインをチェックして、2010Db に表示されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="10662-201">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="10662-202">この比較には、カテゴリ、チャットルーム、またはアドインのすべての設定、カテゴリのスコープ内のプリンシパル、およびカテゴリまたはチャットルームのいずれかのロールのプリンシパルがすべてチェックされます。</span><span class="sxs-lookup"><span data-stu-id="10662-202">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="10662-203">カテゴリまたはチャットルームが2013Db で正しく表示されない場合は、競合ファイルにその違いが出力されます。</span><span class="sxs-lookup"><span data-stu-id="10662-203">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="10662-204">アップグレードが行われた後、2007/2010Db が変更された後、このツールが実行されると、競合ファイルへの相違が出力されます。</span><span class="sxs-lookup"><span data-stu-id="10662-204">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="10662-205">このアプリケーションはデータベース比較ツールにのみ適用され、アップグレードプロセスは検証されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="10662-205">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="10662-206">要件</span><span class="sxs-lookup"><span data-stu-id="10662-206">Requirements</span></span>

<span data-ttu-id="10662-207">常設チャットリソースキットツールを、常設チャットバックエンドデータベース (常設チャットの場合は以前のバージョンと現在のバージョン) にアクセスできるドメインに参加しているコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="10662-207">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="10662-208">ツールを実行するユーザーアカウントは、常設チャットデータベースへの読み取りアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-208">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="10662-209">ChatUpgradeVerifier.exe.config ファイルには、適切なグループチャットデータベース (Groupchat 2007R2 または 2010) への接続文字列を含む GroupChat2007R2Db パラメーターまたは GroupChat2010Db パラメーターのいずれかが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-209">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="10662-210">また、常設チャット2013データベースへの接続文字列を含む PersistentChat2013Db パラメーターも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-210">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="10662-211">使用方法</span><span class="sxs-lookup"><span data-stu-id="10662-211">Usage</span></span>

<span data-ttu-id="10662-212">**Chatupgradeverifier**をパラメーターなしで実行します。</span><span class="sxs-lookup"><span data-stu-id="10662-212">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="10662-213">例</span><span class="sxs-lookup"><span data-stu-id="10662-213">Example</span></span>

<span data-ttu-id="10662-214">![ChatUpgradeVerifier.exe を実行しています。](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "ChatUpgradeVerifier.exe を実行しています。")</span><span class="sxs-lookup"><span data-stu-id="10662-214">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="10662-215">常設チャットの使用レポート</span><span class="sxs-lookup"><span data-stu-id="10662-215">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="10662-216">説明</span><span class="sxs-lookup"><span data-stu-id="10662-216">Description</span></span>

<span data-ttu-id="10662-217">ChatUsageReport ツールは、常設チャットサービスの利用状況の HTML レポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="10662-217">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="10662-218">要件</span><span class="sxs-lookup"><span data-stu-id="10662-218">Requirements</span></span>

<span data-ttu-id="10662-219">常設チャットリソースキットツールを、常設チャットバックエンドデータベースにアクセスできるドメインに参加しているコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="10662-219">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="10662-220">ツールを実行するユーザーアカウントは、常設チャットのバックエンドデータベースに対する読み取りアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-220">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="10662-221">ファイル (ChatUsageReport.exe.config) には、 \<connectionStrings\> 常設チャットバックエンドデータベースへの接続文字列を定義するセクションを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-221">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="10662-222">既定の構成ファイルの内容は、参照用にここに記載されています。</span><span class="sxs-lookup"><span data-stu-id="10662-222">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="10662-223">使用方法</span><span class="sxs-lookup"><span data-stu-id="10662-223">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="10662-224">これらのパラメーターは、データの選択を定義します。</span><span class="sxs-lookup"><span data-stu-id="10662-224">These parameters define the selection of data:</span></span>

<span data-ttu-id="10662-225">**StartDate:** オプションで、選択期間の UTC 開始日を指定します。</span><span class="sxs-lookup"><span data-stu-id="10662-225">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="10662-226">既定値: 最も早い日付</span><span class="sxs-lookup"><span data-stu-id="10662-226">Default: Earliest Date</span></span>

<span data-ttu-id="10662-227">**EndDate:** オプションで、選択期間の UTC 終了日を指定します。</span><span class="sxs-lookup"><span data-stu-id="10662-227">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="10662-228">既定値: Now</span><span class="sxs-lookup"><span data-stu-id="10662-228">Default: Now</span></span>

<span data-ttu-id="10662-229">これらのパラメーターは、どのデータをどのように表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="10662-229">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="10662-230">**Topactiveusers:** この値を指定すると、ユーザーが選択した期間のチャットルームに投稿したメッセージ数に関して、最もアクティブな n 人のユーザーがレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="10662-230">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="10662-231">既定値: 10</span><span class="sxs-lookup"><span data-stu-id="10662-231">Default: 10</span></span>

<span data-ttu-id="10662-232">**TopActiveRooms:** この値が指定されている場合、選択された期間の会議室に投稿されたメッセージの数に関して、最もアクティブなチャットルームがレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="10662-232">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="10662-233">既定値: 10</span><span class="sxs-lookup"><span data-stu-id="10662-233">Default: 10</span></span>

<span data-ttu-id="10662-234">**LeastActiveRooms:** この値が指定されている場合、選択した期間のチャットルームに投稿されたメッセージ数に関して、少なくとも1個のアクティブなチャットルームがレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="10662-234">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="10662-235">ルームには、少なくとも1つのメッセージが投稿されます。</span><span class="sxs-lookup"><span data-stu-id="10662-235">Rooms will have at least one message posted.</span></span> <span data-ttu-id="10662-236">既定値: 10</span><span class="sxs-lookup"><span data-stu-id="10662-236">Default: 10</span></span>

<span data-ttu-id="10662-237">**RoomsInactiveSince:** この指定を指定すると、指定された日付以降に非アクティブになったチャットルームの一覧がレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="10662-237">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="10662-238">既定値: 時間全体</span><span class="sxs-lookup"><span data-stu-id="10662-238">Default: Entire Time</span></span>

<span data-ttu-id="10662-239">**Outputfolder:** ChatUsageReport.html およびグラフ画像が配置されるフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="10662-239">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="10662-240">これは、config ファイルまたはコマンドラインで定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-240">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="10662-241">すべてのコマンドラインパラメーター値は、ツールと同じディレクトリにある ChatUsageReport.exe.config ファイルでも指定できます。</span><span class="sxs-lookup"><span data-stu-id="10662-241">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="10662-242">構成ファイルとコマンドラインの両方でいずれかの値が指定されている場合、コマンドラインの値は構成ファイルの値より優先されます。</span><span class="sxs-lookup"><span data-stu-id="10662-242">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="10662-243">出力</span><span class="sxs-lookup"><span data-stu-id="10662-243">Output</span></span>

<span data-ttu-id="10662-244">レポートには、常に次の出力が含まれます。</span><span class="sxs-lookup"><span data-stu-id="10662-244">The report will always include the following output:</span></span>

  - <span data-ttu-id="10662-245">選択した期間のメッセージ投稿数ごとの最もアクティブなチャットルームの上位 n 個。</span><span class="sxs-lookup"><span data-stu-id="10662-245">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="10662-246">選択した期間のメッセージ投稿数ごとの上位 n 個のアクティブユーザー。</span><span class="sxs-lookup"><span data-stu-id="10662-246">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="10662-247">選択した期間のメッセージ投稿数ごとの、最もアクティブでないチャットルームの上位 n 個。</span><span class="sxs-lookup"><span data-stu-id="10662-247">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="10662-248">データベースの全期間または指定された日付以降に非アクティブなチャットルーム。</span><span class="sxs-lookup"><span data-stu-id="10662-248">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="10662-249">選択した期間の毎日のメッセージ投稿の傾向。</span><span class="sxs-lookup"><span data-stu-id="10662-249">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="10662-250">選択した期間の週単位のメッセージ投稿の傾向。</span><span class="sxs-lookup"><span data-stu-id="10662-250">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="10662-251">選択された期間のメッセージ投稿の月単位の傾向。</span><span class="sxs-lookup"><span data-stu-id="10662-251">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="10662-252">選択した期間のメッセージ投稿の合計数。</span><span class="sxs-lookup"><span data-stu-id="10662-252">Total message posts for selected period.</span></span>

  - <span data-ttu-id="10662-253">有効になっているルームの合計数。</span><span class="sxs-lookup"><span data-stu-id="10662-253">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="10662-254">例</span><span class="sxs-lookup"><span data-stu-id="10662-254">Example</span></span>

<span data-ttu-id="10662-255">次の例では、2001年全体の利用状況レポートを生成し、ChatUsageReport.exe.config で指定されている OutputFolder にレポートを配置します。</span><span class="sxs-lookup"><span data-stu-id="10662-255">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="10662-256">ChatUsageReport.exe.config:</span><span class="sxs-lookup"><span data-stu-id="10662-256">ChatUsageReport.exe.config:</span></span>

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

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="10662-257">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="10662-257">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="10662-258">説明</span><span class="sxs-lookup"><span data-stu-id="10662-258">Description</span></span>

<span data-ttu-id="10662-259">ScheduleADSyncForPrincipal は、常設チャットバックエンドデータベースに接続されている場合に SQL Server Management Studio 内から直接実行する必要がある Microsoft SQL Server 2012 スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="10662-259">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="10662-260">このスクリプトを使用すると、永続的なチャットを強制して、スケジュールされた同期時間を待つのではなく、ユーザーのレコードを Active Directory ドメインサービスのレコードと同期させることができます。</span><span class="sxs-lookup"><span data-stu-id="10662-260">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="10662-261">要件</span><span class="sxs-lookup"><span data-stu-id="10662-261">Requirements</span></span>

<span data-ttu-id="10662-262">スクリプトを実行するユーザーアカウントは、常設チャットのバックエンドデータベースに対する所有者アクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10662-262">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="10662-263">使用方法</span><span class="sxs-lookup"><span data-stu-id="10662-263">Usage</span></span>

<span data-ttu-id="10662-264">既定のスクリプトの内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="10662-264">Following are the contents of the default script:</span></span>

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

