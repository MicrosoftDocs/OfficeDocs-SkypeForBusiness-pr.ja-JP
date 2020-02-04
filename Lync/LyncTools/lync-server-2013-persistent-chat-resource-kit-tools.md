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
ms.openlocfilehash: a827892dac61ff88d0527eafb7d94948afa21885
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="6b767-102">Lync Server 2013 常設チャットリソースキットツール</span><span class="sxs-lookup"><span data-stu-id="6b767-102">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b767-103">_**最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="6b767-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="6b767-104">Lync Server 2013 常設チャットリソースキットツールは、Lync Server 2013 常設チャットサーバーの展開と管理を行う IT 管理者にとって、日常的なタスクを簡単にするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6b767-104">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="6b767-105">このトピックでは、インストール手順に加えて、各ツールの目的とその用途の例について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b767-105">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="6b767-106">リソース キット ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="6b767-106">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="6b767-107">Lync Server 2013 のリソースキットツールをインストールするには、 **PersistentChatReskit**をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6b767-107">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="6b767-108">簡単なインストールを実行するには、 **PersistentChatReskit**を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b767-108">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="6b767-109">.Msi は、次のパスにあるすべてのツールを\\インストールします。 **Program\\ Files\\Microsoft Lync server 2013 常設チャットサーバーリソースキット**。</span><span class="sxs-lookup"><span data-stu-id="6b767-109">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="6b767-110">このフォルダーには、自己完結型のツールの実行可能ファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="6b767-110">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="6b767-111">ファイルが自分のサブフォルダーにもあるツール。</span><span class="sxs-lookup"><span data-stu-id="6b767-111">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6b767-112">Lync server 2013 のリソースキットツールをインストールした後、 <STRONG>PsExec</STRONG>をインストールして、 <STRONG>PsExec</STRONG>を次のパスにコピーする\\必要があります: <STRONG>Program Files \ Lync server 2013 \ 常設チャットサーバーリソース Kit\ChatStressTool</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="6b767-112">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="6b767-113"><STRONG>PsExec</STRONG>をコピーしない場合、常設チャットのストレスツールでエラー例外がスローされ、正しく実行されません。</span><span class="sxs-lookup"><span data-stu-id="6b767-113">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="6b767-114">ツールを実行する前に、必ずこの必須要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6b767-114">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="6b767-115"><STRONG>PsExec</STRONG>のインストールの詳細については<A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b767-115">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="6b767-116">サポートされる環境</span><span class="sxs-lookup"><span data-stu-id="6b767-116">Supported Environments</span></span>

<span data-ttu-id="6b767-117">最適なパフォーマンスを実現するには、Lync Server 2013、リソースキットツールを同じ環境にインストールして、Lync Server 2013 で必要とされる仕様と同じようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b767-117">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="6b767-118">リソース キット ツールの概要</span><span class="sxs-lookup"><span data-stu-id="6b767-118">Resource Kit Tools Overview</span></span>

<span data-ttu-id="6b767-119">Lync Server 2013 常設チャットリソースキットには、次のツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="6b767-119">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="6b767-120">次のセクションでは、要件や使用例など、各ツールの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="6b767-120">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="6b767-121">影響チェック</span><span class="sxs-lookup"><span data-stu-id="6b767-121">AffCheck</span></span>

  - <span data-ttu-id="6b767-122">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="6b767-122">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="6b767-123">ChatStress ツール</span><span class="sxs-lookup"><span data-stu-id="6b767-123">ChatStress Tool</span></span>

  - <span data-ttu-id="6b767-124">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="6b767-124">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="6b767-125">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="6b767-125">ChatUsageReport</span></span>

  - <span data-ttu-id="6b767-126">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="6b767-126">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="6b767-127">影響チェック</span><span class="sxs-lookup"><span data-stu-id="6b767-127">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="6b767-128">説明</span><span class="sxs-lookup"><span data-stu-id="6b767-128">Description</span></span>

<span data-ttu-id="6b767-129">このツールは、常設チャットバックエンドデータベースユーザーとグループの所属レコードが Active Directory ドメインサービスのものと一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b767-129">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="6b767-130">要件</span><span class="sxs-lookup"><span data-stu-id="6b767-130">Requirements</span></span>

