---
title: 'Lync Server 2013: Standard Edition サーバーの復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 101cf0cb2fc4073e2b79aa008187465f84d2d439
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="8cf5c-102">Lync Server 2013 での Standard Edition サーバーの復元</span><span class="sxs-lookup"><span data-stu-id="8cf5c-102">Restoring a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cf5c-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8cf5c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8cf5c-104">中央管理ストアをホストしていない Standard Edition サーバーで問題が発生した場合は、このセクションの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-104">If a Standard Edition server that does not host the Central Management store fails, follow the procedures in this section.</span></span> <span data-ttu-id="8cf5c-105">サーバーの全体管理ストアでエラーが発生した場合は、「 [Lync server 2013 で中央管理ストアをホストしているサーバーの復元](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-105">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="8cf5c-106">復元を開始する前に、システムのイメージコピーを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-106">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="8cf5c-107">復元中に問題が発生した場合に備えて、この画像をロールバックポイントとして使うことができます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-107">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="8cf5c-108">オペレーティングシステムと SQL Server をインストールした後に画像のコピーを取得し、証明書を復元または再登録することができます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-108">You might want to take the image copy after you install the operating system and SQL Server, and restore or re-enroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a><span data-ttu-id="8cf5c-109">Standard Edition サーバーを復元するには</span><span class="sxs-lookup"><span data-stu-id="8cf5c-109">To restore a Standard Edition server</span></span>

1.  <span data-ttu-id="8cf5c-110">障害のあるコンピューターと同じ完全修飾ドメイン名 (FQDN) を持つクリーンで、または新しいサーバーから始め、オペレーティングシステムをインストールして、証明書を復元または reenroll します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-110">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8cf5c-111">組織のサーバー展開手順に従って、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-111">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="8cf5c-112">RTCUniversalServerAdmins グループとローカルの管理者グループのメンバーであるユーザーアカウントから、復元しているサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-112">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="8cf5c-113">適切なファイルストアを $Backup からサーバー上のファイルストアの場所にコピーして、ファイルストアを復元し、フォルダーを共有します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-113">Restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server and share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8cf5c-114">復元されたファイルストアのパスとファイル名は、ファイルを使用するコンポーネントがアクセスできるように、バックアップされたファイルストアとまったく同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-114">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="8cf5c-115">トポロジビルダーを実行します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-115">Run Topology Builder:</span></span>
    
    1.  <span data-ttu-id="8cf5c-116">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="8cf5c-117">[**既存の展開からトポロジをダウンロード**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-117">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="8cf5c-118">トポロジを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-118">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="8cf5c-119">選択内容を確認するには、[**はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-119">Click **Yes** to confirm your selection.</span></span>

5.  <span data-ttu-id="8cf5c-120">Lync Server のインストールフォルダーまたはメディアを参照し、セットアップ\\\\Amd64\\Setup.exe で [lync server 展開ウィザード] を起動します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-120">Browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="8cf5c-121">Lync Server 展開ウィザードを使用して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-121">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="8cf5c-122">**手順 1: ローカル構成ストアをインストール**して、ローカル構成ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-122">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="8cf5c-123">**手順 2: lync server のコンポーネントをセットアップまたは削除**して lync server サーバーの役割をインストールする</span><span class="sxs-lookup"><span data-stu-id="8cf5c-123">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="8cf5c-124">手順 3: 証明書を割り当てるために**証明書を要求、インストール、または割り当て**ます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-124">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="8cf5c-125">**手順 4: サービスを開始**して、サーバー上のサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-125">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="8cf5c-126">展開ウィザードの実行の詳細については、復元するサーバーの役割の展開ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-126">For details about running the Deployment Wizard, see the Deployment documentation for the server role you are restoring.</span></span>

6.  <span data-ttu-id="8cf5c-127">ユーザーデータを復元するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-127">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="8cf5c-128">$Backup\\からローカルディレクトリに ExportedUserData をコピーします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-128">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="8cf5c-129">ユーザーデータを復元する前に、Lync サービスを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-129">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="8cf5c-130">そのためには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-130">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="8cf5c-131">ユーザーデータを復元するには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-131">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="8cf5c-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-132">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="8cf5c-133">次のように入力して Lync サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-133">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

7.  <span data-ttu-id="8cf5c-134">この Standard Edition サーバーで応答グループを展開した場合は、応答グループの構成データを復元します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-134">If you deployed Response Group on this Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="8cf5c-135">詳細については、「 [Lync Server 2013 での応答グループの設定の復元](lync-server-2013-restoring-response-group-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-135">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

8.  <span data-ttu-id="8cf5c-136">この Standard Edition サーバーに常設チャットを展開した場合は、常設チャットデータベース (行う) を復元します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-136">If you deployed Persistent Chat on this Standard Edition server, restore the Persistent Chat database (mgc.mdf).</span></span>
    
    <span data-ttu-id="8cf5c-137">SQL Server バックアップを使って常設チャットデータベースをバックアップした場合は、SQL Server の復元手順を使用して復元します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-137">If you used SQL Server Backup to back up the Persistent Chat database, use SQL Server restore procedures to restore it.</span></span>
    
    <span data-ttu-id="8cf5c-138">CsPersistentChatData コマンドレットを使用してバックアップを作成した場合は、CsPersistentChatData を使用して復元します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-138">If you used the Export-CsPersistentChatData cmdlet to back it up, use the Import-CsPersistentChatData to restore it.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

