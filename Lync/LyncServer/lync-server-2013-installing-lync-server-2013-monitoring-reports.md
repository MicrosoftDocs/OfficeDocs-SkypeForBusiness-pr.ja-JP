---
title: 'Lync Server 2013: Lync Server 2013 の監視レポートのインストール'
description: 'Lync Server 2013: Lync Server 2013 の監視レポートのインストール。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12405f786cbaf095e97f526fae2e1c2d3cb45c32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573933"
---
# <a name="installing-lync-server-2013-monitoring-reports"></a><span data-ttu-id="8cf7c-103">Lync Server 2013 監視レポートのインストール</span><span class="sxs-lookup"><span data-stu-id="8cf7c-103">Installing Lync Server 2013 Monitoring Reports</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cf7c-104">_**トピックの最終更新日:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="8cf7c-104">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="8cf7c-105">Microsoft Lync Server 2013 の監視レポートでは、組織内で発生する通信セッションの品質と量に関するさまざまな情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-105">Microsoft Lync Server 2013 Monitoring Reports provide you with a wealth of information about the quality and quantity of the communication sessions that take place in your organization.</span></span> <span data-ttu-id="8cf7c-106">ただし、Lync Server 2013 をインストールしても、監視レポートは自動的にはインストールされません。その代わりに、Lync Server がコンピューターにインストールされている場合にのみ、監視レポートを個別にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-106">However, Monitoring Reports are not automatically installed when you install Lync Server 2013; instead, you must install Monitoring Reports separately, and only after Lync Server has been installed on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8cf7c-p102">監視レポートは、監視データベースがインストールされているのと同じコンピューターにインストールすることをお勧めします。これにより、レポートへのアクセス許可の割り当てプロセスが簡単になります。監視ストアをホストしているコンピューターに監視レポートをインストールすると、別のコンピューター上で実行されている Reporting Services とデータベースが対話できるようにするためのアクセス許可を構成する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-p102">It is recommended that you install Monitoring Reports on the same computer where the monitoring database is installed. This simplifies the process of assigning permissions for accessing the reports: installing Monitoring Reports on the computer that hosts the monitoring store means that you will not have to configure permissions that allow a database on one computer to interact with Reporting Services running on a second computer.</span></span>



</div>

<span data-ttu-id="8cf7c-109">Lync Server の監視レポートには、電話会議、ピアツーピア IM セッション、ユーザー登録、応答グループアプリケーションなどに関する詳細情報を提供するように設計された30個以上のレポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-109">Lync Server Monitoring Reports include over 30 reports designed to provide detailed information about conferences, peer-to-peer IM sessions, user registrations, the Response Group application, and much more.</span></span> <span data-ttu-id="8cf7c-110">2013バージョンでは、Lync Server の監視レポートにはいくつかの機能拡張が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-110">For the 2013 version, Lync Server Monitoring Reports include a number of enhancements:</span></span>

  - <span data-ttu-id="8cf7c-111">**新しい音声品質レポート**。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-111">**New voice quality reports**.</span></span> <span data-ttu-id="8cf7c-112">これらの新しいレポートには、 [Lync Server 2013 のメディア品質比較レポート](lync-server-2013-media-quality-comparison-report.md)が含まれています。これはさまざまな通話の種類 (たとえば、有線通話とワイヤレス呼び出しの間) で品質を比較します。また、 [Lync Server 2013 の電話会議参加時間レポート](lync-server-2013-conference-join-time-report.md)は、ユーザーが会議に参加するのに必要な時間に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-112">These new reports include the [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), which compares quality between different types of calls (for example, between wired calls and wireless calls); and the [Conference Join Time Report in Lync Server 2013](lync-server-2013-conference-join-time-report.md), which provides information regarding the amount of time requires for users to join a conference.</span></span>

  - <span data-ttu-id="8cf7c-113">**ビデオおよびアプリケーション共有セッションの分析とトラブルシューティングのためのレポートが向上しました。**</span><span class="sxs-lookup"><span data-stu-id="8cf7c-113">**Improved reports for analyzing and troubleshooting both video and application sharing sessions.**</span></span> <span data-ttu-id="8cf7c-114">Lync [server 2013 のメディア品質概要レポート](lync-server-2013-media-quality-summary-report.md) では、ビデオおよびアプリケーション共有の通話を分析することができますが、 [lync Server 2013 のサーバーパフォーマンスレポートで](lync-server-2013-server-performance-report.md) は、これらの呼び出しを生成しているサーバーのパフォーマンスの詳細が示されています。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-114">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) provides a way to analyze video and application sharing calls, while the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) details the performance of servers generating these calls.</span></span> <span data-ttu-id="8cf7c-115">また、ビデオとアプリケーション共有の測定基準は、lync [server 2013 のピアツーピアセッション詳細レポート](lync-server-2013-peer-to-peer-session-detail-report.md) 、および [lync Server 2013 の会議詳細レポート](lync-server-2013-conference-detail-report.md)によって報告されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-115">Video and application sharing metrics are also now reported by the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) and the [Conference Detail Report in Lync Server 2013](lync-server-2013-conference-detail-report.md).</span></span>

  - <span data-ttu-id="8cf7c-p106">**レポートのパフォーマンスの向上**: 応答時間とデータ取得時間が短縮され、レポート間の移動をすばやく簡単に行えるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-p106">**Improved report performance**. This includes faster response and data retrieval time, as well as faster and easier navigation through the reports.</span></span>

