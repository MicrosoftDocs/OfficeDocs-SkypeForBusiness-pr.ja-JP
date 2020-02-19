---
title: バックエンドサーバーまたは Standard Edition サーバーをアップグレードまたは更新する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7b8606089cab35be870f90ee301db052e99c611
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="0df18-102">Lync Server 2013 でのバックエンドサーバーまたは Standard Edition サーバーのアップグレードまたは更新</span><span class="sxs-lookup"><span data-stu-id="0df18-102">Upgrade or update a Back End Server or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0df18-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0df18-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0df18-104">このトピックでは、Enterprise Edition バックエンドサーバーまたは Standard Edition サーバーに更新プログラムをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0df18-104">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>

<span data-ttu-id="0df18-105">アップグレード中のバックエンドサーバーが少なくとも30分間ダウンすると、ユーザーは復元モードになることがあります。</span><span class="sxs-lookup"><span data-stu-id="0df18-105">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="0df18-106">アップグレードが完了し、バックエンドサーバーがプール内のフロントエンドサーバーに再度接続されると、ユーザーはすべての機能に戻ります。</span><span class="sxs-lookup"><span data-stu-id="0df18-106">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="0df18-107">アップグレードの時間が30分未満の場合、ユーザーに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="0df18-107">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="0df18-108">バックエンドサーバーまたは Standard Edition サーバーを更新するには</span><span class="sxs-lookup"><span data-stu-id="0df18-108">To update a back end server or Standard Edition server</span></span>

1.  <span data-ttu-id="0df18-109">CsAdministrator の役割のメンバーとして、アップグレードするサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0df18-109">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="0df18-110">更新プログラムをダウンロードして、ローカルハードディスクに抽出します。</span><span class="sxs-lookup"><span data-stu-id="0df18-110">Download the update and extract it to the local hard disk.</span></span>

3.  <span data-ttu-id="0df18-111">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0df18-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="0df18-112">Lync Server サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="0df18-112">Stop Lync Server services.</span></span> <span data-ttu-id="0df18-113">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0df18-113">At the command line, type:</span></span>
    
        Stop-CsWindowsService

5.  <span data-ttu-id="0df18-114">World Wide Web サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="0df18-114">Stop the World Wide Web service.</span></span> <span data-ttu-id="0df18-115">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0df18-115">At the command line, type:</span></span>
    
        net stop w3svc

6.  <span data-ttu-id="0df18-116">すべての Lync Server 管理シェルウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="0df18-116">Close all Lync Server Management Shell windows.</span></span>

7.  <span data-ttu-id="0df18-117">更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0df18-117">Install the update.</span></span>

8.  <span data-ttu-id="0df18-118">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0df18-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

9.  <span data-ttu-id="0df18-119">Lync Server サービスを再度停止して、グローバルアセンブリキャッシュ (GAC) – d アセンブリをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="0df18-119">Stop Lync Server services again to catch Global Assembly Cache (GAC) –d assemblies.</span></span> <span data-ttu-id="0df18-120">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0df18-120">At the command line, type:</span></span>
    
        Stop-CsWindowsService

10. <span data-ttu-id="0df18-121">World Wide Web サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0df18-121">Restart the World Wide Web service.</span></span> <span data-ttu-id="0df18-122">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0df18-122">At the command line, type:</span></span>
    
        net start w3svc

11. <span data-ttu-id="0df18-123">以下のいずれかの処理を行って、LyncServerUpdateInstaller.exe による SQL Server データベースへの変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="0df18-123">Apply the changes made by LyncServerUpdateInstaller.exe to the SQL Server databases by doing one of the following:</span></span>
    
      - <span data-ttu-id="0df18-124">これが Enterprise Edition バックエンドサーバーで、アーカイブデータベースや監視データベースなど、このサーバーに併置されたデータベースがない場合は、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0df18-124">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - <span data-ttu-id="0df18-125">これが Enterprise Edition バックエンドサーバーで、このサーバーに併置されたデータベースがある場合は、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0df18-125">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - <span data-ttu-id="0df18-126">Standard Edition サーバーの場合は、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0df18-126">If this is an Standard Edition server, type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