<span data-ttu-id="6b767-131">このツールは、ドメインに参加しているコンピューター上の PersistentChatResKit installer と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6b767-131">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="6b767-132">ツールが実行されるユーザーアカウントには、常設チャットのバックエンドデータベースと Active Directory ドメインサービスへの読み取りアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b767-132">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="6b767-133">使用方法</span><span class="sxs-lookup"><span data-stu-id="6b767-133">Usage</span></span>

<span data-ttu-id="6b767-134">構成ファイルに記載されている手順に従って、またはコマンドラインパラメーターを指定せずに、操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b767-134">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="6b767-135">次に示すのは、既定の影響を示す .exe の内容です。</span><span class="sxs-lookup"><span data-stu-id="6b767-135">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="6b767-136">**影響を確認します。**</span><span class="sxs-lookup"><span data-stu-id="6b767-136">**AffCheck.exe.config:**</span></span>

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

## <a name="chatmonitoringsummary"></a><span data-ttu-id="6b767-137">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="6b767-137">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="6b767-138">説明</span><span class="sxs-lookup"><span data-stu-id="6b767-138">Description</span></span>

<span data-ttu-id="6b767-139">PersistentChatMonitoringSummary ツールは、一時的なチャット監視情報を監視データベースから指定された CSV ログファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="6b767-139">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="6b767-140">CSV ファイルには、合計セッション数、成功セッション、予期しないエラー、予期したエラーの数、診断 ID、失敗数、障害の説明による予期しないエラーの内訳が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b767-140">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="6b767-141">要件</span><span class="sxs-lookup"><span data-stu-id="6b767-141">Requirements</span></span>

<span data-ttu-id="6b767-142">固定チャットリソースキットツールを、監視データベースにアクセスできるドメインに参加しているコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="6b767-142">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="6b767-143">ツールを実行するユーザーアカウントには、監視データベースへの読み取りアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b767-143">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="6b767-144">PersistentChatMonitoringSummary というファイルには、監視データベースへの接続\<文字列\>を定義する connectionStrings セクションが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b767-144">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="6b767-145">また、監視データを収集する PersistentChatEndpointUri のキーと、生成される CSV ファイルの場所へのファイルパスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b767-145">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="6b767-146">例については、インストールされている構成ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b767-146">Refer to the installed config file for examples.</span></span> <span data-ttu-id="6b767-147">このファイルは、ツールと同じディレクトリ内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b767-147">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="6b767-148">使用方法</span><span class="sxs-lookup"><span data-stu-id="6b767-148">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="6b767-149">次のパラメーターでデータの選択を定義します。</span><span class="sxs-lookup"><span data-stu-id="6b767-149">These parameters define the selection of data:</span></span>

<span data-ttu-id="6b767-150">**StartDateTime:** 必要に応じて、選択期間の開始日を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b767-150">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="6b767-151">既定値: 1/1/1753 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="6b767-151">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="6b767-152">**Enddatetime:** オプションで、選択期間の最後の日付を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b767-152">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="6b767-153">既定値: 今すぐ</span><span class="sxs-lookup"><span data-stu-id="6b767-153">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="6b767-154">例</span><span class="sxs-lookup"><span data-stu-id="6b767-154">Example</span></span>

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

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="6b767-155">常設チャット応力ツール</span><span class="sxs-lookup"><span data-stu-id="6b767-155">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="6b767-156">説明</span><span class="sxs-lookup"><span data-stu-id="6b767-156">Description</span></span>

<span data-ttu-id="6b767-157">常設チャットのストレスツールでは、継続的なチャットの使用をシミュレートして、さまざまなユーザーモデルを含め、想定される用途のシナリオに合わせてリアルタイムのパフォーマンスをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="6b767-157">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="6b767-158">要件</span><span class="sxs-lookup"><span data-stu-id="6b767-158">Requirements</span></span>

