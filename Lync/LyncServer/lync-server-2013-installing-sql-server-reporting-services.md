---
title: 'Lync Server 2013: SQL Server Reporting Services のインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e1663bad8515082603a411a42de5c98d7f70594
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="8290a-102">Lync Server 2013 での SQL Server Reporting Services のインストール</span><span class="sxs-lookup"><span data-stu-id="8290a-102">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8290a-103">_**トピックの最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="8290a-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="8290a-104">Microsoft Lync Server 2013 の監視レポートを使用する場合 (詳細については、このドキュメントの次のセクションを参照してください)、最初に SQL Server Reporting Services をインストールする必要があります。Reporting Services は、Microsoft SQL Server をインストールするとき、または SQL Server をインストールした後で、いつでもインストールできます。</span><span class="sxs-lookup"><span data-stu-id="8290a-104">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="8290a-105">SQL Server をインストールしていない場合は、このドキュメントで前述した手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8290a-105">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="8290a-106">SQL Server をインストールするときは、[機能の選択] ページで [Reporting Services] を選択していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8290a-106">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="8290a-107">SQL Server Reporting Services がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8290a-107">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="8290a-108">SQL Server はインストールしたが、SQL Server Reporting Services はインストールしていない場合は、SQL Server 2008 R2 または SQL Server 2012 に適した指示に従って、この機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="8290a-108">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="8290a-109">Reporting Services が正常にインストールされたことを確認するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8290a-109">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="8290a-110">Microsoft SQL Server 2008 R2 を実行中の場合は、[**スタート**]、[**すべてのプログラム**]、[**Microsoft SQL Server 2008 R2**]、[**構成ツール**] の順にクリックし、[**Reporting Services 構成マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8290a-110">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="8290a-111">Microsoft SQL Server 2012 を実行中の場合は、[**スタート**]、[**すべてのプログラム**]、[**Microsoft SQL Server 2012**]、[**構成ツール**] の順にクリックし、[**Reporting Services 構成マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8290a-111">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="8290a-p102">[**Reporting Services 構成の接続**] ダイアログ ボックスで、サーバーの名前が [**サーバー名**] ボックスに、および監視データを保存する SQL Server インスタンスの名前が [**レポート サーバー インスタンス**] ボックスに表示されることを確認します。[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8290a-p102">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box. Click **Connect**.</span></span>

<span data-ttu-id="8290a-114">Reporting Service 構成マネージャーで、[レポートサーバーの状態] ウィンドウに、SQL Server Reporting Services がインストールされており、Reporting Services が現在実行中であることを示す必要があります。レポートサーバーの状態は [**開始**] と表示され、[**開始**] ボタンは淡色表示され、使用できません。</span><span class="sxs-lookup"><span data-stu-id="8290a-114">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="8290a-115">Reporting Services が実行されていない場合は、[**開始**] をクリックしてサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="8290a-115">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="8290a-116">[レポート サーバー データベース名] ラベルの横にデータベースが表示されない場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8290a-116">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="8290a-117">Reporting Services 構成マネージャーで、[**データベース**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8290a-117">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="8290a-118">[レポート サーバー データベース] ウィンドウで、[**データベースの変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8290a-118">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="8290a-119">レポート サーバー データベース構成ウィザードで、[**新しいレポート サーバー データベースを作成する**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8290a-119">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="8290a-p104">レポート サーバー データベース構成ウィザードの [データベース サーバー] ウィンドウで、[**サーバー名**] ボックス、[**認証の種類**] ボックス、および [**ユーザー名**] ボックスに表示される情報が正しいことを確認します。[**接続テスト**] をクリックしてデータベース サーバーに接続できることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8290a-p104">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct. Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="8290a-122">レポート サーバー データベース構成ウィザードの [データベース] ウィンドウで、[**データベース名**]、[**言語**]、および [**レポート サーバー モード**] の既定値をそのまま使用し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8290a-122">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="8290a-123">レポート サーバー データベース構成ウィザードの [資格情報] ウィンドウで、[**認証の種類**] ドロップダウン リスト、[**ユーザー名**] ボックス、および [**パスワード**] ボックスに正しい情報が表示されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8290a-123">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="8290a-124">レポート サーバー データベース構成ウィザードの [概要] ウィンドウで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8290a-124">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="8290a-125">レポート サーバー データベース構成ウィザードの [続行して完了する] ウィンドウで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8290a-125">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="8290a-p105">Reporting Services の URL が構成されていることを確認するには、[**Web サービスの URL**] をクリックします。[**レポート サーバー Web サービスの URL**] 見出しの下に、1 つまたは複数の URL が表示されることを確認します。これらの各 URL をクリックすることで、SQL Server Reporting Services のローカル インストール用のホーム ページにアクセスできることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8290a-p105">To verify that the Reporting Service URLs have been configured, click **Web Service URL**. You should see one or more URLs listed under the heading **Report Server Web Service URLs**. Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