<span data-ttu-id="8cf7c-118">個々のレポートの詳細については、監視レポートのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-118">More information on the individual reports can be found in the Monitoring Reports documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8cf7c-119">もう1つの新しいレポートがあります。「QoE Call Detail サブレポート」– Lync Server 2013 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-119">There is another new report – QoE Call Detail Subreport – included in Lync Server 2013.</span></span> <span data-ttu-id="8cf7c-120">ただし、このレポートは主に内部用であり、直接アクセスするためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-120">However, this report is primarily for internal use, and is not intended to be directly accessed.</span></span>



</div>

<span data-ttu-id="8cf7c-121">Lync Server の監視レポートをインストールするには、次の2つの方法があります。 lync server 展開ウィザードを使用するか、Lync Server 2013 のインストールファイルに付属する Windows PowerShell スクリプトを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-121">There are two ways to install Lync Server Monitoring Reports: you can use the Lync Server Deployment Wizard or you can use a Windows PowerShell script included with the Lync Server 2013 installation files.</span></span> <span data-ttu-id="8cf7c-122">どちらの方法でレポートをインストールする場合でも、最初に次のことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-122">Regardless of the method you use to install the reports you must first make sure that you:</span></span>

  - <span data-ttu-id="8cf7c-123">監視データベースのユーザー アカウントにデータベースの役割を追加する権限を持っている。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-123">Have the right to add a database role to a user account in the monitoring database.</span></span>

  - <span data-ttu-id="8cf7c-p109">SQL Server Reporting Services のコンテンツ マネージャーの役割を持っている。この役割では、SQL Server Reporting Services にレポートを展開する権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-p109">Hold the Content Manager role in SQL Server Reporting Services. This role gives you the right to deploy reports to SQL Server Reporting Services.</span></span>

<span data-ttu-id="8cf7c-126">展開ウィザードを使用して監視レポートをインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-126">To install the Monitoring Reports by using the Deployment Wizard, complete the following steps:</span></span>