<span data-ttu-id="6b767-159">常設チャットリソースキットツールを、常設チャットのバックエンドデータベースにアクセスできるドメインに参加しているコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="6b767-159">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="6b767-160">この*コントローラー*マシンに加えて、いくつかの*ローダー*マシンが必要です。</span><span class="sxs-lookup"><span data-stu-id="6b767-160">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="6b767-161">ユーザーモデル内のすべての10K ユーザーに対して、ローダーコンピューターで少なくとも 4 GB の空き RAM が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b767-161">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="6b767-162">たとえば、80K ユーザーとの実行には、すべてのローダーコンピューターで分散した RAM の 32 GB が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b767-162">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="6b767-163">予想される負荷に関係なく、少なくとも3つのローダーコンピューターを持っていることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6b767-163">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="6b767-164">ローダーコンピューターには、.NET 4.5 フレームワークに加えて、Visual C++ 2012 再頒布可能パッケージがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b767-164">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="6b767-165">構成</span><span class="sxs-lookup"><span data-stu-id="6b767-165">Configuration</span></span>

<span data-ttu-id="6b767-166">すべてのローダーコンピューターからアクセスできる共有フォルダーに ChatStressTool ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="6b767-166">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="6b767-167">ストレスの実行で使用するユーザーとチャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b767-167">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="6b767-168">ユーザーモデルを使って通話を発信し、Lync で有効にして、常設チャットポリシーを [有効] に設定します。</span><span class="sxs-lookup"><span data-stu-id="6b767-168">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="6b767-169">応力チャネルのカテゴリを作成し、そのカテゴリに必要なだけのルームを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b767-169">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="6b767-170">カテゴリには、(OU を追加することで)**許可**リスト内のすべてのストレスユーザーを含める必要があります。また、ストレスルームには、 **[開く**] のプライバシー設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b767-170">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="6b767-171">追加のストレス会議を作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6b767-171">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="6b767-172">5万ルームを作成するには、次の Windows PowerShell コマンドラインインターフェイスコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b767-172">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="6b767-173">トポロジに合わせて構成ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="6b767-173">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="6b767-174">**LoaderProcess**で、"controller.contoso.com" をコントローラーコンピューターの完全修飾ドメイン名 (FQDN) に変更します。</span><span class="sxs-lookup"><span data-stu-id="6b767-174">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="6b767-175">**StressLauncher で次のよう**になります。</span><span class="sxs-lookup"><span data-stu-id="6b767-175">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="6b767-176">"LoaderBinary" 設定値を共有フォルダーのパスに変更します。</span><span class="sxs-lookup"><span data-stu-id="6b767-176">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="6b767-177">ローダーコンピューターへの管理者アクセス権を持つ資格情報に "AdminUser"/"Adminuser" を変更します。</span><span class="sxs-lookup"><span data-stu-id="6b767-177">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="6b767-178">"ChannelCategory" を、ストレスチャンネルが作成されたカテゴリの名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="6b767-178">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="6b767-179">"UserNamePattern" と "UserPasswordPattern" を、ストレスユーザーの資格情報と一致するテンプレートに変更します。</span><span class="sxs-lookup"><span data-stu-id="6b767-179">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="6b767-180">{0}は、ユーザーのインデックス番号に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="6b767-180">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="6b767-181">"Domain" をテストトポロジの SIP ドメインに変更します。</span><span class="sxs-lookup"><span data-stu-id="6b767-181">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="6b767-182">"ConnectionString" を永続的なチャットのバックエンドデータベースの接続文字列に変更します。</span><span class="sxs-lookup"><span data-stu-id="6b767-182">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="6b767-183">"UserIndexStart" を最初のストレスユーザーのインデックスに変更します。</span><span class="sxs-lookup"><span data-stu-id="6b767-183">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="6b767-184">"LyncFQDN" をフロントエンドプールの FQDN に変更します。</span><span class="sxs-lookup"><span data-stu-id="6b767-184">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="6b767-185">[マシン] の一覧を変更して、すべてのローダーコンピューターにコンピューター名を含めます。</span><span class="sxs-lookup"><span data-stu-id="6b767-185">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="6b767-186">サービスエンドポイントの baseAddress (既定は "controller.contoso.com") をコントローラーコンピューターの FQDN に変更します。</span><span class="sxs-lookup"><span data-stu-id="6b767-186">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="6b767-187">使用方法</span><span class="sxs-lookup"><span data-stu-id="6b767-187">Usage</span></span>

