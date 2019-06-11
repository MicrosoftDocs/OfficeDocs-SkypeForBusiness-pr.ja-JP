---
title: 'Lync Server 2013: SQL Server Reporting Services のインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6707cafc3a08123bd2189639704741681eb9cdd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="bf818-102">Lync Server 2013 で SQL Server Reporting Services をインストールする</span><span class="sxs-lookup"><span data-stu-id="bf818-102">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf818-103">_**最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="bf818-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="bf818-104">Microsoft Lync Server 2013 監視レポートを使用する場合 (詳細については、このドキュメントの次のセクションを参照してください)、まず SQL Server Reporting Services をインストールする必要があります。Reporting Services は、Microsoft SQL Server のインストール時に、または SQL Server をインストールした後であれば、いつでもインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bf818-104">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="bf818-105">SQL Server がインストールされていない場合は、このドキュメントで前に説明した指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="bf818-105">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="bf818-106">SQL Server をインストールするときに、[機能の選択] ページで [Reporting Services] を選択していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bf818-106">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="bf818-107">これにより、SQL Server Reporting Services がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bf818-107">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="bf818-108">Sql server が既にインストールされているが、SQL Server Reporting Services をインストールしていない場合は、SQL Server 2008 R2 または SQL Server 2012 の適切な手順に従って、その機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="bf818-108">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="bf818-109">レポートサービスが正常にインストールされたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bf818-109">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="bf818-110">Microsoft SQL Server 2008 R2 を実行している場合は、[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft SQL Server 2008 R2**]、[**構成ツール**]、[ **Reporting Services 構成マネージャー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf818-110">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="bf818-111">Microsoft SQL Server 2012 を実行している場合は、[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft SQL Server 2012**]、[**構成ツール**]、[ **Reporting Services 構成マネージャー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf818-111">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="bf818-112">[ **Reporting Services の構成接続**] ダイアログボックスで、[**サーバー名**] ボックスにサーバー名が表示され、監視データを格納する SQL server インスタンスの名前がレポートサーバーに表示されることを確認します。 **インスタンス**ボックス。</span><span class="sxs-lookup"><span data-stu-id="bf818-112">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box.</span></span> <span data-ttu-id="bf818-113">[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf818-113">Click **Connect**.</span></span>

<span data-ttu-id="bf818-114">Reporting Service 構成マネージャーの [レポートサーバーの状態] ウィンドウには、SQL Server Reporting Services がインストールされていて、Reporting Services が現在実行されていることが表示されます。レポートサーバーの状態は [**開始**] と表示され、[**スタート**] ボタンは淡色表示になっていて使用できません。</span><span class="sxs-lookup"><span data-stu-id="bf818-114">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="bf818-115">レポートサービスが実行されていない場合は、[**開始**] をクリックしてサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="bf818-115">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="bf818-116">[レポートサーバーデータベース名] ラベルの横にデータベースが表示されない場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bf818-116">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="bf818-117">Reporting Services 構成マネージャーで [**データベース**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf818-117">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="bf818-118">[レポートサーバーデータベース] ウィンドウで、[**データベースの変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf818-118">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="bf818-119">レポートサーバーデータベース構成ウィザードの [操作] ウィンドウで、[**新しいレポートサーバーデータベースの作成**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf818-119">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="bf818-120">[レポートサーバーデータベース構成ウィザード] の [データベースサーバー] ウィンドウで、[**サーバー名**]、[**認証の種類**]、[**ユーザー名**] ボックスに表示されている情報が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bf818-120">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct.</span></span> <span data-ttu-id="bf818-121">[**接続テスト**] をクリックしてデータベースサーバーへの接続を確立できることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf818-121">Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="bf818-122">レポートサーバーデータベース構成ウィザードの [データベース] ウィンドウで、**データベース名**、**言語**、および**レポートサーバーモード**の既定値をそのまま使用し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf818-122">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="bf818-123">[レポートサーバーデータベースの構成ウィザード] の [資格情報] ウィンドウで、[**認証の種類**] ドロップダウンリストと [**ユーザー名**] ボックスと [**パスワード**] ボックスに正しい情報が表示されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf818-123">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="bf818-124">レポートサーバーデータベース構成ウィザードの [概要] ウィンドウで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf818-124">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="bf818-125">[レポートサーバーデータベースの構成ウィザード] の [進行状況] と [完了] ウィンドウで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf818-125">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="bf818-126">レポートサービスの Url が構成されていることを確認するには、[ **Web サービスの url**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf818-126">To verify that the Reporting Service URLs have been configured, click **Web Service URL**.</span></span> <span data-ttu-id="bf818-127">[見出し**レポートサーバー] Web サービスの url**の下に、1つ以上の url が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf818-127">You should see one or more URLs listed under the heading **Report Server Web Service URLs**.</span></span> <span data-ttu-id="bf818-128">これらの各 Url をクリックして、SQL Server Reporting Services のローカルインストールのホームページにアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bf818-128">Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

