---
title: Lync Server 2013 で SQL Server の非標準ポートおよびエイリアスを展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35365cbd43aa3bea9afe5cdd036bd3834fae5037
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="77fc3-102">Lync Server 2013 で SQL Server の非標準ポートおよびエイリアスを展開する</span><span class="sxs-lookup"><span data-stu-id="77fc3-102">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77fc3-103">_**最終更新日:** 2015-09-16_</span><span class="sxs-lookup"><span data-stu-id="77fc3-103">_**Topic Last Modified:** 2015-09-16_</span></span>

<span data-ttu-id="77fc3-104">Microsoft Lync Server 2013 は、SQL Server で標準以外のポートとエイリアスを使用することをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="77fc3-104">Microsoft Lync Server 2013 supports using a non-standard port and alias in SQL Server.</span></span> <span data-ttu-id="77fc3-105">SQL Server の標準以外のポートとエイリアスを使用すると、セキュリティが強化され、Lync の展開により柔軟な環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-105">Using a SQL Server non-standard port and an alias increases security and creates a more flexible environment for the Lync deployment.</span></span> <span data-ttu-id="77fc3-106">以下の手順は、Lync Server 2013 環境を適切にセキュリティで保護する手順の1つにすぎません。</span><span class="sxs-lookup"><span data-stu-id="77fc3-106">These steps are only a single step in properly securing your Lync Server 2013 environment.</span></span> <span data-ttu-id="77fc3-107">Lync Server 2013 の実装で攻撃を受ける可能性を減らすために、追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77fc3-107">Additional steps should be taken to reduce the attack surface of a Lync Server 2013 implementation.</span></span>

<span data-ttu-id="77fc3-108">次の記事では、Lync Server 2013 で SQL Server 標準以外のポートとエイリアスを設定するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-108">The following article describes the steps required to setup a SQL Server non-standard port and alias in Lync Server 2013.</span></span>

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="77fc3-109">Lync Server 2013 で SQL Server 標準以外のポートと別名を展開する</span><span class="sxs-lookup"><span data-stu-id="77fc3-109">Deploying a SQL Server Non-Standard Port and Alias in Lync Server 2013</span></span>

<span data-ttu-id="77fc3-110">Lync Server 2013 トポロジビルダーは、Lync Server 2013 を構成するときに、実際の SQL Server FQDN ではなく、完全修飾ドメイン名 (FQDN) として SQL Server のエイリアスを使用することをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="77fc3-110">Lync Server 2013 Topology Builder supports using a SQL Server alias as the Fully Qualified Domain Name (FQDN) instead of the actual SQL Server FQDN when configuring Lync Server 2013.</span></span> <span data-ttu-id="77fc3-111">これにより、実際の SQL Server FQDN を悪意のある攻撃者から非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-111">This allows the actual SQL Server FQDN to be hidden from any malicious attacker.</span></span> <span data-ttu-id="77fc3-112">また、次の図に示すように、標準ポート以外のポートを使用すると、攻撃者が標準ポート1433でデータベースを攻撃しようとしている場合に、そのポートの実際のポートが不明瞭になります。</span><span class="sxs-lookup"><span data-stu-id="77fc3-112">In addition, using a non-standard port obscures the actual port from any would be attacker attempting to attack the database on the standard port 1433, as shown in the following figure.</span></span>