<span data-ttu-id="6b767-188">構成が完了したら、コントローラーコンピューターで StressLauncher を開きます。</span><span class="sxs-lookup"><span data-stu-id="6b767-188">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="6b767-189">StressLauncher は、任意のユーザーとして起動できます。</span><span class="sxs-lookup"><span data-stu-id="6b767-189">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="6b767-190">ローダーコンピューターで開始されるローダープロセスの資格情報は、構成ファイルで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b767-190">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="6b767-191">また、常設チャットバックエンドデータベースへの読み取りアクセス権を持つ接続文字列も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b767-191">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="6b767-192">この接続文字列で統合 Windows 認証を使っている場合は、このアクセス権を持つユーザーとして StressLauncher を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b767-192">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="6b767-193">必要に応じて、ユーザーモデルの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="6b767-193">Alter the user model settings as needed.</span></span> <span data-ttu-id="6b767-194">[**読み込みの開始**] をクリックして実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="6b767-194">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="6b767-195">1分以上経過すると、ユーザーはサインインを開始し、進行状況バーの入力が開始されます。</span><span class="sxs-lookup"><span data-stu-id="6b767-195">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="6b767-196">この時点で、コントローラーマシンは動作し、パフォーマンスの測定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6b767-196">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="6b767-197">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="6b767-197">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="6b767-198">説明</span><span class="sxs-lookup"><span data-stu-id="6b767-198">Description</span></span>

<span data-ttu-id="6b767-199">ChatUpgradeVerifier は、常設チャット固有のデータベース比較ツールです。</span><span class="sxs-lookup"><span data-stu-id="6b767-199">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="6b767-200">このツールは、グループチャット 2007 R2 またはグループチャット2010データベース (2007/2010Db) を常設 Chat 2013 データベース (2010Db) に比較します。</span><span class="sxs-lookup"><span data-stu-id="6b767-200">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="6b767-201">ツールは、1つずつ、各カテゴリ、常設チャットルーム、および 2007/2010Db のアドインをチェックして、2010Db に表示されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b767-201">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="6b767-202">比較では、カテゴリ、チャットルーム、アドイン、カテゴリの範囲に含まれるすべてのプリンシパル、カテゴリまたはチャットルームのいずれかのプリンシパルのすべての設定を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="6b767-202">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="6b767-203">カテゴリまたはチャットルームが2013Db で正しく表示されない場合、相違点は競合ファイルに出力されます。</span><span class="sxs-lookup"><span data-stu-id="6b767-203">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="6b767-204">アップグレードが行われた後に、2007/2010Db が変更され、このツールが実行されると、競合ファイルへの相違点が出力されます。</span><span class="sxs-lookup"><span data-stu-id="6b767-204">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="6b767-205">このアプリケーションはデータベースの比較ツールにすぎないことに注意してください。アップグレードプロセスを検証しません。</span><span class="sxs-lookup"><span data-stu-id="6b767-205">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="6b767-206">要件</span><span class="sxs-lookup"><span data-stu-id="6b767-206">Requirements</span></span>

<span data-ttu-id="6b767-207">常設チャットリソースキットツールは、常設チャットのバックエンドデータベースにアクセスできるドメインに参加しているコンピューターにインストールします (これは、常設チャット用の以前のバージョンと現在のバージョンになります)。</span><span class="sxs-lookup"><span data-stu-id="6b767-207">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="6b767-208">ツールを実行するユーザーアカウントには、常設チャットデータベースへの読み取りアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b767-208">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="6b767-209">ChatUpgradeVerifier ファイルには、適切なグループチャットデータベース (Groupchat 2007R2 または 2010) への接続文字列を含む、GroupChat2007R2Db パラメーターまたは GroupChat2010Db パラメーターのいずれかが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b767-209">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="6b767-210">また、常設 Chat 2013 データベースへの接続文字列を持つ PersistentChat2013Db パラメーターも含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b767-210">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="6b767-211">使用方法</span><span class="sxs-lookup"><span data-stu-id="6b767-211">Usage</span></span>

