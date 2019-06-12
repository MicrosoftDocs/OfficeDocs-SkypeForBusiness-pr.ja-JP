---
title: バックエンドサーバーまたは Standard Edition server をアップグレードまたは更新する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b9d5ffba604ed5e32109ed5f1a2020b1e083b22
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="65ad3-102">Lync Server 2013 でバックエンドサーバーまたは Standard Edition サーバーをアップグレードまたは更新する</span><span class="sxs-lookup"><span data-stu-id="65ad3-102">Upgrade or update a Back End Server or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65ad3-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="65ad3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="65ad3-104">このトピックでは、Enterprise Edition バックエンドサーバーまたは Standard Edition サーバーに更新プログラムをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="65ad3-104">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>

<span data-ttu-id="65ad3-105">アップグレード中に少なくとも30分間バックエンドサーバーが停止している場合、ユーザーは回復性モードに移行することがあります。</span><span class="sxs-lookup"><span data-stu-id="65ad3-105">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="65ad3-106">アップグレードが完了し、バックエンドサーバーがプール内のフロントエンドサーバーに再度接続されると、ユーザーは完全な機能に戻ります。</span><span class="sxs-lookup"><span data-stu-id="65ad3-106">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="65ad3-107">アップグレードが 30 分未満の場合、ユーザーには影響ありません。</span><span class="sxs-lookup"><span data-stu-id="65ad3-107">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="65ad3-108">バックエンド サーバーまたは Standard Edition サーバーを更新するには</span><span class="sxs-lookup"><span data-stu-id="65ad3-108">To update a back end server or Standard Edition server</span></span>

1.  <span data-ttu-id="65ad3-109">アップグレードするサーバーに CsAdministrator の役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="65ad3-109">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="65ad3-110">更新をダウンロードして、ローカル ハードディスクに抽出します。</span><span class="sxs-lookup"><span data-stu-id="65ad3-110">Download the update and extract it to the local hard disk.</span></span>

3.  <span data-ttu-id="65ad3-111">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="65ad3-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="65ad3-112">Lync Server サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="65ad3-112">Stop Lync Server services.</span></span> <span data-ttu-id="65ad3-113">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="65ad3-113">At the command line, type:</span></span>
    
        Stop-CsWindowsService

5.  <span data-ttu-id="65ad3-114">World Wide Web サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="65ad3-114">Stop the World Wide Web service.</span></span> <span data-ttu-id="65ad3-115">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="65ad3-115">At the command line, type:</span></span>
    
        net stop w3svc

6.  <span data-ttu-id="65ad3-116">すべての Lync Server 管理シェルウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="65ad3-116">Close all Lync Server Management Shell windows.</span></span>

7.  <span data-ttu-id="65ad3-117">更新をインストールします。</span><span class="sxs-lookup"><span data-stu-id="65ad3-117">Install the update.</span></span>

8.  <span data-ttu-id="65ad3-118">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="65ad3-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

9.  <span data-ttu-id="65ad3-119">もう一度 Lync Server サービスを停止して、グローバルアセンブリキャッシュ (GAC) – d アセンブリをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="65ad3-119">Stop Lync Server services again to catch Global Assembly Cache (GAC) –d assemblies.</span></span> <span data-ttu-id="65ad3-120">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="65ad3-120">At the command line, type:</span></span>
    
        Stop-CsWindowsService

10. <span data-ttu-id="65ad3-121">World Wide Web サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="65ad3-121">Restart the World Wide Web service.</span></span> <span data-ttu-id="65ad3-122">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="65ad3-122">At the command line, type:</span></span>
    
        net start w3svc

11. <span data-ttu-id="65ad3-123">次のいずれかの操作を行って、LyncServerUpdateInstaller によって行われた変更を SQL Server データベースに適用します。</span><span class="sxs-lookup"><span data-stu-id="65ad3-123">Apply the changes made by LyncServerUpdateInstaller.exe to the SQL Server databases by doing one of the following:</span></span>
    
      - <span data-ttu-id="65ad3-124">Enterprise Edition バックエンドサーバーで、データベースのアーカイブや監視など、このサーバー上に併置されたデータベースがない場合は、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="65ad3-124">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - <span data-ttu-id="65ad3-125">Enterprise Edition バックエンドサーバーで、このサーバーに併置されたデータベースがある場合は、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="65ad3-125">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - <span data-ttu-id="65ad3-126">Standard Edition サーバーの場合は、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="65ad3-126">If this is an Standard Edition server, type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

