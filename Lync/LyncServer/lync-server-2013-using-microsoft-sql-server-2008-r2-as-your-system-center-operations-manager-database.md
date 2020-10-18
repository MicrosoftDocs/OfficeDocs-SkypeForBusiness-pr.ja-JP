---
title: 'Lync Server 2013: Microsoft SQL Server 2008 R2 を System Center Operations Manager データベースとして使用する'
description: 'Lync Server 2013: Microsoft SQL Server 2008 R2 を System Center Operations Manager データベースとして使用しています。'
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
ms.openlocfilehash: 870c079e7e5e871fc62358e9bdd21653193fad7c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580353"
---
# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="8930f-103">Lync Server 2013 の System Center Operations Manager データベースとしての Microsoft SQL Server 2008 R2 の使用</span><span class="sxs-lookup"><span data-stu-id="8930f-103">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8930f-104">_**トピックの最終更新日:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="8930f-104">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="8930f-105">SQL Server 2008 R2 をバックエンドデータベースとして使用するには、このトピックに記載されている手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8930f-105">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="8930f-106">SQL Server 2008 R2 および SQL Server Reporting Services の構成</span><span class="sxs-lookup"><span data-stu-id="8930f-106">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="8930f-107">System Center Operations Manager のインストールを開始する前に、SQL Server 2008 R2 と SQL Server Reporting Services の構成に2つの変更を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="8930f-107">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="8930f-108">(これらの変更は、SQL Server 2008 R2 を Operations Manager データベースとして使用している場合にのみ必要です)。まず、Operations Manager データベースをホストするコンピューターで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8930f-108">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="8930f-109">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-109">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="8930f-110">[ファイル名を指定して **実行** ] ダイアログボックスで、「 \*\*C: \\ Program Files \\ Microsoft SQL Server \\ msrs10.archinst \_ 50 \\ \\ \*\* 」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8930f-110">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="8930f-111">**ReportServer** フォルダーで、メモ帳などのテキスト エディターで **rsreportserver.config** ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8930f-111">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="8930f-112">ファイルの先頭付近に "Add Key" ノードがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="8930f-112">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="8930f-113">\*\* \< [キーの追加] = "SecureConnectionLevel"\*\* を開始するエントリを見つけ、値を**0**に設定します。</span><span class="sxs-lookup"><span data-stu-id="8930f-113">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="8930f-114">**rsreportserver.config** ファイルを保存し、テキスト エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8930f-114">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="8930f-p103">レポート サーバーの構成ファイルを更新したら、次は、SQL Server Reporting Services に適切な証明書を割り当てる必要があります。そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8930f-p103">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services. To do that:</span></span>