<span data-ttu-id="6b767-212">パラメーターなしで**Chatupgradeverifier**を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b767-212">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="6b767-213">例</span><span class="sxs-lookup"><span data-stu-id="6b767-213">Example</span></span>

<span data-ttu-id="6b767-214">![ChatUpgradeVerifier.exe の実行](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "ChatUpgradeVerifier.exe の実行")</span><span class="sxs-lookup"><span data-stu-id="6b767-214">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="6b767-215">常設チャットの使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="6b767-215">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="6b767-216">説明</span><span class="sxs-lookup"><span data-stu-id="6b767-216">Description</span></span>

<span data-ttu-id="6b767-217">ChatUsageReport ツールは、常設チャットサービスの利用状況に関する HTML レポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="6b767-217">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="6b767-218">要件</span><span class="sxs-lookup"><span data-stu-id="6b767-218">Requirements</span></span>

<span data-ttu-id="6b767-219">常設チャットリソースキットツールは、常設チャットのバックエンドデータベースにアクセスできるドメインに参加しているコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="6b767-219">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="6b767-220">ツールが実行されるユーザーアカウントには、常設チャットのバックエンドデータベースへの読み取りアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b767-220">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="6b767-221">ChatUsageReport というファイルには、常設チャットバックエンドデータベース\<へ\>の接続文字列を定義する connectionStrings セクションが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b767-221">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="6b767-222">既定の構成ファイルの内容は、参照用にここに記載されています。</span><span class="sxs-lookup"><span data-stu-id="6b767-222">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="6b767-223">使用方法</span><span class="sxs-lookup"><span data-stu-id="6b767-223">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="6b767-224">次のパラメーターでデータの選択を定義します。</span><span class="sxs-lookup"><span data-stu-id="6b767-224">These parameters define the selection of data:</span></span>

<span data-ttu-id="6b767-225">**StartDate:** オプションで、選択期間の UTC 開始日を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b767-225">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="6b767-226">既定値: 最も古い日付</span><span class="sxs-lookup"><span data-stu-id="6b767-226">Default: Earliest Date</span></span>

<span data-ttu-id="6b767-227">終了日 **:** オプションで、選択期間の UTC の終了日を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b767-227">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="6b767-228">既定値: 今すぐ</span><span class="sxs-lookup"><span data-stu-id="6b767-228">Default: Now</span></span>

<span data-ttu-id="6b767-229">これらのパラメーターは、どのように表示されるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="6b767-229">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="6b767-230">**Topactiveusers:** この値が指定されている場合、レポートには、選択した期間にユーザーがチャットルームに投稿したメッセージの数に基づいて、最もアクティブな n 人のユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b767-230">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="6b767-231">既定値:10</span><span class="sxs-lookup"><span data-stu-id="6b767-231">Default: 10</span></span>

<span data-ttu-id="6b767-232">**TopActiveRooms:** この値が指定されている場合、レポートには、選択した期間のルームに投稿されたメッセージ数に基づいて、最もアクティブなチャットルームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b767-232">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="6b767-233">既定値:10</span><span class="sxs-lookup"><span data-stu-id="6b767-233">Default: 10</span></span>

<span data-ttu-id="6b767-234">**LeastActiveRooms:** この値を指定すると、選択した期間のチャットルームに投稿されたメッセージ数に基づいて、アクティブなチャットルームが少なくとも1つ含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b767-234">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="6b767-235">ルームには、少なくとも1つのメッセージが投稿されます。</span><span class="sxs-lookup"><span data-stu-id="6b767-235">Rooms will have at least one message posted.</span></span> <span data-ttu-id="6b767-236">既定値:10</span><span class="sxs-lookup"><span data-stu-id="6b767-236">Default: 10</span></span>

<span data-ttu-id="6b767-237">**RoomsInactiveSince:** 指定した場合、レポートには、指定した日付以降に無効になっているチャットルームのリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b767-237">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="6b767-238">既定値: 時間全体</span><span class="sxs-lookup"><span data-stu-id="6b767-238">Default: Entire Time</span></span>

