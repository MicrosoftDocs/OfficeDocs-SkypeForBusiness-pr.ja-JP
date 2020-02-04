---
title: 'Lync Server 2013: System Center Operations Manager データベースとして Microsoft SQL Server 2008 R2 を使用する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27516e7ca6c3fb70a01b7c1d245054d515ae351b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="34027-102">Lync Server 2013 の System Center Operations Manager データベースとして Microsoft SQL Server 2008 R2 を使用する</span><span class="sxs-lookup"><span data-stu-id="34027-102">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34027-103">_**最終更新日:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="34027-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="34027-104">SQL Server 2008 R2 をバックエンドデータベースとして使用するには、このトピックで説明する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="34027-104">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="34027-105">SQL Server 2008 R2 と SQL Server Reporting Services の構成</span><span class="sxs-lookup"><span data-stu-id="34027-105">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="34027-106">System Center Operations Manager のインストールを開始する前に、SQL Server 2008 R2 と SQL Server Reporting Services の構成に2つの変更を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="34027-106">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="34027-107">(これらの変更は、SQL Server 2008 R2 を Operations Manager データベースとして使用している場合にのみ必要です)。まず、Operations Manager データベースをホストするコンピューターで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="34027-107">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="34027-108">[**スタート**] をクリックし、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-108">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="34027-109">[ファイル名を指定して**実行**] ダイアログボックスで、「 **C:\\Program Files\\Microsoft\\SQL Server\\\\ \_MSRS10 50.** 」と入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="34027-109">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="34027-110">[ **ReportServer** ] フォルダーで、メモ帳またはその他のテキストエディターでファイル**rsreportserver**を開きます。</span><span class="sxs-lookup"><span data-stu-id="34027-110">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="34027-111">ファイルの先頭付近には、一連の「追加キー」ノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="34027-111">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="34027-112">\*\* \<"キーの追加"\*\* を開始するエントリを見つけて、値を**0**に設定します。</span><span class="sxs-lookup"><span data-stu-id="34027-112">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="34027-113">ファイルの**rsreportserver**を保存し、テキストエディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="34027-113">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="34027-114">レポートサーバーの構成ファイルを更新した後、SQL Server Reporting Services に適切な証明書を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="34027-114">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services.</span></span> <span data-ttu-id="34027-115">目的:</span><span class="sxs-lookup"><span data-stu-id="34027-115">To do that:</span></span>