1.  <span data-ttu-id="8930f-117">[ **スタート**]、 **[すべてのプログラム**]、[ **Microsoft SQL Server 2008 R2**]、[ **構成ツール**] の順にクリックし、[ **Reporting Services 構成マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-117">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="8930f-118">[**Reporting Services 構成の接続**] ダイアログ ボックスの [**サーバー名**] ボックスに、サーバーの名前が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8930f-118">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="8930f-119">[**レポートサーバーインスタンス**] ドロップダウンリストから、Operations Manager データベースをホストする SQL Server インスタンス (たとえば、「 **arch inst**」) を選択し、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-119">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="8930f-120">Reporting Services 構成マネージャーで、[**Web サービスの URL**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-120">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="8930f-p105">[**Web サービスの URL**] ページで、Reporting Services に使用する証明書を [**SSL 証明書**] ドロップダウン リストから選択し、[**適用**] をクリックします。2 ～ 3 秒後、[**レポート サーバー Web サービスの URL**] の下に URL のペアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8930f-p105">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**. After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="8930f-123">両方の URL をクリックして、SQL Server Reporting Services にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8930f-123">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="8930f-124">Reporting Services 構成マネージャーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8930f-124">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="8930f-125">SQL Server 2008 R2 で使用する System Center Operations Manager データベースを作成する</span><span class="sxs-lookup"><span data-stu-id="8930f-125">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="8930f-126">SQL Server 2008 R2 データベースを使用するように System Center Operations Manager を構成する場合は、SQL Server 2008 R2 を実行しているコンピューターに Operations Manager データベースを手動で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8930f-126">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="8930f-127">(バックエンドデータベースとして SQL Server 2005 または SQL Server 2008 を使用している場合は、これらの手順は必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="8930f-127">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="8930f-128">Operations Manager データベースを手動で作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8930f-128">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="8930f-129">System Center Operations Manager 2007 R2 セットアップメディアの [SupportTools AMD64] フォルダーで、 \\ [ **DBCreateWizard.exe**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-129">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="8930f-130">データベース構成ウィザードの [**データベース構成ウィザードの開始**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-130">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="8930f-131">[**データベース情報**] ページで、すべての設定をそのまま使用し (一切変更しないで)、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-131">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="8930f-132">[**管理グループの構成**] ページで、[管理グループ**名**] ボックスに管理グループの名前 (例: **Lync Server Monitoring**) を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-132">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="8930f-133">[**Operations Manager エラー レポート**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-133">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="8930f-134">[**概要**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-134">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="8930f-135">SQL Server 2008 R2 で使用する System Center Operations Manager データウェアハウスを作成する</span><span class="sxs-lookup"><span data-stu-id="8930f-135">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="8930f-136">Microsoft Lync Server 2013 には、次の3つの新しい System Center Operations Manager レポートが付属しています。</span><span class="sxs-lookup"><span data-stu-id="8930f-136">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="8930f-137">**エンドツーエンドシナリオの可用性レポート**    このレポートでは、登録やプレゼンスなど、主要な Lync Server サービスの可用性/稼働時間を詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="8930f-137">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="8930f-138">**容量レポート**    このレポートは、パフォーマンスカウンターの情報を使用して、メモリの可用性やプロセッサの使用率などのシステムコンポーネントの傾向を示します。</span><span class="sxs-lookup"><span data-stu-id="8930f-138">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="8930f-139">**コンポーネントレポート**    このレポートには、Lync Server コンポーネントによってグループ化された上位の通知ジェネレーターが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="8930f-139">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="8930f-140">これらの新しいレポートを使用するには、System Center Operations Manager データウェアハウスをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8930f-140">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="8930f-141">(データウェアハウスは、運用データの長期的な保存に使用します)。SQL Server 2008 R2 でデータウェアハウスを使用するには、SQL Server データベースをホストするコンピューターで次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8930f-141">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="8930f-142">System Center Operations Manager セットアップメディアのセットアップ \\ supporttools AMD64 フォルダーで、 \\ [ **DBCreateWizard.exe**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-142">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="8930f-143">データベース構成ウィザードの [**データベース構成ウィザードの開始**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-143">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="8930f-144">[**データベース情報**] ページで、[**データベースのタイプ**] ドロップダウン リストから [**Operations Manager データ ウェアハウス データベース**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-144">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="8930f-145">[**概要**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-145">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="8930f-146">System Center Operations Manager コンソールのインストール</span><span class="sxs-lookup"><span data-stu-id="8930f-146">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="8930f-147">Operations Manager コンソールは、System Center Operations Manager を管理するために使用される主要なツールです。</span><span class="sxs-lookup"><span data-stu-id="8930f-147">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="8930f-148">Operations Manager コンソールをインストールする前に、サポートされているバージョンの SQL Server と SQL Server Reporting Service がインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8930f-148">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="8930f-149">また、SQL Server の Reporting Services 構成マネージャーを実行して、Reporting Service が正しくインストールおよび構成されていることを確認することもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8930f-149">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="8930f-150">System Center Operations Manager コンソールをインストールするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8930f-150">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="8930f-151">System Center Operations Manager セットアップメディアで、[ **SetupOM.exe**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-151">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="8930f-152">System Center Operations Manager 2007 R2 セットアップで、[ **前提条件の確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-152">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="8930f-153">System Center Operations Manager の前提条件ビューアーで、インストールする System Center コンポーネントを選択します。 (**サーバー**; **コンソール**。 **PowerShell**) を選択し、[ **確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-153">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="8930f-154">ブロックの問題が報告されていないことを確認し、[ **閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-154">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="8930f-155">ブロックの問題が報告された場合は、問題を修正し、[ **チェック** ] をクリックして、前提条件のテストを再実行します。</span><span class="sxs-lookup"><span data-stu-id="8930f-155">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="8930f-156">System Center Operations Manager セットアップで、[ **Operations manager のインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-156">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="8930f-157">System Center Operations Manager セットアップウィザードの [ **System Center Operations Manager セットアップウィザードへようこそ** ] ページで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-157">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="8930f-158">[**使用許諾契約書**] ページで、[**使用許諾契約書に同意します**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-158">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="8930f-159">[**製品登録**] ページで、[**ユーザー名**] ボックスに自分の名前を、[**組織**] ボックスに組織の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8930f-159">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="8930f-160">[ **25 桁の CD キーを入力** してください] ボックスに System Center Operations Manager のプロダクトキーを入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-160">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="8930f-p111">[**カスタム セットアップ**] ページで、インストールする System Center オプションを選択し、[**次へ**] をクリックします。インストールする**管理サーバー**、**ユーザー インターフェイス**、および **Web コンソール**を選択する必要があります。**データベース**はインストールしないので選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="8930f-p111">On the **Custom Setup** page select the System Center options to be installed and then click **Next**. You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed. **Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="8930f-164">[ **SC データベースサーバーインスタンス** ] ページで、Operations Manager データベースがインストールされているコンピューターの名前が [ **システムセンターデータベースサーバー** ] ボックスに表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8930f-164">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="8930f-165">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-165">Click **Next**.</span></span>

10. <span data-ttu-id="8930f-p113">[**管理サーバー アクション アカウント**] ページで、[**ドメインまたはローカル コンピューターのアカウント**] を選択し、[**ユーザー アカウント**]、[**パスワード**]、および [**ドメインまたはローカル コンピューター**] ボックスにそれぞれ適切な値を入力します。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-p113">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes. Click **Next**.</span></span>

11. <span data-ttu-id="8930f-p114">[**SDK と Config サービス アカウント**] ページで、[**ドメインまたはローカル コンピューターのアカウント**] を選択し、[**ユーザー アカウント**]、[**パスワード**]、および [**ドメインまたはローカル コンピューター**] ボックスにそれぞれ適切な値を入力します。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-p114">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes. Click **Next**.</span></span>

12. <span data-ttu-id="8930f-170">[**Operations Manager エラー レポート**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-170">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="8930f-171">[**カスタマー エクスペリエンス向上プログラム**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-171">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="8930f-172">[**プログラムのインストールの準備完了**] ページで、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-172">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="8930f-173">[**System Center Operations Manager セットアップ ウィザードを完了しています**] ページで、[**暗号化キーのバックアップ**] および [**コンソールの開始**] チェック ボックスをオフにし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-173">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="8930f-174">System Center Operations Manager セットアップで、[ **終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-174">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="8930f-175">System Center レポート サービスのインストール</span><span class="sxs-lookup"><span data-stu-id="8930f-175">Installing System Center Reporting Services</span></span>

<span data-ttu-id="8930f-176">System Center Operations Manager コンソールをインストールして構成した後、System Center Reporting Services をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8930f-176">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="8930f-177">SQL Server 2008 R2 を Operations Manager のバックエンドデータベースとして使用している場合は、まず、SQL Server Reporting Services に関連付けられているセキュリティグループに一時的な変更を加える必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8930f-177">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="8930f-178">SQL Server 2008 R2 を使用している場合は、次の操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8930f-178">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="8930f-179">[**スタート**] ボタンをクリックし、[**管理ツール**] をポイントします。次に [**サーバー マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-179">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="8930f-180">サーバー マネージャーで、[**構成**]、[**ローカル ユーザーとグループ**] の順に展開し、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-180">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="8930f-181">次のグループを見つけます (ここで、atl-ws-01 はコンピューターの名前を表し、アーキテクチャ INST はシステムセンターデータベースの SQL Server インスタンスを表します。 **SQLServerReportServerUser $ atl-sc-001 $ msrs10.archinst \_ 50.**</span><span class="sxs-lookup"><span data-stu-id="8930f-181">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="8930f-182">このグループを右クリックし、[**名前の変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-182">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="8930f-183">グループ名から\*\* \_ 50\*\*を削除して、グループの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="8930f-183">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="8930f-184">次に例を示します。 **SQLServerReportServerUser $ atl-sc-001 $ msrs10.archinst。アーキテクチャ (INST**)</span><span class="sxs-lookup"><span data-stu-id="8930f-184">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="8930f-185">サーバー マネージャーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8930f-185">Close Server Manager.</span></span>

<span data-ttu-id="8930f-p117">この時点で、System Center レポート サービスをインストールできます。そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8930f-p117">At this point you are ready to install System Center Reporting Services. To do this:</span></span>

1.  <span data-ttu-id="8930f-188">System Center Operations Manager 2007 R2 セットアップメディアで、[ **SetupOM.exe**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-188">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="8930f-189">System Center Operations Manager 2007 R2 セットアップで、[ **Operations Manager レポートのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-189">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="8930f-190">System Center Operations Manager 2007 R2 レポートセットアップウィザードの [ **Operations Manager Reporting のセットアップへようこそ** ] ページで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-190">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="8930f-191">[**使用許諾契約書**] ページで、[**使用許諾契約書に同意します**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-191">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="8930f-192">[**製品登録**] ページで、[**ユーザー名**] ボックスに自分の名前が、[**組織**] ボックスに組織の名前が表示されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-192">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="8930f-p118">[**カスタム セットアップ**] ページで、[**レポート サーバー**] をクリックし、[**このコンポーネントおよびすべての従属コンポーネントは、ローカル ディスク ドライブにインストールされます。**] を選択します。[**データ ウェアハウス**] をクリックし、[**インストールしない**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-p118">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**. Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="8930f-195">[**ルート管理サーバーに接続**] ページで、[**ルート管理サーバー**] ボックスに、Operations Manager のルート管理サーバーの名前を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-195">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="8930f-p119">[**Operations Manager のデータ ウェアハウスに接続**] ページで、[**SQL Server インスタンス**] ボックスに、データ ウェアハウスが配置される SQL Server インスタンスを入力します (データ ウェアハウスが既定のインスタンスに配置される場合は、atl-sql-001 など、サーバー名のみを入力します)。[**名前**] ボックスにデータベース名 "**OperationsManagerDW**" が表示され、[**SQL Server ポート**] ボックスに "**1433**" と表示されることを確認します。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-p119">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box. (If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box. Click **Next**.</span></span>

9.  <span data-ttu-id="8930f-199">[**SQL Server Reporting Services インスタンス**] ページで、[**SQL Server Reporting Services のサーバーを入力してください**] ドロップダウン リストから SQL Server レポート サーバーを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-199">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="8930f-p120">[**データ ウェアハウス書き込みアカウント**] ページで、[**ユーザー アカウント**] および [**パスワード**] ボックスに、データ ウェアハウスに対する書き込みアクセス許可を最初に割り当てるユーザーの名前とパスワードを入力します。[**ドメイン**] ドロップダウン リストからユーザーのドメインを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-p120">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes. Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="8930f-p121">[**データ リーダー アカウント**] ページで、[**ユーザー アカウント**] および [**パスワード**] ボックスに、SQL Reporting Services がデータ ウェアハウスをクエリするときに使用するユーザー アカウントの名前とパスワードを入力します。[**ドメイン**] ドロップダウン リストからアカウントのドメインを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-p121">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes. Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="8930f-204">[**オペレーション データ レポート**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-204">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="8930f-205">[**Microsoft Update**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-205">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="8930f-206">[**プログラムのインストールの準備完了**] ページで、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-206">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="8930f-207">[**Operations Manager Reporting コンポーネント セットアップ ウィザードを完了しています**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-207">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="8930f-208">System Center Operations Manager 2007 R2 セットアップで、[ **終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-208">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="8930f-209">System Center レポートをインストールした後、次の手順を使用して、SQL Server レポートに関連付けられているセキュリティグループの名前をリセットします。</span><span class="sxs-lookup"><span data-stu-id="8930f-209">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="8930f-210">この手順は、SQL Server を使用している場合にのみ必要になります。</span><span class="sxs-lookup"><span data-stu-id="8930f-210">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="8930f-211">[**スタート**] ボタンをクリックし、[**管理ツール**] をポイントします。次に [**サーバー マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-211">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="8930f-212">サーバー マネージャーで、[**構成**]、[**ローカル ユーザーとグループ**] の順に展開し、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-212">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="8930f-213">次のグループを見つけます (atl-sc-bytes はコンピューターの名前を表し、アーキテクチャ INST はアーカイブデータベースおよび監視データベースの SQL Server インスタンスを表します。 **SQLServerReportServerUser $ atl-sc-001 $ msrs10.archinst。アーキテクチャ (INST**)</span><span class="sxs-lookup"><span data-stu-id="8930f-213">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="8930f-214">このグループを右クリックし、[**名前の変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8930f-214">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="8930f-215">グループ名の末尾に、SQL Server インスタンス名の直前に\*\* \_ 50\*\*を追加して、グループの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="8930f-215">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="8930f-216">次に例を示します。 **SQLServerReportServerUser $ atl-sc-001 $ msrs10.archinst \_ 50mb**。</span><span class="sxs-lookup"><span data-stu-id="8930f-216">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="8930f-217">サーバー マネージャーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8930f-217">Close Server Manager.</span></span>

<span data-ttu-id="8930f-p124">System Center Operations コンソールが開いている場合は、アプリケーションをいったん閉じて再起動してください。再起動しないと、Operations コンソール ユーザー インターフェイスに [**レポート**] タブが表示されません。Operations コンソールを初めて再起動したときは、[**レポート**] タブにすべての監視レポートが表示されるまでに数分間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="8930f-p124">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface. Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