<span data-ttu-id="6b767-239">**Outputfolder:** ChatUsageReport とグラフ画像が配置されているフォルダー。</span><span class="sxs-lookup"><span data-stu-id="6b767-239">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="6b767-240">これは、構成ファイルまたはコマンドラインで定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b767-240">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="6b767-241">すべてのコマンドラインパラメーターの値は、ツールと同じディレクトリにある ChatUsageReport ファイルで指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6b767-241">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="6b767-242">構成ファイルとコマンドラインの両方でいずれかの値が指定されている場合、コマンドライン値は構成ファイルの値を上書きします。</span><span class="sxs-lookup"><span data-stu-id="6b767-242">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="6b767-243">出力</span><span class="sxs-lookup"><span data-stu-id="6b767-243">Output</span></span>

<span data-ttu-id="6b767-244">レポートには、常に次の出力が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b767-244">The report will always include the following output:</span></span>

  - <span data-ttu-id="6b767-245">選択された期間のメッセージ投稿数に基づいて、最もアクティブなチャットルームの上位 n 個。</span><span class="sxs-lookup"><span data-stu-id="6b767-245">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="6b767-246">選択した期間のメッセージ投稿数に基づいて、最もアクティブなユーザーの上位 n 個。</span><span class="sxs-lookup"><span data-stu-id="6b767-246">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="6b767-247">選択された期間のメッセージ投稿数の多い、最もアクティブなチャットルーム。</span><span class="sxs-lookup"><span data-stu-id="6b767-247">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="6b767-248">データベースの全期間にわたって、または指定した日付以降、非アクティブなチャットルーム。</span><span class="sxs-lookup"><span data-stu-id="6b767-248">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="6b767-249">選択された期間の毎日のメッセージ投稿の傾向。</span><span class="sxs-lookup"><span data-stu-id="6b767-249">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="6b767-250">選択された期間の毎週のメッセージ投稿の傾向。</span><span class="sxs-lookup"><span data-stu-id="6b767-250">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="6b767-251">選択された期間の月次メッセージ投稿のトレンド。</span><span class="sxs-lookup"><span data-stu-id="6b767-251">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="6b767-252">選択された期間のメッセージ投稿の合計数です。</span><span class="sxs-lookup"><span data-stu-id="6b767-252">Total message posts for selected period.</span></span>

  - <span data-ttu-id="6b767-253">有効なルームの合計数です。</span><span class="sxs-lookup"><span data-stu-id="6b767-253">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="6b767-254">例</span><span class="sxs-lookup"><span data-stu-id="6b767-254">Example</span></span>

<span data-ttu-id="6b767-255">次の例では、2001年全体の利用状況レポートを生成し、ChatUsageReport で指定された OutputFolder にレポートを配置します。</span><span class="sxs-lookup"><span data-stu-id="6b767-255">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="6b767-256">ChatUsageReport:</span><span class="sxs-lookup"><span data-stu-id="6b767-256">ChatUsageReport.exe.config:</span></span>

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

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="6b767-257">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="6b767-257">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="6b767-258">説明</span><span class="sxs-lookup"><span data-stu-id="6b767-258">Description</span></span>

<span data-ttu-id="6b767-259">ScheduleADSyncForPrincipal は、常設チャットバックエンドデータベースに接続しているときに、SQL Server Management Studio 内から直接実行する必要がある Microsoft SQL Server 2012 スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="6b767-259">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="6b767-260">このスクリプトを使用すると、強制チャットによって、スケジュールされた同期時間を待つのではなく、Active Directory ドメインサービスのユーザーのレコードを同期することができます。</span><span class="sxs-lookup"><span data-stu-id="6b767-260">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="6b767-261">要件</span><span class="sxs-lookup"><span data-stu-id="6b767-261">Requirements</span></span>

<span data-ttu-id="6b767-262">スクリプトが実行されるユーザーアカウントには、常設チャットバックエンドデータベースへの所有者アクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b767-262">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="6b767-263">使用方法</span><span class="sxs-lookup"><span data-stu-id="6b767-263">Usage</span></span>

<span data-ttu-id="6b767-264">既定のスクリプトの内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b767-264">Following are the contents of the default script:</span></span>

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