1.  <span data-ttu-id="8cf7c-127">[ **スタート**]、[ **すべてのプログラム**]、[ **Microsoft lync Server 2013**]、[ **lync server 展開ウィザード**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-127">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="8cf7c-128">展開ウィザードで [**監視レポートの展開**] をクリックして、監視レポートの展開ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-128">In the Deployment Wizard, click **Deploy Monitoring Reports** in order to start the Deploy Monitoring Reports wizard.</span></span>

3.  <span data-ttu-id="8cf7c-p110">監視レポートの展開ウィザードの [**監視データベースの指定**] ページで、[**監視データベース**] ドロップダウン リストに、監視ストアをホストしているコンピューターの完全修飾ドメイン名が表示されていることを確認します (複数の監視ストアがある場合は、ドロップダウン リストから適切なサーバーを選択する必要があります)。[**SQL Server Reporting Services (SSRS) インスタンス**] ボックスに正しい SQL Server インスタンス (たとえば **atl-sql-001.litwareinc.com/archinst**) が表示されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-p110">In the Deploy Monitoring Reports wizard, on the **Specify Monitoring Database** page, make sure that the fully qualified domain name of the computer hosting your monitoring store appears in the **Monitoring database** dropdown list. (If you have multiple monitoring stores you will need to select the appropriate server from the dropdown list.) Verify that the correct SQL Server instance appears in the **SQL Server Reporting Services (SSRS) instance** box (for example, **atl-sql-001.litwareinc.com/archinst**) and then click **Next**.</span></span>

4.  <span data-ttu-id="8cf7c-131">[ **資格情報の指定** ] ページの [ **ユーザー名** ] ボックスに、監視レポートにアクセスするときに使用するアカウントのドメイン名とユーザー名を入力します (たとえば、 **litwareinc \\ kenmyer**)。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-131">On the **Specify Credentials** page, in the **User name** box, type the domain name and user name of the account to be used when accessing the Monitoring Reports (for example, **litwareinc\\kenmyer**).</span></span> <span data-ttu-id="8cf7c-132">この形式 (ドメインユーザー名) を使用しない場合は \\ 、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-132">If you do not use this format (domain\\user name) an error will occur.</span></span>
    
    <span data-ttu-id="8cf7c-133">[**パスワード**] ボックスにユーザー アカウントのパスワードを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-133">Type the user account password in the **Password** box, and then click **Next**.</span></span> <span data-ttu-id="8cf7c-134">このアカウントには特別な権限は必要ないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-134">Note that no special rights are required for this account.</span></span> <span data-ttu-id="8cf7c-135">セットアップが完了すると、アカウントには必要なログオンおよびデータベースのアクセス許可が自動的に与えられます。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-135">The account will automatically be granted the required logon and database permissions when setup completes.</span></span>

5.  <span data-ttu-id="8cf7c-p113">[**読み取り専用グループの指定**] ページの [ユーザー グループ] ボックスに、SQL Server Reporting Services への読み取り専用の管理者アクセス権を付与するセキュリティ グループの名前を入力します。たとえば、レポートへの読み取り専用の管理者アクセス権を付与するには、「**RTCUniversalReadOnlyAdmins**」と入力します。その後、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-p113">On the **Specify Read-Only Group** page enter the name of a security group that will be granted read-only access to the SQL Server Reporting Services in the User group box. For example, to give read-only administrators access to the reports enter **RTCUniversalReadOnlyAdmins**. Click **Next**.</span></span>

6.  <span data-ttu-id="8cf7c-139">[**コマンドを実行しています**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-139">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="8cf7c-140">また、DeployReports.ps1 スクリプトを実行することによって、Lync Server 管理シェルから監視レポートをインストールすることもできます。この Windows PowerShell スクリプトは、Lync Server インストールメディアのセットアップの [ \\ \\ reportingsetup] フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-140">Monitoring Reports can also be installed from the Lync Server Management Shell by running the script DeployReports.ps1; this Windows PowerShell script can be found on the Lync Server installation media in the \\Setup\\ReportingSetup folder.</span></span> <span data-ttu-id="8cf7c-141">DeployReports.ps1 を使用して監視レポートをインストールするには、管理シェルプロンプトで次のようなコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-141">To install Monitoring Reports using DeployReports.ps1, type a command similar to the following at the Management Shell prompt:</span></span>

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

<span data-ttu-id="8cf7c-142">このコマンドで使用されているパラメーターの説明を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-142">The parameters used in the preceding command are described in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8cf7c-143">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="8cf7c-143">Parameter Name</span></span></th>
<th><span data-ttu-id="8cf7c-144">必須</span><span class="sxs-lookup"><span data-stu-id="8cf7c-144">Required</span></span></th>
<th><span data-ttu-id="8cf7c-145">説明</span><span class="sxs-lookup"><span data-stu-id="8cf7c-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8cf7c-146">storedUserName</span><span class="sxs-lookup"><span data-stu-id="8cf7c-146">storedUserName</span></span></p></td>
<td><p><span data-ttu-id="8cf7c-147">必要</span><span class="sxs-lookup"><span data-stu-id="8cf7c-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="8cf7c-148">監視ストアへのアクセスに使用するユーザーアカウント (形式はドメイン\ユーザー名)。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-148">User account (in the format domain\username) used to access the monitoring store; for example:</span></span></p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p><span data-ttu-id="8cf7c-149">このアカウントには、SQL Server と SQL Server Reporting Services のアクセス許可が事前に指定されている必要があります。指定されていない場合、スクリプトは失敗します。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-149">This account must have the previously-specified SQL Server and SQL Server Reporting Services permissions or the script will fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cf7c-150">storedPassword</span><span class="sxs-lookup"><span data-stu-id="8cf7c-150">storedPassword</span></span></p></td>
<td><p><span data-ttu-id="8cf7c-151">必要</span><span class="sxs-lookup"><span data-stu-id="8cf7c-151">Yes</span></span></p></td>
<td><p><span data-ttu-id="8cf7c-152">監視ストアへのアクセスに使用するユーザー アカウントのパスワード。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-152">Password for the user account used to access the monitoring store.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cf7c-153">readOnlyGroupName</span><span class="sxs-lookup"><span data-stu-id="8cf7c-153">readOnlyGroupName</span></span></p></td>
<td><p><span data-ttu-id="8cf7c-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="8cf7c-154">No</span></span></p></td>
<td><p><span data-ttu-id="8cf7c-155">監視レポートへの読み取り専用アクセス権を付与するユーザーが属するドメインまたはローカル セキュリティ グループ。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-155">Domain or local security group whose members will be granted read-only access to the Monitoring Reports.</span></span> <span data-ttu-id="8cf7c-156">指定したグループが存在しない場合、スクリプトは失敗することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-156">Note that the script will fail if the specified group does not exist.</span></span> <span data-ttu-id="8cf7c-157">後でこれらのアクセス権を無効にしたり他のユーザーまたはグループにアクセス権を付与したりする必要が生じた場合は、SQL Service Reporting Services レポート マネージャーを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-157">If you later decide to revoke these permissions, or if you decide to grant other users or other groups access permissions, you can do so using the SQL Service Reporting Services Report Manager.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cf7c-158">reportSqlServerInstance</span><span class="sxs-lookup"><span data-stu-id="8cf7c-158">reportSqlServerInstance</span></span></p></td>
<td><p><span data-ttu-id="8cf7c-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="8cf7c-159">No</span></span></p></td>
<td><p><span data-ttu-id="8cf7c-p116">Reporting Service をホストする SQL Server インスタンス。Reporting インスタンスは、レポート サーバーの完全修飾ドメイン名を使用して指定する必要があります。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-p116">SQL Server instance that hosts the Reporting Service. The Reporting instance must be specified using the fully qualified domain name of the Report Server; for example:</span></span></p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p><span data-ttu-id="8cf7c-162">このパラメーターが指定されていない場合、スクリプトは、レポート サービスが監視データベースをホストしているのと同じ SQL Server インスタンスによってホストされていると見なします。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-162">If this parameter is not included the script will assume that the reporting services are hosted by the same SQL Server instance that hosts the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cf7c-163">monitoringDatabaseId</span><span class="sxs-lookup"><span data-stu-id="8cf7c-163">monitoringDatabaseId</span></span></p></td>
<td><p><span data-ttu-id="8cf7c-164">いいえ</span><span class="sxs-lookup"><span data-stu-id="8cf7c-164">No</span></span></p></td>
<td><p><span data-ttu-id="8cf7c-p117">監視データベースのサービス ID。次のコマンドを実行することで、監視データベースの ID を取得できます。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-p117">Service Identity for the monitoring database. You can return the Identities for your monitoring databases by running this command:</span></span></p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8cf7c-167">監視レポートのインストールが完了したら、Set-CsReportingConfiguration コマンドレットを使用して、これらのレポートへのアクセスに使用する URL を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-167">After the Monitoring Reports have been installed you must then use the Set-CsReportingConfiguration cmdlet to configure the URL used to access these reports.</span></span> <span data-ttu-id="8cf7c-168">このタスクは、次の Windows PowerShell コマンドを実行することによって、Lync Server 管理シェルから実行できます。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-168">This task can be carried out from the Lync Server Management Shell by running the following Windows PowerShell command.</span></span> <span data-ttu-id="8cf7c-169">レポート URL の構成時には、必須ではありませんが、HTTPS プロトコルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-169">Note that it is recommended, but not required, that you use the HTTPS protocol when configuring the reporting URL:</span></span>

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

<span data-ttu-id="8cf7c-p119">上のコマンドでは、ReportingUrl プロパティを、SQL Server 2008 R2 Reporting Services で使用されているレポート マネージャー URL に設定する必要があります。レポート マネージャー URL は、SQL Server Reporting Services がインストールされているコンピューターで次の手順を実行することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-p119">In the preceding command, the ReportingUrl property should be set to the Report Manager URL used by SQL Server 2008 R2 Reporting Services. You can determine the Report Manager URL by completing the following steps on the computer where SQL Server Reporting Services has been installed:</span></span>

1.  <span data-ttu-id="8cf7c-172">[スタート]、[すべてのプログラム]、[Microsoft SQL Server 2008 R2] 、[構成ツール]、[Reporting Services 構成マネージャー] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-172">Click Start, click All Programs, click Microsoft SQL Server 2008 R2, click Configuration Tools, and then click Reporting Services Configuration Manager.</span></span>

2.  <span data-ttu-id="8cf7c-p120">[Reporting Services 構成の接続] ダイアログ ボックスで、Reporting Services コンピューターの名前が [サーバー名] ボックスに表示されていることを確認します。[レポート サーバー インスタンス] ドロップダウン リストから SQL Server インスタンスを選択し、[接続] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-p120">In the Reporting Services Configuration Connection dialog box, make sure that the name of the Reporting Services computer appears in the Server Name box. Select the SQL Server instance from the Report Server Instance dropdown list and then click Connect.</span></span>

3.  <span data-ttu-id="8cf7c-p121">Reporting Services 構成マネージャーで、[レポート マネージャー URL] をクリックします。すると、[レポート マネージャー URL] ウィンドウに 1 つ以上の URL が表示されます。いずれの URL もレポート用 URL として使用できますが、上で説明したように ReportingUrl には HTTPS プロトコルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-p121">In Reporting Services Configuration Manager, click Report Manager URL. One or more URLs should appear in the Report Manager URL pane. Any of these URLs can be used as the Reporting URL although, again, it is recommended that the ReportingUrl use the HTTPS protocol.</span></span>

<span data-ttu-id="8cf7c-178">監視データベースのミラーデータベースを設定した場合は、監視レポートをミラーデータベースにも関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-178">If you have set up a mirror database for your monitoring database then you must also associate the Monitoring Reports with the mirror database.</span></span> <span data-ttu-id="8cf7c-179">詳細については、「 [Lync Server 2013 での監視レポートとミラーデータベースの関連付け](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cf7c-179">See the article [Associating Monitoring Reports with a mirror database in Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) for details.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

