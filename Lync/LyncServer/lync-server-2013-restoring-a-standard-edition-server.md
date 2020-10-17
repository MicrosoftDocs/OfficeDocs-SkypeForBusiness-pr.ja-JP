---
title: 'Lync Server 2013: Standard Edition サーバーの復元'
description: 'Lync Server 2013: Standard Edition サーバーを復元しています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2cd6976324492e0539c47999f78434e1a82706
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542393"
---
# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="a9ffe-103">Lync Server 2013 での Standard Edition サーバーの復元</span><span class="sxs-lookup"><span data-stu-id="a9ffe-103">Restoring a Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9ffe-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a9ffe-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a9ffe-105">中央管理ストアをホストしていない Standard Edition サーバーで障害が発生した場合は、このセクションの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-105">If a Standard Edition server that does not host the Central Management store fails, follow the procedures in this section.</span></span> <span data-ttu-id="a9ffe-106">中央管理ストアに障害が発生した場合は、「 [Lync server 2013 の中央管理ストアをホスト](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)しているサーバーを復元する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-106">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="a9ffe-107">復元を開始する前に、システムのイメージコピーを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-107">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="a9ffe-108">復元中に問題が発生した場合に備えて、このイメージをロールバックポイントとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-108">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="a9ffe-109">オペレーティングシステムと SQL Server をインストールしてから、証明書を復元または再登録した後で、イメージコピーを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-109">You might want to take the image copy after you install the operating system and SQL Server, and restore or re-enroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a><span data-ttu-id="a9ffe-110">Standard Edition サーバーを復元するには</span><span class="sxs-lookup"><span data-stu-id="a9ffe-110">To restore a Standard Edition server</span></span>

1.  <span data-ttu-id="a9ffe-111">障害が発生したコンピューターと同じ完全修飾ドメイン名 (FQDN) を持つクリーンサーバーまたは新しいサーバーを起動し、オペレーティングシステムをインストールしてから、証明書を復元または reenroll します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-111">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a9ffe-112">組織で定めるサーバーの展開手順に従って、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-112">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="a9ffe-113">RTCUniversalServerAdmins グループとローカルの Administrators グループのメンバーであるユーザーアカウントから、復元するサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-113">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="a9ffe-114">適切なファイルストアを $Backup からサーバー上のファイルストアの場所にコピーし、フォルダーを共有することによって、ファイルストアを復元します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-114">Restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server and share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a9ffe-115">復元されたファイルストアのパスおよびファイル名は、ファイルを使用するコンポーネントがアクセスできるように、バックアップされたファイルストアと正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-115">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="a9ffe-116">トポロジビルダーを実行します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-116">Run Topology Builder:</span></span>
    
    1.  <span data-ttu-id="a9ffe-117">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="a9ffe-118">[**既存の展開からトポロジをダウンロードする**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-118">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="a9ffe-p103">トポロジを選択し、[**保存**] をクリックします。[**はい**] をクリックして選択を確定します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-p103">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>

5.  <span data-ttu-id="a9ffe-121">Lync Server インストールフォルダーまたはメディアを参照し、[セットアップ amd64Setup.exe にある Lync Server 展開ウィザードを起動し \\ \\ \\ ます。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-121">Browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="a9ffe-122">Lync Server 展開ウィザードを使用して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-122">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="a9ffe-123">[**ステップ 1: ローカル構成ストアのインストール**] を実行して、ローカル構成ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-123">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="a9ffe-124">[ **ステップ 2: lync Server コンポーネントのセットアップまたは削除** を実行して、lync server のサーバーの役割をインストールする」を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-124">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="a9ffe-125">[**ステップ 3: 証明書の要求、インストール、または割り当て**] を実行して、証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-125">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="a9ffe-126">[**ステップ 4: サービスの開始**] を実行して、サーバー上でサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-126">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="a9ffe-127">展開ウィザードの実行の詳細については、展開に関するドキュメントで復元しているサーバーの役割を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-127">For details about running the Deployment Wizard, see the Deployment documentation for the server role you are restoring.</span></span>

6.  <span data-ttu-id="a9ffe-128">次の操作を実行してユーザー データを復元します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-128">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="a9ffe-129">ExportedUserData.zip を $Backup から \\ ローカルディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-129">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="a9ffe-130">ユーザーデータを復元する前に、Lync services を停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-130">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="a9ffe-131">これを行うには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-131">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="a9ffe-132">ユーザー データを復元するには、コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-132">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="a9ffe-133">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-133">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="a9ffe-134">次のように入力して Lync services を再起動します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-134">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

7.  <span data-ttu-id="a9ffe-135">この Standard Edition サーバーで応答グループを展開した場合は、応答グループ構成データを復元します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-135">If you deployed Response Group on this Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="a9ffe-136">詳細については、「 [Lync Server 2013 での応答グループの設定の復元](lync-server-2013-restoring-response-group-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-136">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

8.  <span data-ttu-id="a9ffe-137">この Standard Edition サーバーで常設チャットを展開した場合は、常設チャットデータベース (mgc) を復元します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-137">If you deployed Persistent Chat on this Standard Edition server, restore the Persistent Chat database (mgc.mdf).</span></span>
    
    <span data-ttu-id="a9ffe-138">SQL Server バックアップを使用して常設チャットデータベースをバックアップした場合は、SQL Server の復元手順を使用して復元します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-138">If you used SQL Server Backup to back up the Persistent Chat database, use SQL Server restore procedures to restore it.</span></span>
    
    <span data-ttu-id="a9ffe-139">Export-CsPersistentChatData コマンドレットを使用してバックアップを作成した場合は、Import-CsPersistentChatData を使用して復元します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-139">If you used the Export-CsPersistentChatData cmdlet to back it up, use the Import-CsPersistentChatData to restore it.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