1.  <span data-ttu-id="34027-116">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft SQL Server 2008 R2**]、[**構成ツール**]、[ **Reporting Services 構成マネージャー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-116">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="34027-117">[ **Reporting Services の構成接続**] ダイアログボックスで、[**サーバー名**] ボックスにサーバー名が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="34027-117">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="34027-118">[**レポートサーバーインスタンス**] ドロップダウンリストから Operations Manager データベース (例: **arch inst**) をホストする SQL Server インスタンスを選び、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-118">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="34027-119">Reporting Services 構成マネージャーで、[ **Web サービスの URL**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-119">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="34027-120">[ **Web サービスの URL** ] ページで、[ **SSL 証明書**] ドロップダウンリストから、Reporting Services に使用する証明書を選び、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-120">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**.</span></span> <span data-ttu-id="34027-121">数秒後に、[**レポートサーバー Web サービス url**] の下に表示される url のペアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="34027-121">After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="34027-122">両方の Url をクリックして、SQL Server Reporting Services にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="34027-122">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="34027-123">Reporting Services 構成マネージャーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="34027-123">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="34027-124">SQL Server 2008 R2 で使用する System Center Operations Manager データベースを作成する</span><span class="sxs-lookup"><span data-stu-id="34027-124">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="34027-125">SQL Server 2008 R2 データベースを使用するように System Center Operations Manager を構成する場合は、SQL Server 2008 R2 を実行しているコンピューターで Operations Manager データベースを手動で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34027-125">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="34027-126">(ここでも、バックエンドデータベースとして SQL Server 2005 または SQL Server 2008 を使用している場合は、この手順は必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="34027-126">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="34027-127">Operations Manager データベースを手動で作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="34027-127">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="34027-128">System Center Operations Manager 2007 R2 セットアップメディアの SupportTools\\AMD64 フォルダーで、 **dbcreatewizard .exe**をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-128">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="34027-129">データベース構成ウィザードの [**データベース構成ウィザードへようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-129">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="34027-130">[**データベース情報**] ページで、すべての設定をそのままにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-130">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="34027-131">[**管理グループの構成**] ページで、[管理グループ**名**] ボックスに管理グループの名前 (「 **Lync Server Monitoring**」など) を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-131">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="34027-132">[ **Operations Manager エラーレポート**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-132">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="34027-133">[**概要**] ページで [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-133">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="34027-134">SQL Server 2008 R2 で使用する System Center Operations Manager データウェアハウスの作成</span><span class="sxs-lookup"><span data-stu-id="34027-134">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="34027-135">Microsoft Lync Server 2013 には、次の3つの新しい System Center Operations Manager レポートが付属しています。</span><span class="sxs-lookup"><span data-stu-id="34027-135">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="34027-136">**[終了-終了] シナリオの可用性レポート**   このレポートは、登録やプレゼンスなどの、主要な Lync Server サービスの可用性/稼働時間を詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="34027-136">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="34027-137">\*\*\*\*   [パフォーマンスカウンター情報を使用したキャパシティレポート] このレポートには、メモリの可用性やプロセッサ使用率などのシステムコンポーネントの傾向が表示されます。</span><span class="sxs-lookup"><span data-stu-id="34027-137">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="34027-138">**[コンポーネントレポート**   このレポートには、Lync Server コンポーネントによってグループ化された最上位の通知ジェネレーターが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="34027-138">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="34027-139">これらの新しいレポートを使用するには、System Center Operations Manager データウェアハウスをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="34027-139">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="34027-140">(データウェアハウスは、運営データの長期的なストレージに使用されます)。SQL Server 2008 R2 でデータウェアハウスを使用するには、SQL Server データベースをホストしているコンピューターで次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34027-140">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="34027-141">System Center Operations Manager セットアップメディアの Setup\\supporttools\\AMD64 フォルダーで、 **dbcreatewizard .exe**をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-141">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="34027-142">データベース構成ウィザードの [**データベース構成ウィザードへようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-142">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="34027-143">[**データベース情報**] ページで、[**データベースの種類**] ドロップダウンリストから [ **Operations Manager データウェアハウスデータベース**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-143">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="34027-144">[**概要**] ページで [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-144">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="34027-145">System Center Operations Manager コンソールをインストールする</span><span class="sxs-lookup"><span data-stu-id="34027-145">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="34027-146">Operations Manager コンソールは、System Center Operations Manager を管理するために使用される主要なツールです。</span><span class="sxs-lookup"><span data-stu-id="34027-146">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="34027-147">Operations Manager コンソールをインストールする前に、サポートされているバージョンの SQL Server と SQL Server Reporting Services をインストールしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="34027-147">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="34027-148">また、SQL Server Reporting Services 構成マネージャーを実行して、レポートサービスが正しくインストールされ構成されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="34027-148">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="34027-149">System Center Operations Manager コンソールをインストールするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="34027-149">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="34027-150">System Center Operations Manager のセットアップメディアで、 **SetupOM**をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-150">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="34027-151">System Center Operations Manager 2007 R2 のセットアップで、[**前提条件の確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-151">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="34027-152">System Center Operations Manager の前提条件ビューアーで、インストールする System Center コンポーネントを選択します。 (**サーバー**;**本体**;と**PowerShell**) を選び、[**確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-152">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="34027-153">ブロッキングの問題が報告されていないことを確認し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-153">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="34027-154">ブロッキングの問題が報告された場合は、問題を修正し、[**確認**] をクリックして、前提条件のテストを再実行します。</span><span class="sxs-lookup"><span data-stu-id="34027-154">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="34027-155">System Center Operations Manager のセットアップで、[ **Operations manager のインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-155">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="34027-156">System Center Operations Manager のセットアップウィザードの [ **System Center Operations Manager セットアップウィザードへようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-156">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="34027-157">[**エンドユーザーライセンス契約**] ページで、[**使用許諾契約書の条項に同意**します] を選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-157">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="34027-158">[**製品の登録**] ページで、[**ユーザー名**] ボックスに名前を入力し、[**組織**] ボックスに組織の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="34027-158">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="34027-159">[ **25 桁の CD キーを入力**してください] ボックスに System Center Operations Manager のプロダクトキーを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-159">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="34027-160">[**カスタムセットアップ**] ページで、インストールする System Center のオプションを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-160">On the **Custom Setup** page select the System Center options to be installed and then click **Next**.</span></span> <span data-ttu-id="34027-161">[**管理サーバー**]、[**ユーザーインターフェイス**]、[ **Web コンソール**] を選択してインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="34027-161">You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed.</span></span> <span data-ttu-id="34027-162">選択されていないため、**データベース**をインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="34027-162">**Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="34027-163">[ **SC Database Server インスタンス**] ページで、Operations Manager データベースがインストールされているコンピューターの名前が [ **System Center Database server** ] ボックスに表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="34027-163">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="34027-164">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-164">Click **Next**.</span></span>

10. <span data-ttu-id="34027-165">[ **Management Server アクションアカウント**] ページで、 **[ドメインまたはローカルコンピューターアカウント**] を選び、[**ユーザーアカウント**] ボックス、[**パスワード**] ボックス、[**ドメインまたはローカルコンピューター** ] ボックスに適切な値を入力します。</span><span class="sxs-lookup"><span data-stu-id="34027-165">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="34027-166">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-166">Click **Next**.</span></span>

11. <span data-ttu-id="34027-167">[ **SDK と構成サービスアカウント**] ページで [**ドメインまたはローカルコンピューターアカウント**] を選び、[**ユーザーアカウント**] ボックス、[**パスワード**] ボックス、[**ドメインまたはローカルコンピューター** ] ボックスに適切な値を入力します。</span><span class="sxs-lookup"><span data-stu-id="34027-167">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="34027-168">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-168">Click **Next**.</span></span>

12. <span data-ttu-id="34027-169">[ **Operations Manager エラーレポート**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-169">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="34027-170">[**カスタマーエクスペリエンス向上プログラム**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-170">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="34027-171">[**プログラムをインストールする準備ができ**ました] ページで、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-171">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="34027-172">[ **System Center Operations Manager のセットアップを完了**します] ページで、[**バックアップ暗号化キー** ] をオフにし、**コンソールのチェックボックス**をオンにしてから、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-172">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="34027-173">System Center Operations Manager のセットアップで、[**終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-173">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="34027-174">System Center Reporting Services をインストールする</span><span class="sxs-lookup"><span data-stu-id="34027-174">Installing System Center Reporting Services</span></span>

<span data-ttu-id="34027-175">System Center Operations Manager コンソールをインストールして構成した後、System Center Reporting Services をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="34027-175">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="34027-176">SQL Server 2008 R2 を Operations Manager バックエンドデータベースとして使用している場合は、SQL Server Reporting Services に関連付けられているセキュリティグループに一時的な変更を行う必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="34027-176">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="34027-177">SQL Server 2008 R2 を使用している場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34027-177">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="34027-178">[**スタート**] をクリックし、[**管理ツール**] をポイントして、[**サーバーマネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-178">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="34027-179">サーバーマネージャーで、[**構成**] を展開し、[**ローカルユーザーとグループ**] を展開して、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-179">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="34027-180">次のグループを見つけます (atl-sc.exe はコンピューターの名前を表します)。また、システムセンターデータベースの SQL Server インスタンスは、 **SQLServerReportServerUser $ atl-sc-001 $\_MSRS10 50mb)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34027-180">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="34027-181">グループを右クリックし、[**名前の変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-181">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="34027-182">グループ名から\*\* \_50\*\*を削除して、グループの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="34027-182">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="34027-183">例: **SQLServerReportServerUser $ atl-sc-001 $ MSRS10。ARCH**</span><span class="sxs-lookup"><span data-stu-id="34027-183">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="34027-184">サーバーマネージャーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="34027-184">Close Server Manager.</span></span>

<span data-ttu-id="34027-185">この時点で、System Center Reporting Services をインストールする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="34027-185">At this point you are ready to install System Center Reporting Services.</span></span> <span data-ttu-id="34027-186">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="34027-186">To do this:</span></span>

1.  <span data-ttu-id="34027-187">System Center Operations Manager 2007 R2 セットアップメディアで、 **SetupOM**をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-187">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="34027-188">System Center Operations Manager 2007 R2 のセットアップで、[ **Operations Manager レポートのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-188">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="34027-189">System Center Operations Manager 2007 R2 レポートセットアップウィザードの [ **Operations Manager reporting のセットアップへようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-189">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="34027-190">[**エンドユーザーライセンス契約**] ページで、[**使用許諾契約書に同意**します] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-190">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="34027-191">[**製品の登録**] ページで、自分の名前と組織の名前が [**ユーザー名**] ボックスと [**組織**名] ボックスに表示されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-191">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="34027-192">[**カスタムセットアップ**] ページで、[ **Reporting Server** ] をクリックし、[このコンポーネント] を選択します。**すべての依存コンポーネントはローカルディスクドライブにインストールされ**ます。</span><span class="sxs-lookup"><span data-stu-id="34027-192">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**.</span></span> <span data-ttu-id="34027-193">[**データウェアハウス**] をクリックし、[**このコンポーネントは使用できません**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-193">Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="34027-194">[**ルート管理サーバーに接続する**] ページで、[**ルート管理サーバー** ] ボックスに Operations Manager ルート管理サーバーの名前を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-194">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="34027-195">[ **Operations Manager データウェアハウスに接続する**] ページで、[ **sql server インスタンス**] ボックスにデータウェアハウスが配置されている sql server インスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="34027-195">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box.</span></span> <span data-ttu-id="34027-196">(データウェアハウスが既定のインスタンスに配置されている場合は、サーバー名を入力します。例: atl-sql-dmo)。[**名前**] ボックスに**データベース名の**[サーバー名] が表示されていることを確認します。その場合は、[ **SQL Server のポート**] ボックスに "port **1433** " と表示されます。</span><span class="sxs-lookup"><span data-stu-id="34027-196">(If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box.</span></span> <span data-ttu-id="34027-197">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-197">Click **Next**.</span></span>

9.  <span data-ttu-id="34027-198">[ **Sql Server Reporting インスタンス**] ページで、[ **Sql Server reporting Services サーバーの入力**] ドロップダウンリストから SQL Server reporting Server を選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-198">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="34027-199">[**データウェアハウスの書き込みアカウント**] ページで、[**ユーザーアカウント**] ボックスと [**パスワード**] ボックスに、データウェアハウスへの書き込みアクセス許可を最初に割り当てるユーザーの名前とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="34027-199">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="34027-200">[ **Domain** ] ドロップダウンリストからユーザーのドメインを選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-200">Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="34027-201">[**データリーダーアカウント**] ページで、SQL Reporting Services が [**ユーザーアカウント**] ボックスと [**パスワード**] ボックスにデータウェアハウスを照会するときに使用する、ユーザーアカウントの名前とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="34027-201">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="34027-202">[ **Domain** ] ドロップダウンリストからアカウントドメインを選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-202">Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="34027-203">[**オペレーションデータレポート**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-203">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="34027-204">[ **Microsoft Update** ] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-204">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="34027-205">[**プログラムをインストールする準備ができ**ました] ページで、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-205">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="34027-206">[ **Operations Manager レポートコンポーネントのセットアップウィザードを完了**します] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-206">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="34027-207">System Center Operations Manager 2007 R2 のセットアップで、[**終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-207">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="34027-208">System Center レポートをインストールした後、次の手順を使用して、SQL Server レポートに関連付けられているセキュリティグループの名前をリセットします。</span><span class="sxs-lookup"><span data-stu-id="34027-208">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="34027-209">この手順は、SQL Server を使用している場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="34027-209">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="34027-210">[**スタート**] をクリックし、[**管理ツール**] をポイントして、[**サーバーマネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-210">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="34027-211">サーバーマネージャーで、[**構成**] を展開し、[**ローカルユーザーとグループ**] を展開して、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-211">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="34027-212">次のグループを見つけます。ここでは、atl-sc-001 はコンピューターの名前を表し、 **SQLServerReportServerUser $ atl-sc-001 $ MSRS10 の SQL Server インスタンスを示しています。ARCH**</span><span class="sxs-lookup"><span data-stu-id="34027-212">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="34027-213">グループを右クリックし、[**名前の変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34027-213">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="34027-214">グループ名の末尾に SQL Server インスタンス名の直前に\*\* \_50\*\*を追加して、グループの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="34027-214">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="34027-215">たとえば、 **SQLServerReportServerUser $ atl-sc-001 $ MSRS10\_50mb**。</span><span class="sxs-lookup"><span data-stu-id="34027-215">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="34027-216">サーバーマネージャーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="34027-216">Close Server Manager.</span></span>

<span data-ttu-id="34027-217">System Center Operations コンソールが開いている場合は、アプリケーションを終了して再起動する必要があります。この操作を行わない場合、[**レポート**] タブは [オペレーション] コンソールのユーザーインターフェイスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="34027-217">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface.</span></span> <span data-ttu-id="34027-218">初めて操作コンソールを再起動した後、[**レポート**] タブにすべての監視レポートが表示されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="34027-218">Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