<span data-ttu-id="77fc3-113">![ハッカーは攻撃するポート番号を認識していません。](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "ハッカーは攻撃するポート番号を認識していません。")</span><span class="sxs-lookup"><span data-stu-id="77fc3-113">![A hacker doesn't know the port number to attack.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "A hacker doesn't know the port number to attack.")</span></span>

<span data-ttu-id="77fc3-114">Lync Server 2013 が SQL Server と通信するために使用しているポートを正しく判断するために、攻撃者はすべてのポートをスキャンしてポート情報を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77fc3-114">In order to be successful in determining the port Lync Server 2013 is using to communicate with SQL Server, the attacker would need to scan all ports to obtain the port information.</span></span> <span data-ttu-id="77fc3-115">攻撃者によるポートスキャンにより、セキュリティが命令を検出して停止する可能性が高まります。</span><span class="sxs-lookup"><span data-stu-id="77fc3-115">A port scan by an attacker increases the chances that security can detect and stop the instruction.</span></span> <span data-ttu-id="77fc3-116">SQL Server の別名を使って、標準以外のポートで強化されたセキュリティを追加することに加えて、展開の柔軟性を高めることもできます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-116">In addition to adding increased security with a non-standard port, you can also use a SQL Server alias to provide flexibility for the deployment.</span></span> <span data-ttu-id="77fc3-117">これは、SQL Server 名の変更が必要な状況で構成の変更を削減するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-117">This is valuable in order to reduce configuration changes in situations where a SQL Server name change is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77fc3-118">SQL Server には、2つのフォールトトレランスメソッド (フェールオーバークラスタリングとミラーリング) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="77fc3-118">SQL Server provides two fault tolerance methods (Failover Clustering and Mirroring).</span></span> <span data-ttu-id="77fc3-119">Sql Server のフォールトトレランスメソッドは、いずれも SQL Server の標準以外のポートと、Lync Server 2013 でエイリアスを使用してサポートされています。</span><span class="sxs-lookup"><span data-stu-id="77fc3-119">Both SQL Server fault tolerance methods are supported using a SQL Server non-standard port and alias with Lync Server 2013.</span></span> <span data-ttu-id="77fc3-120">プールで使用される SQL Server バックエンドがミラー化された構成にある場合、SQL Server バックエンドサーバー上の SQL browser サービスが実行されていて、データベースがミラーリングされた SQL にフェールオーバーしたときに、ミラーデータベースに接続する必要があります。Server.</span><span class="sxs-lookup"><span data-stu-id="77fc3-120">If the SQL Server backend used by the pool is in a mirrored configuration, then the SQL browser service on the SQL Server backend servers should be running for Front End servers to connect to the mirrored database when the databases are failed over to the mirrored SQL Server.</span></span>



</div>

<span data-ttu-id="77fc3-121">トポロジビルダー内から SQL Server データベースの接続を構成している場合、または、CsDatabase コマンドレットを使用している場合、SQL Server 標準以外のポート番号を明示的に定義して SQL インスタンスに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="77fc3-121">When configuring SQL Server database connectivity from within Topology Builder, or when using the Install-CsDatabase cmdlet, it’s not possible to explicitly define a SQL Server non-standard port number and associate it with a SQL instance.</span></span> <span data-ttu-id="77fc3-122">標準以外のポートを設定するには、SQL Server および Windows Server ユーティリティを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77fc3-122">To set a non-standard port, you’ll need to use SQL Server and Windows Server utilities.</span></span>

<span data-ttu-id="77fc3-123">Lync Server 2013 で使用するために SQL Server の標準以外のポートとエイリアスを設定するには、3つの主要な手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77fc3-123">To set up a SQL Server non-standard port and alias for use with Lync Server 2013, you will need to complete three primary steps.</span></span> <span data-ttu-id="77fc3-124">手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="77fc3-124">These steps are:</span></span>

  - <span data-ttu-id="77fc3-125">Lync Server 2013 に最新の更新プログラムが適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-125">Confirm that Lync Server 2013 has the Latest Updates Applied.</span></span>

  - <span data-ttu-id="77fc3-126">SQL Server の標準以外のポートと別名を設定します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-126">Setup the SQL Server Non-Standard Port and Alias.</span></span>

  - <span data-ttu-id="77fc3-127">"トポロジビルダー" を使用して、SQL Server の別名で Lync Server 2013 を構成します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-127">Configure Lync Server 2013 with the SQL Server alias using Topology Builder.</span></span>

  - <span data-ttu-id="77fc3-128">トポロジを公開し、データベースを確認します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-128">Publish the Topology, and Verify the Database.</span></span>

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a><span data-ttu-id="77fc3-129">Lync Server 2013 に最新の更新プログラムが適用されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="77fc3-129">Confirm that Lync Server 2013 has the Latest Updates Applied</span></span>

<span data-ttu-id="77fc3-130">Lync Server 2013 を最新の状態に維持することが重要です。</span><span class="sxs-lookup"><span data-stu-id="77fc3-130">It is important to keep Lync Server 2013 up to date.</span></span> <span data-ttu-id="77fc3-131">最新の更新プログラムとその適用方法に関する情報を確認するには、「 [Lync Server 2013 の更新プログラム](http://support.microsoft.com/kb/2809243)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77fc3-131">To check for the most recent updates and information on how to apply them, see [Updates for Lync Server 2013](http://support.microsoft.com/kb/2809243).</span></span>

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a><span data-ttu-id="77fc3-132">SQL Server の標準以外のポートと別名を設定する</span><span class="sxs-lookup"><span data-stu-id="77fc3-132">Setup the SQL Server Non-Standard Port and Alias</span></span>

<span data-ttu-id="77fc3-133">Lync Server 2013 トポロジビルダーから参照できるようにするには、データベースインスタンスで SQL Server 以外の標準ポートと別名を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77fc3-133">The SQL Server non-standard port and alias must be set up on the database instance before it can be referenced from Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="77fc3-134">SQL Server の標準以外のポートと別名を設定するには、3つの主な手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77fc3-134">To set up a SQL Server non-standard port and alias, you will have to complete three primary steps.</span></span> <span data-ttu-id="77fc3-135">手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="77fc3-135">These steps are as follows:</span></span>

  - <span data-ttu-id="77fc3-136">既定の TCP/IP プロトコルの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-136">Change the Default TCP/IP Protocol Values.</span></span>

  - <span data-ttu-id="77fc3-137">SQL Server のエイリアスを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-137">Create and Configure a SQL Server Alias.</span></span>

  - <span data-ttu-id="77fc3-138">ドメインネームシステム (DNS) の正規名 (CNAME) リソースレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-138">Create a Domain Name System (DNS) Canonical Name (CNAME) Resource Record.</span></span>

<span data-ttu-id="77fc3-139">**既定の TCP/IP プロトコルの値を変更する**</span><span class="sxs-lookup"><span data-stu-id="77fc3-139">**Modify the Default TCP/IP Protocol Values**</span></span>

1.  <span data-ttu-id="77fc3-140">次の図に示すように、[**開始**] を選択し、[ **SQL Server 構成マネージャー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-140">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="77fc3-141">![SQL Server Management Studio のアイコン](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio のアイコン")</span><span class="sxs-lookup"><span data-stu-id="77fc3-141">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="77fc3-142">次の図に示すように、ナビゲーションウィンドウで、 **sql server インスタンス**を展開し、[ **sql server ネットワーク構成**] を展開して、[**インスタンス\<名\>のプロトコル**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-142">In the navigation pane, choose to expand the **SQL Server instance**, choose to expand **SQL Server Network Configuration**, and choose **Protocols for \<instance name\>**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="77fc3-143">![Tcp/ip のプロパティに移動する](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Tcp/ip のプロパティに移動する")</span><span class="sxs-lookup"><span data-stu-id="77fc3-143">![Navigate to TCP/IP Properties](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigate to TCP/IP Properties")</span></span>

3.  <span data-ttu-id="77fc3-144">右側のウィンドウで、[ **tcp/ip**] を右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-144">In the right pane, right-click **TCP/IP**, and select **Properties**.</span></span> <span data-ttu-id="77fc3-145">[TCP/IP のプロパティ] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-145">The TCP/IP Properties dialog box is displayed.</span></span>

4.  <span data-ttu-id="77fc3-146">[ **IP アドレス**] タブを選択します。[IP アドレス] タブには、サーバー上のすべてのアクティブ IP アドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-146">Select the **IP Addresses** tab. The IP Addresses tab shows all of the active IP addresses on the server.</span></span> <span data-ttu-id="77fc3-147">これらは、次の図に示すように、IP1、IP2、および IPAll の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="77fc3-147">These are in the format IP1, IP2, up to IPAll, as shown in the following figure.</span></span>
    
    <span data-ttu-id="77fc3-148">![[Tcp/ip のプロパティ] を開きます。](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "[Tcp/ip のプロパティ] を開きます。")</span><span class="sxs-lookup"><span data-stu-id="77fc3-148">![Open TCP/IP properties.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Open TCP/IP properties.")</span></span>

5.  <span data-ttu-id="77fc3-149">すべての IP アドレスの [ **TCP 動的ポート**] フィールドをオフにします。</span><span class="sxs-lookup"><span data-stu-id="77fc3-149">Clear the **TCP Dynamic Ports** field for all IP addresses.</span></span> <span data-ttu-id="77fc3-150">フィールドにゼロの文字が含まれている場合は、SQL Server が動的なポートをリッスンしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-150">If the field contains a zero character, then it means SQL Server is listening on dynamic ports.</span></span> <span data-ttu-id="77fc3-151">これらのフィールドが消去され、ゼロが含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-151">Make sure these fields are cleared and do not contain a zero.</span></span>

6.  <span data-ttu-id="77fc3-152">Lync Server でデータベースへの接続に使用する IP アドレスについては、次の図に示すように、[**有効** **] が [はい**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-152">For the IP address that Lync Server will be using to connect to the database, make sure that **Enabled** is set to **Yes**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="77fc3-153">![正しい IP に対して [はい] に設定します。](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "正しい IP に対して [はい] に設定します。")</span><span class="sxs-lookup"><span data-stu-id="77fc3-153">![Set enabled as Yes for the correct IP.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Set enabled as Yes for the correct IP.")</span></span>

7.  <span data-ttu-id="77fc3-154">ダイアログボックスの下部にある [ **Ipall** ] セクションで、次の図に示すように、[ **TCP port** ] フィールドに必要なポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-154">In the **IPAll** section at the bottom of the dialog, enter the desired port in the **TCP Port** field, as shown in the following figure.</span></span> <span data-ttu-id="77fc3-155">この例では、ポート50062を使用していますが、49152と65535の間の任意のポートを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-155">In this example, we use port 50062, but you can use any port between 49152 and 65535.</span></span> <span data-ttu-id="77fc3-156">これらのポートは動的使用とプライベート機能に割り当てられているため、Lync Server 2013 の展開で使用されている他のポートと競合しないようにします。</span><span class="sxs-lookup"><span data-stu-id="77fc3-156">These are the ports assigned to dynamic and private use, and this ensures you won’t conflict with other ports being used in the Lync Server 2013 deployment.</span></span>
    
    <span data-ttu-id="77fc3-157">![IPAll セクションでポートを設定します。](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "IPAll セクションでポートを設定します。")</span><span class="sxs-lookup"><span data-stu-id="77fc3-157">![Set port in IPAll section.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port in IPAll section.")</span></span>

8.  <span data-ttu-id="77fc3-158">[ **OK]** を選択して、[Tcp/ip のプロパティ] ダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-158">Choose **OK** to exit the TCP/IP Properties dialog.</span></span>

9.  <span data-ttu-id="77fc3-159">Sql server 構成マネージャーの左側のウィンドウで sql **Server サービス**を選択して、sql server インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-159">Restart the SQL Server instance by selecting **SQL Server Services** in the left pane of SQL Server Configuration Manager.</span></span> <span data-ttu-id="77fc3-160">次に、次の図に示すように、右側のウィンドウで [ **SQL Server \<インスタンス\>名**] を右クリックし、[**再起動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-160">Then right-click **SQL Server \<instance name\>** in the right pane, and select **Restart**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="77fc3-161">![インスタンスの SQL Server サービスをリセットします。](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "インスタンスの SQL Server サービスをリセットします。")</span><span class="sxs-lookup"><span data-stu-id="77fc3-161">![Reset the SQL Server service for instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reset the SQL Server service for instance.")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="77fc3-162">新しい SQL Server ポートに対応するように、ファイアウォールの設定が更新されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="77fc3-162">Make sure you update your firewall settings to accommodate the new SQL Server port.</span></span>



</div>

<span data-ttu-id="77fc3-163">**SQL Server の別名を作成および構成する**</span><span class="sxs-lookup"><span data-stu-id="77fc3-163">**Create and Configure a SQL Server Alias**</span></span>

1.  <span data-ttu-id="77fc3-164">次の図に示すように、[**開始**] を選択し、[ **SQL Server 構成マネージャー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-164">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="77fc3-165">![SQL Server Management Studio のアイコン](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio のアイコン")</span><span class="sxs-lookup"><span data-stu-id="77fc3-165">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="77fc3-166">左側のウィンドウで [ **Sql Server インスタンス**] を展開し、[ **sql Native Client \<\> version Configuration**] を展開して、次の図に示すように [**エイリアス**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-166">In the left pane, choose to expand **SQL Server instance**, choose to expand **SQL Native Client \<version\> Configuration**, and then choose **Aliases**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="77fc3-167">![SQL Server 構成マネージャーのエイリアス。](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "SQL Server 構成マネージャーのエイリアス。")</span><span class="sxs-lookup"><span data-stu-id="77fc3-167">![Aliases in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases in SQL Server Configuration Manager.")</span></span>

3.  <span data-ttu-id="77fc3-168">[**エイリアス**] を右クリックし、[**新しいエイリアス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-168">Right-click **Aliases**, and select **New Alias…**.</span></span>

4.  <span data-ttu-id="77fc3-169">次の図に示すように、**エイリアス名**、**ポート番号**、**プロトコル**、**サーバー**を入力します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-169">Enter the **Alias Name**, **Port Number**, **Protocol**, and **Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="77fc3-170">![新しいエイリアスを作成する](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "新しいエイリアスを作成する")</span><span class="sxs-lookup"><span data-stu-id="77fc3-170">![Creating a new alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creating a new alias")</span></span>
    
    <div>
    

    > [!CAUTION]  
    > <span data-ttu-id="77fc3-171">SQL Server がリッスンするポートであるため、前の手順で使ったものと同じ標準以外のポートを入力してください。</span><span class="sxs-lookup"><span data-stu-id="77fc3-171">Make sure to enter the same non-standard port you used in the previous step since that is the port SQL Server will be listening on.</span></span> <span data-ttu-id="77fc3-172">構成されたエイリアスが間違った SQL Server FQDN またはインスタンスに接続している場合は、関連付けられたネットワークプロトコルを無効にしてから再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="77fc3-172">If a configured alias is connecting to the wrong SQL Server FQDN or Instance, disable and then re-enable the associated network protocol.</span></span> <span data-ttu-id="77fc3-173">この操作を実行すると、キャッシュされた接続情報がクリアされ、クライアントが正常に接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="77fc3-173">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>

    
    </div>

<span data-ttu-id="77fc3-174">**DNS CNAME リソースレコードを作成する**</span><span class="sxs-lookup"><span data-stu-id="77fc3-174">**Create a DNS CNAME Resource Record**</span></span>

1.  <span data-ttu-id="77fc3-175">DNS を管理するコンピューターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="77fc3-175">Sign into the computer managing DNS.</span></span>

2.  <span data-ttu-id="77fc3-176">[**スタート**] を選択し、次の図に示すように [**サーバーマネージャー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-176">Select **Start**, and choose **Server Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="77fc3-177">![サーバーマネージャーを開く](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "サーバーマネージャーを開く")</span><span class="sxs-lookup"><span data-stu-id="77fc3-177">![Opening Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Opening Server Manager")</span></span>

3.  <span data-ttu-id="77fc3-178">次の図に示すように、[**ツール**] ドロップダウンを選び、[ **DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-178">Choose the **Tools** drop-down, and select **DNS**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="77fc3-179">![サーバーマネージャーから DNS を開いています。](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "サーバーマネージャーから DNS を開いています。")</span><span class="sxs-lookup"><span data-stu-id="77fc3-179">![Opening DNS from Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Opening DNS from Server Manager.")</span></span>

4.  <span data-ttu-id="77fc3-180">左側のウィンドウで、[サーバー名] ノードを展開し、[前方参照ゾーン] ノードを展開して、関連するドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-180">In the left pane, expand the server name node, expand the Forward Lookup Zones node, and choose the relevant domain.</span></span>

5.  <span data-ttu-id="77fc3-181">次の図に示すように、ドメインを右クリックし、[**新しいエイリアス (CNAME)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-181">Right-click the domain, and select **New Alias (CNAME)…**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="77fc3-182">![新しいエイリアスを作成するためのオプションの選択](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "新しいエイリアスを作成するためのオプションの選択")</span><span class="sxs-lookup"><span data-stu-id="77fc3-182">![Selecting option to create a new alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecting option to create a new alias CNAME")</span></span>

6.  <span data-ttu-id="77fc3-183">次の図に示すように、**エイリアス名**と**SQL Server の FQDN**を入力します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-183">Enter the **Alias Name** and the **FQDN for SQL Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="77fc3-184">![[New ALIAS CNAME] ダイアログボックスに入力します。](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "[New ALIAS CNAME] ダイアログボックスに入力します。")</span><span class="sxs-lookup"><span data-stu-id="77fc3-184">![Filling in the new alias CNAME dialog.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Filling in the new alias CNAME dialog.")</span></span>

7.  <span data-ttu-id="77fc3-185">**[OK]** を選択して CNAME を保存し、DNS マネージャーで表示します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-185">Choose **OK** to save the CNAME and view it in DNS Manager.</span></span>

</div>

<div>

## <a name="validate-database-connectivity"></a><span data-ttu-id="77fc3-186">データベース接続を検証する</span><span class="sxs-lookup"><span data-stu-id="77fc3-186">Validate Database Connectivity</span></span>

<span data-ttu-id="77fc3-187">機能しているかどうかを確認するには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="77fc3-187">There are many different ways to make sure it is working.</span></span> <span data-ttu-id="77fc3-188">エイリアスを使用して、指定したポートで SQL Server データベースがリッスンしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-188">You want to make sure that the SQL Server database is listening on the specified port using the alias.</span></span> <span data-ttu-id="77fc3-189">**Netstat**コマンドと**telnet**コマンドを使用して、クイックチェックを完了することができます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-189">A quick check can be completed using the **netstat** and **telnet** commands.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77fc3-190">Telnet クライアントは Windows Server に付属しているが、インストールが必要な機能です。</span><span class="sxs-lookup"><span data-stu-id="77fc3-190">Telnet Client is a Feature that comes with Windows Server but that must be installed.</span></span> <span data-ttu-id="77fc3-191">Windows Server の機能をインストールするには、サーバーマネージャーを開き、[管理] メニューの [役割と機能の追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-191">A Windows Server Feature can be installed by opening Server Manager and selecting Add Roles and Features from the Manage menu.</span></span>



</div>

<span data-ttu-id="77fc3-192">**Netstat と telnet を使ってデータベース接続を確認する**</span><span class="sxs-lookup"><span data-stu-id="77fc3-192">**Use netstat and telnet to verify database connectivity**</span></span>

1.  <span data-ttu-id="77fc3-193">[**スタート**] を選択し、「 **cmd** 」と入力してコマンドプロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-193">Select **Start**, and type **cmd** to open a command prompt.</span></span>

2.  <span data-ttu-id="77fc3-194">次の図に示すように、「 **netstat-a-f**」と入力し、SQL Server が正しいポートで実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-194">Type **netstat -a -f**, and confirm that SQL Server is running with the correct port, as shown in the following figure.</span></span>
    
    <span data-ttu-id="77fc3-195">![Netstat を使ってポートを確認します。](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Netstat を使ってポートを確認します。")</span><span class="sxs-lookup"><span data-stu-id="77fc3-195">![Using netstat to verify port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Using netstat to verify port.")</span></span>

3.  <span data-ttu-id="77fc3-196">SQL Server インスタンスへの接続を確認するには、「 \*\* \<telnet\> \<alias name port \# \*\* 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-196">Type **telnet \<alias name\> \<port \#\>** to confirm the connection to the SQL Server instance.</span></span> <span data-ttu-id="77fc3-197">接続に成功すると、telnet が接続され、エラーが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="77fc3-197">If the connection is successful, telnet will connect and you shouldn’t see an error.</span></span> <span data-ttu-id="77fc3-198">これは、SQL Server インスタンスが正しいエイリアスで正しいポートをリッスンしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="77fc3-198">This shows that the SQL Server instance is listening on the correct port with the correct alias.</span></span> <span data-ttu-id="77fc3-199">SQL Server データベースへの接続に問題がある場合は、telnet に接続できないというエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-199">If there’s a problem connecting to the SQL Server database, then telnet shows an error that the connection cannot be made.</span></span> <span data-ttu-id="77fc3-200">データベースサーバーでデータベース接続を確認しましたが、Lync Server (ネットワーク経由) から同じことを行うことができます。また、ファイアウォールによってアクセスがブロックされていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="77fc3-200">Now that you have checked database connectivity on the database server, you can do the same thing from Lync Server (over the network) and make sure there aren’t any firewalls blocking access along the way.</span></span>

</div>

<div>

## <a name="conclusion"></a><span data-ttu-id="77fc3-201">終わりに</span><span class="sxs-lookup"><span data-stu-id="77fc3-201">Conclusion</span></span>

<span data-ttu-id="77fc3-202">SQL Server のエイリアスを構成したら、それを使って、トポロジビルダーツールで Lync Server 2013 トポロジを作成できます。</span><span class="sxs-lookup"><span data-stu-id="77fc3-202">Once the SQL Server alias has been configured, you can use it to create a Lync Server 2013 topology in the Topology Builder tool.</span></span> <span data-ttu-id="77fc3-203">トポロジの詳細については、「 [Lync Server 2013 でトポロジを定義して構成する](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77fc3-203">For more information about topologies, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="77fc3-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="77fc3-204">See Also</span></span>


<span data-ttu-id="77fc3-205">[Microsoft lync server 2013](microsoft-lync-server-2013.md) 
[lync server 2013 のセキュリティの計画](lync-server-2013-planning-for-security.md)</span><span class="sxs-lookup"><span data-stu-id="77fc3-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[Planning for security in Lync Server 2013](lync-server-2013-planning-for-security.md)</span></span>  
[<span data-ttu-id="77fc3-206">Lync Server 2013 でのトポロジの定義と構成</span><span class="sxs-lookup"><span data-stu-id="77fc3-206">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)  
[<span data-ttu-id="77fc3-207">Lync Server 2013 の展開</span><span class="sxs-lookup"><span data-stu-id="77fc3-207">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

